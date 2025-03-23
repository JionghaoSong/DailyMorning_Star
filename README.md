# **DailyMorning - 给庆宝的每日早安**

### **更新日志**
- **2024.02.04**：简化了说明文档，增加了农历书写规范  
- **2023.11.15**：修正了时区问题，确保中国时区的日期计算正确  
- **2023.11.13**：修复了每日金句中文 & 英文显示不全的问题（但需要更新推送模板，或许有更优雅的解决方式）  
- **2023.08.14**：修复因 `header` 问题导致的词霸请求无响应  
- **2023.05.07**：新增可用模板  
- **2023.05.06**：折中方案已提供，欢迎优化并提交 PR。`{{xxxx.Data}}` 前必须加可读文字，如：`1. {{xxxx.Data}}`  
- **2023.05.04**：因微信改版，暂时无法发送自定义颜色文字  
- **2023.02.15**：运行稳定，配置公众号模板后可直接使用，持续维护中  
- **2023.02.11**：GitHub 服务器偶尔导致运行不准时，建议提前执行任务，避开整点/半点  
- **2022.12.09**：修复 Python 版本问题，若运行失败请重新 Fork，并记得给 Star ⭐  

---

### **Star History**
[![Star History](https://api.star-history.com/svg?repos=JionghaoSong/DailyMorning_Star&type=Date)](https://www.star-history.com/#JionghaoSong/DailyMorning_Star&Date)

---

## **微信推送模板**
请复制以下模板，并替换变量值：  

```
今日：{{date.DATA}}  
城市：{{city.DATA}}  
天气：{{weather.DATA}}  
最低气温：{{min_temperature.DATA}}  
最高气温：{{max_temperature.DATA}}  

我们已经贴贴了 {{love_day.DATA}} 天💝  
💌 {{birthday1.DATA}}  
💌 {{birthday2.DATA}}  

今天也要乖乖的多喝水哦(^▽^)  

👋 **每日金句**  
☀ {{note_en.DATA}}{{note_en2.DATA}}  
☀ {{note_ch.DATA}}{{note_ch2.DATA}}  
```

---

### **配置说明**
**Fork 之后修改 `config` 文件的参数**：
- `APP_ID`：公众平台 `appID`
- `APP_SECRET`：公众平台 `appSecret`
- `TEMPLATE_ID`：模板 ID
- `USER_ID`：接收人的 OpenID（多个 OpenID 请换行分隔）
- `BIRTHDAY`：生日倒计时，格式：
  - **公历**：`MM-DD`（如 `05-20`）、`YYYY-MM-DD`（如 `1999-11-04`）
  - **农历**：`r-月-日`（如 `r-11-22`）
- `START_DATE`：正数日期（如 `2008-08-08`）
- `CITY`：城市（不要加“市”，如 `北京`、`广州`、`承德`）

---

### **使用指南**
1. 在 [GitHub 仓库](https://github.com/rxrw/daily_morning) 查找关键参数
2. **在微信公众平台** 创建模板，并按示例填充变量  
   ![创建模板](https://user-images.githubusercontent.com/9566402/183242301-fd6ab30e-bfe5-4245-b2a9-f690184db307.png)  
3. **在 GitHub -> Settings -> Secrets -> Actions** 中设置参数  
   ![Secrets 配置](https://user-images.githubusercontent.com/9566402/183242295-4dcf06bb-2083-4883-8745-0af753ca805c.png)  
4. **启用 GitHub Actions**，自动推送每日早安  
   ![启用 Actions](https://user-images.githubusercontent.com/9566402/183242334-9943c538-ba3d-4d01-8377-d040143b7560.png)  

---

**示例效果**：  
![效果图](https://user-images.githubusercontent.com/64049788/190543003-2e33fe0c-a278-492e-96fa-3be0b3110e83.png)  
