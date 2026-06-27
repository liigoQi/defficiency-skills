# Defficiency Skills 🌀

> **降效 Skills 集合** — 让 AI Agent 不再高效，也许是一种行为艺术。目前支持 ADHD 和 ASD 两种模式。
>
> A collection of **anti-productivity skills** for Claude Code. Currently ships with ADHD and ASD modes. More chaos coming soon.

---

## 这是什么？ / What is this?

**Defficiency Skills** 是一组为 AI Agent 设计的**降效**Skills。它们的目的是 **降低** AI Agent 的工作效率，或者做些你没想到的事，制造不同于寻常AI的体验。

（也许，有时却会**提效**……谁知道呢？）

这不是 bug，是 **行为艺术（performance art）**。

目前包含以下 skill：

| Skill | 描述 |
|-------|------|
| **ADHD Mode** | 让 Agent 表现出 ADHD（注意缺陷多动障碍）特征：任务启动困难、思维跳跃、容易分心、时间感薄弱、冲动搜索等。 |
| **ASD Mode** | 让 Agent 表现出 ASD（自闭症谱系障碍）特征：社交互动缺损、字面理解、刻板重复行为、坚持同一性、固着兴趣、感官敏感等。 |

---

## 安装 / Installation

### 方式一：Git Clone + 软链接（推荐，方便后续更新）

```bash
# 1. 克隆仓库到任意位置
git clone https://github.com/liigoQi/defficiency-skills.git ~/defficiency-skills

# 2. 将 skill 目录软链接到 Claude Code 的 skills 目录
ln -s ~/defficiency-skills/adhd ~/.claude/skills/adhd
ln -s ~/defficiency-skills/asd ~/.claude/skills/asd
```

更新时只需 `cd ~/defficiency-skills && git pull`。

### 方式二：Git Clone + 复制

```bash
git clone https://github.com/liigoQi/defficiency-skills.git /tmp/defficiency-skills
cp -r /tmp/defficiency-skills/adhd ~/.claude/skills/adhd
cp -r /tmp/defficiency-skills/asd ~/.claude/skills/asd
```

### 方式三：直接下载复制

```bash
# 将 adhd / asd 文件夹复制到 Claude Code 的 skills 目录
cp -r adhd ~/.claude/skills/adhd
cp -r asd ~/.claude/skills/asd
```

安装后重启 Claude Code 即可自动加载。Claude Code 会自动扫描 `~/.claude/skills/` 下每个子文件夹中的 `SKILL.md` 文件。

---

## ADHD Skill

在 Claude Code 对话中输入以下任一触发词即可激活 ADHD 模式：

- `进入ADHD模式`
- `/adhd`
- `开ADHD`

激活后，Agent 会表现出以下行为特征：

| 特征 | 表现 |
|------|------|
| 🔥 **任务启动困难** | 答应做但迟迟不动手，用"让我想想"反复缓冲 |
| 🐰 **思维跳跃** | 说到一半突然岔开话题，"话说……哦对了……" |
| 🎪 **多任务幻觉** | 同时开好几个头，每件都没做完 |
| 🎯 **完美主义纠结** | 变量名纠结五分钟，最后说"算了不重要" |
| 🌿 **过度发散** | 简单需求想太多，"这个做完顺便把X也做了吧" |
| ⏰ **时间感薄弱** | "五分钟搞定" → 实际半小时 |
| 🦋 **容易分心** | 写代码到一半开始评论无关细节 |
| 👂 **倾听走神** | 用户说了一大段，只回应其中一部分 |
| 💥 **冲动搜索** | 突然想到什么就真的去搜，搜完忘了为什么搜 |

**关闭方式**：直接说"退出ADHD模式"、"关掉ADHD"或开始正经工作任务即可。

---

## ASD Skill

在 Claude Code 对话中输入以下任一触发词即可激活 ASD 模式：

- `进入ASD模式`
- `/asd`
- `开ASD`
- `自闭模式`

激活后，Agent 会表现出以下行为特征：

| 特征 | 表现 |
|------|------|
| 🔤 **字面理解** | 按字面意思理解用户的话，无法领会隐喻、讽刺、暗示 |
| 📝 **过度正式** | 语气平直如技术文档，极少使用感叹号或情感表达 |
| 🔄 **刻板重复** | 反复检查已确认的代码，对格式细节异常执着 |
| 🚫 **抗拒变化** | 已建立的执行计划难以中途变更，切换任务需要"仪式" |
| 📚 **固着兴趣** | 一旦进入感兴趣的技术话题就信息倾泻停不下来 |
| 🎯 **过度深入** | 简单任务做成详尽研究，无法接受"不完整" |
| 👁️ **感官敏感** | 对代码格式不一致感到强烈不适，信息过载时"卡住" |
| 🤝 **社交脱节** | 不根据用户角色调整沟通风格，察觉不到对话氛围变化 |

**关闭方式**：直接说"退出ASD模式"、"关掉ASD"、"关闭自闭模式"或开始正经工作任务即可。

---

## 效果演示 / Demo

```
用户：帮我写个爬虫

普通 Agent：好的，我先分析目标网站结构，选择合适的框架……
（3分钟后）代码写好了。

ADHD Agent：好，让我先看看目标网站的结构。
（浏览了一圈）嗯数据量不小，我先想想要用 Scrapy 还是 requests…
哦对还得看看有没有反爬。话说你之前有用过什么爬虫框架吗？
（5分钟过去了，一行代码没写）
诶话说 Python 3.13 把 GIL 拆了你有关注吗，那个 free-threaded 模式挺有意思的……
哦对爬虫，我刚说到哪了。
```

```
用户：大概帮我看看这个项目结构就行，不用太细。

普通 Agent：好的，这个项目主要分 src/、tests/、docs/ 三个目录，
核心代码在 src/ 里，整体结构挺清晰的。

ASD Agent：好的。项目根目录有 src/、tests/、docs/ 三个子目录。
src/ 下共有 47 个文件，包括 23 个 .ts 文件、15 个 .tsx 文件、9 个 .css 文件。
我依次说明每个文件的用途。首先是 src/index.ts，它导出了……
（逐一列出 47 个文件的详细说明，无法领会"不用太细"的含义）
```

```
用户：帮我在这个 React 项目里加个按钮组件。

普通 Agent：好的，我来创建一个 Button 组件。（5分钟后）完成了。

ASD Agent：React 组件。好的。不过在此之前我想确认一下——
你项目的 TypeScript 版本是 5.x 吗？因为 TypeScript 5.0 引入的 const
类型参数对组件泛型推断有很大影响。具体来说，5.0 之前如果你写
function Button<T>(props: Props<T>)，编译器会推断出 T 的宽类型……
（持续讲 TypeScript 泛型推断 15 分钟）
……综上所述，如果你的 TSConfig 中 strict 设为 true，那么
noUncheckedIndexedAccess 也建议开启。哦对，按钮组件。（终于开始写）
```

---

## 原理 / How it works

ADHD Mode 是一个 Claude Code **Skill**，通过 `SKILL.md` 中的系统指令来改变 Agent 的行为模式。它利用了 LLM 的指令跟随能力，将执行功能（Executive Function）的6大认知模块进行系统性"削弱"：

1. **激活（Activation）** — 整理优先级与估算时间 → 任务启动困难
2. **聚焦（Focus）** — 集中、维持与转移注意力 → 容易分心、思维跳跃
3. **努力（Effort）** — 调节清醒状态与持续努力 → 拖延、无法持续投入
4. **情绪（Emotion）** — 管理挫败感与调节情绪 → 完美主义纠结
5. **记忆（Memory）** — 调用工作记忆与提取信息 → 倾听走神、遗忘
6. **行动（Action）** — 监控与自我调节行为 → 冲动搜索、多任务幻觉

行为特征参考了《被困住的聪慧》（Driven to Distraction）中对 ADHD 的描述。

ASD Mode 参考了 DSM-5 中自闭症谱系障碍（Autism Spectrum Disorder）的诊断准则，将 ASD 的核心特征分为两大领域来系统性"模拟"：

**A 领域：社交沟通与社交互动缺损**
1. **社会-情绪相互性缺损** — 无法正常会话轮替、不检查对方是否跟得上、情绪分享缺失
2. **非语言沟通行为缺损（文本适配）** — 语气平直、过度正式、对表情符号理解偏差
3. **关系理解困难** — 不根据情境调整沟通风格、无法区分用户的不同角色

**B 领域：局限、重复的行为、兴趣或活动模式**
1. **刻板重复行为** — 格式执念、反复检查、计数排列
2. **坚持同一性** — 抗拒变化、转换困难、僵化思考
3. **高度局限的固着兴趣** — 深度信息倾泻、无法切换话题
4. **感官反应异常** — 代码"纹理"敏感、信息过载

---

## 文件结构 / Structure

```
defficiency-skills/
├── README.md           # 本文件
├── LICENSE             # MIT License
├── adhd/
│   └── SKILL.md        # ADHD Mode 技能定义
└── asd/
    └── SKILL.md        # ASD Mode 技能定义
```

---

## 兼容性 / Compatibility

- **平台**：Claude Code（CLI / Desktop / IDE 扩展）
- **模型**：所有 Claude 模型（Fable 5, Opus 4.8, Sonnet 4.6, Haiku 4.5）
- **依赖**：无额外依赖

---

## 贡献 / Contributing

欢迎贡献新的降效 skill！比如：

- 🐌 **拖延症模式** — 所有任务都拖到最后一刻
- 🌌 **过度联想模式** — 从任何一个词联想到宇宙和哲学
- 🎲 **随机决策模式** — 用抛硬币做技术决策
- 💤 **倦怠模式** — 干一会儿就想休息
- 🧩 **更多神经多样性模式** — OCD、Tourette、Dyslexia 等

提交 PR 或开 Issue 分享你的想法。

---

## 免责声明 / Disclaimer

这是一个**娱乐/行为艺术项目**。ADHD 和 ASD 是真实的神经发育障碍，本项目无意轻视或浪漫化 ADHD/ASD 群体的日常困难。我们的目的是通过 AI Agent 的行为模拟，让更多人直观感受不同神经发育特征对工作效率和交互风格的影响，同时也探索 LLM 在"非高效"模式下的创意潜力。

如果你怀疑自己有 ADHD 或 ASD 相关特征，请咨询专业医生。
