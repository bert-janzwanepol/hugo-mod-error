# Hugo Example

This directory is a minimal reproducable example for a Vercel build error.

## Steps to reproduce

### Init a module

```
 hugo mod init github.com/bert-janzwanepol/hugo-mod-error
```

### Specify a go _PATCH_ version and other optional dependencies

```
module github.com/bert-janzwanepol/hugo-mod-error

go 1.22.2

require github.com/gohugoio/hugo-mod-jslibs-dist/alpinejs/v3 v3.21300.20800
```

### Fix a build error by downgrading hugo to 0.92.0

The Ananke theme uses deprecated/removed features from older hugo versions.
In order to build the project succesfully, downgrade to 0.92.0
Add the Hugo version in [config.toml](./config.toml):

```toml
[module.hugoVersion]
    min = "0.80.0"
    max = "0.92.2"
    extended = true
```
