# jsHint

## 安装

全局node安装

```
npm i jshint -g
```

## 配置

这里通过.jshintrc配置文件的方式写配置

* 新建.jshintrc文件 [htaccess必须键入文件名问题](http://jingyan.baidu.com/article/c74d600082eb280f6a595d18.html)

* 写个基本的配置

  ```xml
  {
    //严格模式
    "strict":true,
    //禁用位运算符，位运算符在 JavaScript 中使用较少，经常是把 && 错输成 &
    "bitwise":true,
    //循环或者条件语句必须使用花括号包围
    "curly": true,
    //禁止定义之前使用变量
    "latedef": true,
    //构造器函数首字母大写
    "newcap": true,
    //代码字符串禁止单引号双引号混用 single/double--只允许单/双引号
    "quotmark": true,
    //变量未定义
    "undef": true,
    //变量未使用
    "unused": true,
    //最多参数个数
    "maxparams":4,
    //最大嵌套深度
    "maxdepth": 4,
    //最大行数
    "maxlen": 800,
    //最多参数个数
    "maxparams":4,

    //--------------宽松选项 设置为true时,JSHint将不会警告------------
    //禁止缺少分号警告
    "asi": true,
    //允许在if，for，while语句中使用赋值;在条件语句中使用赋值经常是笔误if (a = 10) {}
    //"boss": true,
    //检查逗号在代码行最前面的编程风格
    "laxcomma":true,

    //--------------暴露环境变量------------
    //暴露浏览器属性的全局变量如 window/document
    "browser": true,
    //这个选项定义了全局变量,通常用于日志调试: console/alert等等
    "devel": true,
    //这个选项定义全局暴露的jQuery库
    "jquery": true,
    //这个选项定义全局变量可以当你的代码运行在node的运行时环境
    "node": true,
    //这个选项定义非标准但广泛采用全局变量等 escape和 unescape
    "nonstandard": true
  }
  ```

* 注意：需要配置暴露环境变量，否则alert等将保持；jshint支持宽松选项，设置为true时是被允许不报错

## 执行

### 全局命令执行

```
jshint js/a.js  //检测某文件
jshint js		//检测某目录
```

### npm命令执行

在package.json文件中写好配置

```
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "hint": "jshint js/1.js"
  },
```

执行

```
npm run hint
```

