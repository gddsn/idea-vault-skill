# idea-vault-skill

一个用来沉淀零散想法的 skill。

它会把一句突然冒出来的话、一个观察、一个触动、一个没想完的判断，整理成稳定的「想法卡」：有种子句、有标签、有三个延伸方向，也会和过去的卡片发生 1-2 个真实碰撞。

这个仓库不包含任何作者的私人旧想法。`idea-vault/references/ideas-vault.md` 和 `idea-vault/references/tag-taxonomy.md` 都是空模板，适合直接拿去建立自己的想法库。

## 适合什么场景

- 写公众号、博客、论文、产品笔记之前，先把碎片想法存起来
- 读书、看电影、聊天、散步时，有一句话突然值得留下
- 想让旧想法和新想法互相呼应，而不是散落在聊天记录里
- 想搭一个轻量的个人第二大脑，但不想一开始就设计复杂系统

## 仓库结构

```text
idea-vault-skill/
├── idea-vault/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       ├── ideas-vault.md
│       └── tag-taxonomy.md
├── dist/
│   └── idea-vault.skill
├── LICENSE
└── README.md
```

## 在 Claude Skills 中使用

最简单的方式：

1. 下载 `dist/idea-vault.skill`。
2. 在 Claude 的 Skills 设置页上传这个 `.skill` 文件。
3. 开始对话，例如：

```text
按 idea-vault 帮我存一下这个想法：我发现很多想法不是消失了，是因为没有被放到能再次遇见它的地方。
```

如果你想直接编辑源码，也可以把 `idea-vault/` 文件夹作为一个 skill 目录使用。

## 在 Codex Skills 中使用

把 `idea-vault/` 目录复制到你的 Codex skills 目录中，例如：

```bash
mkdir -p ~/.codex/skills
cp -R idea-vault ~/.codex/skills/idea-vault
```

然后重新打开 Codex，使用：

```text
Use $idea-vault to capture this thought: ...
```

## 第一次使用

第一次使用时，`ideas-vault.md` 没有任何卡片。skill 会把第一张卡编号为 `#001`，碰撞部分写 `无`。

每张卡确认保存后，你会得到两段可复制内容：

- 粘贴到 `idea-vault/references/ideas-vault.md` 末尾的完整卡片
- 粘贴到 `idea-vault/references/tag-taxonomy.md` 的新标签

如果这次没有新标签，标签词典可以不改。已有标签的累计次数不必每次手动更新，定期整理即可。

## 想法卡格式

```text
✦ 想法卡 #001 · 2026-05-14

【种子】
想法不是因为弱小才消失，而是因为没有被放到一个能再次相遇的地方。

【标签】
#想法管理 #再次相遇 #写作素材

【三延伸】
-> 深: 为什么人会误以为自己缺少想法，而不是缺少承接想法的容器？
-> 事: 可以写一个人翻旧卡片时突然找回半年前某个问题答案的场景。
-> 反: 有些想法也许确实应该自然消散，不必全部保存。

【碰撞】
无
```

## 隐私提醒

这个 skill 会把想法沉淀到本地 reference 文件中。开源前请确认：

- 不要把私人想法卡、聊天记录、真实人名、联系方式放进公开仓库
- 如果你 fork 这个仓库来使用，建议把自己的 `references/` 私有化
- 公开发布时，只发布空模板或者经过确认可以公开的样例

## 公众号引用建议

可以这样介绍：

```text
我把一个「沉淀想法」的小 skill 开源了。它不是替你写文章，而是帮你把零散念头做成可积累、可碰撞的想法卡。你可以把它接到 Claude 或 Codex 里，用来建立自己的 idea vault。
```

仓库名：`idea-vault-skill`

## License

MIT
