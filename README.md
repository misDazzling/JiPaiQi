# JiPaiQI

<h2>更新日志</h2>
  <br>
2023.06.09<br>
<br>
1.优化了卡牌会因为牌数减少而自适应改变布局的BUG<br>
  <br>
 
2.新增了撤销上一次的操作，防止误触。<br>


## 一、项目介绍

这是一个记牌器，可以帮助记不了牌的小趴菜们哦~~



`功能介绍：`

目前功能比较单一，首先自己输入一共几副牌。然后每点击一次，该牌数量减少一张，实现计数。



`界面截图：`



`电脑端：`

![image-20230607032835125](https://cdn.jsdelivr.net/gh/misdazzling/photobed1@main/img/image-20230607032835125.png)

`移动端：`

![Screenshot_2023-06-07-03-29-21-559-edit_mark.via](https://cdn.jsdelivr.net/gh/misdazzling/photobed1@main/img/Screenshot_2023-06-07-03-29-21-559-edit_mark.via.jpg)





## 二、项目部署

如何将项目部署到vercel中进行托管呢？



> 1. 克隆本项目到自己的仓库中。
> 2. 访问 https://vercel.com/ 并使用 GitHub 账户登录。
> 3. 进入“Import Project”页面，选择GitHub项目并设定部署配置：
>
> - 在“Git Repository”中选择你的GitHub项目。
> - 在“Framework Preset”中选择Vue。
> - 在“Build Command”中输入`npm run build` （这个命令会在本地编译打包你的Vue项目）。
> - 在“Output Directory”中输入`dist`（这是编译打包后的项目文件夹名称）。

![image-20230607025434226](https://cdn.jsdelivr.net/gh/misdazzling/photobed1@main/img/image-20230607025434226.png)

当进行部署时，Vercel将会自动从GitHub仓库拉取最新的代码，并基于上述配置编译并部署你的Vue项目。在部署完毕后，你会获得一个链接，这就是你的网站。目前vercel被国内墙了，需要自己自定义一个域名哦!

部署域名在setting中的domain设置哦（还需要给域名设置dns解析哦~）。

![image-20230607025616658](https://cdn.jsdelivr.net/gh/misdazzling/photobed1@main/img/image-20230607025616658.png)
