---
layout: post
current: post
navigation: True
cover:  assets/images/posts/elixir-local-config.jpg
title: Elixir local development config
date: 2020-06-21 11:30:00
tags: 
  - Tips
  - Elixir
class: post-template
subclass: 'post'
author: col
---

When you're working in a team it's common for each developers setup to be a little different. A great way to deal with this in Elixir projects is to include an optional config file called `local.exs`. This file should not be tracked in source control and can override any config each developer needs for their local machine. 

`config/local.exs`
```
use Mix.Config
```

`config/dev.exs`
```
...

# Local, untracked config overrides.
if File.exists?("#{__DIR__}/local.exs") do
  import_config "local.exs"
end
```

`.gitignore`
```
# Local, untracked config overrides.
config/local.exs
```
