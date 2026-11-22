<div align="center">

<img src="assets/logo-full.jpg" alt="NUCS Batch 4 logo" width="110">

# MONOLITH TEAM — Social Network Analyzer

**Understanding connections through data and graph theory**

[![Live site](https://img.shields.io/badge/Live%20site-open-4f8cff?style=for-the-badge)](https://jaurdet-marvin.github.io/monolith-by-kyse/)
![HTML5](https://img.shields.io/badge/HTML5-e44d26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-264de4?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-f7df1e?style=flat-square&logo=javascript&logoColor=black)
![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-222?style=flat-square&logo=github&logoColor=white)

### 🌐 Official website: https://jaurdet-marvin.github.io/monolith-by-kyse/

<img src="assets/og-image.jpg" alt="MONOLITH TEAM Social Network Analyzer" width="720">

</div>

---

## About

**MONOLITH TEAM** is a student team from the **National University of Computer Studies (NUCS), Batch 4**.
This website is our Social Network Analysis (SNA) project: an interactive graph where you can watch
**BFS, DFS and Dijkstra** run step by step, see real-world applications, read our 98-slide presentation,
and meet the team. It is plain **HTML + CSS + JavaScript** — no frameworks, no build step.

## Features

- **Login screen** with an animated HD video background
- **Algorithm visualizer** — BFS (queue), DFS (stack) and Dijkstra (priority queue) on a 10-person network, with play / step / auto controls and a live log
- **Real-world applications** — social media, recommendation systems, marketing, communication networks, cybersecurity
- **Slides viewer** — all 98 slides with Neon Mix transitions (glitch, iris portal, light sweep, cube, 3D slide, zoom, flip), autoplay, grid view and fullscreen
- **Case study & results** — degree centrality on the sample network (10 nodes · 15 edges · 3 algorithms · 5 applications)
- **Team section**, **Marvin Skill** (HTML / CSS / JS showcase) and a **Summary** of takeaways, value and future scope
- **Music player** with bars / wave visualiser, **English ⇄ Burmese** language switch, **dark / light** theme
- Responsive layout, reduced-motion support, SEO tags, social preview image and `sitemap.xml`

## Project structure

```
monolith-by-kyse/
├── index.html            ← page markup
├── css/
│   └── style.css         ← all styles and animations
├── js/
│   └── script.js         ← all behaviour: graph, algorithms, slides, music, login, i18n
├── assets/               ← images, 98 slides (WebP), videos, song, team photos, icons
├── 404.html  robots.txt  sitemap.xml  site.webmanifest  favicon.ico  apple-touch-icon.png
└── vercel.json  firebase.json  .firebaserc.example  .nojekyll  .gitignore
```

**Source code:** [`index.html`](index.html) · [`css/style.css`](css/style.css) · [`js/script.js`](js/script.js)

## Code highlights

### HTML — sections are plain markup; text is swapped by `data-i18n`
```html
<section id="results" class="wrap reveal">
  <h2 data-i18n="res_h">Results</h2>
  <div class="stats">
    <div class="st"><b data-count="10">0</b><span data-i18n="s1">People (nodes)</span></div>
    <div class="st"><b data-count="15">0</b><span data-i18n="s2">Friendships (edges)</span></div>
  </div>
</section>
```

### CSS — the slide frame's neon glow
```css
#slides .deck{animation:deckGlow 6s ease-in-out infinite}
@keyframes deckGlow{
  0%,100%{box-shadow:0 20px 60px -20px rgba(79,140,255,.55),0 0 34px -6px rgba(79,140,255,.45)}
  50%    {box-shadow:0 24px 70px -18px rgba(168,85,247,.6), 0 0 44px -4px rgba(168,85,247,.55)}
}
```

### JavaScript — the sample network and the algorithms (`js/script.js`)
```js
const E = [["A","B",4],["A","C",2],["B","D",5],["B","E",3],["C","E",6],["C","F",4],
           ["D","G",3],["E","G",2],["E","H",5],["F","H",3],["G","I",4],["G","J",6],
           ["H","J",2],["I","J",3],["D","E",7]];            // 10 people, 15 friendships

// BFS — visit neighbours level by level with a queue
const q = [s]; vis.add(s);
while (q.length) {
  const u = q.shift(); ord.push(u);
  for (const [v] of adj[u].sort()) if (!vis.has(v)) { vis.add(v); q.push(v); }
}

// Dijkstra — always settle the cheapest unvisited node
const pq = [[0, s]]; d[s] = 0;
while (pq.length) {
  pq.sort((a, b) => a[0] - b[0]);
  const [du, u] = pq.shift();
  if (done.has(u)) continue; done.add(u);
  for (const [v, w] of adj[u])
    if (du + w < d[v]) { d[v] = du + w; prev[v] = u; pq.push([d[v], v]); }
}
```

## Run locally

Double-click `index.html` (works offline), or serve the folder:

```bash
python3 -m http.server 8000      # then open http://localhost:8000
```

Keep the folder structure together — the page loads media from `assets/` by relative path.

## Deploy

| Host | How |
|---|---|
| **GitHub Pages** (official) | Settings → Pages → *Deploy from a branch* → `main` / `(root)` |
| **Vercel** | vercel.com/new → import this repo → Framework **Other**, output directory `.` |
| **Firebase Hosting** | `firebase use --add` then `firebase deploy --only hosting` |

**Google Search:** add the site in Google Search Console (URL prefix), verify with the HTML tag shown in the
`<head>` of `index.html`, submit `sitemap.xml`, then *Request indexing*.
If the final address changes, update it in `index.html`, `robots.txt` and `sitemap.xml`.

## Team

| Boys | Role | Girls | Role |
|---|---|---|---|
| Silent boy | Network Data | Polar | Introduction |
| Nway oo | Preprocessing | Noble | Fundamentals |
| Jassen | BFS & Dijkstra | Han | Centrality |
| Zaim | BFS & Dijkstra | Ni Nina | Shortest Path |
| Beau valor | Community Detection | Yuki | Centrality |
| Marvin | Visualization & Demo | Jeon Rhoda | Slides |
| Maevik | Visualization & Demo | Anglena | Data Collection |
| Yoko | Super Leader | Ki Ki | BFS & Dijkstra |

---

<div align="center">

© 2026 **MONOLITH TEAM** · National University of Computer Studies (NUCS) · Batch 4
Educational project — built with HTML, CSS and JavaScript.

</div>
