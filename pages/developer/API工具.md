alias:: tools

- #+BEGIN_TIP
  以下的工具涵盖了 `iOS` `Android` `Windows` `Mac` 平台，通过这些工具，你可以将 **URL 发送到简悦的稍后读**。
  #+END_TIP
- # 描述
	- 下面这些工具来自 [简悦社区](https://t.me/simpreadgroup) 和官方开发，同时需要 [[开通开放平台]]。
- # 收藏助手
  id:: 61f63f40-eebd-4649-a311-74059d48a715
	- #+BEGIN_TIP
	    服务器端行为，**不经过同步助手，即可将任意导入的 URL**，支持 [[API快照]] ，详细请看 [[收藏助手]] 。
	  #+END_TIP
- # Telegram Bot
  id:: 61f63f40-e012-4800-b29c-7164dd632457
	- ## 说明
		- 将任意 URLs 发送给[@simpread_bot](https://t.me/simpread_bot) 自动保存到你的稍后读，支持 [[API快照]] 。
	- ## 如何使用
	  
	  #+BEGIN_TIP
	  1. 详细教程可以看 [如何玩转 Telegram bot](https://github.com/Kenshin/simpread/discussions/2792)。
	  2. 调用失败的 [解决方案汇总](https://github.com/Kenshin/simpread/discussions/2919)。
	  #+END_TIP
		- 添加 [@simpread_bot](https://t.me/simpread_bot)
		- 使用 `/token xxxx` 来绑定你的 Token ((61f4e352-67e3-4ada-82c9-e8c9b1f30bcd))
		- 发送包含 URLs 的内容给它，它就会自动帮你整理到网盘。
# 快捷指令
id:: 61f63f40-a4e7-496e-99bc-45395f8561e0
	- > 开发者来自社区的 [Easycat 废柴](https://t.me/Orz_3_s_father)。
	- ## 说明
		- 在 iOS 系统上，通过分享给快捷指令，保存到你的稍后读。
	- ## 不支持 [[API快照]]
		- [快速添加到简悦](https://www.icloud.com/shortcuts/0ffc62f9bf7c419ab1e769ab89a10fde)
		- [完整添加到简悦](https://www.icloud.com/shortcuts/5362ad74759f4e5fae5f48e3ec92a5f8)
	- ## 支持快照版
		- > 关于此功能的详细说明 [请看这里](https://zhuanlan.zhihu.com/p/504650351)。
		- [快速添加到简悦](https://www.icloud.com/shortcuts/10bafe20900b4740ab7721aad0c56258)
		- [完整添加到简悦](https://www.icloud.com/shortcuts/b69cf018e84b4e1da19d523ff771c584)
- # Popclip 插件
  id:: 61f63f40-147b-40c6-be95-68c6c41a3d68
	- > 开发者来自社区的 [lyserenity](https://t.me/lyserenity)。
	- ## 说明
		- 将任意通过 Popcip 划取的包含链接内容发送到简悦的稍后读，暂不支持  [[API快照]] 。
	- ## 特点
		- 可以一次发送多个链接，同时支持任意 App，浏览器。
	- ## 下载地址
		- [坚果云](https://www.jianguoyun.com/p/DQKs_lwQwobGBxjXzdUD)
		- [Box.net](https://app.box.com/s/cahedmamrebo8xwgmtf6dwhtqrpmbq2d)
	- ## 如何使用
		- 填入 **Token** 以及 **标签** 即可。（标签可支持嵌套标签如：`参考/简悦` 以及多个标签如：`aaa/bbb, ccc` ）
- # Quicker
	- > 开发者来自社区的 [yu jiale](https://t.me/Joel2561)
	- ## 说明
		- 在 Windows 中，可以使用 [Quicker](https://getquicker.net/) ，实现将任意页面的链接发送到简悦的稍后读。
	- ## 下载地址
		- [Quicker 官方](https://getquicker.net/Sharedaction?code=6bdc2ec2-026d-44d2-c3a3-08d908802222)
	- ## 如何使用
		- ![](https://files.getquicker.net/_actionDemos/6bdc2ec2-026d-44d2-c3a3-08d908802222/10.gif)
# 如何选择

> 目前基于简悦 API 的工具基本上涵盖了大部分的场景，这里有个简单的表格来区别这些工具的具体使用场景。

|              | iOS  | Android | Mac  | Windows | 可多选 | 描述                                    |
| ------------ | ---- | ------- | ---- | ------- | ------ | --------------------------------------- |
| Telegram Bot | •    | •       | •    | •       | •      | 发送给 bot 的内容如果包含 URLs          |
| Popclip 插件 |      |         | •    |         | •      | 在 Mac 上任意划取的内容                 |
| Quicker      |      |         |      | •       |        | 在 Windows 上通过点击任意 URL → Quicker |
| iOS 快捷指令 | •    |         |      |         |        | 在 iOS 在任意 App 分享到快捷指令        |
- # 关联
	- [[开通开放平台]]
	- [[收藏助手]]
	- [[建立资料库]]