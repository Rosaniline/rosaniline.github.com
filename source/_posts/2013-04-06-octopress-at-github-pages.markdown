---
layout: post
title: "Octopress@github pages"
date: 2013-04-06 23:20
comments: true
categories: 

---

受到了 [fawkeswei](https://github.com/fawkeswei) 的激勵，毅然決然加入了 [Octopress](http://octopress.org/) + [Github pages](http://pages.github.com/) 的行列。想不到這一折騰便是幾把小時，第一篇文章便是要來好好記錄一下。
<br/>	
	

### step 1. 建立 Github pages

首先得在你的 github 裡建立一名為 username.github.com 的 repository。得注意此處的 username 是真的 username，像小弟的便是 rosaniline.github.com，千萬別傻傻的輸入 "username"。

### step 2. 建立 Octopress

	git clone git://github.com/imathis/octopress.git octopress
	cd octopress  
	ruby --version 
	
此時千萬要確定你的 ruby 至少要是 1.9.2+，Mac OS 隨機附贈的只有 ruby 1.8.7，可是會讓你在往後的路上吃盡悶虧的。

	gem install bundler
	bundle install
	rake install
	
若是此時出現了

	rake aborted!
	You have already activated rake 10.0.4, but your Gemfile requires rake 0.9.2.2. Using bundle exec may solve this.
	…

就改為 `bundle exec rake install` 即可！ 

	
### step 3. Octopress @ Github Pages

	rake setup_github_pages
	
此時 octopress 會像您詢問 github pages 的 repository url，別吝嗇複製一番就好。

	rake generate
	rake deploy
	
就大功告成囉！你的網誌會出現在 `username.github.com`
但還是別忘記 push 一番。

	git add .
	git commit -m 'message'
	git push origin source
	
### step 4. Octopress

在 `octopress/_config.yml` 可以修改 blog 的一些面貌，包括了


一切準備妥當後便是要趕緊來搶 po 第一篇文章

	rake new_post["title"]
	
octopress 是用 Markdown 語法寫成，可參考 [Markdown 的語法說明](http://markdown.tw/) 或是 [Markdown: Syntax](http://daringfireball.net/projects/markdown/syntax)。如果是用 Mac 的朋友們，就可以用好用的 [Mou](http://mouapp.com/) editor！

	rake generate 
	rake preview

`rake preview` 可以先在本機上偷看你剛剛的辛苦成果，只需在瀏覽器中鍵入 `http://localhost:4000/` 即可看到。

	git add .
	git commit -m 'message'
	git push source origin

最後別忘了要 push & deploy.
  
  
<br/> <br/>	  
---

以上內容參考自[Deploying to Github Pages](http://octopress.org/docs/deploying/github/) 以及 [李嘉玲的技術筆記](http://zerodie.github.io/blog/2012/01/19/octopress-github-pages/)。