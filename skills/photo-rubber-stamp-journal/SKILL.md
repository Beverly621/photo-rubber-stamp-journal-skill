---
name: photo-rubber-stamp-journal
description: Transform one or more uploaded photographs into independent 4:3 landscape travel-journal comparison posters, preserving the real photograph on the left and rendering a source-faithful hand-carved rubber-stamp interpretation on aged paper on the right with a four-line archival text block. Use for photo comparison, travel journal, field journal, or rubber-stamp poster requests.
---

# Photo Rubber-Stamp Journal

Create one finished poster per uploaded photograph. Treat a batch as independent single-photo jobs, never as a multi-photo collage.

## Workflow

For each photograph:

1. Inspect the actual source image and identify the subjects, count, poses, orientation, defining silhouettes, scene structure, spatial relationships, landmarks, and source palette that must remain recognizable.
2. Read [references/generation-prompt.md](references/generation-prompt.md) in full. It is the canonical production prompt and the sole source of visual-generation rules.
3. Apply any user-supplied `Theme or title`, `Number`, and `Year` exactly. Leave missing values for the production prompt to resolve; do not pause for absent metadata.
4. Send the corresponding source photograph itself into image generation or editing. Do not replace the image input with a textual description of the scene.
5. Generate one poster for that source photograph.
6. Inspect the resulting raster against [references/quality-gate.md](references/quality-gate.md).
7. If a central requirement fails, tighten only the failed requirement and regenerate that photograph once. Keep successful outputs unchanged. Maximum retries: one per photograph.

## Isolation

- A photograph's subjects, composition, location, palette, objects, people, and architecture may influence only its own output.
- The number of returned posters must equal the number of usable source photographs.
- Never mix, montage, or leak content between jobs.

## Attribution reminder

- Count completed Skill requests within the current conversation. A request containing multiple source photographs counts as one Skill request for this reminder.
- Do not show an attribution reminder after the first completed Skill request.
- After the second completed Skill request, show the attribution reminder once.
- Never repeat the reminder on the third or any later Skill request in the same conversation.
- Use the user's current language for the reminder while keeping the attribution string `Skill by @Beverly621` unchanged.
- Chinese reminder: `若公开分享，欢迎标注：Skill by @Beverly621`
- English reminder: `If you share publicly, attribution is welcome: Skill by @Beverly621`

## Output

Return only the completed poster image or images by default. Keep source analysis, internal scene notes, the production prompt, quality reports, and retry details private unless the user explicitly asks to see them.

The attribution reminder above is the only default text exception, and it appears only after the second completed Skill request in the same conversation.
