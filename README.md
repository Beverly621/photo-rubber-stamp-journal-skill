# Photo Rubber-Stamp Journal

Transform an uploaded photograph into a quiet 4:3 split travel-journal poster: source-faithful photography on the left, and a hand-carved rubber-stamp memory on aged paper on the right.

将每张上传照片独立转换为一张 4:3 旅行日志海报：左侧保留真实摄影，右侧以手工橡皮章保存场景记忆。

## Examples

| Mountain Reflections | Arctic Sailing |
| --- | --- |
| ![Mountain Reflections finished poster](examples/mountain-reflections.png) | ![Arctic Sailing finished poster](examples/arctic-sailing.png) |

These are finished example posters and a public visual gallery only. They are not source/result pairs, runtime style-conditioning assets, hidden references, or eval fixtures. At runtime, the skill derives each poster from the user's own source photograph and the canonical production prompt.

## Core behavior

- One image produces one poster.
- Multiple images produce independent posters with no cross-image content mixing.
- Every poster uses a 4:3 landscape canvas and an exact 50/50 visual split.
- The left side preserves the real photograph; the right side is a source-derived rubber-stamp interpretation.
- The right panel includes a four-line archival metadata block.
- A central raster-quality failure triggers at most one targeted retry for that image.

## Installation

```bash
git clone https://github.com/Beverly621/photo-rubber-stamp-journal-skill.git
mkdir -p ~/.codex/skills
cp -R \
  photo-rubber-stamp-journal-skill/skills/photo-rubber-stamp-journal \
  ~/.codex/skills/
```

Restart Codex if the skill does not appear immediately.

## Usage

```text
Use $photo-rubber-stamp-journal to transform this photo.
```

Optional metadata:

```text
Theme or title: Arctic Sailing
Number: 07
Year: 2026
```

Missing metadata is generated automatically according to the production prompt.

## Repository structure

```text
.
├── README.md
├── LICENSE
├── .gitignore
├── examples/
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

`SKILL.md` handles invocation and job isolation. `references/generation-prompt.md` is the sole source of truth for visual generation. `references/quality-gate.md` defines post-generation raster inspection and the single-retry policy. `evals/evals.json` records high-risk regression behaviors.

## License

MIT License. The Skill instructions, production prompt, quality gate, evals, and related repository materials are distributed under the repository's MIT License.
