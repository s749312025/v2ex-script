# 如何安装/使用该脚本？

<details>
  <summary>点击展开</summary>

1. 先安装一个脚本管理器扩展
   ### 在线安装
    - Chrome / Firefox / Edge：安装 [Tampermonkey](https://www.tampermonkey.net/index.php?browser=chrome&locale=zh)
    - Safari：安装 [Userscripts](https://apps.apple.com/us/app/userscripts/id1463298887)
        - Mac上的Tampermonkey收费，如果你已经安装过了Tampermonkey可以不用安装Userscripts
    - 国产浏览器：请自动百度如何安装Tampermonkey
   ### 离线安装（无法打开应用商店）
    - 请在 [这个页面](https://www.tampermonkey.net/index.php?browser=chrome&locale=zh)或自行百度 下载Tampermonkey的文件
        - Chrome、Edge请使用crx后缀的文件
        - Firefox请使用xpi后缀的文件
    - 然后重新开启浏览器，进入扩展页面
        - Chrome、Edge，打开chrome://extensions/页面
        - Firefox，打开about:addons页面
    - 把”开发者模式“或”开发人员模式“打开
    - 拖动下载的文件到浏览器中


2. 点击[本页](https://greasyfork.org/zh-CN/scripts/458024)的 “安装此脚本” 按钮

</details>

# 为什么选择V2EX - 超级增强，脚本的优势在哪？

在社区中早已存在众多用于增强 v2ex.com 的[脚本](https://greasyfork.org/zh-CN/scripts/by-site/v2ex.com)
和[插件](https://chrome.google.com/webstore/search/v2ex?_category=extensions)，然而它们带来的体验良莠不齐，且大多数已经停止更新。

- 秒杀其他脚本或插件的楼中楼功能：
    - 其他脚本：只解析当前页，如果有很多页回复，楼中楼就会前言不搭后语莫名其妙的
    - 我：加载所有回复然后再解析楼中楼
- 长期维护，快速响应，打造最高质量的 V2EX 脚本，提供最佳的体验。

# 功能列表

## ⊙主要功能

### # 楼中楼

回复以楼中楼的方式展示，并支持按感谢排序

- 加载所有回复，保持楼中楼回复解析正确
- 如果回复中指定了楼层，优先解析
- 提供三种展示方式：楼中楼、按感谢排序、V2原版
- 超过15层嵌套，默认隐藏剩余回复，点击可展开，保证嵌套过多不会导致页面变形

> **默认楼中楼** 如需切换，可随时点击帖子回复上方的按钮切换

### # 预览帖子内容

在首页、节点页面，点击帖子的回复数，可直接预览帖子内容。也支持一键展开所有帖子内容和关闭

### # 弹框显示帖子内容和回复

列表点击帖子弹出帖子回复（不跳转页面），异步加载帖子内容
> **默认开启** 如需关闭，请点击[V站首页](v2ex.com)的设置按钮，在设置弹框里面关闭 “点击列表的帖子，打开详情弹框”

### # 对用户打标签

可以对用户打标签，数据保存在你的V2EX的记事本里面，换浏览器也能显示

> **默认开启** 如需关闭，请点击[V站首页](v2ex.com)的设置按钮，在设置弹框里面关闭 “用户打标签”

### # 正文超长自动折叠

当帖子的正文和回复的内容超长时，自动折叠收起，点击可展开。可在设置里面关闭
> **默认开启** 如需关闭，请点击[V站首页](v2ex.com)的设置按钮，在设置弹框里面关闭 “正文超长自动折叠”

### # 划词 base64 解码，支持解码中文

在回复里面，划词弹出base64解码气泡卡片

## ⊙更多功能

- 一键@所有人，@管理员：回复时，可一键@所有人和@管理员
- 回复指定用户添加楼层号：回复时，自动添加楼层号，以保证脚本解析回复时能更准确的判断
- 自适应屏幕宽度，支持黑暗模式： 帖子详情弹框自适应屏幕宽度，无论什么分辨率都能完美展示，同时也支持黑暗模式
- 按钮异步请求：操作按钮（感谢、收藏、回复、隐藏）异步请求，不会刷新页面

# 常见问题

<details>
  <summary>为什么要加载所有回复？</summary>
 其他脚本的楼中楼功能，是基于当页的回复解析。如果回复没超过一页，显示正常，如果回复超过一页，楼中楼就会显示的莫名奇妙
</details>
<details>
  <summary>为什么有的「楼中楼」回复的楼层不正确？</summary>
由于 V2EX 的原回复并没有记录回复的楼层，本脚本只能根据被回复的用户去寻找此用户的最近一条回复，然后嵌入到这后面去，这种方法并不能保证正确识别用户真正要回复的是哪一个楼层。
</details>
<details>
  <summary>为什么有的「楼中楼」回复指定了楼层还是不正确？</summary>

- 屏蔽用户导致楼层塌陷：你屏蔽了A，自A以后的回复的楼层号都会减1
- 忽略回复导致楼层塌陷：原理同上
- 回复时指定错了楼层号
- 脚本解析错误，请在[这里](https://github.com/zyronon/v2ex-script/discussions/7)反馈给我

</details>
<details>
  <summary>详情页加载很慢？</summary>

- 回复多时会加载很慢，其实不是脚本的问题。是因为请求V站的其他页的回复，V站迟迟未返回，导致我无法进行后续的解析，所以只能显示加载中...

- V2EX 的帖子详情页，打开时并不总是第一页，比如回复有3页时，打开帖子详情页会自动展示最后一页，所以我需要请求其他页，拿到所有回复，才能进行楼中楼解析

</details>

# 如何帮助我

作为开发者，创造对他人有用的东西始终是我们的热情所在，这个项目也不例外。我投入了大量的时间和精力，致力于为 V2EX
用户带来更好的体验。因此，如果我的项目帮助了你，欢迎你为我的项目：

- 点个 Star ⭐️ 或分享给他人，让更多的人知道我们的存在。
- 提供反馈，帮助我们改进。

#### 源代码：[https://github.com/zyronon/v2ex-script](https://github.com/zyronon/v2ex-script)

#### 更新日志：[https://greasyfork.org/zh-CN/scripts/458024/versions](https://greasyfork.org/zh-CN/scripts/458024/versions)


# 问题反馈

我需要你的建议和反馈，以持续完善脚本。如果在使用中遇到任何问题，都可以在[这里](https://github.com/zyronon/v2ex-script/discussions/7)
提出。

如果我的脚本有帮助到你，请在[这里](https://greasyfork.org/zh-CN/scripts/458024/feedback)给我好评！🥰

# 待实现

- 自动签到
- 高亮楼主回复
- 如果回复中，指定了楼层，用hover的形式显示
- 打标签功能
  https://gist.github.com/y4code/241e8a7d05286211ccf9ee05b996a02e
- 回复太多，考虑放后台，如924034
- 链接自动转图片
- 自动加载下一页
- 新标签页打开链接
- 表情功能
    - https://greasyfork.org/zh-CN/scripts/435299-v2ex-emoticon/code

# 开发指南

## 步骤有点麻烦。但是是一次性的

1. 在硬盘新建一个空白目录。
2. 复制Chrome的快捷方式。然后右键新的快捷方式，点击属性，在属性弹框里面，点击上面的第二个Tab（快捷方式）
3. 找到目标，在输入框里面加上 --args --disable-web-security --disable-site-isolation-trials
   --user-data-dir=第一步建的目录地址（不用加引用）
   例："C:\Program Files\Google\Chrome\Application\chrome.exe" --args --disable-web-security
   --disable-site-isolation-trials --user-data-dir=C:\Users\abc\Documents\chrome2
4. 保存，然后双击打开这个快捷方式。这样子新打开的Chrome就允许跨域了
5. 在新开的Chrome里面安装tampermonkey这个插件
6. 在里面“添加新脚本”，复制以下内容

```js
// ==UserScript==
// @name         开发：V2EX - 超级增强
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  try to take over the world!
// @author       You
// @match        https://*.v2ex.com/
// @match        https://*.v2ex.com/?tab=*
// @match        https://*.v2ex.com/t/*
// @match        https://*.v2ex.com/recent*
// @match        https://*.v2ex.com/go/*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=v2ex.com
// @grant        none
// ==/UserScript==

(function () {
  'use strict';
  let $vue = document.createElement('iframe');
  $vue.src = 'http://localhost:3000/';
  document.body.appendChild($vue);
})();
```

7. 克隆本项目，然后安装依赖，然后启动。
8. 修改本项目的index.html文件里面第30行，将const isDev = false 改为const isDev = ture
9. 用新的Chrome打开v2ex.com。本脚本会自动注入到v2的网页里面
10. 像正常的vue项目一样开发即可

# 打包指南

1. 如果你修改了index.html里面的第一个<script>标签的内容。那么也要复制到脚本里面。注意：const isDev = true 要修改为 const
   isDev = false。其他的js内容全部复制替换到脚本的大约第80行之后即可
2. 运行npm run build
3. 复制dist/assets目录下的css和js，css复制替换到脚本的21行，js复制替换到脚本的32行
4. 注意，js和css一定要同时复制。vue打包后的"data-v-c9f8a6c7"这种东西，会重新生成
