+++
title = "Webpack"
date = 2020-04-06T01:23:00+08:00
draft = false
[menu.other]
  weight = 1001
  identifier = "webpack"
+++

在使用 webpack `build` 项目时，提示文件大小超过限制，而且项目上线后加载特别特别慢，
stackoverflow 了一下，原来 `webpack.config.js` 加了 `devtool: source-map` ，虽然有利于 `development` 时 debug，但是会影响网站性能，所以 `build` 时不需要
`devtool` ，尝试之后，
`bundle.js` 大小缩至 1/6， 至于怎么解决，是 `webpack.config.js` 拆分成 `webpack.dev.js` 和
`webpack.prod.js` ，还是用三元运算符
`devtool: (mode === 'development') ? 'inline-source-map' : false`
有待斟酌。