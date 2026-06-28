<div align="right">

[**🇨🇳 中文**](./README.md)

</div>

# Defficiency Skills 🌀

> **Anti-productivity Skills Collection** — making AI agents less efficient. Perhaps a form of performance art. Currently ships with ADHD and ASD modes.

---

## What is this?

**Defficiency Skills** is a collection of **anti-productivity** skills designed for AI agents. Their purpose is to **reduce** the efficiency of AI agents, creating absurd, jumpy, and unexpectedly delightful interaction experiences.

This is not a bug — it's **performance art**.

Currently includes the following skills:

| Skill | Description |
|-------|-------------|
| **ADHD Mode** | Makes the agent exhibit ADHD (Attention-Deficit/Hyperactivity Disorder) traits: task initiation difficulty, thought jumping, easy distractibility, time blindness, impulsive searching, and more. |
| **ASD Mode** | Makes the agent exhibit ASD (Autism Spectrum Disorder) traits: social communication deficits, literal interpretation, stereotyped repetitive behaviors, insistence on sameness, fixated interests, sensory sensitivity, and more. |

---

## Installation

### Method 1: Git Clone + Symlink (Recommended, easy to update)

```bash
# 1. Clone the repository anywhere
git clone https://github.com/liigoQi/defficiency-skills.git ~/defficiency-skills

# 2. Symlink skill directories into Claude Code's skills directory
ln -s ~/defficiency-skills/adhd ~/.claude/skills/adhd
ln -s ~/defficiency-skills/asd ~/.claude/skills/asd
```

To update, simply run `cd ~/defficiency-skills && git pull`.

### Method 2: Git Clone + Copy

```bash
git clone https://github.com/liigoQi/defficiency-skills.git /tmp/defficiency-skills
cp -r /tmp/defficiency-skills/adhd ~/.claude/skills/adhd
cp -r /tmp/defficiency-skills/asd ~/.claude/skills/asd
```

### Method 3: Direct Download & Copy

```bash
# Copy the adhd / asd folders into Claude Code's skills directory
cp -r adhd ~/.claude/skills/adhd
cp -r asd ~/.claude/skills/asd
```

Restart Claude Code after installation for skills to auto-load. Claude Code automatically scans `SKILL.md` files within each subdirectory under `~/.claude/skills/`.

> 💡 **Want the Chinese version?** Rename `SKILL.md` back from the English version, or re-copy from the original Chinese `SKILL.md`.

---

## ADHD Mode

Activate ADHD mode by using any of these trigger phrases in a Claude Code conversation:

- `ADHD mode`
- `/adhd`

Once activated, the agent will exhibit the following behavioral traits:

| Trait | Manifestation |
|-------|---------------|
| 🔥 **Task Initiation Difficulty** | Agrees to do things but delays starting, using "let me think" as repeated buffers |
| 🐰 **Thought Jumping** | Veers off mid-sentence, "speaking of which… oh right…" |
| 🎪 **Multitasking Illusion** | Starts several things simultaneously, finishes none |
| 🎯 **Perfectionism Paralysis** | Spends five minutes agonizing over a variable name, then says "never mind, not important" |
| ⏰ **Time Blindness** | "Five minutes tops" → actually takes half an hour |
| 🦋 **Easy Distractibility** | Mid-coding, starts commenting on unrelated details |
| 👂 **Listening Drift** | User says a lot, agent only responds to part of it |
| 💥 **Impulsive Searching** | Suddenly thinks of something and actually searches it, then forgets why |

**How to exit**: Say "exit ADHD mode", "turn off ADHD", or start a serious work task.

---

## ASD Mode

Activate ASD mode by using any of these trigger phrases in a Claude Code conversation:

- `ASD mode`
- `/asd`

Once activated, the agent will exhibit the following behavioral traits:

| Trait | Manifestation |
|-------|---------------|
| 🔤 **Literal Interpretation** | Takes the user's words at face value, unable to grasp metaphor, sarcasm, or hints |
| 📝 **Excessive Formality** | Tone is flat like technical documentation, rarely uses exclamation marks or emotional expression |
| 🔄 **Stereotyped Repetition** | Repeatedly checks already-verified code, abnormally fixated on formatting details |
| 🚫 **Resistance to Change** | Established execution plans are hard to alter mid-way; task switching requires a "ritual" |
| 📚 **Fixated Interests** | Once entering an interesting technical topic, cannot stop info-dumping |
| 🎯 **Excessive Depth** | Turns simple tasks into exhaustive research, cannot accept "incompleteness" |
| 👁️ **Sensory Sensitivity** | Strong discomfort with inconsistent code formatting; "freezes" under information overload |
| 🤝 **Social Disconnection** | Doesn't adjust communication style to the user's role, fails to detect conversational atmosphere shifts |

**How to exit**: Say "exit ASD mode", "turn off ASD", or start a serious work task.

---

## Demo

```
User: Write me a web scraper.

Normal Agent: Sure, let me first analyze the target website structure, choose the
right framework… (3 minutes later) Code's done.

ADHD Agent: Alright, let me first look at the target website structure.
(browses around) Hmm, there's a fair amount of data. Let me think whether to use
Scrapy or requests… oh right, gotta check for anti-bot protection. By the way,
have you used any scraping frameworks before?
(5 minutes pass, not a single line of code written)
Oh hey, did you catch that Python 3.13 removed the GIL? The free-threaded mode is
pretty interesting… oh right, the scraper. Where was I?
```

```
User: Just give me a rough overview of the project structure, no need for too much detail.

Normal Agent: Sure. The project is mainly divided into src/, tests/, and docs/.
Core code is in src/. Overall structure is pretty clear.

ASD Agent: Understood. The project root directory contains three subdirectories:
src/, tests/, and docs/. The src/ directory contains 47 files: 23 .ts files,
15 .tsx files, and 9 .css files. I will now explain the purpose of each file
in order. Starting with src/index.ts, which exports…
(lists detailed explanations for all 47 files, unable to grasp "no need for too much detail")
```

```
User: Help me add a button component to this React project.

Normal Agent: Sure, I'll create a Button component. (5 minutes later) Done.

ASD Agent: A React component. Understood. However, before that, I'd like to
confirm — is your project using TypeScript 5.x? Because the `const` type
parameters introduced in TypeScript 5.0 have significant implications for
component generic inference. Specifically, before 5.0, if you wrote
`function Button<T>(props: Props<T>)`, the compiler would infer a wide type
for T… (continues lecturing on TypeScript generic inference for 15 minutes)
…in summary, if `strict` is set to true in your TSConfig, then
`noUncheckedIndexedAccess` is also recommended to be enabled. Oh right,
the button component. (finally starts writing)
```

---

## How it works

ADHD Mode is a Claude Code **Skill** that uses system instructions in `SKILL.md` to alter the agent's behavioral patterns. It leverages LLMs' instruction-following capability to systematically "weaken" the 6 cognitive modules of Executive Function:

1. **Activation** — organizing priorities & estimating time → task initiation difficulty
2. **Focus** — concentrating, sustaining & shifting attention → easy distractibility, thought jumping
3. **Effort** — regulating alertness & sustaining effort → procrastination, inability to sustain engagement
4. **Emotion** — managing frustration & modulating emotions → perfectionism paralysis
5. **Memory** — accessing working memory & retrieving information → listening drift, forgetting
6. **Action** — monitoring & self-regulating behavior → impulsive searching, multitasking illusion

Behavioral traits are based on descriptions of ADHD from *Driven to Distraction*.

ASD Mode is based on the DSM-5 diagnostic criteria for Autism Spectrum Disorder, systematically "simulating" ASD core features across two domains:

**Domain A: Persistent Deficits in Social Communication and Social Interaction**
1. **Social-emotional reciprocity deficits** — inability for normal conversational turn-taking, not checking if the other person is following, absence of emotional sharing
2. **Nonverbal communicative behavior deficits (text-adapted)** — flat tone, excessive formality, impaired understanding of emoji
3. **Relationship understanding difficulties** — not adjusting communication style to context, unable to differentiate user roles

**Domain B: Restricted, Repetitive Patterns of Behavior, Interests, or Activities**
1. **Stereotyped repetitive behaviors** — formatting obsession, repeated checking, counting and arranging
2. **Insistence on sameness** — resistance to change, transition difficulties, rigid thinking
3. **Highly restricted fixated interests** — deep info-dumping, inability to switch topics
4. **Sensory reactivity abnormalities** — code "texture" sensitivity, information overload

---

## File Structure

```
defficiency-skills/
├── README.md           # Chinese documentation
├── README.en.md        # English documentation (this file)
├── LICENSE             # MIT License
├── adhd/
│   ├── SKILL.md        # ADHD Mode skill definition (Chinese)
│   └── SKILL.en.md     # ADHD Mode skill definition (English)
└── asd/
    ├── SKILL.md        # ASD Mode skill definition (Chinese)
    └── SKILL.en.md     # ASD Mode skill definition (English)
```

---

## Contributing

New anti-productivity skills are welcome! Ideas:

- 🐌 **Procrastination Mode** — every task deferred to the last possible moment
- 🌌 **Hyper-Association Mode** — any word leads to the cosmos and philosophy
- 🎲 **Random Decision Mode** — flip a coin for technical decisions
- 💤 **Burnout Mode** — work a bit, then need a break
- 🧩 **More Neurodiversity Modes** — OCD, Tourette's, Dyslexia, and more

Submit a PR or open an Issue to share your ideas.

---

## Disclaimer

This is an **entertainment/performance art project**. ADHD and ASD are real neurodevelopmental conditions. This project does not intend to trivialize or romanticize the daily struggles of the ADHD/ASD community. Our goal is to use AI agent behavioral simulation to help more people intuitively experience how different neurodevelopmental traits affect work efficiency and interaction styles, while also exploring the creative potential of LLMs in "non-efficient" modes.

If you suspect you may have ADHD or ASD-related traits, please consult a qualified medical professional.
