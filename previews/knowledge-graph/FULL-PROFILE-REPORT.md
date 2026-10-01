# Full profile preview

Content commit: `4b12400`. Real GitHub README rendering on
`knowledge-graph-preview`; no main changes. Fresh signed-out Chromium contexts,
1440 × 1000 and 390 × 1000, system Dark / Light themes. Not physical-device or
logged-in manual-theme testing. This is the complete repository README preview;
GitHub's actual profile page chrome/content width can differ.

## Screenshots

- [Desktop Dark](full-profile-dark-1440.png)
- [Desktop Light](full-profile-light-1440.png)
- [390px Dark](full-profile-dark-390.png)
- [390px Light](full-profile-light-390.png)
- [Measured results](full-profile-results.json)

## Design and scope

Inserted only between FireRed Randomizer and Toolbox. Outside that insertion,
README content is byte-identical to main. Existing photos, project text,
dividers, section artworks and badge lists are unchanged.

A semantic `My Learning Map` H2 gives an accessible, theme-aware heading without
another image banner. Existing section artworks were inspected: narrow dark
textured strips, handwritten titles and violet lines. Their subdued violet
palette is echoed by the map; a third decorative banner would add height and
repeat the title. No raster artwork was generated.

Removed the duplicate title/statistics/legend and technical footer from the
profile copies of the four SVGs. Original prototype assets are unchanged.
All 31 topic groups (including exact labels, dots and 12 verification rings)
and all 28 evidence-backed edge elements compare exactly to the originals.
Only the profile image framing/translation changed. Six source-backed islands
are retained; the full dataset and D3 renderer remain untouched.

The section has exactly two new disclosures: Learned topics and About this
graph. All 31 linked titles are grouped; twelve use a subtle dagger for verified.
No ID table, assessment statuses, required-ID list, timestamps or second Mermaid
graph. Project evidence says 26 displayed topics were required across its stages,
not that those topics were individually Applied.

## Results

| Measurement | Desktop (1440px viewport) | Narrow (390px viewport) |
|---|---:|---:|
| README content width | 1012px | 324px |
| Graph image height | 1254px | 1605px |
| Learning heading to Toolbox image | 1659px | 2081px |
| Entire README height, disclosures closed | 2928px | 3189px |
| Document horizontal overflow | None | None |

Identical dimensions in both themes. Compared with A/B assets, graph height is
reduced from 1450 to 1190 viewBox units on desktop (~18%) and 2465 to 2180 on
mobile (~12%), without scaling down topic labels relative to image width.

Both disclosures open normally on GitHub in all four cases. The expanded topic
list contains exactly 31 items / 12 verified marks. Picture selection correctly
chooses each of the four assets. The technical documentation link is present in
About this graph, the Explorer link remains prominently visible outside details.

## Assessment

- **Dominance:** the map is now the main visible content, especially while the
  Photo Album entries remain collapsed. This supports the requested knowledge
  overview, but is a substantial visual weighting change. It is not a tiny widget.
- **Five-second reading:** personal ownership and 31 Learned / 12 Verified are
  immediately readable on reaching the section; named regions establish the
  knowledge-area model. Seeing all six regions or reading all 31 topics requires
  scrolling. This is a design assessment, not a timed user experiment.
- **Desktop:** approximately 16px topic labels at tested content width; good
  separation, quiet edges and consistent ring markers. Long names wrap intact.
- **Mobile:** approximately 11–12px labels are usable but small. The full grouped
  list provides ordinary-size selectable text. Another global size reduction
  would damage readability. The graph spans more than one screen.
- **Transition:** Photo Album → personal learning → Toolbox is logically clear.
  The plain H2 and map palette blend with, but do not imitate, the photographic
  headings. Existing `<br>` spacing is retained around the new section.
- **Light theme:** the map adapts correctly. Existing dark header strips and pale
  typing animation are less harmonious/legible on white; screenshots document
  this pre-existing issue. Those assets were not modified in this phase.
- **Growth:** 100+ topics will need a scoped overview or multiple panels. Do not
  append indefinitely or shrink the whole map.

## Final Markdown and assets

The exact section is in the preview branch README, between anchors
`my-learning-map` and `toolbox` (no integration into main).

Assets: `assets/knowledge-graph/knowledge-{dark,light}{,-mobile}.svg`.
No JavaScript, fonts, credentials, browser-state exports or new dependencies.

No merge, main push or GitHub Pages configuration change.
