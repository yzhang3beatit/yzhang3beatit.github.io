---
layout: post
title:  "How to store username&password in git"
date:   2016-01-21
author: Author
category: coach
tags: [github]
---

`cd ~`
`touch .git-credentials`
`vim .git-credentials`
`# 将以下内容写入该文件中`
`https://{username}:{password}@github.com` 
`#运行以下git配置命令`
`git config --global credential.helper store`