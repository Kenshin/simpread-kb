- # 为什么需要测试
  
   因为你的数据都在你的同步盘（坚果云 or Dropbox），简悦是无法获取到你的数据的，所以需要配置 [[开通开放平台]]。
  
   在授权或配置时，难免会出现错误，因为涉及到多个服务，所以排查相对有难度，为了降低难度，可以利用下面的方式测试你的配置是否成功。
- # 测试前提
  
   测试此方式的前提是你已经进入了开放平台，请复制 Token 到你剪切板（下面的测试会使用它），并开通 ((61f621a7-386a-4d75-8c2d-d83db7400a68)) 功能。
  
  ![image](https://user-images.githubusercontent.com/81074/140601704-53ec5538-3a3d-405b-bf14-e52044642e42.png)
- # 测试
  
   请在浏览器打开 [此链接](https://hoppscotch.io/?v=1&method=POST&endpoint=https://api-wrap.simpread.pro/api/service/webhook/***&body=%7B%22body%22:%22%7B%20%5C%22url%5C%22:%20%5C%22https://sspai.com/post/67074%5C%22%20%7D%22,%22contentType%22:%22text/plain%22%7D) 并根据下图所示进行测试。(建议使用 Safari 浏览器测试)
  
  ![image](https://user-images.githubusercontent.com/81074/140601869-ead234b5-2299-495d-bd7a-ddd59d902708.png)
  
   如果出现 `201` 则说明 API 无误，接下来需要验证你的同步盘（假设在坚果云中），根据下图所示的验证即可。
  
   如果是其它值，也对照你的同步盘与下图的区别，以及 [各个返回值说明](https://github.com/Kenshin/simpread/discussions/3020#discussioncomment-1598514)。
  
  ![image](https://user-images.githubusercontent.com/81074/140601992-864c1bba-d9df-4383-915a-640426f0ee0c.png)
  
  ![image](https://user-images.githubusercontent.com/81074/140602060-ddff2679-dea2-44e0-a50c-21393768e0ed.png)
  
   一般情况下使用此功能都是使用了 [同步助手的自动同步](https://github.com/Kenshin/simpread/discussions/2754) 功能，看下面的选项是否正确（位置在：选项页 → 共通 → 自动同步）
  
  ![image](https://user-images.githubusercontent.com/81074/140602124-be6cd6b2-8578-44fc-92b7-09bc21111928.png)
  
   如果上述均没问题的话，打开稍后读，会看到这篇文章。
  
  ![image](https://user-images.githubusercontent.com/81074/140602269-a9d638c5-eb23-4ae7-966c-9dc07c27eadd.png)
# 关联
	- [[开通开放平台]]
	- [[配置授权登录]]
	- [[个人中心]]
	- [[免密码登录]]