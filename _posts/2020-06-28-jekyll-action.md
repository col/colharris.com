---
layout: post
current: post
navigation: true
cover: assets/images/posts/jekyll-action.png
title: "Jekyll Github Action"
date: 2020-06-28 18:15:00
tags: [Jekyll GitHub BlogEditor]
class: post-template
subclass: 'post'
author: col
---

I've realised that in order for the Blog Editor to be useful I need to streamline the publishing process. This first 
step towards this was to setup a GitHub Action to build the site for each commit and push the changes to the `gh-pages` 
branch.

I found this existing Jekyll Action [here](https://github.com/helaili/jekyll-action) that would do the job. 
Unfortunately this action force pushes the changes and overwrites the previous commits. I wouldn't mind so much but 
that also removes the `CNAME` config file I need in order to use a custom domain name. 

Long story short, I've forked the jekyll action [here](https://github.com/col/jekyll-action) and it should now only push
the changes without using force push. 
      
**Update:** Turns out it's a bad time to be trying to implement my first GitHub Action.️ 

![GitHub Actions Incident](assets/images/posts/jekyll-action-outage.png)