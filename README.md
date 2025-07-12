# DailyMorning - 微信推送每日早安

-----

## 更新日志

### 2025.07.12

**大幅增强程序健壮性与可维护性**

  * **网络请求优化：**
    * 引入 `requests.Session` 并配置**自动重试机制**，有效应对网络波动及服务器瞬时故障。
    * 为所有外部 API 请求设置**超时限制**，防止程序长时间无响应。
  * **错误处理与日志记录：**
    * 全面集成 **`logging` 模块**，将运行信息和错误日志详细输出到控制台及 `app.log` 文件，大幅提升问题追踪和排查效率。
    * 重构 `get_weather` 函数，使其职责更单一，通过抛出**自定义异常**来通知主程序处理错误，而不是直接终止。
  * **数据解析安全性提升：**
    * 移除 `get_weather` 函数中不安全的 `eval()` 调用，改用更安全的**正则表达式结合 `json.loads()`** 精确解析天气数据。
  * **代码可维护性优化：**
    * 将散布在代码中的固定参数及 API URL 提炼为**全局常量**，显著提高代码可读性与未来修改效率。
    * 精简了 `get_color` 函数的实现。

🚀 本次更新是在 **Google Gemini** 的帮助下完成的，通过一步步的指导，程序在功能和稳定性上都取得了显著进步。

### 2024.02.04

  * 简化了说明文档，增加了农历生日书写规范。

### 2023.11.15

  * 修正了时区问题，确保中国时区的日期计算正确。

### 2023.11.13

  * 修复了每日金句中文 & 英文显示不全的问题（提示：可能需要更新推送模板，或有更优雅的解决方式）。

### 2023.08.14

  * 修复因 `header` 问题导致的词霸请求无响应。

### 2023.05.07

  * 新增可用模板。

### 2023.05.06

  * 提供了折中解决方案，欢迎优化并提交 PR。（注意：`{{xxxx.DATA}}` 前必须加可读文字，如：`1. {{xxxx.DATA}}`）

### 2023.05.04

  * 因微信改版，暂时无法发送自定义颜色文字。

### 2023.02.15

  * 程序运行稳定，配置公众号模板后可直接使用，持续维护中。

### 2023.02.11

  * **温馨提示**：GitHub 服务器偶尔可能导致运行不准时，建议提前执行任务，避开整点/半点高峰。

### 2022.12.09

  * 修复 Python 版本问题，若运行失败请重新 Fork，并记得给 **Star** ⭐。

-----

## 微信推送模板

请复制以下模板，并替换其中的变量值：

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

👋 **每日金句** ☀ {{note_en.DATA}}{{note_en2.DATA}} 
☀ {{note_ch.DATA}}{{note_ch2.DATA}} 
```

-----

## 配置指南

---

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


**重要提示：** JSON 格式**不支持注释**。请在实际的 `config.json` 文件中**删除所有以 `//` 开头的注释行**，否则程序将无法正确解析并运行。

```json
{
    // 公众号配置：用于与微信公众号平台交互
    "app_id": "YOUR_WECHAT_APP_ID", // 您的公众号AppID，例如：wxa1XXXX56def789
    "app_secret": "YOUR_WECHAT_APP_SECRET", // 您的公众号AppSecret，例如：1f28c7b7dXXXXXX10deb45b96e5
    "template_id": "YOUR_WECHAT_TEMPLATE_ID", // 您在微信公众号平台申请的消息模板ID，例如：WwPUydeN9tHXXXXXXXXXOzxnepTi2KmBaAVs
    "user": [
        "YOUR_WECHAT_USER_OPENID_1", // 第一个接收消息的用户的微信OpenID，例如："oVtAf5XXXXXXXPnMrrVQzI"
        "YOUR_WECHAT_USER_OPENID_2"  // 如果有多个用户，在此处添加更多OpenID，用英文逗号分隔
    ],

    // 信息配置：用于生成推送消息的具体内容
    "province": "YOUR_PROVINCE", // 消息接收者所在省份，例如："河北"
    "city": "YOUR_CITY",       // 消息接收者所在城市，例如："石家庄"

    // 生日配置：可以配置多个生日提醒
    "birthday1": {
        "name": "PERSON_NAME_1", // 第一个生日对应的人名，例如："AA"
        // 生日日期，格式为"YYYY-MM-DD"
        // - 公历生日：直接填写，例如："2001-01-01"
        // - 农历生日：在年份前加小写字母"r"，例如："r2001-01-01" (表示2001年农历四月初四)
        "birthday": "PERSON_BIRTHDAY_1"
    },
    "birthday2": {
        "name": "PERSON_NAME_2", // 第二个生日对应的人名，例如："BB"
        "birthday": "PERSON_BIRTHDAY_2"
    },
    // 如需添加更多生日，可以继续添加 "birthday3", "birthday4" 等，格式保持一致

    "love_date": "YOUR_LOVE_DATE" // 在一起的日子，格式为"YYYY-MM-DD"，例如："2022-06-26"
}
```

-----

## 使用指南

1. 在 [GitHub 仓库](https://github.com/JionghaoSong/DailyMorning_Star/) 查找关键参数

2. **在微信公众平台** 创建模板，并按示例填充变量  
   ![创建模板](https://user-images.githubusercontent.com/9566402/183242301-fd6ab30e-bfe5-4245-b2a9-f690184db307.png)  

3. **在 GitHub -> Settings -> Secrets -> Actions** 中设置参数  
   ![Secrets 配置](https://user-images.githubusercontent.com/9566402/183242295-4dcf06bb-2083-4883-8745-0af753ca805c.png)  

4. **启用 GitHub Actions**，自动推送每日早安  

   ### ![启用 Actions](https://user-images.githubusercontent.com/9566402/183242334-9943c538-ba3d-4d01-8377-d040143b7560.png)  <br><br>**Star History**

[![Star History](https://api.star-history.com/svg?repos=JionghaoSong/DailyMorning_Star&type=Date)](https://www.star-history.com/#JionghaoSong/DailyMorning_Star&Date)

---