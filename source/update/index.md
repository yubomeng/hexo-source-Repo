---
title: 更新日志
date: 2023-10-26 10:46:57
aside: false
comments: false
top_img: false
type: "updatelog"
---

<div id="page">
  <div class="author-content author-content-item updatelogPage single">
  <div class="card-content">
  <div class="author-content-item-tips">记录</div>
    <span class="author-content-item-title">博客更新日志</span>
    <div class="content-bottom">
    <div class="tips">每一次更新，都是一次成长。</div>
    </div>
    </div>
  </div>
</div>


{% timeline 2023 %}

<!-- timeline 11-15 -->

## 主题 1.6.9

- 漏洞
  【字体】修复部分页面字体过小的问题
  【朋友圈】适配新版rust朋友圈
  【banner-button-group】修复在移动端 banner-button-group错乱的情况
  【字体】修复部分页面未应用主题 config-font-family 的 bug
  【阅读模式】修复 阅读模式退出按钮
  【即可】修复首页顶部即刻logo大小错误的bug
  【footerBar】调整footerBar中bdageitem的位置
  【右键菜单】修复 config.rightClickMenu 右键菜单未开启时，config.ptool.share_copyurl 无效的 bug
  【首页】修复 config-pjax 未开启时，首页即刻短文无法跳转的 bug
  【中控台】修复 config.darkmode/comment_barrage_config 未开启时，中控台控制按钮依旧显示的 bug
  【pjax】修复 config.pjax 未开启时，随机文章跳转失效的 bug，修复未开启pjax功能，首页顶部  home_top-category词条无法跳转的bug
  【页脚】增加允许页脚显示网站运行时间时 work_img 不显示
  【中控台】分离 centerConsole 和 aside 卡片页影响，单独控制卡片页显示，用以修复 config.aside.  card_tags/card_archives 未使能时，中控台右侧页不显示的问题
  【音乐球】修复config.nav_music功能未开启时中控台仍然有音乐开关按钮，修复中控台右卡片页nav_music功能未开启时依旧可以显示音乐内容
  【即刻】修复即刻 video 缩进问题，缩进导致非B站链接无法播放
- 优化
  【阅读模式】阅读模式界面优化
  【天气】在移动端浏览下，不显示【天气】。桌面端不受影响
此版本配置文件无需更新。
- 功能
【朋友圈】支持修改顶部【使用 友链朋友圈 订阅友链最新文章】
<!-- endtimeline -->

<!-- timeline 10-01 -->

## 主题 1.6.8

- 漏洞
【即刻】修复即刻 bilibili 视频无法播放报错的问题
此版本配置文件无需更新。
<!-- endtimeline -->

<!-- timeline 09-28 -->

## 主题 1.6.7

- 漏洞
  【文章列表】修复文章列表标签被点击冒泡造成的事件错误跳转
  【algolia 搜索】修复 algolia 搜索打开时 TOC 的 fixed 失效的问题
  【标签】修复 introduction-card 的 img-alt 的异常
  【关于页】修复移动端关于页面头像样式异常
  【文章列表】修复文章添加多个分类时，post-meta-categories 会粘住 fixed #110
- 优化
  【关于】优化关于页面地图的文字深色模式切换时的动画
  【Twikoo】优化 Twikoo 评论样式
  【移动端 TOC】优化移动端 TOC 点击
  【footer】footer 对 copyright 的判断
  【即刻】即刻对 bilibili 视频进行额外的支持
- 功能
  【关于页】支持关于页-人格-字体颜色 personality_type_color #113
  【bilibili】支持 bilibili 标签
- 依赖
【twikoo】更新 twikoo 前端版本为 1.6.21
此版本配置文件无需更新。
<!-- endtimeline -->

{% endtimeline %}
