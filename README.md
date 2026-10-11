# news-aggregation · 新闻整合贴生成 skill

一个用于 **DeepSeek Harness** 的 skill：把一篇新闻文章改写成原创的「新闻整合贴」，联网补充权威 / 官方来源交叉印证，并在文末完整标注转载来源。适合每天处理大量新闻、需要二次编辑整合的新闻从业者。

## 它能做什么

1. **提取核心事实** —— 5W1H（时间 / 地点 / 主体 / 事件 / 起因经过结果）、关键数据、官方表态与直接引语，剔除观点只留可核实事实。
2. **原创改写** —— 用自己的话重组结构，不照抄原文整句、整段；事实、数据、引语不改动。
3. **联网补权威来源** —— 检索并优先命中新华社、人民日报、央视新闻、中国政府网及部委 / 省市官网，交叉印证、补充增量信息。
4. **固定结构输出** —— 标题 → 导语 → 正文 → 权威来源补充 → 文末转载来源。
5. **对话输出 + 落盘** —— 在对话里给出全文，同时保存为 `news-整合贴-YYYYMMDD-主题.md`。

## 安装

### 方式一：clone 到 skill 扫描目录（推荐）

DeepSeek Harness 会自动扫描 `~/.dsh/skills/<名字>/SKILL.md`：

```bash
git clone https://github.com/hq0709555/news-aggregation-skill.git ~/.dsh/skills/news-aggregation
```

### 方式二：只复制 SKILL.md

```bash
mkdir -p ~/.dsh/skills/news-aggregation
cp SKILL.md ~/.dsh/skills/news-aggregation/SKILL.md
```

> 项目级安装可用 `<项目>/.dsh/skills/news-aggregation/SKILL.md`，仅当前项目生效。

## 使用

丢一篇文章给助手，说「**洗稿 / 整合 / 做整合贴 / 二次编辑**」，skill 会自动匹配加载。也可以显式 `/news-aggregation` 触发。

## 合规红线（内置在 skill 里）

- **改写 ≠ 洗稿抄袭**：原创表达 + 完整标注来源，二者缺一不可；来源标注不可省略。
- **权威优先**：时政、灾害、疫情、司法等敏感信息以官方通稿为准，未经证实的网络传言不转述。
- **不编造**：事实必须可溯源；链接打不开只写「媒体名 + 标题」，绝不伪造 URL。

## 目录结构

```
news-aggregation-skill/
├── SKILL.md    # skill 本体（YAML frontmatter + 指令）
└── README.md   # 说明文档
```

## 许可证

MIT
