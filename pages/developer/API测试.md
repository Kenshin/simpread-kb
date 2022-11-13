- # 为什么需要测试
  
  因为你的数据都在你的同步盘（坚果云），简悦是无法获取到你的数据的，所以需要配置 [[开通开放平台]]。
  
  在授权或配置时，难免会出现错误，因为涉及到多个服务，所以排查相对有难度，为了降低难度，可以利用下面的方式测试你的配置是否成功。
- # 测试前提
  
   测试此方式的前提是你已经进入了开放平台，请复制 Token 到你剪切板（下面的测试会使用它），并开通 [[API快照]] 功能。
  
  ![image](https://s1.ax1x.com/2022/11/13/zFDdeK.png)
- # 测试
  
   请在浏览器打开 [此链接](https://hoppscotch.io/?v=1&method=POST&endpoint=https://api-wrap.simpread.pro/api/service/webhook/***&body=%7B%22body%22:%22%7B%20%5C%22url%5C%22:%20%5C%22https://sspai.com/post/67074%5C%22%20%7D%22,%22contentType%22:%22text/plain%22%7D) 并根据下图所示进行测试。(建议使用 Safari 浏览器测试)
  
  ![image](https://s1.ax1x.com/2022/11/13/zFDcQI.png)
  
   如果出现 `201` 则说明 API 无误，接下来需要验证你的同步盘（假设在坚果云中），根据下图所示的验证即可。
  
   如果是其它值，也对照你的同步盘与下图的区别，以及 [各个返回值说明](https://github.com/Kenshin/simpread/discussions/3020#discussioncomment-1598514)。
  
  ![image](https://s1.ax1x.com/2022/11/13/zFDWef.png)
  
  ![image](https://s1.ax1x.com/2022/11/13/zFDIYQ.png)
  
   一般情况下使用此功能都是使用了知识库方案，这是 [一站式教程](https://www.yuque.com/kenshin/simpread/wkswh7) 功能。
  
  ![image](https://s1.ax1x.com/2022/11/13/zFDjTU.png)
  
   如果上述均没问题的话，打开稍后读，会看到这篇文章。
  
  ![image](https://s1.ax1x.com/2022/11/13/zFDxkF.png)
- # 关联
	- [[开通开放平台]]
	- [[个人中心]]
	- [[免密码登录]]