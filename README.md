# sujithpl.github.io
Hugo based static site for my personal blog & webpage

## References
- [Hugo Official Documentation](https://gohugo.io/documentation/)
- [GitHub Hosting Documentation](https://gohugo.io/host-and-deploy/host-on-github-pages/)
- [Anatole Theme Documentation](https://github.com/lxndrblz/anatole/wiki)

## Local Development
- Update theme: `hugo mod get -u github.com/lxndrblz/anatole`
- Run locally: `hugo serve`
- Browse: http://localhost:1313/

## Update Dependencies
### [Go](https://go.dev/doc/install)
- Download Linux release from the [Go website](https://go.dev/dl/)
- Remove existing installation: `rm -rf /usr/local/go`
- Install new version: `tar -C /usr/local -xzf go1.25.6.linux-amd64.tar.gz`
### Hugo
- Download Linux Extended release from [GitHub](https://github.com/gohugoio/hugo/releases)
- Install: `sudo dpkg -i hugo_extended_0.154.4_linux-amd64.deb`
### Sass
- Download release from [GitHub](https://github.com/sass/dart-sass/releases)
- Remove existing installation: `rm -rf ~/libs/dart-sass`
- Install new version: `tar -C ~/libs -xzf dart-sass-1.97.3-linux-x64.tar.gz`
