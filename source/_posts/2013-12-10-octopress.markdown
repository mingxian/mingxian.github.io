---
layout: post
title: "在Github上搭建Octopress博客"
date: 2013-12-10 15:06:50 +0800
comments: true
categories: 
---
今天尝试在github搭建了Octopress博客，现将过程记录如下：
<h2>安装Octopress前的注意事项</h2>
<ol>
<li>确保你已经安装了Git(brew git),并且已经与github关联。</li>
<li>在Ternimal中执行ruby --version，确保Ruby的版本至少为1.9.3或更新。</li>
</ol>

<h2>clone Octopress</h2>

	$git clone git://github.com/imathis/octopress.git octopress

	$cd octopress

<h2>安装Octopress依赖</h2>

	$gem install bundler

	$bundle install

<h2>安装Octopress默认主题</h2>
	
	$rake install

<h2>在github上部署Octopress</h2>
<ol>
<li>在github创建一个名为<code>username.github.io</code>的repository,username是你的github账户名。</li>
<li>复制下clone所需的地址：git@github.com:username/username.github.io.git</li>
<li>执行如下命令，过程中会提示你粘贴刚才复制的地址</li>
</ol>

	$rake setup_github_pages

	$rake generate

	$rake deploy

<p>这一步将会生成blog，并将其提交到origin的master分支</p>

<p>最后别忘记将源代码提交到origin的source分支</p>

	$git add .

	$git commit -m "write what you want"

	$git push origin source

<p>参考链接：</p>
<ul>
<li><a href="http://octopress.org/docs/setup/" target="_blank">http://octopress.org/docs/setup/</a></li>
<li><a href="http://octopress.org/docs/deploying/github/" target="_blank">http://octopress.org/docs/deploying/github/</a></li>
<li><a href="http://octopress.org/docs/blogging/" target="_blank">http://octopress.org/docs/blogging/</a></li>
</ul>