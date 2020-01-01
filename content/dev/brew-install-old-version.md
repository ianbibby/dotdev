---
title: "Brew Install Old Version"
date: 2019-12-30T21:52:37-08:00
draft: false
type: post
categories:
    - dev
tags:
    - brew
    - howto
---

I recently needed to install an older version of hugo via brew but ran into some issues:

```
$ brew install hugo@0.57.1
...
Error: No available formula with the name "hugo@0.57.1" 
==> Searching for a previously deleted formula (in the last month)...
Warning: homebrew/core is shallow clone. To get complete history run:
  git -C "$(brew --repo homebrew/core)" fetch --unshallow
...
```

Now the brew repository is rather large, so getting the complete history when all I need is a single package just seemed unreasonable.

The solution was surprisingly easy:

Browse to the brew formula for the package, in my case it was https://github.com/Homebrew/homebrew-core/commits/master/Formula/hugo.rb

Click on the `<>` link to *browse the repository at this point in history*.  Next is to browse once again to the formula and copy the URL for passing directly to brew:

`brew install https://github.com/Homebrew/homebrew-core/blob/b3375784ad033442c182caac5240fbe4d0a3d581/Formula/hugo.rb`

Done! 👍🏻