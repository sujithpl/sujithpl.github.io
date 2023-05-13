---
categories:
- professional
date: "2018-09-21T00:00:00Z"
tags:
- java
- programming
- testing
title: Balancing Expressiveness and Brevity
---
I really enjoy refactoring code. However, I rarely get that opportunity at my job because I primarily work on a large Java application that is mature and well maintained.

Recently, I was modifying an existing feature in the application. When I looked at the accompanying unit tests, I was surprised by their structure. I saw that all the test cases were repeating the initialization steps. My immediate thought was that I could refactor the tests by extracting out the setup steps into an utility method.

Let me demonstrate the scenario with a contrived example. Assume that the feature being enhanced is a risk model that evaluates whether a particular person can be given a particular loan. Lets say that the model only uses the monthly payment amount to make this determination and returns a true or false. To test this, we start by creating a model with an individual's risk profile and then pass in a loan object.
```java
RiskModel model = new RiskModel(riskProfile);
boolean safeBet = model.evaluate(loan);
```

So the test methods check to see if the model correctly evaluates the risk for different loans.
```java
Loan loan = new Loan();
loan.setPrincipal(150000.00);
loan.setInterest(4.55);
loan.setTerm(360);
assertFalse(model.evaluate(loan));
```
The test code was full of methods like this.

So I created a utility method to isolate the loan creation.
```java
private Loan createLoan(double principal, double interest, int term) {
    //loan initialization code here
};
```
And in the methods, I replaced the existing steps as follows.
```java
Loan loan = createLoan(150000.00, 4.55, 360);
assertFalse(model.evaluate(loan));
```
So I had significantly the lines of code reduced through this refactoring.

But when I read through the tests again, I realized a major drawback of my approach. I could not easily tell the purpose of each test. Only the short test method name and additional comments could provide the appropriate context.

Suddenly I realized why the tests were verbose in the first place. The testers were being explicit about the the type of loan they were using in each unit test. My zealous attempt at refactoring had reduced the overall readability of the tests.

However I didn't want to rollback all my changes. I figured that I could still keep the utility method while improving the readability of the tests. I took the following approach.
```java
double highPrincipal = 750000.00;
double lowInterestRate = 3.275;
int shortTerm = 120;
Loan loan = createLoan(highPrincipal, lowInterestRate, shortTerm);
```
Now I was describing each loan type clearly and making the purpose of the tests very clear.

In the end, I ended up increasing the overall amount of lines of code. But I had also improved the expressiveness of the code. Separating out the loan creation process was still worthwhile because it reduces duplication of functionality.

The lesson is that we should always consider readability while refactoring code. Balance is key.
