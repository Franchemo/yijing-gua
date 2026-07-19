# 易卦 · 意识占

基于《易经白话讲座》（王思迅著）的**意识卦**卜卦工具。

输入心中浮现的汉字，自动计算本卦、变爻、之卦，并给出深度解读。

---

## 使用方式

### 方式一：Claude Code Skill（推荐）

适合使用 Claude Code / Claudian 的用户，支持 AI 动态解读。

**安装步骤：**

```bash
# 1. 克隆仓库
git clone https://github.com/YOUR_USERNAME/yijing-gua.git

# 2. 把 Skill 文件放到 Claude 的 skills 目录
mkdir -p ~/.claude/skills/yijing
cp yijing-gua/skill/SKILL.md ~/.claude/skills/yijing/SKILL.md
```

**使用方式：**

在 Claude Code 或 Claudian 中直接说：
> 「帮我算一卦」「起卦」「算意识卦」

---

### 方式二：网页版

直接打开 `webapp/index.html`，或访问部署后的链接。

适合分享给不使用 Claude Code 的朋友。

---

## 卜卦方法

来自《易经白话讲座》「卦象的结构与卜卦的方法」章节：

1. **静心** → 默想问题，闭眼 15 秒
2. **起字** → 心中浮现一个汉字
3. **算上卦** → 康熙笔画数 ÷ 8 取余数 → 对应先天八卦
4. **算下卦** → 从上卦起，按时辰数往后数步
5. **得本卦** → 上卦 + 下卦 查表得卦
6. **得变爻** → （笔画 + 时辰序号）÷ 6 取余数
7. **得之卦** → 变爻阴阳互换后重新组卦

---

## 先天八卦顺序

乾(1) 兑(2) 离(3) 震(4) 巽(5) 坎(6) 艮(7) 坤(8)

---

*内容来源：《易经白话讲座》王思迅著*
