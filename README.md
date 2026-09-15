<div align="center">

# 🧳 Photo Rubber-Stamp Journal

**Turn a photograph into a quiet field-journal spread.**

<p>
  <a href="./README.md">🇬🇧 <b>English</b></a>
  &nbsp; · &nbsp;
  <a href="./README.zh-CN.md">🇨🇳 <b>简体中文</b></a>
  &nbsp; · &nbsp;
  <a href="./README.ja.md">🇯🇵 <b>日本語</b></a>
</p>

<p>
  <img src="https://img.shields.io/badge/Codex-Skill-111111?style=flat-square" alt="Codex Skill">
  <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue?style=flat-square" alt="MIT License"></a>
</p>

</div>

---

## 👀 About

**Photo Rubber-Stamp Journal** is a Codex image-generation Skill that turns each uploaded photograph into an independent **4:3 travel-journal poster** with an exact **50/50 split**.

⬅️ **Left · Photograph:** the uploaded scene stays recognizable and photographic.

➡️ **Right · Rubber stamp:** the same scene is distilled into a compact, hand-carved multi-color stamp on aged paper.

1️⃣ People, animals, architecture, objects, scenery, pose, orientation, and spatial relationships remain tied to the uploaded source.

2️⃣ Only the silhouettes, landmarks, horizons, poses, color relationships, and structural cues needed to recognize the same scene are carried into the stamp.

3️⃣ Broken contours, dry ink, uneven pressure, pigment grain, paper fibers, and subtle color misregistration create a hand-printed result.

---

## 🖼️ Examples

<p align="center">
  <img src="./examples/test-matrix/01-walden-pond.png" width="32%" alt="Walden Pond">
  <img src="./examples/test-matrix/02-desert-road.png" width="32%" alt="Desert Road">
  <img src="./examples/test-matrix/03-snowy-dog.png" width="32%" alt="Snowy Dog">
</p>
<p align="center">
  <img src="./examples/test-matrix/04-gothic-church-tower.png" width="32%" alt="Gothic Church Tower">
  <img src="./examples/test-matrix/05-old-town-alley.png" width="32%" alt="Old Town Alley">
  <img src="./examples/test-matrix/06-city-tram-street.png" width="32%" alt="City Tram Street">
</p>
<p align="center">
  <img src="./examples/test-matrix/07-fishing-boat-harbor.png" width="32%" alt="Fishing Boat Harbor">
  <img src="./examples/test-matrix/08-crowd-crossing-riga.png" width="32%" alt="Crowd Crossing Riga">
  <img src="./examples/test-matrix/09-night-tram.png" width="32%" alt="Night Tram">
</p>

<p align="center">
  <sub>Nature · Architecture · City · Harbor · People · Night</sub>
</p>

> These are finished example posters for the public gallery. They are not runtime reference images or style-conditioning assets.

> Source photographs: [Pexels](https://www.pexels.com/). Across varied subjects, photo identity, scene relationships, and the 50/50 journal layout remain stable.

---

## 🚀 Quick Start

### 💻 Method 1 · Codex Skill

#### 1. Install

```bash
git clone https://github.com/Beverly621/photo-rubber-stamp-journal-skill.git
mkdir -p ~/.codex/skills
cp -R \
  photo-rubber-stamp-journal-skill/skills/photo-rubber-stamp-journal \
  ~/.codex/skills/
```

Restart Codex if the Skill does not appear immediately.

#### 2. Upload

Start a new conversation and attach the photograph you want to transform.

You can upload one or multiple photographs. Each source image is processed as its own independent job.

#### 3. Run

```text
Use $photo-rubber-stamp-journal to transform this photo.
```

For multiple photos:

```text
Use $photo-rubber-stamp-journal to transform each uploaded photo into an independent poster.
```

### 📱 Method 2 · Mobile Work

Open **Work** on mobile, attach your photograph, and enter:

```text
Read the photo-rubber-stamp-journal skill rules from:

https://github.com/Beverly621/photo-rubber-stamp-journal-skill

Use them to transform the attached photo.
```

> Work can read and execute the repository rules directly for the current task; no permanent Skill installation is required.

**Optional overrides**

Title, number, and year are generated automatically by default. Add them only when you want to override the result.

```text
Theme or title: Arctic Sailing
Number: 07
Year: 2026
```

You can append the same fields to the Mobile Work prompt when needed.

---

## 📁 Repository Structure

```text
photo-rubber-stamp-journal-skill/
├── README.md
├── README.zh-CN.md
├── README.ja.md
├── LICENSE
├── examples/
│   └── test-matrix/
│       ├── 01-walden-pond.png
│       ├── 02-desert-road.png
│       ├── 03-snowy-dog.png
│       ├── 04-gothic-church-tower.png
│       ├── 05-old-town-alley.png
│       ├── 06-city-tram-street.png
│       ├── 07-fishing-boat-harbor.png
│       ├── 08-crowd-crossing-riga.png
│       └── 09-night-tram.png
├── evals/
│   └── evals.json
└── skills/
    └── photo-rubber-stamp-journal/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        └── references/
            ├── generation-prompt.md
            └── quality-gate.md
```

---

## 📄 License

Released under the [MIT License](./LICENSE).

The Skill, production prompt, quality gate, evals, and related repository materials may be used, modified, and redistributed under the terms of the MIT License.

---

<div align="center">

**Keep the scene. Leave an imprint.**

📷 → 🖋️ → 📖

</div>
