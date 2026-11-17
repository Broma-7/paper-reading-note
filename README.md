# Paper Reading Note · 个人论文阅读笔记

将已有的论文精读笔记，改写为从具体任务出发、沿原论文图讲清方法的中文阅读笔记。

适合已经读过论文、希望把较长的精读材料整理为便于回看和讲解的笔记。内置 AdaRSI 和 MobiAgent 的用户写作示例，也可以提供自己的风格示例。

## 写作方式

- 从具体任务和失败原因引出动机。
- 配合原论文图，说明模块职责、输入输出与连接关系。
- 用贯穿全文的例子串起信息流、训练对象和数据来源。
- 将精读问答中的概念澄清融入正文，过滤阅读进度和材料整理记录。
- 每篇末尾固定总结实验结果：先交代任务、指标与基线，优先放原论文结果图，图不适合时改用表格，并解释主要发现。
- 保存的 Markdown 使用相对图片路径，并显示论文原图号与图题。

## 安装到 Codex

克隆仓库后，将完整技能目录复制到个人技能目录。以下命令用于 macOS / Linux；安装前确认目标目录没有需要保留的同名技能。

```bash
git clone https://github.com/Broma-7/paper-reading-note.git
mkdir -p ~/.codex/skills/paper-reading-note
cp -R paper-reading-note/SKILL.md paper-reading-note/agents paper-reading-note/references ~/.codex/skills/paper-reading-note/
```

技能需要 `SKILL.md`、`agents/` 和 `references/`，请保留目录结构。安装后在新会话中调用。

## 使用

提供精读笔记的路径，例如：

```text
请用 $paper-reading-note，将 /你的论文目录/精读笔记.md 改写成阅读笔记。
```

也可以指定自己的示例与输出位置：

```text
用 paper-reading-note，参考我的“论文阅读示例.md”，
把这两篇论文的精读笔记整理成一份阅读笔记，保存到指定目录。
```

建议输入目录包含：

```text
论文目录/
├── 精读笔记.md
├── figures/
│   ├── index.md
│   └── fig-01.png
└── outline.md          # 可选
```

必要时可读取同目录的论文文本和源码，澄清影响主解释的矛盾。改写以已有材料为主，不默认重新下载或运行模型。

默认输出为论文目录中的 `阅读笔记.md`。可指定多篇合并、其他保存位置，或只在对话中输出。

## 文件

| 文件 | 内容 |
|---|---|
| [SKILL.md](SKILL.md) | 技能触发范围与改写流程 |
| [改写对照](references/rewrite-patterns.md) | 从精读材料到阅读笔记的具体写法 |
| [用户示例](references/user-example.md) | 清理后的风格示例 |
| [界面配置](agents/openai.yaml) | Codex 中的名称与默认提示词 |

原示例中的模型、日期和数字仅属于对应论文。新笔记使用目标论文的材料；原论文图片从用户自己的论文目录读取，仓库不附带论文全文或图片。
