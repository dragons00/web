
## ES6简介
ECMAScript 6.0（以下简称 ES6）是 JavaScript 语言的下一代标准，已经在 2015 年 6 月正式发布了。它的目标，是使得 JavaScript 语言可以用来编写复杂的大型应用程序，成为企业级开发语言。
## 语法提案的批准流程 
任何人都可以向标准委员会（又称 TC39 委员会）提案，要求修改语言标准。  
一种新的语法从提案到变成正式标准，需要经历五个阶段。每个阶段的变动都需要由 TC39 委员会批准。
* Stage 0 - Strawman（展示阶段）
* Stage 1 - Proposal（征求意见阶段）
* Stage 2 - Draft（草案阶段）
* Stage 3 - Candidate（候选人阶段）
* Stage 4 - Finished（定案阶段）
一个提案只要能进入 Stage 2，就差不多肯定会包括在以后的正式标准里面。ECMAScript 当前的所有提案，可以在 TC39 的官方网站GitHub.com/tc39/ecma262查看。
## 部署进度
各大浏览器的最新版本，对 ES6 的支持可以查看kangax.github.io/compat-table/es6/。随着时间的推移，支持度已经越来越高了，超过 90%的 ES6 语法特性都实现了。  
一个工具 ES-Checker，用来检查各种运行环境对 ES6 的支持情况。访问ruanyf.github.io/es-checker，可以看到您的浏览器支持 ES6 的程度。  
运行下面的命令，可以查看你正在使用的 Node 环境对 ES6 的支持程度。$ npm install -g es-checker    $ es-checker
使用下面的命令，可以查看 Node 已经实现的 ES6 特性。
`// Linux & Mac
$ node --v8-options | grep harmony
  
  
// Windows
$ node --v8-options | findstr harmony`  
一个工具 ES-Checker，用来检查各种运行环境对 ES6 的支持情况。访问ruanyf.github.io/es-checker，可以看到您的浏览器支持 ES6 的程度。运行下面的命令，可以查看你正在使用的 Node 环境对 ES6 的支持程度。  
`$ npm install -g es-checker
$ es-checker

=========================================
Passes 24 feature Detections
Your runtime supports 57% of ECMAScript 6
=========================================`
## Babel 是一个广泛使用的 ES6 转码器
下面的命令在项目目录中，安装 Babel。  
$ npm install --save-dev @babel/core
Babel 的配置文件是.babelrc，存放在项目的根目录下。使用 Babel 的第一步，就是配置这个文件。
presets字段设定转码规则，官方提供以下的规则集，你可以根据需要安装。
## 最新转码规则
`$ npm install --save-dev @babel/preset-env
  
  
react 转码规则
$ npm install --save-dev @babel/preset-react`

