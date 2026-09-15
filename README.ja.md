<div align="center">

# 🧳 Photo Rubber-Stamp Journal

**一枚の写真を、静かな旅の記録へ。**

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

## 👀 このプロジェクトについて

**Photo Rubber-Stamp Journal** は、アップロードした写真を1枚ずつ、正確な **50/50 分割**を使った **4:3 横長のトラベルジャーナル・ポスター**へ変換する Codex 向け画像生成 Skill です。

⬅️ **左側 · 写真：** アップロードした風景を、元の写真として認識できる状態で保ちます。

➡️ **右側 · ラバースタンプ：** 同じ風景を必要な形と色に絞り込み、古びた温かみのある紙に押した小さな多色の手彫りスタンプとして表現します。

1️⃣ 人物、動物、建築、物体、風景、姿勢、向き、空間関係はアップロードされた写真を基準に保ちます。

2️⃣ スタンプには、同じ風景だと認識するために必要なシルエット、ランドマーク、水平線、姿勢、色の関係、構造的な手がかりだけを残します。

3️⃣ 途切れた輪郭、かすれたインク、不均一な圧力、顔料の粒子、紙の繊維、わずかな版ズレによって手刷りらしい質感を作ります。

---

## 🖼️ 作例

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
  <sub>自然 · 建築 · 都市 · 港 · 人物 · 夜景</sub>
</p>

> これらは公開ギャラリー用の完成作品です。実行時の参照画像や隠れたスタイル条件としては使用されません。

> 元写真：[Pexels](https://www.pexels.com/)。異なる題材でも、写真の同一性、場面の関係、50/50 のジャーナル構成を安定して保ちます。

---

## 🚀 クイックスタート

### 💻 方法 1 · Codex Skill

#### 1. インストール

```bash
git clone https://github.com/Beverly621/photo-rubber-stamp-journal-skill.git
mkdir -p ~/.codex/skills
cp -R \
  photo-rubber-stamp-journal-skill/skills/photo-rubber-stamp-journal \
  ~/.codex/skills/
```

Skill がすぐに表示されない場合は Codex を再起動してください。

#### 2. 写真をアップロード

新しい会話を開始し、変換したい写真を添付します。

1枚でも複数枚でもアップロードできます。各写真は独立したジョブとして処理されます。

#### 3. Skill を実行

```text
Use $photo-rubber-stamp-journal to transform this photo.
```

複数写真の場合：

```text
Use $photo-rubber-stamp-journal to transform each uploaded photo into an independent poster.
```

### 📱 方法 2 · モバイル Work

モバイルで **Work** を開き、写真を添付して次のように入力します。

```text
このリポジトリから photo-rubber-stamp-journal Skill のルールを読み取ってください：

https://github.com/Beverly621/photo-rubber-stamp-journal-skill

そのルールを使って、添付した写真を変換してください。
```

> Work は現在のタスク内でリポジトリのルールを直接読み取り、実行できます。Skill を永続的にインストールする必要はありません。

**オプションの上書き**

タイトル、番号、年はデフォルトで自動生成されます。指定したい場合だけ追加してください。

```text
Theme or title: Arctic Sailing
Number: 07
Year: 2026
```

必要であれば、同じ項目をモバイル Work のプロンプト末尾に追加できます。

---

## 📁 リポジトリ構成

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

## 📄 ライセンス

本プロジェクトは [MIT License](./LICENSE) で公開されています。

Skill、production prompt、quality gate、evals、および関連するリポジトリ資料は MIT License の条件に従って利用・変更・再配布できます。

---

<div align="center">

**風景を残し、印を残す。**

📷 → 🖋️ → 📖

</div>
