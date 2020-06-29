---
layout: post
current: post
navigation: true
cover: assets/images/posts/jekyll-action.png
title: "Jekyll Github Action"
date: 2020-06-28 18:15:00
tags:
  - Tip
  - Jekyll
  - GitHub
  - BlogEditor
class: post-template
subclass: 'post'
author: col
---

I've realised that in order for the Blog Editor to be useful I need to streamline the publishing process. Due to some 
plugins I'm using I need to run the build locally then manually push the generated static files to `gh-pages` 
branch. 

GitHub provides a lightweight CI system called GitHub Actions that should be able to run the build for each 
commit to master and push the static files to the `gh-pages` branch automatically. Surprisingly I have not tried GitHub 
Actions yet so this is a good opportunity to try them out.  

I found this existing custom Jekyll Action [here](https://github.com/helaili/jekyll-action) that would do the job. 

It's very simple to implement, just add the following config to `.github/workflows/github-pages.yml`. 

```yaml
name: Build and deploy Jekyll site to GitHub Pages

on:
  push:
    branches:
      - master

jobs:
  github-pages:
    runs-on: ubuntu-16.04
    steps:
      - uses: actions/checkout@v2
      - uses: helaili/jekyll-action@2.0.3
        env:
          JEKYLL_PAT: ${{ secrets.JEKYLL_PAT }}
```


Unfortunately, the action does not trigger when I push changes. 🤔 
      
**Update:** Turns out it's a bad time to be trying GitHub Actions for the first time. The service is currently down. 🤦‍♂️ 

![GitHub Actions Incident](assets/images/posts/jekyll-action-outage.png)

**Update 2:** The service is back up! The build action now gets triggered as expected and working perfectly. 

![GitHub Actions Success](assets/images/posts/jekyll-action-success.png)