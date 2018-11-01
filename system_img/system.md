<!DOCTYPE html>
<!-- saved from url=(0024)http://www.mdeditor.com/ -->
<html lang="zh" style=""><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <title>Markdown在线编辑器 - MdEditor</title>
    <meta name="keywords" content="markdown在线编辑器,online markdown editor,markdown编辑器,在线编辑markdown,mdeditor">
    <meta name="description" content="mdeditor是一个在线编辑markdown的工具">
    <link rel="stylesheet" href="./system_files/style.css">
    <link rel="stylesheet" href="./system_files/editormd.min.css">
    <link rel="shortcut icon" href="http://www.mdeditor.com/images/logos/favicon.ico" type="image/x-icon">
    <script src="./system_files/hm.js"></script><script>
        var _hmt = _hmt || [];
        (function() {
            var hm = document.createElement("script");
            hm.src = "https://hm.baidu.com/hm.js?076c2cebde2229783d44f7f8cd54d2a4";
            var s = document.getElementsByTagName("script")[0];
            s.parentNode.insertBefore(hm, s);
        })();
    </script>
<link type="text/css" rel="stylesheet" href="./system_files/codemirror.min.css"><link type="text/css" rel="stylesheet" href="./system_files/dialog.css"><link type="text/css" rel="stylesheet" href="./system_files/matchesonscrollbar.css"><link type="text/css" rel="stylesheet" href="./system_files/foldgutter.css"><script id="-lib-codemirror-codemirror-min" type="text/javascript" src="./system_files/codemirror.min.js"></script><script id="-lib-codemirror-modes-min" type="text/javascript" src="./system_files/modes.min.js"></script><script id="-lib-codemirror-addons-min" type="text/javascript" src="./system_files/addons.min.js"></script><link type="text/css" rel="stylesheet" href="./system_files/eclipse.css"><script id="-lib-marked-min" type="text/javascript" src="./system_files/marked.min.js"></script><script id="-lib-prettify-min" type="text/javascript" src="./system_files/prettify.min.js"></script><script id="-lib-raphael-min" type="text/javascript" src="./system_files/raphael.min.js"></script><script id="-lib-underscore-min" type="text/javascript" src="./system_files/underscore.min.js"></script><script id="-lib-flowchart-min" type="text/javascript" src="./system_files/flowchart.min.js"></script><script id="-lib-jquery-flowchart-min" type="text/javascript" src="./system_files/jquery.flowchart.min.js"></script><script id="-lib-sequence-diagram-min" type="text/javascript" src="./system_files/sequence-diagram.min.js"></script><link type="text/css" rel="stylesheet" href="./system_files/katex.min.css"><script id="-cdnjs-cloudflare-com-ajax-libs-KaTeX-0-3-0-katex-min" type="text/javascript" src="./system_files/katex.min.js"></script><script id="-lib-plugins-link-dialog-link-dialog" type="text/javascript" src="./system_files/link-dialog.js"></script><script id="-lib-plugins-image-dialog-image-dialog" type="text/javascript" src="./system_files/image-dialog.js"></script><script id="-lib-plugins-table-dialog-table-dialog" type="text/javascript" src="./system_files/table-dialog.js"></script><script id="-lib-plugins-download-dialog-download-dialog" type="text/javascript" src="./system_files/download-dialog.js"></script></head>
<body class="" style="">
<div id="layout">
    <div id="test-editormd" style="width: 1440px; height: 685px;" class="editormd editormd-vertical editormd-theme-eclipse editormd-fullscreen"><textarea class="editormd-markdown-textarea" placeholder="Enjoy Markdown! coding now..." name="test-editormd-markdown-doc" style="display: none;"># 爬虫系统设计文档，开发排期--v0.1版本（2018-第四季度）
- 文档说明：第四季度爬虫框架开发需求，流程设计图，模块设计图，本季度主要完成，调度模块，爬取模块，12月中旬之后能够投入测试阶段

## 爬虫流程图设计

![爬虫流程图](https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/%E7%88%AC%E8%99%AB%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg "爬虫流程图")

### 模块说明
1. Schedule：调度器；
1. Crawler：爬取模块；
1. Parse：解析模块；
1. Persistence：数据持久化。

## 调度器设计
![调度器](https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/Scheduler.jpg "调度器")

#### 调度器设计排期表
| 名称  | 描述  | 目标形式  | 指派人  | 预期完成时间  | 实际完成时间  |  验收人 |  备注 |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| 配置文件  | 爬取的需求说明，包括需要爬取的数据格式，周期等  | 文本文件  | Eileen  |  12月初 |   |   |   |
| 资源状态判断  | 在做数据爬取之前对网站的一个状态判定，包括服务是否存在，平均响应时间判定  |   | 脚本  |  Eileen | 12月10日前  |   |   |
| 日志模块  |  调度过程日志需求 | 脚本  | Eileen  |11月中旬   |   |   |   |
| 定时器  | 定时启动脚本任务  |  脚本 | Vinndy  |  12月初 |   |   |   |
| 去重模块  | 去除重复数据请求 |  脚本 |  Eileen |  12月初 |   |   |   |
| url生成器  | 去除重复url，给出正确可以爬取的url地址  | 脚本，接口调用  |  Vinndy | 12月初  |   |   |   |


## 爬取模块设计
![crawler](https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/crawler.jpg "crawler")

#### 模块构成时间排期表格

|  名称 | 描述  | 目标形式  |  指派人 |  预期完成时间 | 实际完成时间  |  验收人 | 备注  |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| session池  | session池，cookie管理主流网站的登录  |  脚本 | Eileen  |  11月底 |   |   |   |
| 请求池httpApi  |  请求池 |  脚本，接口 |  Eileen | 11月中旬  |   |   |   |
| 代理池  |  IP代理池 | 脚本，接口  | Vinddy  | 11月中旬  |   |   |   |
| UA池  | User-Agent，提供各种浏览器的伪装  |   脚本，接口|  Vinddy | 11月中旬  |   |   |   |
| 中间件  | 接收url，发送新的url  |  脚本 |  Vinddy | 11月中旬  |   |   |   |
| 日志模块  |  收集爬取的正常，报警，错误信息等 | 调用接口  | Eileen  |  11月中旬 |   |   |   |


##### 1、session管理池开发排期表
开发步骤
- 调研各个网站的登录结构，找到预期困难点---时间节点：十一月中旬
- 采用公共账号管理所有网站，文本方式管理---时间节点：十一月中旬
- 做成公共session池，在爬取数据时调用---时间节点：十一月底

|  网站名称 |  描述 | 预计完成时间  | 实际完成时间  |  完成形式 |  备注 |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| 知乎  | 用户名,密码登陆  |   |   |   |   |
| 微博 | 用户名,密码登陆  |   |   |   |   |
| 拉勾网  | 用户名，密码登陆  |   |   |   |   |
| CSND博客网  | 用户名，密码登陆  |   |   |   |   |
| Github  | 用户名，密码登陆  |   |   |   |   |
|  B站 | 用户名，密码登陆  |   |   |   |   |
| 豆瓣  | 用户名，密码登陆  |   |   |   |   |
| 珍爱网  | 用户名，密码登陆  |   |   |   |   |
| 果壳网  | 用户名，密码登陆  |   |   |   |   |

##### 2、HttpApiPool 请求池开发排期
##### 6、日志模块
请求模块中的日志模块开发
开发步骤
- 确定日志格式，包括(时间，事件，响应结果) ,确定日志包含内容，正常响应，错误响应，报警信息---时间节点：11月5日；
- 开发日志调用接口---时间节点：11月中旬；

## 解析/存储模块
![解析模块](https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/pp.jpg "解析模块")

- 爬虫项目构成
![爬虫项目构成](https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/pcxm.jpg "爬虫项目构成")

## 数据存储
采用json格式存储在redis或mongodb中





</textarea><div class="CodeMirror cm-s-eclipse CodeMirror-wrap CodeMirror-focused" style="font-size: 13px; width: 721px; margin-top: 40px; height: 646px; display: block;"><div style="overflow: hidden; position: relative; width: 3px; height: 0px; top: 136px; left: 140px;"><textarea autocorrect="off" autocapitalize="off" spellcheck="false" style="position: absolute; padding: 0px; width: 1000px; height: 1em; outline: none;" tabindex="0"></textarea></div><div class="CodeMirror-vscrollbar" cm-not-content="true" style="bottom: 0px; display: block;"><div style="min-width: 1px; height: 2123px;"></div></div><div class="CodeMirror-hscrollbar" cm-not-content="true"><div style="height: 100%; min-height: 1px; width: 0px;"></div></div><div class="CodeMirror-scrollbar-filler" cm-not-content="true"></div><div class="CodeMirror-gutter-filler" cm-not-content="true"></div><div class="CodeMirror-scroll" tabindex="-1"><div class="CodeMirror-sizer" style="margin-left: 48px; margin-bottom: -7px; border-right-width: 23px; min-height: 2120px; padding-right: 7px; padding-bottom: 0px;"><div style="position: relative; top: 0px;"><div class="CodeMirror-lines"><div style="position: relative; outline: none;"><div class="CodeMirror-measure"><pre>x</pre></div><div class="CodeMirror-measure"><pre><span style="padding-right: 0.1px;">采用json格式存储在redis或mongodb中</span></pre></div><div style="position: relative; z-index: 1;"></div><div class="CodeMirror-cursors" style="visibility: hidden;"><div class="CodeMirror-cursor" style="left: 92px; top: 132px; height: 22px;">&nbsp;</div></div><div class="CodeMirror-code" style=""><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">1</div><div class="CodeMirror-gutter-elt" style="left: 38px; width: 9px;"><div class="CodeMirror-foldgutter-open CodeMirror-guttermarker-subtle"></div></div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-header cm-header-1"># 爬虫系统设计文档，开发排期--v0.1版本（2018-第四季度）</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">2</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-variable-2">- 文档说明：第四季度爬虫框架开发需求，流程设计图，模块设计图，本季度主要完成，调度模块，爬取模块，12月中旬之后能够投入测试阶段</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">3</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">4</div><div class="CodeMirror-gutter-elt" style="left: 38px; width: 9px;"><div class="CodeMirror-foldgutter-open CodeMirror-guttermarker-subtle"></div></div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-header cm-header-2">## 爬虫流程图设计</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">5</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div class="CodeMirror-activeline" style="position: relative;"><div class="CodeMirror-activeline-background CodeMirror-linebackground"></div><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">6</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tag">![爬虫流程图]</span><span class="cm-string">(https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/%E7%88%AC%E8%99%AB%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg "爬虫流程图")</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">7</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">8</div><div class="CodeMirror-gutter-elt" style="left: 38px; width: 9px;"><div class="CodeMirror-foldgutter-open CodeMirror-guttermarker-subtle"></div></div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-header cm-header-3">### 模块说明</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">9</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-variable-2">1. Schedule：调度器；</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">10</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-variable-2">1. Crawler：爬取模块；</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">11</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-variable-2">1. Parse：解析模块；</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">12</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-variable-2">1. Persistence：数据持久化。</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">13</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">14</div><div class="CodeMirror-gutter-elt" style="left: 38px; width: 9px;"><div class="CodeMirror-foldgutter-open CodeMirror-guttermarker-subtle"></div></div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-header cm-header-2">## 调度器设计</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">15</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tag">![调度器]</span><span class="cm-string">(https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/Scheduler.jpg "调度器")</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">16</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">17</div><div class="CodeMirror-gutter-elt" style="left: 38px; width: 9px;"><div class="CodeMirror-foldgutter-open CodeMirror-guttermarker-subtle"></div></div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-header cm-header-4">#### 调度器设计排期表</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">18</div></div><pre class=""><span style="padding-right: 0.1px;">| 名称  | 描述  | 目标形式  | 指派人  | 预期完成时间  | 实际完成时间  |  验收人 |  备注 |</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">19</div></div><pre class=""><span style="padding-right: 0.1px;">| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">20</div></div><pre class=""><span style="padding-right: 0.1px;">| 配置文件  | 爬取的需求说明，包括需要爬取的数据格式，周期等  | 文本文件  | Eileen  |  12月初 | &nbsp; | &nbsp; | &nbsp; |</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">21</div></div><pre class=""><span style="padding-right: 0.1px;">| 资源状态判断  | 在做数据爬取之前对网站的一个状态判定，包括服务是否存在，平均响应时间判定  | &nbsp; | 脚本  |  Eileen | 12月10日前  | &nbsp; | &nbsp; |</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">22</div></div><pre class=""><span style="padding-right: 0.1px;">| 日志模块  |  调度过程日志需求 | 脚本  | Eileen  |11月中旬 &nbsp; | &nbsp; | &nbsp; | &nbsp; |</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">23</div></div><pre class=""><span style="padding-right: 0.1px;">| 定时器  | 定时启动脚本任务  |  脚本 | Vinndy  |  12月初 | &nbsp; | &nbsp; | &nbsp; |</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">24</div></div><pre class=""><span style="padding-right: 0.1px;">| 去重模块  | 去除重复数据请求 |  脚本 |  Eileen |  12月初 | &nbsp; | &nbsp; | &nbsp; |</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">25</div></div><pre class=""><span style="padding-right: 0.1px;">| url生成器  | 去除重复url，给出正确可以爬取的url地址  | 脚本，接口调用  |  Vinndy | 12月初  | &nbsp; | &nbsp; | &nbsp; |</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">26</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">27</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">28</div><div class="CodeMirror-gutter-elt" style="left: 38px; width: 9px;"><div class="CodeMirror-foldgutter-open CodeMirror-guttermarker-subtle"></div></div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-header cm-header-2">## 爬取模块设计</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">29</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tag">![crawler]</span><span class="cm-string">(https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/crawler.jpg "crawler")</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">30</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">31</div><div class="CodeMirror-gutter-elt" style="left: 38px; width: 9px;"><div class="CodeMirror-foldgutter-open CodeMirror-guttermarker-subtle"></div></div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-header cm-header-4">#### 模块构成时间排期表格</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">32</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative; display: none;"><div class="CodeMirror-gutter-wrapper" style="left: -48px; width: 48px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 20px;">69</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tag">![解析模块]</span><span class="cm-string">(https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/pp.jpg "解析模块")</span></span></pre></div></div></div></div></div></div><div style="position: absolute; height: 23px; width: 1px; top: 2120px;"></div><div class="CodeMirror-gutters" style="height: 2143px;"><div class="CodeMirror-gutter CodeMirror-linenumbers" style="width: 28px;"></div><div class="CodeMirror-gutter CodeMirror-foldgutter"></div></div></div></div><a href="javascript:;" class="fa fa-close editormd-preview-close-btn" style="display: none;"></a>
<textarea class="editormd-html-textarea" name="test-editormd-html-code">&lt;h1 id="h1--v0-1-2018-"&gt;&lt;a name="爬虫系统设计文档，开发排期—v0.1版本（2018-第四季度）" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;爬虫系统设计文档，开发排期—v0.1版本（2018-第四季度）&lt;/h1&gt;&lt;ul&gt;
&lt;li&gt;文档说明：第四季度爬虫框架开发需求，流程设计图，模块设计图，本季度主要完成，调度模块，爬取模块，12月中旬之后能够投入测试阶段&lt;/li&gt;&lt;/ul&gt;
&lt;h2 id="h2-u722Cu866Bu6D41u7A0Bu56FEu8BBEu8BA1"&gt;&lt;a name="爬虫流程图设计" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;爬虫流程图设计&lt;/h2&gt;&lt;p&gt;&lt;img src="https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/%E7%88%AC%E8%99%AB%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg" alt="爬虫流程图" title="爬虫流程图"&gt;
&lt;h3 id="h3-u6A21u5757u8BF4u660E"&gt;&lt;a name="模块说明" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;模块说明&lt;/h3&gt;&lt;ol&gt;
&lt;li&gt;Schedule：调度器；&lt;/li&gt;&lt;li&gt;Crawler：爬取模块；&lt;/li&gt;&lt;li&gt;Parse：解析模块；&lt;/li&gt;&lt;li&gt;Persistence：数据持久化。&lt;/li&gt;&lt;/ol&gt;
&lt;h2 id="h2-u8C03u5EA6u5668u8BBEu8BA1"&gt;&lt;a name="调度器设计" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;调度器设计&lt;/h2&gt;&lt;p&gt;&lt;img src="https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/Scheduler.jpg" alt="调度器" title="调度器"&gt;
&lt;h4 id="h4-u8C03u5EA6u5668u8BBEu8BA1u6392u671Fu8868"&gt;&lt;a name="调度器设计排期表" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;调度器设计排期表&lt;/h4&gt;&lt;table&gt;
&lt;thead&gt;
&lt;tr&gt;
&lt;th&gt;名称&lt;/th&gt;
&lt;th&gt;描述&lt;/th&gt;
&lt;th&gt;目标形式&lt;/th&gt;
&lt;th&gt;指派人&lt;/th&gt;
&lt;th&gt;预期完成时间&lt;/th&gt;
&lt;th&gt;实际完成时间&lt;/th&gt;
&lt;th&gt;验收人&lt;/th&gt;
&lt;th&gt;备注&lt;/th&gt;
&lt;/tr&gt;
&lt;/thead&gt;
&lt;tbody&gt;
&lt;tr&gt;
&lt;td&gt;配置文件&lt;/td&gt;
&lt;td&gt;爬取的需求说明，包括需要爬取的数据格式，周期等&lt;/td&gt;
&lt;td&gt;文本文件&lt;/td&gt;
&lt;td&gt;Eileen&lt;/td&gt;
&lt;td&gt;12月初&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;资源状态判断&lt;/td&gt;
&lt;td&gt;在做数据爬取之前对网站的一个状态判定，包括服务是否存在，平均响应时间判定&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;脚本&lt;/td&gt;
&lt;td&gt;Eileen&lt;/td&gt;
&lt;td&gt;12月10日前&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;日志模块&lt;/td&gt;
&lt;td&gt;调度过程日志需求&lt;/td&gt;
&lt;td&gt;脚本&lt;/td&gt;
&lt;td&gt;Eileen&lt;/td&gt;
&lt;td&gt;11月中旬&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;定时器&lt;/td&gt;
&lt;td&gt;定时启动脚本任务&lt;/td&gt;
&lt;td&gt;脚本&lt;/td&gt;
&lt;td&gt;Vinndy&lt;/td&gt;
&lt;td&gt;12月初&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;去重模块&lt;/td&gt;
&lt;td&gt;去除重复数据请求&lt;/td&gt;
&lt;td&gt;脚本&lt;/td&gt;
&lt;td&gt;Eileen&lt;/td&gt;
&lt;td&gt;12月初&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;url生成器&lt;/td&gt;
&lt;td&gt;去除重复url，给出正确可以爬取的url地址&lt;/td&gt;
&lt;td&gt;脚本，接口调用&lt;/td&gt;
&lt;td&gt;Vinndy&lt;/td&gt;
&lt;td&gt;12月初&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;/tbody&gt;
&lt;/table&gt;
&lt;h2 id="h2-u722Cu53D6u6A21u5757u8BBEu8BA1"&gt;&lt;a name="爬取模块设计" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;爬取模块设计&lt;/h2&gt;&lt;p&gt;&lt;img src="https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/crawler.jpg" alt="crawler" title="crawler"&gt;
&lt;h4 id="h4-u6A21u5757u6784u6210u65F6u95F4u6392u671Fu8868u683C"&gt;&lt;a name="模块构成时间排期表格" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;模块构成时间排期表格&lt;/h4&gt;&lt;table&gt;
&lt;thead&gt;
&lt;tr&gt;
&lt;th&gt;名称&lt;/th&gt;
&lt;th&gt;描述&lt;/th&gt;
&lt;th&gt;目标形式&lt;/th&gt;
&lt;th&gt;指派人&lt;/th&gt;
&lt;th&gt;预期完成时间&lt;/th&gt;
&lt;th&gt;实际完成时间&lt;/th&gt;
&lt;th&gt;验收人&lt;/th&gt;
&lt;th&gt;备注&lt;/th&gt;
&lt;/tr&gt;
&lt;/thead&gt;
&lt;tbody&gt;
&lt;tr&gt;
&lt;td&gt;session池&lt;/td&gt;
&lt;td&gt;session池，cookie管理主流网站的登录&lt;/td&gt;
&lt;td&gt;脚本&lt;/td&gt;
&lt;td&gt;Eileen&lt;/td&gt;
&lt;td&gt;11月底&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;请求池httpApi&lt;/td&gt;
&lt;td&gt;请求池&lt;/td&gt;
&lt;td&gt;脚本，接口&lt;/td&gt;
&lt;td&gt;Eileen&lt;/td&gt;
&lt;td&gt;11月中旬&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;代理池&lt;/td&gt;
&lt;td&gt;IP代理池&lt;/td&gt;
&lt;td&gt;脚本，接口&lt;/td&gt;
&lt;td&gt;Vinddy&lt;/td&gt;
&lt;td&gt;11月中旬&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;UA池&lt;/td&gt;
&lt;td&gt;User-Agent，提供各种浏览器的伪装&lt;/td&gt;
&lt;td&gt;脚本，接口&lt;/td&gt;
&lt;td&gt;Vinddy&lt;/td&gt;
&lt;td&gt;11月中旬&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;中间件&lt;/td&gt;
&lt;td&gt;接收url，发送新的url&lt;/td&gt;
&lt;td&gt;脚本&lt;/td&gt;
&lt;td&gt;Vinddy&lt;/td&gt;
&lt;td&gt;11月中旬&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;日志模块&lt;/td&gt;
&lt;td&gt;收集爬取的正常，报警，错误信息等&lt;/td&gt;
&lt;td&gt;调用接口&lt;/td&gt;
&lt;td&gt;Eileen&lt;/td&gt;
&lt;td&gt;11月中旬&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;/tbody&gt;
&lt;/table&gt;
&lt;h5 id="h5-1-session-"&gt;&lt;a name="1、session管理池开发排期表" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;1、session管理池开发排期表&lt;/h5&gt;&lt;p&gt;开发步骤&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;调研各个网站的登录结构，找到预期困难点—-时间节点：十一月中旬&lt;/li&gt;&lt;li&gt;采用公共账号管理所有网站，文本方式管理—-时间节点：十一月中旬&lt;/li&gt;&lt;li&gt;做成公共session池，在爬取数据时调用—-时间节点：十一月底&lt;/li&gt;&lt;/ul&gt;
&lt;table&gt;
&lt;thead&gt;
&lt;tr&gt;
&lt;th&gt;网站名称&lt;/th&gt;
&lt;th&gt;描述&lt;/th&gt;
&lt;th&gt;预计完成时间&lt;/th&gt;
&lt;th&gt;实际完成时间&lt;/th&gt;
&lt;th&gt;完成形式&lt;/th&gt;
&lt;th&gt;备注&lt;/th&gt;
&lt;/tr&gt;
&lt;/thead&gt;
&lt;tbody&gt;
&lt;tr&gt;
&lt;td&gt;知乎&lt;/td&gt;
&lt;td&gt;用户名,密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;微博&lt;/td&gt;
&lt;td&gt;用户名,密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;拉勾网&lt;/td&gt;
&lt;td&gt;用户名，密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;CSND博客网&lt;/td&gt;
&lt;td&gt;用户名，密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;Github&lt;/td&gt;
&lt;td&gt;用户名，密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;B站&lt;/td&gt;
&lt;td&gt;用户名，密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;豆瓣&lt;/td&gt;
&lt;td&gt;用户名，密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;珍爱网&lt;/td&gt;
&lt;td&gt;用户名，密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;果壳网&lt;/td&gt;
&lt;td&gt;用户名，密码登陆&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;td&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;/tbody&gt;
&lt;/table&gt;
&lt;h5 id="h5-2-httpapipool-"&gt;&lt;a name="2、HttpApiPool 请求池开发排期" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;2、HttpApiPool 请求池开发排期&lt;/h5&gt;&lt;h5 id="h5-6-"&gt;&lt;a name="6、日志模块" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;6、日志模块&lt;/h5&gt;&lt;p&gt;请求模块中的日志模块开发&lt;br&gt;开发步骤
&lt;ul&gt;
&lt;li&gt;确定日志格式，包括(时间，事件，响应结果) ,确定日志包含内容，正常响应，错误响应，报警信息—-时间节点：11月5日；&lt;/li&gt;&lt;li&gt;开发日志调用接口—-时间节点：11月中旬；&lt;/li&gt;&lt;/ul&gt;
&lt;h2 id="h2--"&gt;&lt;a name="解析/存储模块" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;解析/存储模块&lt;/h2&gt;&lt;p&gt;&lt;img src="https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/pp.jpg" alt="解析模块" title="解析模块"&gt;
&lt;ul&gt;
&lt;li&gt;爬虫项目构成&lt;br&gt;&lt;img src="https://raw.githubusercontent.com/chenyanfun/spider_system/master/system_img/pcxm.jpg" alt="爬虫项目构成" title="爬虫项目构成"&gt;&lt;/ul&gt;
&lt;h2 id="h2-u6570u636Eu5B58u50A8"&gt;&lt;a name="数据存储" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;数据存储&lt;/h2&gt;&lt;p&gt;采用json格式存储在redis或mongodb中&lt;/p&gt;
</textarea>
<div class="editormd-preview editormd-preview-theme-eclipse" style="display: block; width: 720px; top: 40px; height: 646px; background: rgb(255, 255, 255); position: absolute;"><div class="markdown-body editormd-preview-container" previewcontainer="true" style="padding: 20px;"><h1 id="h1--v0-1-2018-"><a name="爬虫系统设计文档，开发排期—v0.1版本（2018-第四季度）" class="reference-link"></a><span class="header-link octicon octicon-link"></span>爬虫系统设计文档，开发排期—v0.1版本（2018-第四季度）</h1><ul>
<li>文档说明：第四季度爬虫框架开发需求，流程设计图，模块设计图，本季度主要完成，调度模块，爬取模块，12月中旬之后能够投入测试阶段</li></ul>
<h2 id="h2-u722Cu866Bu6D41u7A0Bu56FEu8BBEu8BA1"><a name="爬虫流程图设计" class="reference-link"></a><span class="header-link octicon octicon-link"></span>爬虫流程图设计</h2><p><img src="./system_files/爬虫流程图.jpg" alt="爬虫流程图" title="爬虫流程图">
</p><h3 id="h3-u6A21u5757u8BF4u660E"><a name="模块说明" class="reference-link"></a><span class="header-link octicon octicon-link"></span>模块说明</h3><ol>
<li>Schedule：调度器；</li><li>Crawler：爬取模块；</li><li>Parse：解析模块；</li><li>Persistence：数据持久化。</li></ol>
<h2 id="h2-u8C03u5EA6u5668u8BBEu8BA1"><a name="调度器设计" class="reference-link"></a><span class="header-link octicon octicon-link"></span>调度器设计</h2><p><img src="./system_files/Scheduler.jpg" alt="调度器" title="调度器">
</p><h4 id="h4-u8C03u5EA6u5668u8BBEu8BA1u6392u671Fu8868"><a name="调度器设计排期表" class="reference-link"></a><span class="header-link octicon octicon-link"></span>调度器设计排期表</h4><table>
<thead>
<tr>
<th>名称</th>
<th>描述</th>
<th>目标形式</th>
<th>指派人</th>
<th>预期完成时间</th>
<th>实际完成时间</th>
<th>验收人</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr>
<td>配置文件</td>
<td>爬取的需求说明，包括需要爬取的数据格式，周期等</td>
<td>文本文件</td>
<td>Eileen</td>
<td>12月初</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>资源状态判断</td>
<td>在做数据爬取之前对网站的一个状态判定，包括服务是否存在，平均响应时间判定</td>
<td></td>
<td>脚本</td>
<td>Eileen</td>
<td>12月10日前</td>
<td></td>
<td></td>
</tr>
<tr>
<td>日志模块</td>
<td>调度过程日志需求</td>
<td>脚本</td>
<td>Eileen</td>
<td>11月中旬</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>定时器</td>
<td>定时启动脚本任务</td>
<td>脚本</td>
<td>Vinndy</td>
<td>12月初</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>去重模块</td>
<td>去除重复数据请求</td>
<td>脚本</td>
<td>Eileen</td>
<td>12月初</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>url生成器</td>
<td>去除重复url，给出正确可以爬取的url地址</td>
<td>脚本，接口调用</td>
<td>Vinndy</td>
<td>12月初</td>
<td></td>
<td></td>
</tr>
</tbody>
</table>
<h2 id="h2-u722Cu53D6u6A21u5757u8BBEu8BA1"><a name="爬取模块设计" class="reference-link"></a><span class="header-link octicon octicon-link"></span>爬取模块设计</h2><p><img src="./system_files/crawler.jpg" alt="crawler" title="crawler">
</p><h4 id="h4-u6A21u5757u6784u6210u65F6u95F4u6392u671Fu8868u683C"><a name="模块构成时间排期表格" class="reference-link"></a><span class="header-link octicon octicon-link"></span>模块构成时间排期表格</h4><table>
<thead>
<tr>
<th>名称</th>
<th>描述</th>
<th>目标形式</th>
<th>指派人</th>
<th>预期完成时间</th>
<th>实际完成时间</th>
<th>验收人</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr>
<td>session池</td>
<td>session池，cookie管理主流网站的登录</td>
<td>脚本</td>
<td>Eileen</td>
<td>11月底</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>请求池httpApi</td>
<td>请求池</td>
<td>脚本，接口</td>
<td>Eileen</td>
<td>11月中旬</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>代理池</td>
<td>IP代理池</td>
<td>脚本，接口</td>
<td>Vinddy</td>
<td>11月中旬</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>UA池</td>
<td>User-Agent，提供各种浏览器的伪装</td>
<td>脚本，接口</td>
<td>Vinddy</td>
<td>11月中旬</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>中间件</td>
<td>接收url，发送新的url</td>
<td>脚本</td>
<td>Vinddy</td>
<td>11月中旬</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>日志模块</td>
<td>收集爬取的正常，报警，错误信息等</td>
<td>调用接口</td>
<td>Eileen</td>
<td>11月中旬</td>
<td></td>
<td></td>
</tr>
</tbody>
</table>
<h5 id="h5-1-session-"><a name="1、session管理池开发排期表" class="reference-link"></a><span class="header-link octicon octicon-link"></span>1、session管理池开发排期表</h5><p>开发步骤</p>
<ul>
<li>调研各个网站的登录结构，找到预期困难点—-时间节点：十一月中旬</li><li>采用公共账号管理所有网站，文本方式管理—-时间节点：十一月中旬</li><li>做成公共session池，在爬取数据时调用—-时间节点：十一月底</li></ul>
<table>
<thead>
<tr>
<th>网站名称</th>
<th>描述</th>
<th>预计完成时间</th>
<th>实际完成时间</th>
<th>完成形式</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr>
<td>知乎</td>
<td>用户名,密码登陆</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>微博</td>
<td>用户名,密码登陆</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>拉勾网</td>
<td>用户名，密码登陆</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>CSND博客网</td>
<td>用户名，密码登陆</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>Github</td>
<td>用户名，密码登陆</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>B站</td>
<td>用户名，密码登陆</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>豆瓣</td>
<td>用户名，密码登陆</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>珍爱网</td>
<td>用户名，密码登陆</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>果壳网</td>
<td>用户名，密码登陆</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>
<h5 id="h5-2-httpapipool-"><a name="2、HttpApiPool 请求池开发排期" class="reference-link"></a><span class="header-link octicon octicon-link"></span>2、HttpApiPool 请求池开发排期</h5><h5 id="h5-6-"><a name="6、日志模块" class="reference-link"></a><span class="header-link octicon octicon-link"></span>6、日志模块</h5><p>请求模块中的日志模块开发<br>开发步骤
</p><ul>
<li>确定日志格式，包括(时间，事件，响应结果) ,确定日志包含内容，正常响应，错误响应，报警信息—-时间节点：11月5日；</li><li>开发日志调用接口—-时间节点：11月中旬；</li></ul>
<h2 id="h2--"><a name="解析/存储模块" class="reference-link"></a><span class="header-link octicon octicon-link"></span>解析/存储模块</h2><p><img src="./system_files/pp.jpg" alt="解析模块" title="解析模块">
</p><ul>
<li>爬虫项目构成<br><img src="./system_files/pcxm.jpg" alt="爬虫项目构成" title="爬虫项目构成"></li></ul>
<h2 id="h2-u6570u636Eu5B58u50A8"><a name="数据存储" class="reference-link"></a><span class="header-link octicon octicon-link"></span>数据存储</h2><p>采用json格式存储在redis或mongodb中</p>
</div></div>
<div class="editormd-container-mask" style="display: none;"></div>
<div class="editormd-mask" style="background-color: rgb(255, 255, 255); opacity: 0.1; z-index: 100000; display: none;"></div><div class="editormd-toolbar" style="display: block;"><div class="editormd-toolbar-container"><ul class="editormd-menu"><li><a href="javascript:;" title="撤销（Ctrl+Z）" unselectable="on"><i class="fa fa-undo" name="undo" unselectable="on"></i></a></li><li><a href="javascript:;" title="重做（Ctrl+Y）" unselectable="on"><i class="fa fa-repeat" name="redo" unselectable="on"></i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="粗体" unselectable="on"><i class="fa fa-bold" name="bold" unselectable="on"></i></a></li><li><a href="javascript:;" title="删除线" unselectable="on"><i class="fa fa-strikethrough" name="del" unselectable="on"></i></a></li><li><a href="javascript:;" title="斜体" unselectable="on"><i class="fa fa-italic" name="italic" unselectable="on"></i></a></li><li><a href="javascript:;" title="引用" unselectable="on"><i class="fa fa-quote-left" name="quote" unselectable="on"></i></a></li><li><a href="javascript:;" title="将每个单词首字母转成大写" unselectable="on"><i class="fa" name="ucwords" style="font-size:20px;margin-top: -3px;">Aa</i></a></li><li><a href="javascript:;" title="将所选转换成大写" unselectable="on"><i class="fa fa-font" name="uppercase" unselectable="on"></i></a></li><li><a href="javascript:;" title="将所选转换成小写" unselectable="on"><i class="fa" name="lowercase" style="font-size:24px;margin-top: -10px;">a</i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="标题1" unselectable="on"><i class="fa editormd-bold" name="h1" unselectable="on">H1</i></a></li><li><a href="javascript:;" title="标题2" unselectable="on"><i class="fa editormd-bold" name="h2" unselectable="on">H2</i></a></li><li><a href="javascript:;" title="标题3" unselectable="on"><i class="fa editormd-bold" name="h3" unselectable="on">H3</i></a></li><li><a href="javascript:;" title="标题4" unselectable="on"><i class="fa editormd-bold" name="h4" unselectable="on">H4</i></a></li><li><a href="javascript:;" title="标题5" unselectable="on"><i class="fa editormd-bold" name="h5" unselectable="on">H5</i></a></li><li><a href="javascript:;" title="标题6" unselectable="on"><i class="fa editormd-bold" name="h6" unselectable="on">H6</i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="无序列表" unselectable="on"><i class="fa fa-list-ul" name="list-ul" unselectable="on"></i></a></li><li><a href="javascript:;" title="有序列表" unselectable="on"><i class="fa fa-list-ol" name="list-ol" unselectable="on"></i></a></li><li><a href="javascript:;" title="横线" unselectable="on"><i class="fa fa-minus" name="hr" unselectable="on"></i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="链接" unselectable="on"><i class="fa fa-link" name="link" unselectable="on"></i></a></li><li><a href="javascript:;" title="引用链接" unselectable="on"><i class="fa fa-anchor" name="reference-link" unselectable="on"></i></a></li><li><a href="javascript:;" title="添加图片" unselectable="on"><i class="fa fa-picture-o" name="image" unselectable="on"></i></a></li><li><a href="javascript:;" title="行内代码" unselectable="on"><i class="fa fa-code" name="code" unselectable="on"></i></a></li><li><a href="javascript:;" title="预格式文本 / 代码块（缩进风格）" unselectable="on"><i class="fa fa-file-code-o" name="preformatted-text" unselectable="on"></i></a></li><li><a href="javascript:;" title="代码块（多语言风格）" unselectable="on"><i class="fa fa-file-code-o" name="code-block" unselectable="on"></i></a></li><li><a href="javascript:;" title="表格" unselectable="on"><i class="fa fa-table" name="table" unselectable="on"></i></a></li><li><a href="javascript:;" title="日期时间" unselectable="on"><i class="fa fa-clock-o" name="datetime" unselectable="on"></i></a></li><li><a href="javascript:;" title="Emoji表情" unselectable="on"><i class="fa fa-smile-o" name="emoji" unselectable="on"></i></a></li><li><a href="javascript:;" title="HTML实体字符" unselectable="on"><i class="fa fa-copyright" name="html-entities" unselectable="on"></i></a></li><li><a href="javascript:;" title="插入分页符" unselectable="on"><i class="fa fa-newspaper-o" name="pagebreak" unselectable="on"></i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="跳转到行" unselectable="on"><i class="fa fa-terminal" name="goto-line" unselectable="on"></i></a></li><li><a href="javascript:;" title="关闭实时预览" unselectable="on"><i class="fa fa-eye-slash" name="watch" unselectable="on"></i></a></li><li><a href="javascript:;" title="全窗口预览HTML（按 Shift + ESC还原）" unselectable="on"><i class="fa fa-desktop" name="preview" unselectable="on"></i></a></li><li><a href="javascript:;" title="清空" unselectable="on"><i class="fa fa-eraser" name="clear" unselectable="on"></i></a></li><li><a href="javascript:;" title="搜索" unselectable="on"><i class="fa fa-search" name="search" unselectable="on"></i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="使用帮助" unselectable="on"><i class="fa fa-question-circle" name="help" unselectable="on"></i></a></li><li><a href="javascript:;" title="关于Editor.md" unselectable="on"><i class="fa fa-info-circle" name="info" unselectable="on"></i></a></li><li><a href="javascript:;" title="" unselectable="on"><i class="fa fa-download" name="download" unselectable="on"></i></a></li><li><a href="javascript:;" title="" unselectable="on"><i class="fa fa-download" name="download" unselectable="on"></i></a></li><li><a href="javascript:;" title="" unselectable="on"><i class="fa fa-download" name="download" unselectable="on"></i></a></li><li><a href="javascript:;" title="" unselectable="on"><i class="fa fa-download" name="download" unselectable="on"></i></a></li><li><a href="javascript:;" title="" unselectable="on"><i class="fa fa-download" name="download" unselectable="on"></i></a></li><li><a href="javascript:;" title="" unselectable="on"><i class="fa fa-download" name="download" unselectable="on"></i></a></li></ul></div></div><div class="editormd-dialog editormd-dialog-1540989209511" style="display: none; z-index: 99999; width: 380px; height: 211px; top: 237px; left: 530px;"><div class="editormd-dialog-header" style="cursor: move;"><strong class="editormd-dialog-title">添加链接</strong></div><a href="javascript:;" class="fa fa-close editormd-dialog-close"></a><div class="editormd-dialog-container"><div class="editormd-form"><label>链接地址</label><input type="text" value="http://" data-url=""><br><label>链接标题</label><input type="text" value="" data-title=""><br></div><div class="editormd-dialog-footer"><button class="editormd-btn editormd-enter-btn">确定</button><button class="editormd-btn editormd-cancel-btn">取消</button></div></div><div class="editormd-dialog-mask editormd-dialog-mask-bg"></div><div class="editormd-dialog-mask editormd-dialog-mask-con"></div></div><div class="editormd-dialog editormd-image-dialog" id="editormd-image-dialog-1540989270246" style="display: none; z-index: 100001; width: 380px; height: 254px; top: 215.5px; left: 530px;"><div class="editormd-dialog-header" style="cursor: move;"><strong class="editormd-dialog-title">添加图片</strong></div><a href="javascript:;" class="fa fa-close editormd-dialog-close"></a><div class="editormd-dialog-container"><div class="editormd-form"><br><label>图片描述</label><input type="text" value="" data-alt=""><br><label>图片链接</label><input type="text" value="http://" data-link=""><br></div><div class="editormd-dialog-footer"><button class="editormd-btn editormd-enter-btn">确定</button><button class="editormd-btn editormd-cancel-btn">取消</button></div></div><div class="editormd-dialog-mask editormd-dialog-mask-bg"></div><div class="editormd-dialog-mask editormd-dialog-mask-con"></div></div><div class="editormd-dialog editormd-table-dialog editormd-user-unselect" style="display: none; z-index: 100003; width: 360px; height: 226px; top: 229.5px; left: 540px;"><div class="editormd-dialog-header" style="cursor: move;"><strong class="editormd-dialog-title">添加表格</strong></div><a href="javascript:;" class="fa fa-close editormd-dialog-close"></a><div class="editormd-dialog-container"><div class="editormd-form" style="padding: 13px 0;">
<label>单元格数</label>
行数 <input type="number" value="3" class="number-input" style="width:40px;" max="100" min="2" data-rows="">&nbsp;&nbsp;
列数 <input type="number" value="2" class="number-input" style="width:40px;" max="100" min="1" data-cols=""><br>
<label>对齐方式</label>
<div class="fa-btns"><a href="javascript:;"><label for="editormd-table-dialog-radio0" title="默认"><input type="radio" name="table-align" id="editormd-table-dialog-radio0" value="_default" checked="checked">&nbsp;<i class="fa fa-align-justify"></i></label></a><a href="javascript:;"><label for="editormd-table-dialog-radio1" title="左对齐"><input type="radio" name="table-align" id="editormd-table-dialog-radio1" value="left">&nbsp;<i class="fa fa-align-left"></i></label></a><a href="javascript:;"><label for="editormd-table-dialog-radio2" title="居中对齐"><input type="radio" name="table-align" id="editormd-table-dialog-radio2" value="center">&nbsp;<i class="fa fa-align-center"></i></label></a><a href="javascript:;"><label for="editormd-table-dialog-radio3" title="右对齐"><input type="radio" name="table-align" id="editormd-table-dialog-radio3" value="right">&nbsp;<i class="fa fa-align-right"></i></label></a></div>
</div><div class="editormd-dialog-footer"><button class="editormd-btn editormd-enter-btn">确定</button><button class="editormd-btn editormd-cancel-btn">取消</button></div></div><div class="editormd-dialog-mask editormd-dialog-mask-bg"></div><div class="editormd-dialog-mask editormd-dialog-mask-con"></div></div><div class="editormd-dialog editormd-download-dialog" style="display: none; z-index: 100005; width: 840px; height: 540px; top: 72.5px; left: 300px;"><div class="editormd-dialog-header" style="cursor: move;"><strong class="editormd-dialog-title">Html源码</strong></div><a href="javascript:;" class="fa fa-close editormd-dialog-close"></a><div class="editormd-dialog-container"><div class="markdown-body" style="font-family:微软雅黑, Helvetica, Tahoma, STXihei,Arial;height:390px;overflow:auto;font-size:14px;border-bottom:1px solid #ddd;padding:0 20px 20px 0;"></div><div class="editormd-dialog-footer"><button class="editormd-btn editormd-close-btn">关闭</button></div></div><div class="editormd-dialog-mask editormd-dialog-mask-bg"></div><div class="editormd-dialog-mask editormd-dialog-mask-con"></div></div></div>
</div>
<script src="./system_files/jquery.min.js"></script>
<script src="./system_files/editormd.js"></script>
<script src="./system_files/light.js"></script>

<i title="Raphaël Colour Picker" style="display: none; color: white;"></i></body></html>