+++
date = "2016-01-12T02:33:53+05:30"
title = "How to host hugo websites on github"

+++

<link rel="stylesheet" type="text/css" href="/overrides.css" />
<link rel="stylesheet" type="text/css" href="/asciinema-player.css" />
<script src="/asciinema-player.js"></script>

[Hugo](https://gohugo.io/) is a really fast static site generator. However, it is not
very accessible. In this short post I'll show you how to get your Hugo website
built on Github automatically for each git push.

 1. Sign up for [https://zammu.in/hugo](https://zammu.in/hugo?invitation_code=GOHUGO16) using the invitation code `GOHUGO16`.
 2. Link up your Github Profile from zammu.in's home page after signing in.
 3. Create a new site using the "Github => Hugo => Github" recipe and enter the
     github url of your hugo website e.g. *zammu/hugo.zammu.in* with the other
     details.
 4. That's it. Now you whenever you push to your github repository, your website
    built using Hugo will be published to the subdomain.zammu.in

P.S I am the founder of https://zammu.in/hugo and would love to hear your feedback on
it at [https://zammu.in/feedback](https://zammu.in/feedback?utm_src=hugo.zammu.in)

P.P.S This website is also hosted on https://zammu.in/hugo . You can checkout its
source at https://github.com/zammu/hugo.zammu.in

<div id="player-container"></div>
<script src='/load-player.js'></script>

- - -

**Here are the commands used in the above screencast if you want to copy them**

~~~bash
# init the new site
hugo new site awesome-hugo-blog

# init the repo
cd awesome-hugo-blog
git init
git commit -m 'init'

# setup the theme
git submodule add https://github.com/htdvisser/hugo-base16-theme themes/base16
# it is VERY important that you add it as a submodule and not just clone it

# commit the theme
git commit -m 'added theme'

# update the config
vim config.toml
title = "My very awesome blog"
theme = "base16"
^
git commit -m 'updated config'

# now we need to go to github and create our repository and then
git remote add origin git@github.com:minhajuddin/awesome-hugo-blog
git push origin master -u

# now we need to go to https://zammu.in/ and create a new site with the following  info
# Recipe = Github => Hugo => Github
# Title = My awesome Blog
# Domain =
# Subdomain = awesomehugo
# Github URL = minhajuddin/awesome-hugo-blog

echo "That's it we are done"
~~~
