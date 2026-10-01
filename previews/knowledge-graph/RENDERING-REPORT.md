# GitHub rendering A/B test

Test date: 2026-10-01. Signed-out Chromium, fresh nonpersistent contexts,
1440 × 1000 and 390 × 1000 CSS pixels, system dark/light preferences. Real
GitHub Markdown blob pages, not a local imitation. No profile integration.
Narrow-screen emulation is not a physical iOS/Android device test. First-glance
and aesthetic judgments below are design assessments, not a timed user study.

## A — Visual First

[Live preview](variant-a.md). Screenshots:
[desktop dark](a-dark-1440.png), [desktop light](a-light-1440.png),
[mobile dark](a-dark-390.png), [mobile light](a-light-390.png).

All 31 original topic labels are present. Six stable, softly grouped islands,
28 evidence-backed prerequisite arrows and 12 additional verification rings.
The muted violet palette and free-standing labels fit the profile's dark photo
album better than rectangular flowchart containers. Categories read as areas of
knowledge rather than workflow stages. No invented connections for isolated
Numeric literals. Dark/light picture selection and mobile assets work on GitHub.

The price is vertical space: at a 1012 px content width the image is about
1529 px tall; at a 324 px content width the mobile image is about 1815 px tall.
Mobile topic text is approximately 12 px, smaller than normal README prose but
much larger than B's fitted text. Six areas cannot all be read in the first
phone viewport. The headline conveys 31 Learned / 12 Verified immediately.
No claim that all 31 titles are comprehensible within five seconds.

## B — Interactive First

[Live preview](variant-b.md). Screenshots:
[desktop dark](b-dark-1440.png), [desktop light](b-light-1440.png),
[mobile dark](b-dark-390.png), [mobile light](b-light-390.png).

GitHub renders all 31 nodes, six subgraphs, 28 overview edges and the complete
38-edge graph on disclosure. Verified text and thicker outlines survive.
No semantic simplification was made to favor Mermaid. A second preview commit
adds absolute links for all 31 main-graph topics after the separate link probe
confirmed GitHub support. Graph content and edge set did not change.

GitHub fits a roughly 2130 × 2088 viewBox into the available width. A sampled
single-line label box becomes about 11.4 px tall on desktop and 3.65 px on
mobile (line-box height, NOT CSS font size). All names exist in the SVG, but
the initial mobile overview is not readable. Pan/zoom restores readable detail
only by sacrificing the overview. Large subgraph rectangles and rank-based
placement feel like a dependency flowchart rather than an organic knowledge
map. Light theme uses pale yellow groups; dark theme uses grey groups. These
default group colors are less consistent with the album aesthetic than A.

## Actual GitHub vs local

- GitHub's `info` diagram reports **11.17.2**; the earlier local test used 11.12.0.
- GitHub uses its own sandboxed renderer iframe and viewer controls. The local
  strict-security parser test did not establish their availability.
- GitHub offers Zoom in/out, directional Pan, Reset, and an expanded viewer.
- The expanded viewer opened during testing; opening it remains a click, not
  an improvement to the initial README overview.
- Three probe node anchors survive. GitHub rewrites requested `_blank` to
  `_parent`; the Pages node actually navigated the current tab in all four
  theme/width combinations. Hyperskill hrefs were inspected, not authenticated.
- The full Mermaid detail graph renders after opening its native details block.
- No document-level horizontal overflow in any of the eight A/B cases.
- A's picture selects the correct four assets without author-supplied scripts.

See [measurements](github-results.json), [interaction checks](interaction-results.json)
and [link/version probe](node-links.md). Measurements capture rendered SVG
geometry inside the GitHub iframe; the outer SVG height is not the visible
fitted diagram height. Screenshots are the visual reference.

## Interaction matrix

| Feature | A | B |
|---|---|---|
| Native details | Works | Works |
| Normal project / Pages / topic-index links | Present | Present |
| Individual overview topic links | Not in image | 31 SVG anchors |
| Mermaid pan / zoom / reset | In expanded detail | In main graph and detail |
| Expanded GitHub diagram viewer | Detail graph | Main and detail |
| Force simulation / independent node dragging | Not provided | Not provided |
| Neighbor selection / search / roadmap filters | Pages only | Pages only |

Zoom/Pan/Reset and Pages-node navigation were exercised using real clicks in
both themes and widths. No session, HAR, cookie jar or auth state was saved.

## Recommendation and C

Choose **A** for the current profile, after the Photo Album's FireRed Randomizer
entry and before Toolbox. It gives topic names and recognizable areas priority
while keeping Mermaid exploration available on demand. B has real interaction,
but it does not solve initial readability. Adding more topics will worsen its
auto-fit problem; A also needs multiple panels or explicitly scoped summaries
at 100/300 topics rather than shrinking a single enormous image.

C was evaluated conceptually, not published as a third tested variant: a second
always-visible connection diagram would repeat information, lengthen the
section and arbitrarily spotlight a small subset. No demonstrated advantage
over A justifies this additional component for the current 31-topic dataset.

The Pages explorer should share the same six groups and Learned/Verified
semantics, then add zoom, search, neighborhood selection, project requirements
and full roadmap. No Pages configuration or D3 source was changed.

## Exact proposed profile section

[proposed-final-section.md](proposed-final-section.md) contains the entire
proposed Markdown section, not an abbreviated placeholder. Its image paths
assume assets would later be copied to `assets/knowledge-graph/`; that copy and
README insertion have NOT been performed. It retains the 31-topic index,
38-edge Mermaid detail and precise project/aggregate evidence notes.

## Scope and evidence

Base main: `320c214156cb5e40ee66e733831f402b9ac12f42`.
README blob: `c9cb11dd820b049d25d9eccc5af4e4f03a4a8064`.
Only new files below `previews/knowledge-graph/` are committed on
`knowledge-graph-preview`. No existing files, main, Pages settings or dataset
were changed. Project 113 retains 26 required targets; no project_applies
edges or topic-level Applied claims. Aggregate Applied remains 26 / 85.
