- #+BEGIN_NOTE
  1. 因为涉及到隐私， 所以目前仅开放了 `读取` 和 `添加` 功能；可随时通过 **删除/更改 Token** 的方式管理你的权限。
  2. 下方的 API 有可能并不是最新的，如果你是开发者的话，可随时 [联系我](mailto:kenshin@ksria.com)，我会根据你的需求定制你需要的 API。
  #+END_NOTE
- # 添加 /add （单条）
  id:: 61f64711-9c15-4ea6-8015-400c5a8012f3
	- ```bash
	  POST HTTP/1.1
	  URL: https://simpread.ksria.cn/api/service/add
	  Accept: application/json
	  Content-Type: application/json
	  
	  Headers:
	  {
	    token: <你的 token>
	  }
	  
	  Body:
	  {
	    "url": "example.com", // 必填
	    "title": "测试", // 尽量填写
	    "desc": "描述内容", // 选填
	    "tags": "标签", // 选填，e.g. 收件箱/<来源> → 收件箱/iOS 收件箱/Pocket 收件箱/Telegram
	    "note": "备注", // 选填
	  }
	  
	  Response:
	  {
	    "code": 201 // 建立成功
	    "code": -1  // 服务器错误
	    "code": 401 // 未找到 Token 或当前用户不是高级账户
	    "code": 404 // 未授权任何服务
	    "code": 403 // 未授权坚果云
	  }
	  ```
- # 添加 /new
	- > 与 ((61f64711-9c15-4ea6-8015-400c5a8012f3)) 功能一致，区别是在于：**可在 10 秒内，可添加多条**。多用于其它服务导入到简悦，如 Pocket → 简悦
- # 添加 /adds （多条）
	- ```bash
	  POST HTTP/1.1
	  URL: https://api-wrap.simpread.pro/api/service/adds
	  Accept: application/json
	  Content-Type: application/json
	  
	  Headers:
	  {
	    token: <你的 token>
	  }
	  
	  Body:
	  {
	    "urls": "http://a.com;;;http://b.com", // 必填由多 ;;; 分割，如：http://a.com;;;http://b.com
	    "titles": "标题1;;;标题2", // 必填由多 ;;; 分割，如：标题1;;;标题2
	    "tags": "标签", // 选填，e.g. 收件箱/<来源> → 收件箱/iOS 收件箱/Pocket 收件箱/Telegram 支持多个标签由,分隔
	  }
	  
	  Response:
	  {
	    "code": 201 // 建立成功
	    "code": -1  // 服务器错误
	    "code": 401 // 未找到 Token 或当前用户不是高级账户
	    "code": 404 // 未授权任何服务
	    "code": 403 // 未授权坚果云
	  }
	  ```
- # 添加 /webhook
  id:: 61f64ae4-1126-47d6-a4fe-cc22ed5b844a
	- > 与 ((61f64711-9c15-4ea6-8015-400c5a8012f3)) 类似，区别是 token 由 `query` 携带而非 `headers`。主要用于一些可以使用 Webhook 的场合，如 **IFTTT**，更多例子可以看 ((61f642c6-d323-4296-9185-f25138a57fd6))。
	  
	  ```bash
	  POST HTTP/1.1
	  URL: https://api-wrap.simpread.pro/api/service/webhook/<token>
	  Accept: application/json
	  Content-Type: application/json
	  
	  Params:
	  {
	    token: <你的 token>
	  }
	  
	  Body:
	  {
	    "url"  : "example.com", // 必填
	    "title": "测试", // 尽量填写
	    "desc" : "描述内容", // 选填
	    "img"  : "http://sr.ksria.cn/introduce-2.png" // 题图，选填
	    "tags" : "标签", // 选填，e.g. 收件箱/<来源> → 收件箱/iOS 收件箱/Pocket 收件箱/Telegram，支持多标签用 , 分割
	    "note" : "备注", // 选填
	  }
	  
	  Response:
	  {
	    "code": 201 // 建立成功
	    "code": -1  // 服务器错误
	    "code": 401 // 未找到 Token 或当前用户不是高级账户
	    "code": 404 // 未授权任何服务
	    "code": 403 // 未授权坚果云
	  }
	  ```
- # 读取 /reading
	- > 返回 **阅读列表** 的 JSON 结构。
	  
	  ```bash
	  POST HTTP/1.1
	  URL: https://simpread.ksria.cn/api/service/reading
	  Accept: application/json
	  Content-Type: application/json
	  
	  Headers:
	  {
	    id: <你的 id>
	    token: <你的 token>
	    type: 'reading' // 固定值
	  }
	  
	  Body:
	  {
	    "title": "index", // index || <title>
	  }
	  
	  Response: // title == index 时
	  {
	  "data": [
	      {
	          "title": "<title 1>",
	          "create": "Wed, 09 Dec 2020 08:46:25 GMT"
	      },
	      {
	          "title": "<title 2>",
	          "create": "Fri, 11 Dec 2020 11:05:38 GMT"
	      }
	  ]
	  }
	  ```
	  
	  当 `index == <title>` 会返回这个 `<title>.html` 的数据，如下图所示：
	  
	  ![ss8eET.png](https://s3.ax1x.com/2021/01/17/ss8eET.png)
	  
	  根据 idx 返回 HTML，e.g. `/api/service/reading/1023?title=我是标题`
	  1. 当 idx 不存在时，查询 `title` 的值
	  2. 当 idx 存在时，依次查询   `idx` `idx-title` `idx-title@annote` `title` 当都不存在时返回 `404`
	  
	  ```bash
	  POST HTTP/1.1
	  URL: https://simpread.ksria.cn/api/service/reading/idx
	  Accept: application/json
	  Content-Type: application/json
	  
	  Params:
	  {
	  	idx: <稍后读 idx>
	  }
	  
	  Headers:
	  {
	  id: <你的 id>
	  token: <你的 token>
	  type: 'reading' // 固定值
	  }
	  
	  Query:
	  {
	  "title": "xxxxxx", // <title>
	  }
	  
	  Response: 
	  
	  返回 `<title>.html` 的数据
	  ```
- # 读取 /list
	- > 返回 **稍后读** 的 JSON 结构。
	  
	  ```bash
	  POST HTTP/1.1
	  URL: https://simpread.ksria.cn/api/service/list
	  Accept: application/json
	  Content-Type: application/json
	  
	  Params:
	  {
	    id: <你的 id>
	    token: <你的 token>
	    filter: <all|daily|dr|reading|tag|search>
	    value: <你的 token>
	  }
	  
	  Response:
	  {
	    "data": [{
	               "url": "https://mp.weixin.qq.com/s/tav4wVOcigiaMHY5KC_ZZQ",
	               "title": "这位新世界首富，到底有多强...",
	               "desc": "",
	               "img": "",
	               "note": "",
	               "favicon": "",
	               "tags": [
	                   "收件箱"
	               ],
	               "create": "2021年01月17日 11:33:27",
	               "annotations": [],
	               "idx": 1281
	           }
	    ]}
	   }
	    ]}
	  ```
		- ## 参数详细说明
		  
		  | Key     | Description                                              |
		  | ------- | -------------------------------------------------------- |
		  | all     | 获取 **前二十条** 的数据                                 |
		  | daily   | 获取 **每日回顾** 的数据                                 |
		  | dr      | 获取 **灵感回顾** 的数据                                 |
		  | reading | 获取 **阅读列表** 的数据，同 `/reading` 调用结果     |
		  | tag     | 获取 **标签** 的数据                                     |
		  | search  | 获取 **检索任意内容** 的数据，包括：`标题` `描述` `备注` |
		  | value   | 仅在`key == tag or search` 生效                            |
		  
		  结果如下图所示：
		  
		  ![ssNF0I.png](https://s3.ax1x.com/2021/01/17/ssNF0I.png)
- # 关联
	- [[API工具]]
	- [[开通开放平台]]