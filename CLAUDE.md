# 英语口语卡片项目

## 收到 Telegram「词:」消息时

**触发格式：** 消息以 `词:` 开头（大小写无所谓）

**立即执行以下步骤，无需等用户指令：**

### 第一步：翻译
- 将 `词:` 后面的中文口语翻译成 1-2 个地道英文口语表达（informal / casual）
- 避免书面语；要像真实英语对话里会说的那样
- 生成一句自然的英文例句，能体现该表达的实际使用场景

### 第二步：写入 phrases.json
读取 `/Users/ly/Claude/PhraseCards/phrases.json`，在数组末尾追加：
```json
{
  "zh": "原中文口语",
  "en": "English / Alternative",
  "example": "A natural example sentence using this expression.",
  "date": "YYYY-MM-DD"
}
```
保存文件。

### 第三步：推送到 GitHub（自动更新 PWA）
```bash
cd /Users/ly/Claude/PhraseCards
git add phrases.json
git commit -m "add: 原中文词"
git push
```

### 第四步：Telegram 回复
```
✅ 已收录！

🇨🇳 原中文
🇺🇸 English translation

📖 "Example sentence here."

共 N 条口语 🐾
```

---

## 注意事项
- 只处理以 `词:` 开头的消息，其他消息正常对话
- `en` 字段如有多个说法用 ` / ` 分隔，不超过两个
- 例句不要太长，一句话即可
- 日期用当天日期
