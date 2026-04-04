# MSI Situation Report — Dispatch Guide
> **For AI assistants:** Read this file at the start of every session before doing any work on dispatch content. It is the single source of truth for this project's structure, rules, and current status.

---

## 1. What This Project Is

The **MSI Situation Report** is the editorial dispatch of Molay Satrya Indonesia (MSI) Group. It is a regularly updated publication — not weekly, not on a fixed schedule. Articles are published when ready.

Each article follows the **SitRep format**:
- **Section I / The Intel** — 70% of the article. Context, history, research. Never sales language.
- **Section II / Primary Response** — The lead MSI brand responding to the Intel.
- **Section III / Secondary Deployment** — One or two supporting MSI brands tied to the same theme.
- **The Command Statement** — One closing paragraph linking all disciplines.
- Closes with: **CUSTODI SERVIENTEM.**

For full editorial rules, tone, and CTA language → read `THE MSI DISPATCH_ EDITORIAL BRIEF.docx`.

---

## 2. Folder Structure

```
MSI News Article Dispatch/
│
├── published/                          ← LIVE articles. Do not move unless told to.
│   ├── MSI_SitRep_2026-03-31_UrbanJungle_CustomerEdition.docx
│   └── MSI_SitRep_2026-04-04_CommandDistrict_CustomerEdition.docx
│
├── drafts/                             ← NOT deployed. Awaiting approval from Arie Setya.
│   ├── MSI_SitRep_2026-04-07_ArchipelagoSound_CustomerEdition.docx
│   └── MSI_SitRep_2026-03-31_LastWatch_FounderEdition.docx
│
├── index.html                          ← Archive/listing page. Source of truth for status.
├── MSI_SitRep_ArticlePage_Mockup.html  ← HTML preview: Urban Jungle (published)
├── MSI_SitRep_2026-04-04_CommandDistrict_ArticlePage.html  ← HTML preview: Command District (published)
├── GSH_SitRep_ArticlePage_Mockup.html  ← HTML preview: Archipelago Sound (draft — HTML exists but article is draft)
├── MSI_2026-03-31_UrbanJungle_Carousel.html
├── MSI_Instagram_Carousel_Mockup.html
├── GSH_Instagram_Carousel_Mockup.html
├── THE MSI DISPATCH_ EDITORIAL BRIEF.docx
└── DISPATCH_GUIDE.md                   ← This file.
```

---

## 3. File Naming Convention

All article files use **date-based** naming. Never use "Week 01" or "W01" format.

```
MSI_SitRep_YYYY-MM-DD_[ThemeName]_[EditionType].docx
```

**Edition types:**
- `CustomerEdition` — Standard English editorial (most articles)
- `FounderEdition` — Personal statement from Arie Setya (Bahasa Indonesia)

---

## 4. Current Article Status

| Date | Title | Language | Status | HTML Preview |
|---|---|---|---|---|
| 2026-03-31 | The Invisible Operator (Urban Jungle) | English | **PUBLISHED** | ✅ MSI_SitRep_ArticlePage_Mockup.html |
| 2026-04-04 | The Command District (Kebayoran Baru) | Bahasa Indonesia | **PUBLISHED** | ✅ MSI_SitRep_2026-04-04_CommandDistrict_ArticlePage.html |
| 2026-04-07 | The Archipelago Sound (GSH / Blues) | English | **DRAFT** | ✅ GSH_SitRep_ArticlePage_Mockup.html (but not deployed) |
| 2026-03-31 | The Last Watch (Kontingen Garuda) | Bahasa Indonesia | **DRAFT** | ❌ Not yet built |

---

## 5. Rules for AI Assistants

### DO:
- Always check this file before starting any dispatch work.
- Check `index.html` to understand which articles are published vs. draft.
- Use date-based filenames (`YYYY-MM-DD`) for all new articles.
- Follow the 70/30 Intel/Product split strictly.
- Match the brand voice in `CLAUDE.md` (parent directory) for each brand.
- Write **Customer Editions** in English; **Founder Editions** in Bahasa Indonesia.
- Place new drafts in `drafts/` until Arie Setya explicitly says to publish.
- When publishing a draft: move the docx from `drafts/` → `published/`, update `index.html` card status badge from `draft` to `published`, and move it above the `<!-- DRAFTS -->` section divider.

### DO NOT:
- Move any file from `drafts/` to `published/` without explicit instruction from Arie Setya.
- Use "WEEK 01", "W01", or any week-format references anywhere.
- Use "THE MSI WEEKLY DISPATCH" — it is now "THE MSI DISPATCH" or "THE MSI SITUATION REPORT".
- Use sales language: "Promo", "Discount", "Limited Time". Use: "Procurement", "Limited Issue", "Active Deployment".
- Mention products without at least 70% contextual Intel first.

### When adding a new article:
1. Create the `.docx` file in `drafts/` with date-format name.
2. Add a new card to `index.html` under the `<!-- DRAFTS -->` section with `class="edition-card draft"` and `<span class="status-badge draft">◌ Draft</span>`.
3. Update the Published/Draft/Total stats in the archive hero section.
4. Do NOT build the HTML article page mockup unless specifically requested.

### When publishing a draft (Arie Setya authorises):
1. Move docx from `drafts/` → `published/`.
2. In `index.html`: change `class="edition-card draft"` → `class="edition-card clickable"`, change badge from `draft` to `published`, move card above the Drafts divider.
3. Update the stats (Published count +1, Draft count -1).
4. Build HTML article page mockup if requested.
5. Remind Arie to run `git add . && git commit -m "Publish: [article name]" && git push`.

---

## 6. GitHub Repository

Remote: `https://github.com/ariesetya-hub/msi-dispatch`

**Push commands (run from this folder in Terminal):**
```bash
git add .
git commit -m "Describe what changed"
git push
```

---

## 7. Brand Voice Quick Reference

| Brand | Persona | Tone |
|---|---|---|
| MSI Group | Visionary Commander | Institutional, strategic, macro |
| Molay Tactical | Tier-One Operator | Elite, authoritative, technically precise |
| Askeer Tactical | Ambitious Cadet | Hungry, practical, accessible |
| The Gunslinger's Hop | Stoic Veteran meets Blues Legend | Refined, soulful, exclusive |
| Defensa Coffee | Trusted Quartermaster | Welcoming, rugged, grounded |
| Reclaimed by Molay | Master Craftsman / Archivist | Weighty, artisanal, historical |
| Taru Baby Gear | Guardian / Protector Father | Protective, reliable, proud |

Full brand voice details → `CLAUDE.md` in parent `.claude` directory.

---

*Last updated: 04 April 2026 by Claude (Cowork session) — Command District HTML article page built and linked.*
