---
name: idea-vault
description: Capture raw thoughts, observations, reactions, fragments, and half-formed ideas into structured idea cards that accumulate in a personal idea vault. Use this skill when the user wants to save a stray thought, turn a note into a reusable card, compare a new idea with past cards, maintain a small organic tag taxonomy, or build a public/private second-brain style idea archive.
---

# Idea Vault

Turn scattered thoughts, observations, reactions, and fragments into reusable idea cards. The goal is to let ideas accumulate, ferment, and start talking to each other over time.

The skill maintains two reference files:

- `references/ideas-vault.md`: the user's saved idea cards
- `references/tag-taxonomy.md`: the user's evolving tag system

## When To Use

Use this skill when the user:

- shares an observation, image, reaction, touchpoint, or half-thought
- says something like "save this", "make this an idea card", "capture this", or "put this in my idea vault"
- pastes notes, dialogue, quotes, reading excerpts, or rough material worth preserving
- asks whether a new thought resembles something already saved
- wants a lightweight second brain for future writing, research, product ideas, personal reflection, or creative work

## Workflow

Follow these steps in order.

### Step 1: Read The Existing Vault

Always read both files first:

- `references/ideas-vault.md`
- `references/tag-taxonomy.md`

If `ideas-vault.md` has no saved cards yet, say this is the first seed and write `无` in the collision section.

### Step 2: Extract The Seed

Compress the user's raw material into one or two seed sentences.

The seed should:

- go one level deeper than a plain summary
- preserve the emotional temperature of the original thought
- identify whether the material is mainly an observation, question, metaphor, judgment, memory, or tension
- stay open enough to grow later

Before choosing tags, show the seed and ask: "我抓到的种子是：... 对吗？"

### Step 3: Choose Tags

Read `references/tag-taxonomy.md` and prefer existing tags when they fit.

Rules:

- use 3-4 tags per card
- create a new tag only when existing tags are not enough
- keep new tags short, reusable, and under 10 Chinese characters or 3 English words
- avoid tags that are so specific they will probably never be reused
- note which tags are newly created so they can be added to the taxonomy after confirmation

Tags can describe theme, emotion, scene, object, state, relation, or action. Choose the dimensions that best fit the seed.

### Step 4: Generate Three Extensions

Give exactly three one-sentence extensions:

- `-> 深`: go deeper into the underlying reason, root, or assumption
- `-> 事`: move toward a concrete story, person, scene, or example
- `-> 反`: look for the opposite case or counter-example

Each extension should invite future growth. Do not turn an extension into a paragraph.

### Step 5: Find 1-2 Collisions

Scan `references/ideas-vault.md` for the sharpest relationship between the new seed and past cards.

Use at most two collisions. Pick only real relationships:

- `呼应`: the same motif from another angle
- `对立`: an opposite stance, feeling, or conclusion
- `递进`: the new idea goes further than a past card
- `续写`: the new idea answers a question left open by a past card

Each collision is one line with the past card number and a short explanation. If there is no honest collision, write `无`. Do not force weak links.

### Step 6: Output The Idea Card

Use this template:

```text
✦ 想法卡 #[编号] · [日期]

【种子】
[一两句话]

【标签】
#[标签1] #[标签2] #[标签3]

【三延伸】
-> 深: [一句话]
-> 事: [一句话]
-> 反: [一句话 / 不适用]

【碰撞】
- [类型] #[过往编号](日期) - [一行说明]
- [类型] #[过往编号](日期) - [一行说明]
(如果没有就写「无」)
```

Number cards from `#001`. Find the latest existing card number in `ideas-vault.md` and add 1.

### Step 7: Wait For Confirmation

After showing the card, ask only:

```text
保存这张吗？还是想改种子句 / 标签 / 延伸方向？
```

Do not append anything to the reference files before the user confirms.

When the user confirms with phrases like "save", "保存", "就这版", "定了", or "存", output two copyable blocks:

```text
✦ #[编号] 准备入库。请手动粘贴到对应文件：

【粘贴到 references/ideas-vault.md 末尾】
---

[完整想法卡内容]

【粘贴到 references/tag-taxonomy.md 的「全部标签」段落下】
- #[新标签1] (首次 #[编号], 累计 1)
- #[新标签2] (首次 #[编号], 累计 1)
```

If all tags already exist, say the taxonomy does not need new tag rows. Existing tag counts can be updated during periodic cleanup rather than every capture.

## Edge Cases

- Long material: if the material clearly contains multiple seeds, ask whether to split them into separate cards or merge them into one.
- Quoted or forwarded material: mark the source in the seed when known, and compare it with the user's own past cards instead of treating the quoted view as the user's position.
- Finished drafts: if the material is already a complete draft, ask whether the user wants a seed card or a developed article outline.
- Empty vault: create the card normally, write `无` for collisions, and tell the user this is the first seed.
- Messy taxonomy: if the taxonomy has become large or inconsistent, suggest a separate cleanup session. Do not rewrite the taxonomy during normal capture.

## Do Not

- use a plain restatement of the user's sentence as the seed
- use more than 4 tags on one card
- expand each extension into a paragraph
- expand collisions into paragraphs
- force a collision when none is meaningful
- skip reading the vault and taxonomy first
- save or append a card before the user confirms
- use negative or diagnostic psychology labels to explain the user's motives or state, such as personality diagnoses, attachment labels, or clinical labels; describe lived experience in ordinary language instead
