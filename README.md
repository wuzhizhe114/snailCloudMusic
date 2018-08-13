
# 蜗牛云音乐-微信小程序（尝试）

### 借助工具：

- 小程序组件化开发框架（wepy）：[https://tencent.github.io/wepy/index.html](https://tencent.github.io/wepy/index.html "WePY | 小程序组件化开发框架")
- 网易云音乐API：[https://binaryify.github.io/NeteaseCloudMusicApi/#/?id=neteasecloudmusicapi](https://binaryify.github.io/NeteaseCloudMusicApi/#/?id=neteasecloudmusicapi "网易云音乐API")
- 服务器反向代理（ngrok）：[https://ngrok.com/](https://ngrok.com/ "服务器反向代理")
- 参照作品：[https://github.com/MengZhaoFly/wechatApp-netease_cloudmusic](https://github.com/MengZhaoFly/wechatApp-netease_cloudmusic)

### 底部导航栏配置
> 发现：wepy的页面文件，重命名后原来生成的旧文件不会被覆盖，而是会重新生成新文件
> 目前新建页面的步骤是：
 - 0, 参照页面模板：[https://tencent.github.io/wepy/document.html#/?id=%E9%A1%B5%E9%9D%A2pagewpy](https://tencent.github.io/wepy/document.html#/?id=%E9%A1%B5%E9%9D%A2pagewpy "wepy page模板")
 - 1, 直接在pages文件夹下新建文件夹（可在生成小程序文件时，将其所属的wxml，wxss，json，js文件划到同一目录下）或.wpy结尾的文件
 - 2, 在app.wpy文件中 配置页面路径，略显繁琐；

> 遇到问题：

	wepy 格式校验报错
	解决：（猜想，实践有效）单条js语句后不必加分号，对象里最后一项不能有逗号，缩进规则不能跟设定不符，

	小程序控制台： pages/find/index.js 出现脚本错误或者未正确调用 Page()
	网上答案：原生小程序代码下这个错误是因为所引用的js文件为空，需要设置Page({})即可，另有人说将es6转es5关闭即可（暂试无效）

	推论：既然为空报错，所以在js代码中加上一句执行语句，使之不为空即可；

