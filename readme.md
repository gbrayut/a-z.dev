# Overview

Github actions deploys staging to https://gbrayut.github.io/a-z.dev/

# How to build locally for https://a-z.dev

```bash
# rendered static files will be placed in ./public/ using hugo.toml settings
hugo --gc --minify

# Explicit Parameter Override (-b or --baseURL)
hugo --gc --minify --baseURL "https://stage.a-z.dev/"

# Output to a specific destination folder (-d)
hugo --gc --minify --baseURL "https://a-z.dev/" --destination ./dist-prod
```

# Docs and other examples repos

- Getting Started https://gohugo.io/getting-started/
- Hugo releases https://github.com/gohugoio/hugo/releases
- Hugo Theme https://github.com/MeiK2333/github-style
- https://github.com/carsonoid/forgeutah.tech
- https://github.com/carsonoid/carson-anderson.com
- https://github.com/carsonoid/vitess-website

# Other links/todo

- https://www.junian.dev/markdown-resume/edit/1734299304068
- https://github.com/gethugothemes/hugo-modules
