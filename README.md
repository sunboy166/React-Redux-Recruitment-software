# 实时聊天招聘APP
## 描述
这是一款React + React Router + Redux 开发的高颜值实时聊天招聘APP，技术上使用React16 + Redux + React Router4开发复杂的单页面应用，并使用node.js + express + socket.io管理实时应用的后端
## 下载源码
```
git clone https://github.com/fangfeiyue/React-Redux-Recruitment-software.git
```
## 运行项目
```
npm install
npm start
```
## 技术选型
- 版本控制：git
- 开发工具：vscode
- 软件开发过程：敏捷开发
- 前端：React16 + Redux + React Router4
- 后端：node.js + express + socket.io
- 模块化方案：ES6 + Webpack
- 前后端分离方式：完全分离，纯静态方式
## 知识点总结
### React开发环境
- create-react-app的使用
  - npm install -g create-react-app 
  - npm create-react-app 创建的项目名称
  - cd到项目目录，运行npm start 启动安装好的项目
  - 浏览器输入localhost:3000
  - npm install redux --save 安装第三方库
  - npm run eject 弹出配置文件，可以自定义配置webpack
  - 扩展package.json里的script字段，扩展 npm run命令
遇到的问题：在运行`npm install redux --save`安装redux时，报错
```
Failed to parse json
npm ERR! Unexpected token '/' at 8:5
npm ERR!     // webpack、eslint的配置都在react-scripts
npm ERR!     ^
npm ERR! File: /Users/fangfeiyue/Desktop/GuoAn/recruitment/package.json
npm ERR! Failed to parse package.json data.
```
原因：package.json文件中用了双斜杠注释
```
"dependencies": {
    "react": "^16.0.0",
    "react-dom": "^16.0.0",
    // webpack、eslint的配置都在react-scripts
    "react-scripts": "1.0.15"
},
```
解决办法：去掉双斜杠注释
- 对象赋值
```
//第一种
var name  = 'fang';
var obj   = {};
obj[name] = 'fei';
console.log(obj);//{fang: "fei"}
//第二种
var name  = 'fang';
var obj   = {
    name:'张'//取不到外面的变量
};
obj[name] = 'fei';
console.log(obj);{name: "张", fang: "fei"}
//第三种
var name  = 'fang';
var obj   = {
    [name]: '张'
};
console.log(obj);//{fang: "张"}
obj[name] = 'fei';
console.log(obj);//{fang: "fei"}
//第四种
var name = 'fang';
var obj = {
    name: name
    print: function(){
        console.log(this.name);
    }
}
可简写为：
var name = 'fang';
var obj = {
    name,
    print(){
        console.log(this.name);
    }
};
```
### [Express基础应用](http://www.expressjs.com.cn/)
- Express简单使用
    - 安装
    ```
    npm install express --save
    ```
    - 简单使用--创建server.js，写入以下内容
    ```
    const express = require('express');
    // 新建app
    const app = express();

    // 返回html 
    app.get('/', function(req, res){
        res.send('<h1>hello express,I am learning</h1>');
    });

    // 返回json数据
    app.get('/data', function(req, res){
        res.json({name: 'learning', type: 'react'});
    });

    app.listen(9093, function(){
        console.log('Node app start at port 9093');
    });
    ```
    - 启动
    ```
    node server.js
    ```
    这样用有个缺点，每次修改server.js的文件内容都要停止服务然后再启动，这样太麻烦了，我们可以使用`nodemon`让node自动启动
    - 安装nodemon
    ```
    npm install -g nodemon
    ```
    - 使用nodemon
    ```
    nodemon server.js
    ```
- Express常用的几个特性
    - app.get、app.post分别开发get和post接口
    - app.use使用模块
    - res.send（文本）、res.json（json）、res.sendfile（文件）响应不同的内容
### [MongoDB](https://www.mongodb.com/)
- 安装Homebrew (MAC),其他安装方式见[官网](https://www.mongodb.com/download-center#community)
```
brew install mongodb
```
如果报`brew: command not found`，可能是没有安装Homebrew，在终端执行
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
### React
- React16是第一个核心代码重写的版本，整体API变化不大，主要变更了错误处理、生命周期、打包，对开发影响不是特别大
- 安装
```
npm install --save react
```
- React生命周期
![react生命周期](https://github.com/fangfeiyue/React-Redux-Recruitment-software/blob/master/react%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)
## 传说中的彩蛋
## 说明
如果对您有帮助，您可以点右上角 "Star" 支持一下 谢谢！ ^_^

或者您可以 "follow" 一下，我会不断开源更多的有趣的项目
## 个人简介
作者：房飞跃

博客地址：[前端网](http://www.qdfuns.com/house/31986/note)  [博客园](https://www.cnblogs.com/fangfeiyue)  [GitHub](https://github.com/fangfeiyue)

职业：web前端开发工程师

爱好：探索新事物，学习新知识

座右铭：一个终身学习者

## 联系方式
坐标：北京

QQ：294925572

微信：

![XinShiJieDeHuHuan](http://note.youdao.com/yws/public/resource/c2361265179a03449f6d52397fd50033/xmlnote/100D55934BB446839482D3EA0CDC3E8D/17820)

## 赞赏
觉得有帮助可以微信扫码支持下哦，赞赏金额不限，一分也是您对作者的鼎力支持

![微信打赏](http://note.youdao.com/yws/public/resource/c2361265179a03449f6d52397fd50033/xmlnote/D77744C8EC944CF6AA232272CBC5CF6D/17828)
