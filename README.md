☁ **天翼云盘签到脚本** 🤖✨

---

### 🔑 账号配置 & 环境变量  
**路径**：  `Settings` → `Secrets and variables` → `Actions` → `Variables`  → `Environment variables`

在这里新建一个 `user`

在`Environment secrets`这里添加以下变量
| 变量名🐈             | 说明 📌                                                                 | 示例 🖼️                 |
|----------------------|-----------------------------------------------------------------------|-------------------------|
| `TY_ACCOUNTS`        | 账号密码组合，格式：`[{"userName":"账号","password":"密码"},...]`      | `[{"userName":"u1","password":"p1"},{"userName":"u2","password":"p2"}]` |
| `EXEC_THRESHOLD`     | 个人云和家庭云签到线程数（不填或者默认1就行，默认主号签到一次，小号签到10次）                                       | `1`                    |
| `FAMILYID`           | 家庭云ID抓取教程：[Alist文档](https://alist.nn.ci/zh/guide/drivers/189.html#%E5%AE%B6%E5%BA%AD%E8%BD%AC%E7%A7%BB)  | `123456`                |
| `WX_PUSHER_UID`      | 微信推送UID（扫码获取）[二维码](https://wxpusher.zjiecode.com/api/qrcode/4Ix7noqD3L7DMBoSlvig3t4hqjFWzPkdHqAYsg8IzkPreW7d8uGUHi9LJO4EcyJg.jpg) | `UID_123`               |

---
**如果EXEC_THRESHOLD不设置。或者设置为1。就主号签到一次个人跟家庭。其他号签到10次家庭。不签到个人。如果EXEC_THRESHOLD设置其他数字。所有号个人签到EXEC_THRESHOLD次数。家庭签到EXEC_THRESHOLD次数。TY_ACCOUNTS账密。跟群主格式一致FAMILYID家庭IDEXEC_THRESHOLD线程。不设置默认保号模式PUSH_PLUS_TOKEN推送
### 🚀 快速执行指南  
1️⃣ **启用Workflow**  
  ✅ 点击仓库顶部 `操作` → **`I understand my workflows, go ahead 和 enable them`**  

2️⃣ **触发运行**  
  🌟 给仓库点 **星标** 立即执行  

3️⃣ **定时任务**  
  ⏰ 每日 **北京时间 5:00** 自动签到  

---

### 🐉 青龙面板部署  
```bash
ql repo https://github.com/Aijiaobin/Cloud189Checkin.git "src|.env" "image" "src|.eslintrc.js|accounts.js|config.js|serverChan.js|telegramBot.js|wecomBot.js|wxPusher.js|.env" "main" "js" "rm -rf /ql/data/repo/wes-lin_Cloud189Checkin"
```

---
# 通知服务配置说明

## GOTIFY 通知
- **GOTIFY_URL**：Gotify 地址（如 `https://push.example.de:8080`）
- **GOTIFY_TOKEN**：Gotify 的消息应用 Token
- **GOTIFY_PRIORITY**：推送消息优先级（默认 `0`）

---

## go-cqhttp 通知
- **GOBOT_URL**：请求地址
  - 推送到个人 QQ：`http://127.0.0.1/send_private_msg`
  - 推送到群：`http://127.0.0.1/send_group_msg`
- **GOBOT_TOKEN**：go-cqhttp 配置的访问密钥
- **GOBOT_QQ**：
  - 若 `GOBOT_URL` 为 `/send_private_msg`，填写 `user_id=个人QQ`
  - 若为 `/send_group_msg`，填写 `group_id=QQ群`

---

## 微信 Server 酱通知
- **PUSH_KEY**：申请的 SCKEY

---

## PushDeer 通知
- **DEER_KEY**：PushDeer 的 KEY
- **DEER_URL**：PushDeer 的 URL（可选，默认 `https://api2.pushdeer.com/message/push`）

---

## Synology Chat 通知
- **CHAT_URL**：申请的 CHAT_URL
- **CHAT_TOKEN**：申请的 CHAT_TOKEN

---

## Bark App 通知
- **BARK_PUSH**：Bark 推送地址（如 `https://api.day.app/XXXXXXXX`）
- **BARK_ICON**：推送图标（仅 iOS15+ 生效）
- **BARK_SOUND**：推送铃声
- **BARK_GROUP**：消息分组（默认 `QingLong`）

---

## Telegram 机器人通知
- **TG_BOT_TOKEN**：Telegram Bot 的 Token
- **TG_USER_ID**：接收消息用户的 ID
- **TG_PROXY_HOST**：HTTP 代理主机地址
- **TG_PROXY_PORT**：HTTP 代理端口号
- **TG_PROXY_AUTH**：代理认证参数
- **TG_API_HOST**：Telegram API 反向代理地址（默认 `api.telegram.org`）

---

## 钉钉机器人通知
- **DD_BOT_TOKEN**：钉钉机器人 Webhook
- **DD_BOT_SECRET**：加签密钥（以 `SEC` 开头）

---

## 企业微信配置
### 基础设置
- **QYWX_ORIGIN**：反向代理地址（默认 `https://qyapi.weixin.qq.com`）

### 机器人通知
- **QYWX_KEY**：机器人 Webhook

### 应用消息通知
- **QYWX_AM**：依次填入 `corpid,corpsecret,touser(多成员用|隔开),agentid,消息类型（默认文本）`

---

## iGot 聚合推送
- **IGOT_PUSH_KEY**：iGot 推送 Key

---

## Push+ 设置
- **PUSH_PLUS_TOKEN**：一对一/多推送 Token
- **PUSH_PLUS_USER**：群组编码（一对多模式需填）

---

## Cool Push 设置
- **QQ_SKEY**：Cool Push 授权 Skey
- **QQ_MODE**：推送模式

---

## 智能微秘书设置
- **AIBOTK_KEY**：个人中心 API Key
- **AIBOTK_TYPE**：发送目标（`room` 或 `contact`）
- **AIBOTK_NAME**：目标名称（与类型对应）

---

## 飞书机器人设置
- **FSKEY**：飞书机器人 Key

---

## SMTP 邮件设置
- **SMTP_SERVER**：邮件服务器（如 `smtp.exmail.qq.com:465`）
- **SMTP_SSL**：是否启用 SSL（`true`/`false`）
- **SMTP_EMAIL**：收发件邮箱
- **SMTP_PASSWORD**：登录密码/特殊口令
- **SMTP_NAME**：收发件人姓名

---

## PushMe 通知
- **PUSHME_KEY**：PushMe 的 KEY
## WXPUSHER通知
- **WXPUSHER_APP_TOKEN:** '', // wxpusher 的 appToken
- **WXPUSHER_TOPIC_IDS: **'', // wxpusher 的 主题ID，多个用英文分号;分隔 topic_ids 与 uids 至少配置一个才行**
- **WXPUSHER_UIDS: **'', // wxpusher 的 用户ID，多个用英文分号;分隔 topic_ids 与 uids 至少配置一个才行

## 🙏 **特别鸣谢**  
- 原项目：[wes-lin/Cloud189Checkin](https://github.com/wes-lin/Cloud189Checkin)  
- README优化：[ShelbyAlan](https://github.com/ShelbyAlan) 💡  

## 交流群

![](https://cdn.jsdelivr.net/gh/wes-lin/Cloud189Checkin/image/group.jpg)

## [更新内容](https://github.com/wes-lin/Cloud189Checkin/wiki/更新内容)
