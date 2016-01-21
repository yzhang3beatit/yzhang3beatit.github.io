---
layout: post
title:  "How to build jekyll and QA"
date:   2016-01-21
author: Zhang Yang
category: coach
tags: [jekyll, github]
---

## Steps

1.  Submit or login [Github](https://github.com)
2.  Fork from ["Theme on Github"](https://github.com/fengzhichu/fengzhichu-theme)
3.  Clone your master branch to local directory
4.  Custom the '_config.yml' to your style
	1. Empty 'baseurl' and 'url'
	2. Rename 'title' 'yoursitetitle' 'header_text' 'footer_text'
	3. Update Icons 'email_address', 'github'
5.  Install jekyll in local env
	1. sudo gem install ruby <--http-proxy http://host:port>
	2. sudo gem install jekyll <--http-proxy http://host:port>
	3. sudo gem install github-pages <--http-proxy http://host:port>
	4. sudo gem install bundler <--http-proxy http://host:port>
	5. bundler update

6.  Run: jekyll serve -w

7.  firefox localhost:4000

## Question and Answer

1.  sudo gem install jekyll    

  > ERROR:  Error installing jekyll:

  > ERROR: Failed to build gem native extension.

  >   Error installing jekyll:
       jekyll requires Ruby version >= 2.0.0.

A: 安装最新的ruby2.3

  `wget http://ftp.ruby-lang.org/pub/ruby/2.3/ruby-2.3-0.tar.gz`

  `cd ruby-2.3-0`

  `./configure --prefix=/usr/local`

  `make`

  `sudo make install`

2. jekyll serve -w
   >Error:
   
   >bundler/resolver.rb:203:Bundler could not find compatible versions for gem "nokogirl"

A: bundle update

3. How to upgrade rubygems ?
A: `gem install rubygems-update`
   `update_rubygems`
   `gem update --system`

4. `jekyll serve -w` failed
     
   >ERROR: YOUR SITE COULD NOT BE BUILT:
   
   >------------------------------------
   
   >redcarpet

A: `bundler update`

   `bundle exec jekyll serve -w`
