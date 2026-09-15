# Raster Quality Gate

Inspect the actual generated raster, not only the prompt. Judge success against the corresponding source photograph and any exact user metadata.

## 1. Canvas and split

Success: a 4:3 landscape canvas split at the exact vertical midpoint into directly adjacent 50/50 regions. The join is not itself a design element.

Typical drift: a gutter, border, overlap, before/after label, visible divider, or misplaced split.

## 2. Left photograph

Success: the left side still reads unmistakably as the original photograph. Preserve scene identity, subject count, pose, orientation, spatial relationships, perspective, recognizable architecture, objects and landscape, using only proportional cropping. Vintage grading remains restrained: slightly faded color, gentle warmth, grain, and archival paper finish without redrawing or obscuring the subject.

Typical drift: stretched or mirrored content, invented or moved subjects, changed identity, a painted or illustrated appearance, or destructive texture.

## 3. Right panel

Success: warm off-white handmade archival paper with subtle beige variation, fibers, tiny flecks, matte tactility, and generous empty area. A compact illustration sits in the middle-to-lower region and occupies approximately 65%–78% of the panel width and 25%–38% of its height.

Typical drift: full-page illustration, insufficient blank paper, glossy surface, logo, circular seal, postage stamp, or decorative badge.

## 4. Source fidelity

Success: the simplified stamp clearly traces back to the same source through its dominant silhouette, primary subject, foreground/background relationship, horizon or ground line, exact important subject count, orientation, and left-to-right relationships.

- Architecture retains defining silhouette, arches, dome, roof, tower, or facade rhythm.
- Landscapes retain major mountain, shoreline, water, road, tree, or horizon contours.
- People and animals retain count, pose, distinctive shapes, and relationships.
- Vehicles and objects retain recognizable silhouette, orientation, primary color placement, and scene relationship.

Typical drift: generic scenery, wrong count or orientation, lost landmark structure, or invented content.

## 5. Rubber-stamp material

Success: the right image first reads as a physically hand-carved, hand-inked rubber-stamp print. Look for irregular engraved contours, uneven line weight, broken edges, dry-ink gaps, granular pigment, sparse hatching, incomplete pressure, paper bleed-through, minor double impressions, and subtle color misregistration.

Typical drift: clean vector art, watercolor, pencil, cartoon, a photo-filter effect, digital illustration, or a posterized photograph.

## 6. Color

Success: 2–4 muted spot colors visibly derived from the source, including one dark structural ink, one or two scene-specific colors, and at most one small accent. Color behaves as flat printed ink and remains connected to the source palette.

Typical drift: smooth gradients, oversaturation, unrelated colors, or too many inks.

## 7. Text

Success: one legible four-line archival block below the stamp:

1. theme or location title;
2. `No. [NUMBER]`;
3. exactly three uppercase English keywords separated by `•`;
4. year.

Use typewriter-like mechanical printing with correct spelling. Reproduce user-provided title, number, and year exactly.

Typical drift: missing or extra lines, pseudo-text, misspelling, incorrect metadata, the wrong keyword count, missing bullets, or added slogan, logo, coordinates, handle, or watermark.

## 8. Multi-photo isolation

Success: input photo count equals poster count, and every output can be traced only to its corresponding source.

Typical drift: subject, location, palette, object, or person leakage between photographs; multiple sources combined into one poster.

## Decision and retry

Central requirements are source-photo fidelity, the 4:3 exact 50/50 composition, genuine rubber-stamp material, correct four-line text structure, and multi-photo isolation.

If any central requirement clearly fails, refine the generation instruction only around the observed failure and regenerate that source image once. Do not touch successful jobs. After the second attempt, return the candidate that better satisfies the production contract. Never enter a further regeneration loop.
