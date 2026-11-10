# Awesome_Math_Books — Catalog Quality & Integration Audit

**Date:** 2026-11-10. **Scope:** current `main` README and tracked-file inventory, not a full audit of external books or their hosts.
**Inspected revision:** `3ab4deb456d7b52a28cfefa5b52ebed9b850187e`.
**Disposition:** useful curated reading index; not a proof repository, endorsement, copyright license, or executable evidence source.

## Repository inventory

Three tracked files were found at the inspected revision: `README.md` (about 54 KB) and `kiselev_cover.jpg` / `kiselev_cover.png`. No Lean source, tests, package manifests, or repository-root LICENSE file were present. A missing LICENSE does **not** establish permission to redistribute the README, images, or linked works.

The README spans mathematics, machine learning, physics, probability, econometrics, optimization, information theory, signal processing, and history. A static Markdown-pattern scan extracted approximately 307 HTTP(S) Markdown hyperlinks (approximately 277 distinct destinations using that pattern). The number varies with Markdown parsing rules because the README includes malformed link constructs. **No HTTP availability check of all links was performed.** The index is heavily weighted toward Archive.org and includes publisher, merchant, university, Mega, and personal-host links. A link to a scan is not evidence of distribution rights.

## Findings & recommended fixes

| Finding | Evidence in current README | Recommended treatment |
| --- | --- | --- |
| Attribution ambiguity | Stars badge identifies `valeman/Awesome_Math_Books`; prose says “my translations” and “support my work” | Credit the upstream curator. If this repository is a mirror, describe it as such and keep first-person advertising attributed to its author rather than implying new authorship |
| Missing clear reuse license | No root LICENSE file in inspected tree | Establish README/text/image rights before adding a license; never assume linked book PDFs are covered |
| Invalid Markdown links | Entries numbered 173 and 175 contain nested `[https://...](...)` inside the link destination; entry 185 has a line-broken link | Repair the link syntax and validate rendered Markdown |
| Non-navigating / inconsistent navigation | `[Table of Contents]()`; navigation label `Probabiltity` | Use working local heading anchors, correct the typo, standardize category labels |
| Duplicate and near-duplicate entries | Higher Mathematics (Efimov–Demidovich), selected analytic geometry and limits texts recur | Deduplicate by normalized title+authors+edition; retain multiple legitimate editions as variants |
| Typos and source quality | “What is mathemarics,” “Challenhing,” “Algorirhmic,” “Optimiz(a)ion” and author spellings need correction | Normalize bibliographic metadata; verify editions and authors against primary sources |
| Unreviewed direct-download rights | Mixed Archive.org, Mega, direct PDF, and merchant links | Record `rights_status: unknown` by default; prefer author/publisher/institution landing pages; do not copy hosted material into this repo |
| Unverified promotional claims | Extensive marketing and historical popularity statements | Label claims as attributed or remove unsupported quantitative statements |
| Non-machine-readable data | More than two hundred mathematics entries exist in one README list | Optional later migration to a small curated YAML/CSV source with stable IDs, validated links, metadata and generated README; preserve original citations |

## Suggested selection rubric

Each future curated entry should include `id`, `title`, `authors`, `edition_or_year`, `subject`, `primary_source_url`, `secondary_url`, `rights_status`, `url_checked_at`, `last_reviewed_at`, and `curation_notes`. Unknown is a valid value; inventing licensing or availability is not.

Recommended prioritization: (1) primary/author/university publications with explicit rights, (2) texts closely connected to proof techniques, induction, divisibility, number theory and probability, (3) links with independently verified bibliographic identity, (4) source histories that can survive hostile review.

## Bounded integration into Math_Build1994

The target repository's proposed [reference integration](https://github.com/ryansctt1994-sudo/Math_Build1994) uses only bibliographic pointers and independently authored potential Lean proof tasks. It does not vendor books or modify Lean source. The catalog is **non-authoritative context**: `a book link != a theorem proof`; `a proof idea != a compiled Lean module`; `a compiled module != an independent reproduction`.

## Evidence and limitations

- **Observed:** files, catalog text, static link structures, navigation, repetition patterns, upstream attribution clues.
- **Not performed:** live validation of every external URL; legal clearance, examination of every linked edition, independent validation of promotional/history claims, or execution of new Lean builds.
- **Required for a verified curation pipeline:** syntax and duplicate checks in CI; separate asynchronous external-link checking with clear error classifications; human license/provenance review and recorded evidence.
