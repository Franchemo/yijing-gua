# 易卦 · 意识占

基于《易经白话讲座》（王思迅著）的**意识卦**卜卦工具。

输入心中浮现的汉字，自动计算本卦、变爻、之卦，并给出深度解读。

---

## 功能特点

- 🈶 **全自动笔画识别**：内置 Unicode Unihan 数据库，覆盖 20,000+ 汉字（含生僻字），无需手动调整
- 🕐 **自动识别时辰**：根据当前系统时间自动判断十二时辰
- 🎴 **完整算卦流程**：上卦 → 下卦 → 本卦 → 变爻 → 之卦，全程自动计算
- 🎨 **吉卜力 × 中式美学**：适合手机使用的 PWA 页面

---

## 使用方式

### 方式一：网页版（推荐分享）

访问部署后的链接，或本地打开：

```
webapp/index.html
```

> ⚠️ 本地打开时需通过 HTTP 服务（如 `npx serve webapp`）而非直接双击，否则 `strokes.json` 无法加载。

**本地快速启动：**

```bash
git clone https://github.com/Franchemo/yijing-gua.git
cd yijing-gua
npx serve webapp
# 浏览器访问 http://localhost:3000
```

**部署到 Vercel（免费）：**

1. 在 [Vercel](https://vercel.com) 导入本仓库
2. Root Directory 设为 `webapp`
3. 点击 Deploy，完成！

---

### 方式二：Claude Code Skill（AI 动态解读）

适合使用 Claude Code / Claudian 的用户，支持 AI 结合当下处境进行动态解读。

**安装步骤：**

```bash
# 1. 克隆仓库
git clone https://github.com/Franchemo/yijing-gua.git

# 2. 把 Skill 文件放到 Claude 的 skills 目录
mkdir -p ~/.claude/skills/yijing
cp yijing-gua/skill/SKILL.md ~/.claude/skills/yijing/SKILL.md
```

**触发方式：**

在 Claude Code 或 Claudian 中直接说：

> 「帮我算一卦」「起卦」「算意识卦」「算一卦」

**其他 Agent 平台（WorkBuddy / 飞书等）：**

将 `skill/SKILL.md` 的内容粘贴为 Agent 的 System Prompt 即可使用。

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

**康熙笔画特殊规则：**

| 偏旁 | 计为 | 画数 |
|------|------|------|
| 扌 | 手 | 4 画 |
| 艹 | 艸 | 6 画 |
| 辶 | 走 | 7 画 |
| 氵 | 水 | 4 画 |
| 忄 | 心 | 4 画 |

---

## 先天八卦顺序

乾(1) 兑(2) 离(3) 震(4) 巽(5) 坎(6) 艮(7) 坤(8)

---

## 项目结构

```
yijing-gua/
├── webapp/
│   ├── index.html     # 单文件 PWA 应用
│   └── strokes.json   # Unihan 笔画数据库（20,992 字）
├── skill/
│   └── SKILL.md       # Claude Code Skill 定义
└── README.md
```

---

*内容来源：《易经白话讲座》王思迅著*
