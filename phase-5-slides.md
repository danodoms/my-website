---
marp: true
paginate: true
backgroundColor: '#0a0a0a'
color: '#e6e6e6'
style: |
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700;800&display=swap');
  section {
    font-family: 'JetBrains Mono', ui-monospace, monospace;
    background: #0a0a0a;
    color: #e6e6e6;
    font-size: 26px;
    padding: 64px 78px;
    line-height: 1.65;
  }
  h1 { color: #ffffff; font-weight: 800; font-size: 46px; letter-spacing: -1px; margin: 0 0 16px; }
  h2 { color: #ffffff; font-weight: 700; font-size: 32px; }
  strong { color: #7ee787; }
  a { color: #7ee787; word-break: break-all; }
  ul, ol { line-height: 1.75; }
  code { background: #1a1a1a; color: #7ee787; padding: 2px 8px; border-radius: 4px; font-size: 0.86em; }
  pre { background: #121212; border: 1px solid #262626; border-radius: 12px; padding: 20px 24px; font-size: 0.9em; }
  pre code { background: transparent; color: #e6e6e6; padding: 0; }
  table { border-collapse: collapse; font-size: 0.9em; margin-top: 10px; }
  th, td { border: 1px solid #262626; padding: 10px 16px; text-align: left; }
  th { color: #7ee787; }
  .muted { color: #6f6f6f; font-size: 0.82em; }
  .tag { color: #7ee787; letter-spacing: 5px; text-transform: uppercase; font-size: 20px; margin: 0 0 6px; }
  section.lead { display: flex; flex-direction: column; justify-content: center; }
  section.lead h1 { font-size: 58px; }
  section::after { color: #4a4a4a; font-weight: 700; }
  section.dense { font-size: 20px; padding: 48px 60px; line-height: 1.55; }
  section.dense h1 { font-size: 36px; margin: 0 0 10px; }
  section.dense pre { font-size: 0.82em; padding: 14px 16px; }
  section.dense ul, section.dense ol { line-height: 1.5; }
---

<!-- _class: lead -->
<!-- _paginate: false -->

# Ship It

Host it, make it public-ready, and ship it for real.

---

# Outline

1. **Hosting** — what it means, then going live on Vercel
2. **The loop** — push a change, watch it deploy
3. **Public-ready** — favicon, title & description
4. **SEO & speed** — being found, and being fast
5. **The full story** — everything you built, end to end

<p class="muted">You have a site and a backend. Now you take it all the way to shipped.</p>

---

# Where you are

- Your site is **built** (frontend) and **remembers data** (Supabase backend)
- It lives on **GitHub**
- But it's not **hosted**, and not yet **polished** for the public

<p class="muted">A live URL plus a few finishing touches = a site you'd hand to a real client.</p>

---

# First — what "hosting" actually is

Right now your files sit on **your laptop** — nobody else can reach them. To go public, they need to live on a computer that's **always on**, ready to send your page to anyone who visits.

- That always-on computer is a **server**
- You rent space on one from a **hosting provider**
- People find it through your **domain** — your web address, like `acme.com`

<p class="muted">"Hosting" = putting your files on an always-on server so anyone can load them.</p>

---

# The traditional way (and its terms)

Without a tool like Vercel, going live means wiring up a few parts **yourself**:

- **Server** — rent one, then keep it running and updated
- **Domain + DNS** — buy a domain, then use **DNS** to point it at your server
- **Upload** — copy your files onto the server (often by **FTP**), by hand, every change

<p class="muted">It works — but it's manual, and you've basically become a part-time server admin.</p>

---

<!-- _class: dense -->

# Host it on Vercel

![bg right:42% fit](images/add-project.png)

**Vercel does all of that for you** — server, HTTPS, and a free URL, wired to your GitHub.

1. **Create an account** at **https://vercel.com** → **Continue with GitHub**
2. Click the **Add New…** dropdown (top right) → choose **Project**

<p class="muted">Signing in with GitHub lets Vercel see the repos you just pushed.</p>

---

<!-- _class: dense -->

# Import your repo

![bg right:42% fit](images/import-repo.png)

3. Find your site's repo in the list → click **Import**
4. **Leave every setting on its default** — don't change anything

<p class="muted">Vercel auto-detects a plain HTML site — no configuration needed.</p>

---

<!-- _class: dense -->

# Deploy → live

![bg right:42% fit](images/deploy.png)

5. Click the **Deploy** button
6. A few seconds later → your **live URL** 🎉

<p class="muted">No server to rent, no files to upload, no DNS to wire — Vercel handles it all, free.</p>

---

# The magic loop

The same git loop — now every push updates your **live** site:

```bash
git add .                    # gather
git commit -m "what I did"   # save
git push                     # upload → Vercel auto-deploys
```

<p class="muted">Change something → push → refresh your URL → it's live. That's the loop.</p>

---

<!-- _class: lead -->

<p class="tag">Now the polish</p>

# A live URL isn't "public-ready"

A few small touches make it look **professional** instead of unfinished.

---

<!-- _class: dense -->

# Favicon — the little tab icon

![bg right:42% fit](images/diagram-browser-tab.svg)

- The tiny icon in the **browser tab** and bookmarks
- No favicon = a generic, unfinished look
- Add a small image (`favicon.ico` or a PNG) + **one line** in `<head>`:

```html
<link rel="icon" href="favicon.png">
```

<p class="muted">Ask your AI: "add a favicon to my page using this image." Read the line it adds.</p>

---

<!-- _class: dense -->

# Metadata — title & description

What shows in the **browser tab** and in **Google results**:

```html
<title>Acme Inc. — Handmade Soy Candles</title>
<meta name="description" content="Hand-poured soy candles in small batches. Shop the collection.">
```

- **Title** — clear, says what you offer
- **Description** — one sentence that makes people click

<p class="muted">Without these, Google shows "index.html" and a random line of your page.</p>

---

# SEO — being found

**SEO = Search Engine Optimisation** — helping Google understand your page.

- A clear **title** + **description** (you just did these)
- Real **headings** (`<h1>`, `<h2>`) — not just big text
- **Alt text** on images — describes them for Google & screen readers

<p class="muted">You don't need tricks. Clear, well-labelled content is 90% of SEO.</p>

---

# Page speed — being fast

Speed isn't a nice-to-have — it's the experience:

- Users **leave** slow pages; Google **ranks** faster pages higher
- Biggest, easiest win: **shrink your images** (huge photos = slow load)
- **Don't guess — measure it** with a free tool called **Lighthouse** ↓

<p class="muted">Ask your AI: "are my images too large, and how do I compress them?"</p>

---

<!-- _class: dense -->

# Measure it with Lighthouse

**Install (once):** open the **Chrome Web Store**, search **"Lighthouse"** by Google → **Get** → **Add extension**.

**Run it on your live site:**

1. Open your **Vercel URL** in Chrome
2. Click the **Lighthouse** toolbar icon → **Generate report**
3. Read the four scores — **Performance · Accessibility · Best Practices · SEO**, each out of 100

<p class="muted">🟢 90–100 good · 🟠 50–89 improve · 🔴 0–49 fix. The report also lists exactly what to change. (Lighthouse is also built into Chrome DevTools → F12.)</p>

---

# Check on mobile

- Most visitors are on a **phone**, not a laptop
- Open your live URL on your phone — does it look right?
- Or in the browser: **DevTools → device toolbar** (`Ctrl/Cmd + Shift + M`)
- Fix anything squashed or overflowing with your AI

<p class="muted">A site that breaks on mobile isn't public-ready — no matter how good the desktop looks.</p>

---

# The public-ready checklist

- [ ] **Live** on Vercel · a push auto-deploys
- [ ] **Favicon** shows in the tab
- [ ] **Title + description** set
- [ ] Headings + **alt text** in place
- [ ] Images **compressed** · loads fast
- [ ] Looks right on **mobile**

<p class="muted">Tick all six and you've shipped something you'd give a real client.</p>

---

<!-- _class: dense -->

# The full story — end to end

Open your **live URL** — here's everything behind it, and you can explain each step:

1. **Designed** it in Figma
2. Turned it into **code** with AI — *and you can explain it*
3. Saved it with **git** → **GitHub**
4. Gave it a **backend** (Supabase) + used an **API**
5. **Hosted** it on Vercel + made it **public-ready**

<p class="muted">That's the whole modern web workflow — design → code → version control → backend → host — start to finish.</p>

---

<!-- _class: lead -->

<p class="tag">Done when</p>

# Shipped · public-ready · yours

Your site is live, polished, works on mobile — and you can explain every part.

---

# All the links

| Tool | Link |
|---|---|
| Vercel | https://vercel.com |
| GitHub | https://github.com |
| Cursor | https://cursor.com |
| AI · Claude | https://claude.ai |

<p class="muted">You've now done the whole process, end to end. That's the job.</p>
