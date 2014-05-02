---
layout: post
status: publish
published: true
title: WordPressのmod_rewriteをhttpd.confに書く。
date: 2011-02-05 00:00:26
categories:
- Server
tags:
- http.conf
- mod_rewrite
- WordPress
---
.htaccessに書くより、パフォーマンスが上がると思ってやった。blogにすべてリダイレクトされたり、CSSだけ見つからなかったりしたけど解決したよ。

このblogと同じようなディレクトリ構成になっていることが前提です。
<pre>RewriteRule ^blog\/index\.php$ blog\/ [L]
RewriteCond %{REQUEST_FILENAME} ^\/blog\/
RewriteCond %{DOCUMENT_ROOT}/%{REQUEST_FILENAME} !-f
RewriteCond %{DOCUMENT_ROOT}/%{REQUEST_FILENAME} !-d
RewriteRule . /blog/index.php [L]
</pre>
