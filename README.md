# DailyMorning
# 给庆宝的每日早安
2023.05.04：非常抱歉的通知大家，因为微信改版原因，暂时无法发送自定义颜色的文字了。<br>
更新如下：<br>
1）去除自定义颜色、表情符号；（表情符号由替换为“□”改为直接去除）<br>
2）去除尾部/备注内容；<br>
3）去除首行内容。<br>
~~具体可以移步  https://developers.weixin.qq.com/community/develop/doc/000a2ae286cdc0f41a8face4c51801?blockType=1&page=1#comment-list ~~
2023.02.15：迄今运行稳定，若配置过公众号模板的配置后直接运行。后续会持续维护<br><br>
2023.02.11： 因为用的是Github的服务器，所以不准时是很正常的。建议时间提前以及避开拥挤时间段(整点/半点)<br><br>
2022.12.09 更新：修复了因为Python版本导致的运行失败，小伙伴们可以重新Fork一下，记着给Star<br><br>
################### 为了怕小伙伴们直接运行，我做了脱敏处理###################  <br>
<br>需要修改的，直接Fork到自己的仓库，修改config的里面的参数就行。<br>
APP_ID: 公众平台 appID<br>
APP_SECRET: 公众平台 appSecret<br>
TEMPLATE_ID: 模板 ID<br>
USER_ID: 接收人的 OpenID 多个用换行分隔<br>
BIRTHDAY: 倒数日（原生日），换行分隔，见更新说明。格式如 05-20，1999-11-04 这种<br>
START_DATE: 正数日期，格式：2008-08-08<br>
CITY: 城市，不要加市，准确到地级市。比如：北京、天津、广州、承德。  
~~具体可以移步 https://github.com/rxrw/daily_morning 寻找几个关键参数~~  该项目已经被官方封了  <br>

VX模板如下  
{{date.DATA}}   
城市：{{city.DATA}}   
天气：{{weather.DATA}}   
最低气温: {{min_temperature.DATA}}   
最高气温: {{max_temperature.DATA}}   
  
今天是我们恋爱的第{{love_day.DATA}}天❤❤❤  
{{birthday1.DATA}}  
{{birthday2.DATA}}  
  
今天也要乖乖的多喝水~(*^▽^*)  
  
{{note_en.DATA}}   
{{note_ch.DATA}}  
      
效果如图
![7DD39B07860A54664A542CE7202B8E9D](https://user-images.githubusercontent.com/64049788/187068544-f7a97567-d1f3-42d5-a762-7357c5c3d113.png)

按下图，创建模板，设置变量，把微信公众平台上的各种字符串按说明创建到 GitHub -> Settings -> Secrets -> Actions 中。
![71bf9d11a876d23ef0f0728645a8ba0](https://user-images.githubusercontent.com/9566402/183242301-fd6ab30e-bfe5-4245-b2a9-f690184db307.png)
![381e8ee4a7c5ec6b8c09719f2c7e486](https://user-images.githubusercontent.com/9566402/183242295-4dcf06bb-2083-4883-8745-0af753ca805c.png)
![1](https://user-images.githubusercontent.com/64049788/190543003-2e33fe0c-a278-492e-96fa-3be0b3110e83.png)

启用自己项目下的 Action！
![30a5b1b2b06ba4a40a3d8ef01652409](https://user-images.githubusercontent.com/9566402/183242334-9943c538-ba3d-4d01-8377-d040143b7560.png)

