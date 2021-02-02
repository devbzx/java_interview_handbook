* [一、AJAX](#%E4%B8%80ajax)
  * [1、对 ajax 的认实](#1%E5%AF%B9-ajax-%E7%9A%84%E8%AE%A4%E5%AE%9E)
  * [2、jsonp 原理](#2jsonp-%E5%8E%9F%E7%90%86)
* [二、Linux](#%E4%BA%8Clinux)
  * [1、常用的 linux 命令](#1%E5%B8%B8%E7%94%A8%E7%9A%84-linux-%E5%91%BD%E4%BB%A4)
  * [2、 查看日志](#2-%E6%9F%A5%E7%9C%8B%E6%97%A5%E5%BF%97)
  * [3、关闭进程](#3%E5%85%B3%E9%97%AD%E8%BF%9B%E7%A8%8B)
* [三、常用的前端框架](#%E4%B8%89%E5%B8%B8%E7%94%A8%E7%9A%84%E5%89%8D%E7%AB%AF%E6%A1%86%E6%9E%B6)

# 一、AJAX

## 1、对 `ajax` 的认实

`Ajax` 是一种创建交互式网页应用的网页开发技术；`Asynchronous JavaScript and XML` 的缩写。

**`Ajax` 的优势**

通过异步模式，提升了用户体验。优化了浏览器和服务器之间的传输，减少不必要的数据往返，减少了带宽占用。

`Ajax` 引擎在客户端运行，承担了一部分本来由服务器承担的工作，从而减少了大用户量下的服务器负载。

**`Ajax` 的最大特点**

局部刷新，提升用户体验

## 2、`jsonp` 原理

`jsonp` 的最基本的原理是：动态添加一个`<script>`标签，使用 `script` 标签的 `src` 属性没有跨域的限制的特点
实现跨域。

首先在客户端注册一个 `callback`, 然后把 `callback` 的名字传给服务器。此时，服务器先生成 `json` 数 
据。

然后以 `javascript` 语法的方式，生成一个 `function` , `function` 名字就是传递上来的参数 `jsonp`。

最后将`json` 数据直接以入参的方式，放置到 `function` 中，这样就生成了一段 `js` 语法的文档，返回给客户端。 

客户端浏览器，解析 `script` 标签，并执行返回的 `javascript `文档，此时数据作为参数，传入到了客户端预先定义好的 `callback` 函数里。 

# 二、Linux

## 1、常用的 `linux` 命令

列出文件列表：`ls` 【参数 -a -l】

创建目录和移除目录：`mkdir`   `rmdir`

显示文件后几行：`tail`

打包：`tar -xvf`

打包并压缩：`tar -zcvf`

查找字符串：`grep`

显示当前所在目录：`pwd`

创建空文件：`touch`

编辑器：`vim` `vi`

## 2、 查看日志

动态打印日志信息：tail -f 日志文件

## 3、关闭进程

`ps` 查看当前正在运行的进程

`grep` 搜索

如：`ps -ef | grep java`

表示查看所有进程里 `CMD` 是 `java` 的进程信息。

`ps -aux | grep java`

`-aux` 显示所有状态

`kill` 命令用于终止进程，如`kill -9 [PID]` -9 表示强迫进程立即停止。

# 三、常用的前端框架

`EasyUI`、`MiniUI`、`JQueryUI`、`vue.js`、`AngularJS`



