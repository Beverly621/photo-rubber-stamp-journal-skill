<div align="center">

# 🧳 Photo Rubber-Stamp Journal

**写真には現実の風景を。紙の上には、その風景の記憶を小さなスタンプとして残します。**

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

## 📖 このプロジェクトについて

**Photo Rubber-Stamp Journal** は、アップロードした写真を1枚ずつ独立した **4:3 横長のトラベルジャーナル・ポスター** に変換する Codex 向け画像生成 Skill です。

画面は中央で正確に二分されます。

- **左側 — 写真：** 元の風景を、写真として認識できる状態で残します。
- **右側 — ラバースタンプ：** 同じ風景から重要な輪郭・色・空間関係だけを抽出し、古い紙に押した多色の手彫りスタンプとして再構成します。

単なる写真フィルターやベクター化ではなく、同じ風景を二つの方法で記録することが目的です。

**写真は現場を残し、スタンプは記憶を残します。**

```text
PHOTO  →  PRESERVE  →  DISTILL  →  STAMP  →  ARCHIVE
```

---

## 🖼️ 作例

<p align="center">
  <img src="./examples/mountain-reflections.png" width="48%" alt="Mountain Reflections">
  <img src="./examples/arctic-sailing.png" width="48%" alt="Arctic Sailing">
</p>

<p align="center">
  <sub>Mountain Reflections · Arctic Sailing</sub>
</p>

> これらは完成作品の公開ギャラリーです。Skill 実行時の隠れた参照画像やスタイル条件としては使用されません。

### 3×3 シーン多様性テスト

<p align="center">
  <img src="./examples/test-matrix/01-walden-pond.png" width="32%" alt="ウォールデン池">
  <img src="./examples/test-matrix/02-desert-road.png" width="32%" alt="砂漠の道">
  <img src="./examples/test-matrix/03-snowy-dog.png" width="32%" alt="雪原の犬">
</p>
<p align="center">
  <img src="./examples/test-matrix/04-gothic-church-tower.png" width="32%" alt="ゴシック教会の塔">
  <img src="./examples/test-matrix/05-old-town-alley.png" width="32%" alt="旧市街の路地">
  <img src="./examples/test-matrix/06-city-tram-street.png" width="32%" alt="街路を走るトラム">
</p>
<p align="center">
  <img src="./examples/test-matrix/07-fishing-boat-harbor.png" width="32%" alt="港の漁船">
  <img src="./examples/test-matrix/08-crowd-crossing-riga.png" width="32%" alt="リガの横断歩道を渡る人々">
  <img src="./examples/test-matrix/09-night-tram.png" width="32%" alt="夜のトラム">
</p>

<p align="center">
  <sub>自然 · 建築 · 都市 · 港 · 人物 · 夜景</sub>
</p>

9 回の独立生成により、異なる被写体でも写真の同一性、場面の関係、50/50 のジャーナル構成が安定して保たれることを確認しています。元写真は Pexels 提供で、リガの群衆写真は Vlad Fonsark によるものです。

---

## ✨ 写真から残すもの

- **写真は写真のまま。** 人物、動物、建築、物体、風景、姿勢、向き、空間関係はアップロードされた写真を基準に保ちます。
- **スタンプは視覚的な記憶。** シルエット、ランドマーク、水平線、姿勢、色の関係、場面構造など、同じ風景だと認識するために必要な要素だけを残します。
- **素材感は手仕事らしく。** 途切れた輪郭、かすれたインク、不均一な圧力、顔料の粒子、紙の繊維、わずかな版ズレによって物理的なスタンプらしさを作ります。

---

## 🚀 クイックスタート

### 1. インストール

```bash
git clone https://github.com/Beverly621/photo-rubber-stamp-journal-skill.git
mkdir -p ~/.codex/skills
cp -R \
  photo-rubber-stamp-journal-skill/skills/photo-rubber-stamp-journal \
  ~/.codex/skills/
```

Skill がすぐに表示されない場合は Codex を再起動してください。

### 2. 写真をアップロード

新しい Codex の会話を開始し、変換したい写真を添付します。

### 3. Skill を実行

```text
Use $photo-rubber-stamp-journal to transform this photo.
```

これだけです。

---

## 🏷️ オプション情報

タイトル、番号、年を指定することもできます。

```text
Theme or title: Arctic Sailing
Number: 07
Year: 2026
```

指定されていない項目は自動生成されます。

---

## 🖼️ 複数写真の処理

一度に複数の写真をアップロードできます。

各写真は**独立した生成ジョブ**として処理されます。

```text
3 source photos
      ↓
3 independent generations
      ↓
3 finished posters
```

人物、場所、色、物体、シーン情報が別の写真と混ざることはありません。

---

## 🧩 Skill の仕組み

ランタイム構成は意図的に小さく保っています。

```text
SKILL.md
   ↓
generation-prompt.md
   ↓
image generation
   ↓
quality-gate.md
   ↓
finished poster
```

- `SKILL.md` — 実行フローと写真ごとの分離
- `references/generation-prompt.md` — 正式な production prompt
- `references/quality-gate.md` — 生成後のビジュアル検査
- `evals/evals.json` — 重要な挙動の回帰テスト

ビジュアルスタイルの基準は production prompt に一本化されています。

---

## 📁 リポジトリ構成

```text
photo-rubber-stamp-journal-skill/
├── README.md
├── README.zh-CN.md
├── README.ja.md
├── LICENSE
├── examples/
│   ├── mountain-reflections.png
│   ├── arctic-sailing.png
│   └── test-matrix/
│       └── 9 点のシーン多様性ポスター
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

## 📄 ライセンス

本プロジェクトは [MIT License](./LICENSE) で公開されています。

Skill、production prompt、quality gate、evals、および関連するリポジトリ資料は MIT License の条件に従って利用・変更・再配布できます。

---

<div align="center">

**左には現実の風景を。  
右にはインクで残した記憶を。**

📷 → 🪵 → 🖋️ → 📖

</div>
