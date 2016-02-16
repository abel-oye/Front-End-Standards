# 前端规范

## 1 规范说明

此为前端开发团队遵循和约定的代码书写规范，意在提高代码的规范性和可维护性。
此规范为参考规范，不全是硬性要求，部分硬性约定见下一条书写规范，统一团队编码规范和风格。让所有代码都是有规可循的，并且能够得到沉淀，减少重复劳动。

## 2 书写规范

### 2.1 样式和内容分离

### 2.2 

### 2.3 命名规范
* 文件及文件夹：全部英文小写+数字或者连接符号“-，_”;
* ID ：      *匈牙利命名法* && *驼峰式命名* 如： firstName topBar
* Class：采用减号连接符 如：list-item main-box
* 尽量使用语义化的单名词命名。

### 2.4 格式&编码
* 文本文件：.xxx UTF-8(无BOM)编码
* 图片文件：.png (png-24) .jpg(压缩率8-12)
* 动态图片：.gif
* 压缩文件：.tar.gz .zip

## 3 Css 规范

### 3.1 目录结构（含sass或less）
以_开头的文件为非编译文件

  -——../{css/styles}
    |——_Libs/ 主要用于预编译文件的部分，比如变量，函数和单位比较小的功能部分
        |——————_minxin.{scss,less}
         |——————variables.{scss,less}
         |——————reset.{scss,less}
         |——————reset.{scss,less}
         |——————common.{scss,less} 存放通用的类：比如 clearfix
    |——_Components/ 主要存放可复用的组件

### 3.2 注释格式约定
  /*
    @name: Drop Down Menu
    @description: Style of top bar drop down menu.
    @require: reset.css
    @author: abel(e23jiang@sina.com)
    */
 其中，**@require**为可选项
 * CSS换行制表：使用 2 或4 个空格，而非[Tab]
 * 书写格式：
  * 避免中文，或使用转义，推荐前者 ：如 font-family: "Microsoft YaHei"; font-family:\5fae\8f6f\96c5\9ed1;
  * 每一个选择器和属性都需要换行；如：
    ```
        .box1,
        .box2,
        .box3,
        .box4:after{
          float:left;
            margin-left:1px;
            padding: 0 .1px;
        }        
      ```
      
    *如果个位数为零，可省略；

### 3.2 嵌套规则
* 嵌套层级不能超过3级
* 

## 4 Html 规范
* 避免使用style="xxx:xxx;"的内联样式表
* 使用data-xxx来添加自定义数据，如：&lt;input data-xxx="yyy"/&gt;
* 特殊符号使用参考HTML [符号实体](http://www.w3school.com.cn/html/html_entities.asp)
* 避免使用已过时标签，如：&lt;b&gt; &lt;u&gt; &lt;i&gt; 而用 &lt;strong&gt; &lt;em&gt;等代替
* 一律统一标签结尾斜杠的书写形式：&lt;br /&gt;&lt;hr/&gt; 注意之间空格
* 所有标签需要符合XHTML标准闭合

### 4.1注释格式规范
```
<!--
@name: Drop Down Menu
@description: Style of top bar drop down menu.
@author: Abel (e23jiang@sina.com)
-->
```
对于这种注释在实际开发中使用场景有限，更多适用于代码片段；
以下几种场景建议适当加入注释：
* 一个完整功能或者使用重复功能建议加入注释分割便于阅读和便于修改成模板文件，供前后端修改；
  ```
    <!--repeat start-->
    <div>
      ....
    </div>
    <!--repeat end-->
   ```
* 存在样式切换，特别在切页面和功能分离的场景尤为重要；
  ```
    <nav class="ui-nav">
      <ul class="ui-list">
        <!--status [toggle]：actived-->
        <li class="ui-list-item"></li>
        <li class="ui-list-item"></li>
      </ul>
    </nav>
   ```
## 5 javascript 规范
* JS 换行缩进：采用 4 空格
* 结束行需添加分号;
* jQuery变量要求首字符为 $, 私有变量:首字符为_; 尽量避免全局变量.
* 避免使用 eval()，setTimeOut使用调用函数，考虑重绘，回流 操作对页面影响 参看：[reflows，repaints](http://www.zhangxinxu.com/wordpress/2010/01/%E5%9B%9E%E6%B5%81%E4%B8%8E%E9%87%8D%E7%BB%98%EF%BC%9Acss%E6%80%A7%E8%83%BD%E8%AE%A9javascript%E5%8F%98%E6%85%A2%EF%BC%9F/)
* JS调试使用console.log()及console.dir()进行，避免使用弹出框，线上版需要注释所有调试代码
* JS压缩混淆工具: JS Compressor 如果使用了压缩，需要留 name-src.js在同路径供今后修改使用

### 5.1 JSON格式规范
参考[JSON Style Guide翻译](https://github.com/darcyliu/google-styleguide/blob/master/JSONStyleGuide.md)，原版：[Google JSON Style Guide](http://google-styleguide.googlecode.com/svn/trunk/jsoncstyleguide.xml)