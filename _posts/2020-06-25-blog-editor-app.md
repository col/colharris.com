---
layout: post
current: post
navigation: true
cover: assets/images/posts/blog-editor-app.jpg
title: "Project Idea: Blog Editor App"
date: 2020-06-23 17:30:00
tags: [WWDC20 SwiftUI BlogEditor]
class: post-template
subclass: 'post'
author: col
---

# Project Idea: Blog Editor App

While setting up this blog last week I started looking around for a Markdown app I could use to manage the content. I've
been using [Notable](https://notable.app/) for awhile now to keep my own notes but due to some issues, such as the one I 
[raised here](https://github.com/notable/notable/issues/1192), it doesn't work well for Jekyll content.

I'll be watching a few of the WWDC20 videos this week and, as a way to try out whatever I learn, I like to come up a 
relatively simple app idea I can work along the way. For WWDC18 I ended up creating a Harry Potter style 
Augmented Reality photo wall app to try out the ARKit framework. I'll post about that another day.

So for this year, I think I'll try to create a simple, cross platform, Jekyll content editor using SwiftUI.

Here's some high level requirements for what I'm thinking.

- Simple split view style layout with a list of posts in the sidebar
- Clicking a post when open a plain text editor on the right to edit markdown
- A preview button that will switch the text editor to a HTML view that renders the markdown
- Ability to save changes and somehow sync with other devices
- Support Jekyll metadata in the markdown content
  - Strip it out before displaying the content in the editor
  - Provide the ability to edit the metadata in a popup window
- Target platforms would be iPad and MacOS
- Try to stick pure SwiftUI as much as possible

At this point this feels mostly achievable. Bring on WWDC20!
