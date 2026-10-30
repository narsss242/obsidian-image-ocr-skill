---
name: obsidian-image-ocr-skill
description: "Obsidian image OCR workflow: transcribe and proofread images in Markdown notes while preserving originals and source links. Transcribe, proofread, and organize local images embedded in Obsidian Markdown while keeping the transcription at the image's original position and retaining the source image for verification. Use when the user says “图片归文”, “处理新粘贴图片”, asks to turn screenshots or pasted images in Obsidian into searchable text, or wants newly embedded study-note images processed in place."
---

# 图片归文

Convert embedded images into searchable Obsidian content without changing where the information appears in the note.

## Non-negotiable invariant

Place the transcription at the exact location of the original image embed. Do not append it to the end of the note, collect it in another note, or move it to a different section.

Replace the original embed in place with this pattern:

```md
<!-- 图片归文 -->

[校对后的 Markdown 文字]

> [!example]- 原始图片
> ![[原图片路径]]
```

Keep the source image immediately after its transcription in a collapsed callout. Never delete an original image unless the user explicitly requests deletion.

## Workflow

1. Identify the requested Obsidian vault, note, or scope. When the user says only “图片归文”, use the active workspace and process newly pasted or explicitly marked images.
2. Find local image embeds in both Obsidian and standard Markdown syntax:
   - `![[path/image.png]]`
   - `![alt](path/image.png)`
3. Prefer targets marked with `<!-- 待转写 -->`. Otherwise distinguish new images from already processed images by ignoring embeds inside an `原始图片` callout following `<!-- 图片归文 -->`.
4. Resolve every image path against the vault and note location. Report a missing image instead of guessing its contents.
5. Inspect every target image at sufficient resolution. Transcribe the visible text, then proofread it against the image.
6. Preserve wording, language, punctuation, examples, symbols, and meaningful line breaks. Correct obvious OCR mistakes, but do not silently invent obscured content.
7. Structure the transcription as useful Markdown at the same position:
   - use headings only when the image clearly introduces a section;
   - use bullets for vocabulary, examples, or parallel points;
   - preserve sentence order;
   - retain pronunciation, stress, linking, and phonetic annotations accurately;
   - use tables only for genuinely tabular material.
8. For unclear content, write `[待确认：可辨认部分]` and keep the image available for review.
9. If a pasted image is stored in a cluttered vault-root location, it may be moved to `附件/<笔记名>/`; update the embed at the same time. Otherwise keep its existing path.
10. Edit only the targeted image blocks and necessary links. Preserve surrounding headings, prose, ordering, frontmatter, and unrelated user edits.

## Study-note handling

For TOEFL notes, prefer editable learning content over raw OCR:

- keep English examples as separate searchable lines;
- keep Chinese explanations close to the relevant example;
- distinguish vocabulary, sentence patterns, pronunciation rules, and corrections;
- do not “improve” or paraphrase English source sentences unless asked;
- preserve visual diagrams when their spatial meaning cannot be represented faithfully in text, and add a concise description above them.

## Validation

Before finishing:

- confirm each transcription occupies the former embed position;
- confirm every original image remains embedded directly below its transcription;
- confirm all image links resolve;
- confirm no already processed image was duplicated;
- compare the final text with every target image for omissions and OCR errors;
- report the number of images processed and any `[待确认]` items.
