# hugo.zammu.in

This is a sample website which uses [zammu.in](https://zammu.in/hugo) to automatically deploy [Hugo](https://gohugo.io) websites to [Github Pages](https://pages.github.com)

## You can use the steps/commands below to setup your Hugo site on zammu

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
