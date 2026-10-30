# Obsidian 图片转文字 · obsidian-image-ocr-skill

Obsidian image OCR workflow: transcribe and proofread images in Markdown notes while preserving originals and source links.

适用于支持 Agent Skills 的 Codex 等智能体。工作流默认使用中文；实际 PDF、图像、文档、转写服务和脚本能力取决于接收者的运行环境。

## 快速开始

使用 Skills CLI 安装（需要 Node.js；按提示选择你的智能体）：

```bash
npx skills add narsss242/obsidian-image-ocr-skill
```

也可以下载 [独立 ZIP](https://github.com/narsss242/obsidian-image-ocr-skill/raw/refs/heads/main/packages/obsidian-image-ocr-skill.zip)，解压后把完整 `obsidian-image-ocr-skill` 文件夹放到所用客户端的技能目录。Codex 常用 `~/.codex/skills/`，以客户端设置为准。不要只复制 SKILL.md；保留 references、scripts、agents 等配套文件。

若通过 GitHub 的 Code → Download ZIP 下载，解压后的文件夹可能带 `-main` 后缀，安装前改为 `obsidian-image-ocr-skill`。已有旧版时先备份；不要同时启用旧名和新名两个副本。没有技能安装功能时，可让能读取本地文件的助手先阅读 [SKILL.md](SKILL.md)。

提供自己的材料后，输入：

```text
请使用 $obsidian-image-ocr-skill。
请把这篇 Obsidian 笔记中的图片文字转写到原位置，保留原图，标出不确定内容。
```

## 输入与结果

具体输入、工作步骤、适用边界和验收要求见 [SKILL.md](SKILL.md)。这是给智能体执行的工作流，不是独立运行的转写引擎、OCR 引擎或文档应用；所需服务由接收者自己的环境提供。图片与论文结论须回查原材料，结构检查通过不等于学术事实核验完成。

## 来源与版本

本项目从此前公开分享版独立发布，原调用名为 `transcribe-obsidian-images`。 本次调整名称、使用入口与可移植说明；未附带私人材料或账号配置。未新增统一授权条款，第三方内容仍按其原许可。

[全部学习与科研技能目录](https://github.com/narsss242/learning-and-research-skills) · [本地材料与服务配置](https://github.com/narsss242/learning-and-research-skills/blob/main/docs/configuration.md)
