# DailyMorning_for_DXQ
# 给庆宝的每日早安

需要修改的，直接Fork到自己的仓库，修改config的里面的参数就行。<br>
APP_ID: 公众平台 appID<br>
APP_SECRET: 公众平台 appSecret<br>
TEMPLATE_ID: 模板 ID<br>
USER_ID: 接收人的 OpenID 多个用换行分隔<br>
BIRTHDAY: 倒数日（原生日），换行分隔，见更新说明。格式如 05-20，1999-11-04 这种<br>
START_DATE: 正数日期，格式：2008-08-08<br>
CITY: 城市，不要加市，准确到地级市。比如：北京、天津、广州、承德。  
~~具体可以移步 https://github.com/rxrw/daily_morning 寻找几个关键参数~~  该项目已经闭源  
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
