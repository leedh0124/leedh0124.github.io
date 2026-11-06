# Content review — November 6, 2026

This is an editorial record, excluded from the generated website.

## Sources and decisions

- Primary personal sources: the current `../myCV/DHL_CV.tex` / `.pdf`, the
  approved one-page industry résumé, and the user's clarifications in this
  conversation. Expected graduation is May 2028; opportunities include both
  research internships and future full-time roles.
- UT Austin affiliation, contact, and research interests checked against the
  [CLeAR Lab profile](https://clearoboticslab.github.io/people/Dongho_Lee/index.html).
- Google Scholar returned HTTP 429. The site links to the user's profile, but
  no citation counts or claim of a complete Scholar synchronization was added.
- The reduced GOOP work remains a
  [2026 preprint](https://arxiv.org/abs/2603.26950). Its SIAM Journal on Optimization
  review status comes from the current academic CV; acceptance was not inferred.
- GOOP publication checked against
  [IEEE](https://ieeexplore.ieee.org/abstract/document/11018386/) and
  [arXiv](https://arxiv.org/abs/2410.21447).
- Mixed-hierarchy paper checked against
  [arXiv](https://arxiv.org/abs/2602.01568) and the
  [official WAFR 2026 program](https://algorithmic-robotics.org/alls/).
  Hardware results are attributed to the team, not to personal hardware deployment.
- Hierarchical routing: [arXiv](https://arxiv.org/abs/2503.13790) and current CV.
- Approximate GOOP: [arXiv](https://arxiv.org/abs/2507.11021), the current CV,
  and the coauthors' public publication records.
- Information gathering: [official AAMAS proceedings](https://www.ifaamas.org/Proceedings/aamas2025/pdfs/p1595.pdf).
- Learning-based routing: [Springer publisher record](https://link.springer.com/article/10.1007/s10489-024-05367-4), published 2024.
- Aerodynamic prediction: [ScienceDirect publisher record](https://www.sciencedirect.com/science/article/pii/S1270963823001049), published 2023.
- Earlier Korean publications and project history were retained from the
  existing site. No unrelated papers from authors with the same name were added.

## User corrections incorporated into website text

- CLeAR Lab is linked directly throughout the site.
- Original GOOP code verified from its README:
  https://github.com/CLeARoboticsLab/ordered-preferences
- Reduced-GOOP is linked separately:
  https://github.com/CLeARoboticsLab/Reduced-GOOP
- The published reformulation benchmark improvement is attributed to the
  formulation change alone; it does not establish real-time performance. The
  absolute 0.54 s benchmark is omitted. Later user-provided descriptions support
  real-time computation in the preliminary current-work overtaking example;
  no production latency or new timing figures are claimed.
- Polynomial growth describes the size of the optimality system, not a general
  polynomial-time solver guarantee. The research page distinguishes the quadratic
  equivalence result from the limitations of general nonlinear problems.
- The ongoing project targets real-time receding-horizon control of multiple
  robots with ordered objectives; it is explicitly labeled ongoing.

## Deferred document changes

The user requested résumé revisions be recorded for later. The downloadable
résumé and academic CV are exact copies of the existing PDFs; they were not
rewritten as part of this website task. Before publishing a revised résumé:

1. Add the direct CLeAR Lab link.
2. Revise the 5.09 s → 0.54 s bullet to emphasize formulation-only improvement,
   and reconsider including the absolute timings.
3. Add the original GOOP repository link above.

The academic CV also contains stronger real-time wording than the current
website text. Review that wording when the CV documents are next revised.

## Implementation and verification

- Preserved existing URLs and the Jekyll/Minimal Mistakes theme.
- Updated all five core pages, shared identity/contact metadata, and navigation.
- Added a single publication data file and reusable rendering include.
- Replaced missing manuscript download links with publisher/arXiv links.
- Retained the dormant blog and earlier research assets.
- Built successfully using Jekyll 3.10.0 in safe mode; checked generated internal
  links, anchors, document targets, publication counts, and stale affiliation text.
- Desktop homepage was visually inspected in Chrome. Mobile styling uses the
  existing responsive theme plus explicit single-column layouts; a separate
  mobile visual review remains recommended before publishing.

## Homepage style revision — November 6, 2026

User requested a lighter, more personal style based on the original About
introduction and these references:

- https://kh-ryu.github.io/ (primary style reference)
- https://sites.google.com/view/jingqi-li
- https://n00nspr1ng.github.io/

Replaced the slogan and opportunity banner with a short first-person introduction.
Moved the implementation summary into that introduction. Reduced type and spacing,
shortened the research cards, used Current work / Prior work labels and Read more
links, and removed the separate implementation section. Removed alternate
publication-version links and body links that repeat the main navigation; retained
links to specific research sections, papers, code, contact, and the academic CV.

## Advisor description incorporated — November 6, 2026

The user supplied the advisor's description of the ongoing GOOP research. Home,
About, and Research now distinguish compact reformulations that remove redundant
variables and constraints from the inexact Newton algorithm that omits high-order
derivative terms with a small, bounded effect on solution error. The September
2025 date refers to this ongoing research, not the August 2023 Ph.D. start.
Current simulations remain preliminary, and earlier formulation-only benchmark
limitations remain explicit. No convergence rate, numerical error bound, solver
frequency, or new publication status was inferred. Funding information was
omitted at the user's request.

## Terminology update — November 6, 2026

At the user's request, Home, About, and Research now use “Newton solver”
in place of “inexact Newton” terminology. The public descriptions omit the
high-order derivative approximation and solution-error details for now.

## Pre-publication recruiter review — November 6, 2026

Reviewed Home, About, Research, Publications, Experience, and CV/Resume.

Changes:
- Matched all three Home research cards to their destination sections. Current
  work now names highway overtaking and cooperative pot transfer; the third
  card describes mixed-hierarchy robot interaction rather than routing.
- Simplified the Home research introduction and removed generic closing
  sentences from Research. Preserved the user's Newton solver terminology,
  preliminary simulation label, figures, justified text, and benchmark caveat.
- Changed the Home document icon to open the one-page industry resume.
- Restored the missing reduced-GOOP entry under Preprints on Publications.
  All 10 entries in the publication data now appear on that page.
- Corrected the Experience role-line HTML entities, a missing article, and
  the overlapping/incomplete technical-method labels. Current solver work
  is consistent with Home, About, and Research.
- Excluded editable PowerPoint files and editor lock files from Jekyll output;
  original source assets remain in the repository.

Verification:
- Production safe-mode build generated in /private/tmp/dhl-website-prepublish
  to avoid concurrent local servers overwriting _site during verification.
- All six main production pages have correct public canonical URLs; all their
  internal links, anchors, image paths, and document targets resolve. No
  duplicate IDs, missing image alt attributes, or unrendered Liquid found.
- Verified current arXiv metadata for reduced GOOP, mixed-hierarchy games, and
  approximate GOOP; checked the CLeAR Lab profile and core GitHub repositories.
  Sources: https://arxiv.org/abs/2603.26950,
  https://arxiv.org/abs/2602.01568, https://arxiv.org/abs/2507.11021,
  https://clearoboticslab.github.io/people/Dongho_Lee/index.html.
- Publisher and LinkedIn endpoints sometimes reject automated requests. The
  AIAA 2022 DOI and approximate-GOOP IEEE identifier were corroborated by
  official KAIST/IP Paris research records; blocked responses were not treated
  as proof of broken links. Google Scholar full-content fetch returned 429;
  no citation metrics or claim of a full Scholar synchronization was added.
- Desktop Home and About were visually inspected in Chrome. A separate mobile
  visual check was not completed because the active browser kept changing
  during inspection. Existing responsive stacking rules were reviewed in CSS.

Before publication, the deferred resume fixes remain: direct CLeAR Lab and
original GOOP code links, and the formulation-only solve-time wording. The
PDFs were not modified. The portrait is about 2.3 MB; a smaller web copy would
be a useful later loading-speed improvement. No files were committed or pushed.

The isolated browser preview also revealed a missing favicon request. Added
a small SVG initials icon and an explicit favicon link in the shared head.

User correction: the third Home research card features hierarchical routing,
not mixed-hierarchy robot interaction. Its description and destination now
match the hierarchical-routing section.

## Industry resume updated — November 6, 2026

The user resumed the industry-resume revision after the website edits. All
three previously deferred corrections are now implemented: direct CLeAR Lab
link, formulation-only benchmark wording, and original GOOP code link. The
resume also includes the current Newton solver and preliminary simulations,
2027 internship availability, the personal website, and hierarchical routing.
The updated one-page PDF has replaced the local downloadable resume.

The resume uses the approximately 10x speedup supported by the four-agent,
four-level nonquadratic benchmark in Table 1, rather than the website's current
up-to-40x claim, which needs a separate benchmark reference. The academic CV
is unchanged. No commit or publication was performed.
