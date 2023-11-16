---
title: day04_软件测试
abbrlink: 2c5e06dd
date: 2023-11-05 23:32:06
tags: 软件测试
categories: 软件测试
top_img: "https://s3.qjqq.cn/37/6555b06e3407a.webp!color"
cover: "https://s3.qjqq.cn/37/6555b06e3407a.webp!color"
---

### 今天目标

- 能够说出常见的html标签（10+）的作用
- 项目（登录）测试

---

### 一、html介绍

#### 1.1 前端三大核心

- html:超文本标记语言，由一套标记标签组成
- 标签：
  - 单标签：`<标签名 />`
  - 双标签:`<标签名></标签名>`
  - 属性：`描述某一特征 示例:<a 属性名="属性值">`

#### 1.2 html骨架标签


```
html:根标签，所有的内容都应该放到html标签中
head：头部标签
body:身体标签（代码编写区域）
```

#### 1.3 注释

- 作用：描述的内容不会被浏览器执行
- 说明：解析程序给程序员看
- 快捷键：ctrl+/ `<!--注释区域-->`
- 测试点：`前端页面上线之前检查注释描述或去除注释`

#### 1.4 标签

- 标题：`h1~h6`

  - 说明：h1最大，h6最小

  - 示例：

    ```html
    <h1>我是h1</h1>
    <h6>我是h6</h6>
    ```

- 段落：`p`

  - 特点：语义化、独占一块（换行）

  - 示例：

    ```html
    <p>我是段落</p>
    ```

- 超链接`a`

  - 说明：`点击文本跳转到指定页面`
  - 语法：`<a href="https://www.baidu.com">文本</a>`
  - 属性：
    - href：跳转的地址或文件
    - target:打开窗口模式。`新窗口：target="_blank"`

- 图片

  - 说明：`在页面中插入一张图片`

  - 测试点：必须有title属性（悬停和未加载显示）

  - 示例

    ```html
    <!--
    			图像标签：img
    			属性：
    				src:图片路径
    				title：悬停显示文字
    				width:宽100px   px:像素
    				height:高 
    				alt:图片未加载显示
    		-->
    		<img src="011.jpg" title="希望在田野" width="100px" height="200px" alt="此处有一张田野照片"/>
    ```

- 空格与换行

  - 空格：`&nbsp;`     `&->shift+7`
  - 换行：`<br />`

- 布局标签

  > 布局：设置页面布局，便于排版

  - 大盒子：div、独占一行
  - 小盒子：span、一行可以放多个

- 列表


  ```yacas
  script:js标签
  style:css标签
  link:外部加载css标签
  ```

- input标签

  - 文本框：`<input type="text" />`

  - 密码框：`<input type="password" />`

  - 单选按钮：<input type="radio">

  - 复选框：<input type="checkbox">

  - 按钮：

    - 普通：type=button

    - 提交：type=submit

    - 重置: type=reset

      ```yacas
      <!--
      				按钮测试点：统一使用value进行赋值
      			  提示：普通按钮默认没有执行效果，需要配合Js来实现。
      -->
      ```

- form标签

  - 作用：提交页面输入的数据到指定页面或后台

  ```yacas
  <!--
  			form
  				作用：将页面输入的数据提交到后台或指定页面
  				属性：
  					action：  指定将数据提交到那个页面。
  					method:提交参数的方法（get、post）
  						get:查询使用
  							1、参数url明文显示
  							2、提交速度快
  							3、提交参数有长度限制
  						post:提交数据、登录、注册
  							1、非明文显示
  							2、提交速度慢
  							3、提交参数的长度无限制
  -->
  ```

  ```html
  <form action="10-接受数据.html" method="get">
  			用户名：<input type="text" name="username"/>
  			<br />
  			密码框：<input type="password" name="password"/>
  			<br />
  			<!--
  				单选效果：
  					1、相同一组的radio才能做单选。
  					2、设置相同（组名）name属性值为一组。
  			-->
  			性别：
  			<input type="radio" name="one"/>男
  			<input type="radio" name="one"/>女
  			<br />
  			您的爱好：
  			<input type="checkbox" />挣钱
  			<input type="checkbox" />吃饭
  			<input type="checkbox" />欣赏美
  			<input type="checkbox" />个人发挥
  			<br />
  			<input type="submit" />
  			<input type="reset" />
  			<input type="button" value="点我试试"/>
  		</form>
  ```

### 二 、作业

```
登录模块设计用例
```


