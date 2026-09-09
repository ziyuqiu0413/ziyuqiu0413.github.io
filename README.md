# Ziyu Qiu 邱子吁 — scholarly page

A four-page static site. No build step, no dependencies: open the `.html` files in a
browser, or upload the whole folder to any web host.

```
index.html        首頁  Home
education.html    學歷  Educational Background
research.html     研究  Research Interests
works.html        著述  Works & Publications
assets/css/style.css
assets/img/portrait.jpg     (from Desktop/"Qiu,Ziyu pic.jpg", resized)
assets/img/landscape.jpg    (from Desktop/清 弘旿秋山紅樹圖軸.jpg, resized)
.claude/launch.json         local preview config, not needed for hosting
```

## Previewing locally

```bash
cd ~/work/personalwebsite && python3 -m http.server 8777
```

Then open <http://localhost:8777>. (Opening `index.html` by double-clicking also works.)

## Editing

Everything is plain HTML. The patterns you'll reuse:

**Add a publication or paper** — copy one `<li class="entry">` block in `works.html`:

```html
<li class="entry">
  <div class="entry__date">June 2027</div>
  <div>
    <p class="entry__title">“Title of the paper”<span class="tag">Forthcoming</span></p>
    <p class="entry__where">Journal or conference name</p>
    <p class="entry__note">Optional one-line note.</p>
  </div>
</li>
```

The `<span class="tag">` is the small outlined label (Accepted, Best Paper, Published).
Drop it if you don't need one. Wrap titles of books and theses in `<cite>` for italics,
and Chinese in `<span class="han">` so it picks up the Songti face.

**Change a colour or the type size** — every value lives in the `:root` block at the top
of `assets/css/style.css`. `--seal` is the cinnabar accent; `--paper` and `--ink` are the
two grounds.

**Traditional → simplified characters** — the navigation and section labels use
traditional forms (首頁, 學歷, 研究, 著述, 領域…) to suit the period you work on. Search
and replace in the four HTML files if you'd rather have simplified.

## Hosting

Any of these will take the folder as-is:

- **GitHub Pages** — create a repo, push these files, enable Pages on the `main` branch.
- **Netlify / Cloudflare Pages** — drag the folder onto their dashboard.
- **Harvard** — `scholar.harvard.edu` gives you a hosted page instead; if you use it,
  this site is still useful as a standalone at a custom domain.

## Notes on the content

Drawn from `Desktop/Ziyu Qiu_CV_2025 .docx` and the AAS 2026 abstract in
`Desktop/MA Thesis/`. A few editorial decisions worth checking:

- **Standing:** the site presents you as a Ph.D. student in History and East Asian
  Languages (entered 2026, advisor Mark C. Elliott), with the M.A. listed as completed in
  May 2026. The CV predates both.
- **Contact:** only the FAS email is published. Phone number and office address are
  deliberately left off the public page.
- **The bio and project descriptions are my drafts**, paraphrased from your own abstract
  and thesis titles. Read them as your own voice or rewrite — this is the part most worth
  putting in your own words.
- **The painting** is 弘旿 (1743–1811), 《秋山紅樹圖軸》, long out of copyright. If the
  file came from a museum with its own image terms, check those before publishing.
