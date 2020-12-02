步骤：
【1】拉取远程仓库, npm init初始化生成package.json文件
【2】在package.json文件中将相应的开发以来写入
"dependencies": {
    "commander": "^4.1.1",
    "download-git-repo": "^3.0.2",
    "inquirer": "^7.0.4",
    "chalk": "^3.0.0",
    "child_process": "^1.0.2",
}
依赖作用：
    commander：用于定义自己的命令
    download-git-repo：下载git仓库代码的库
    inquirer：用于向用户提出问题和获取回答
    chalk：改变命令行打印内容的样式
    child_process：用于执行命令行的指令
    
<!-- 【3】npm i 将相关的npm包下载到node_modules中 -->
【3】在项目根目录创建index.js文件，写入相应的处理逻辑
#! /usr/bin/env node是执行这个文件时使用node方式执行
program.version是解析别人输入lcj-cli-vue -v时输出的内容: 1.0.0
command解析输入lcj-cli-vue init vue my-vue-project，init后面两个参数，一个模板名，一个项目名
action是根据上面的两个参数做相应的逻辑处理，判断模板名，去相应的git仓库下载代码。download的第一个参数下载地址不是填我们git的网址，按照我的格式填就行，第二个参数是生成的项目名，第三个参数是错误的回调执行函数。
【4】在package.json文件中加入，这一步是我们在命令行jkc-cli的时候执行的文件。
