# Overview

Github actions deploys staging to https://gbrayut.github.io/a-z.dev/

# Installing https://gohugo.io

See https://gohugo.io/installation/ or use the following for static binary:

```bash
cd /tmp
HUGO_VERSION=0.169.0  # from https://github.com/gohugoio/hugo/releases
wget -O /tmp/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb
sudo dpkg -i /tmp/hugo.deb

/usr/local/bin/hugo version
hugo v0.169.0-1da10fc44701c566b1669cdb2d12638f155138bd+extended linux/amd64 BuildDate=2026-10-27T14:52:20Z VendorInfo=gohugoio
```

# How to build locally for https://a-z.dev

```bash
# rendered static files will be placed in ./public/ using hugo.toml settings
hugo --gc --minify

# Explicit Parameter Override (-b or --baseURL)
hugo --gc --minify --baseURL "https://stage.a-z.dev/"

# Output to a specific destination folder (-d)
hugo --gc --minify --baseURL "https://a-z.dev/" --destination ./dist-prod
```

# Special content types

- Youtube embeddings https://github.com/gohugoio/hugo/blob/master/docs/content/en/shortcodes/youtube.md

# Docs and other examples repos

- Getting Started https://gohugo.io/getting-started/
- Hugo releases https://github.com/gohugoio/hugo/releases
- Hugo Theme https://github.com/MeiK2333/github-style

Other Examples
- https://engineering.getweave.com/post/
- https://github.com/carsonoid/forgeutah.tech
- https://github.com/carsonoid/carson-anderson.com
- https://github.com/carsonoid/vitess-website

# Other links/todo

- https://www.junian.dev/markdown-resume/edit/1734299304068
- https://github.com/gethugothemes/hugo-modules
