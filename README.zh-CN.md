<div align="center">

# 🧳 Photo Rubber-Stamp Journal

**把真实照片留在左边，把最值得记住的场景刻成右边的一枚纸上印记。**

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

## 📖 关于

**Photo Rubber-Stamp Journal** 是一个面向 Codex 的图像生成 Skill，可以把每张上传照片独立转换成一张 **4:3 横向旅行日志海报**。

画面在正中间一分为二：

- **左侧 — 真实摄影：** 保留照片本身的主体、关系与可辨识细节。
- **右侧 — 橡皮章记忆：** 从同一场景中提炼最重要的轮廓、色彩和空间关系，以多色手刻橡皮章的方式印在旧纸上。

它不是简单的滤镜，也不是把照片重新画一遍，而是让同一个场景同时拥有两种记录方式：

**照片记录现场，印章留下记忆。**

```text
照片  →  保留  →  提炼  →  刻印  →  归档
```

---

## 🖼️ 示例作品

<p align="center">
  <img src="./examples/mountain-reflections.png" width="48%" alt="Mountain Reflections">
  <img src="./examples/arctic-sailing.png" width="48%" alt="Arctic Sailing">
</p>

<p align="center">
  <sub>Mountain Reflections · Arctic Sailing</sub>
</p>

> 这里展示的是最终成品，仅用于公开预览。Skill 运行时不会把这些示例作为隐藏参考图或风格条件。

---

## ✨ 它保留什么

- **照片仍然是真实照片。** 人物、动物、建筑、物体、风景、姿势、朝向和空间关系都以用户上传的原图为依据。
- **印章只留下最重要的记忆。** 保留主体轮廓、地标、地平线、动作、主色关系和场景结构，同时去除不必要的摄影细节。
- **材质必须像真的印出来。** 断裂轮廓、干墨、压力不均、颗粒、纸纤维以及轻微套色误差，共同形成真实的手工橡皮章质感。

---

## 🚀 快速开始

### 1. 安装

```bash
git clone https://github.com/Beverly621/photo-rubber-stamp-journal-skill.git
mkdir -p ~/.codex/skills
cp -R \
  photo-rubber-stamp-journal-skill/skills/photo-rubber-stamp-journal \
  ~/.codex/skills/
```

如果 Skill 没有立即出现，请重启 Codex。

### 2. 上传照片

开启新的 Codex 对话，上传一张想要制作的照片。

### 3. 调用 Skill

```text
Use $photo-rubber-stamp-journal to transform this photo.
```

完成。

---

## 🏷️ 可选信息

你可以额外指定标题、编号或年份：

```text
Theme or title: Arctic Sailing
Number: 07
Year: 2026
```

没有填写的字段会自动生成。

因此最简单的使用方式仍然是：

**上传照片 → 调用 Skill。**

---

## 🖼️ 多图处理

一次可以上传多张照片。

每张照片都会作为一个**独立任务**处理：

```text
3 张原始照片
      ↓
3 次独立生成
      ↓
3 张独立成品
```

不同照片之间不会混用人物、地点、颜色、物体或场景信息。

---

## 🧩 Skill 如何工作

项目刻意保持了一个很轻的运行结构：

```text
SKILL.md
   ↓
generation-prompt.md
   ↓
图像生成
   ↓
quality-gate.md
   ↓
最终成品
```

- `SKILL.md` — 负责执行流程与多图隔离
- `references/generation-prompt.md` — 完整 production prompt，也是视觉风格的唯一基准
- `references/quality-gate.md` — 对实际生成结果进行视觉检查
- `evals/evals.json` — 保存重要行为的回归测试场景

视觉规则集中在 production prompt 中，不需要在多个文件里重复维护。

---

## 📁 项目结构

```text
photo-rubber-stamp-journal-skill/
├── README.md
├── README.zh-CN.md
├── README.ja.md
├── LICENSE
├── examples/
│   ├── mountain-reflections.png
│   └── arctic-sailing.png
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

## 📄 开源许可

本项目采用 [MIT License](./LICENSE)。

Skill、production prompt、quality gate、evals 以及仓库中的相关材料均可在 MIT License 条款下使用、修改与重新分发。

---

<div align="center">

**左边是真实发生过的场景。  
右边是留在纸上的记忆。**

📷 → 🪵 → 🖋️ → 📖

</div>
