# 微信天气预报推送

<div align="center">
  <h1>wx-weather</h1>
</div>

这是一个基于GitHub Actions的微信天气预报推送项目，可以定时向指定用户推送天气预报信息。使用Python实现，代码简单易懂，适合新手学习。

## ✨ 功能特点

- 🌤️ 每日定时推送天气预报（早8:30和晚20:30）
- 📅 支持纪念日、生日倒计时提醒
- 🌈 集成彩虹屁API，每天发送不同的暖心话语
- 🌅 包含日出日落时间
- 💨 显示风向和风力等级
- 🎯 支持多个接收者
- 💝 解决微信测试号字数限制问题
- 🚀 使用GitHub Actions，无需服务器

## 📝 使用步骤

### 1. 申请微信公众号测试号
1. 访问[微信公众平台测试号](https://mp.weixin.qq.com/debug/cgi-bin/sandbox?t=sandbox/login)
2. 使用微信扫码登录
3. 获取以下信息：
   - appID
   - appSecret
   - openId（接收者扫码后获取）
   - template_id（创建模板后获取）

### 2. 申请和风天气API
1. 访问[和风天气开发平台](https://dev.qweather.com/)
2. 注册账号并创建应用
3. 获取API密钥

### 3. 配置项目
1. Fork 本仓库
2. 添加相关配置
```
START_DATE: 纪念日（格式：YYYY-MM-DD，示例："2021-03-14"）
APP_KEY: 和风天气API密钥
BIRTHDAY: 生日（格式：YYYY-MM-DD，示例："2025-02-02"）
APP_ID: 微信公众号的appid
APP_SECRET: 微信公众号的app_secret
USER_IDS: 接收者ID（多个用分号;分隔，示例："xxx;xxx"）
TEMPLATE_ID_DAY: 白天模板ID
TEMPLATE_ID_NIGHT: 晚上模板ID
NAME: 接收者昵称（示例："小A"）
CITY: 城市名称（示例："北京"）
```

### 4. 配置模板消息
创建两个模板，分别用于早晚推送：

#### 早上模板
```
💓可爱的：{{name.DATA}} 
📅今天是：{{today.DATA}} 
🌍城市：{{city.DATA}} 
☁️今日天气：{{weather.DATA}} 
🌡️当前温度：{{now_temperature.DATA}} 
🌕今日最低温度：{{min_temperature.DATA}}
🌞今日最高温度：{{max_temperature.DATA}}  
❤️我们已经恋爱：{{love_date.DATA}}  
🎂距离你这个小笨蛋的生日还有：{{birthday.DATA}}  
🏮距离春节还有：{{diff_date1.DATA}}
🌄日出时间：{{sunrise.DATA}}
🌄日落时间：{{sunset.DATA}}
🌛夜间天气：{{textNight.DATA}}
☁️白天风向：{{windDirDay.DATA}}
☁️夜间风向：{{windDirNight.DATA}}
🐝风力等级：{{windScaleDay.DATA}}
💬{{note1.DATA}}{{note2.DATA}}{{note3.DATA}}{{note4.DATA}}{{note5.DATA}}
```

#### 晚上模板
```
💓可爱的：{{name.DATA}} 
📅今天是：{{today.DATA}} 
🌍城市：{{city.DATA}} 
☁️明日天气：{{weather.DATA}} 
🌡️当前温度：{{now_temperature.DATA}} 
🌕明日最低温度：{{min_temperature.DATA}}
🌞明日最高温度：{{max_temperature.DATA}}  
❤️我们已经恋爱：{{love_date.DATA}}  
🎂距离你这个小笨蛋的生日还有：{{birthday.DATA}}  
🏮距离春节还有：{{diff_date1.DATA}}
🌄日出时间：{{sunrise.DATA}}
🌄日落时间：{{sunset.DATA}}
🌛夜间天气：{{textNight.DATA}}
☁️白天风向：{{windDirDay.DATA}}
☁️夜间风向：{{windDirNight.DATA}}
🐝风力等级：{{windScaleDay.DATA}}
💬{{note1.DATA}}{{note2.DATA}}{{note3.DATA}}{{note4.DATA}}{{note5.DATA}}
```

### 5. 配置推送时间
进入项目的 Actions -> 天气预报推送 -> weather_repo.yml，修改 cron 表达式设置推送时间（默认为早8:30和晚20:30）

## ⚠️ 注意事项

- 确保所有 Secrets 都已正确配置
- 城市名称需要准确，建议使用标准城市名称
- 模板消息需要按照指定格式配置
- 确保接收者已关注测试号

<div align="center" style="background-color: #0D1117; padding: 20px; border-radius: 10px; margin: 20px 0; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
  <h3 style="color: #58A6FF; margin-top: 0;">❤️ Support My Work</h3>
  <p style="color: #C9D1D9;">If you find my projects useful, please consider:</p>
  <div style="display: flex; justify-content: center; gap: 10px; margin: 10px 0;">
    <img src="https://img.shields.io/badge/Star-Follow-blue?style=for-the-badge" alt="Star" />
    <img src="https://img.shields.io/badge/Fork-Contribute-green?style=for-the-badge" alt="Fork" />
    <img src="https://img.shields.io/badge/Follow-Updates-yellow?style=for-the-badge" alt="Follow" />
  </div>
  
  <h3 style="color: #58A6FF;">🐛 Found a Bug?</h3>
  <p style="color: #C9D1D9;">Feel free to:</p>
  <ul style="list-style-type: none; padding-left: 0;">
    <li style="margin: 10px 0; color: #C9D1D9;">📝 Open an Issue (I'll check it when I have time)</li>
    <li style="margin: 10px 0; color: #C9D1D9;">💝 Or show your appreciation to get a quicker response</li>
  </ul>
  
  <img src="https://github.com/SJYssr/img/raw/main/1/zanshang.jpg" alt="Appreciation" width="300" style="border-radius: 10px; margin: 20px 0; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);" />
  <p><i>Your support is the motivation that drives me to keep updating.</i></p>
</div>

## 📜 免责声明

<div style="border: 2px solid #dc3545; padding: 15px; border-radius: 5px; margin: 20px 0;">
  <h4 style="color: #dc3545; margin-top: 0;">⚠️ 重要提示</h4>
  <ul style="margin-bottom: 0;">
    <li>本代码遵循 <a href="https://github.com/SJYssr/SJYssr/blob/main/LICENSE">GPL-3.0 License</a> 协议</li>
    <li>允许开源/免费使用和引用/修改/衍生代码的开源/免费使用</li>
    <li>不允许修改和衍生的代码作为闭源的商业软件发布和销售</li>
    <li>禁止使用本代码盈利</li>
    <li>以此代码为基础的程序必须同样遵守 GPL-3.0 License 协议</li>
    <li>本代码仅用于学习讨论，禁止用于盈利</li>
    <li>他人或组织使用本代码进行的任何违法行为与本人无关</li>
  </ul>
</div>

<div align="center">
  <p>Made with ❤️ by <a href="https://github.com/SJYssr">SJYssr</a></p>
</div>