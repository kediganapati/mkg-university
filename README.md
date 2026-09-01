# MKG Digital University — Hugo Starter Site

Ye starter site **Hugo** (static site generator) se bani hai aur **GitHub Pages** par free host hogi. Content sirf **English** me likhna hai — website me lagi **Google Translate widget** visitors ke liye automatically 100+ languages me translate kar degi (header ke top-right corner me dropdown).

---

## 📁 Structure Samjho

```
mkg-university/
├── hugo.toml                  ← Site settings + menu + sidebar widgets (yaha sabse zyada edit karoge)
├── content/                   ← Saara content English me
│   ├── _index.md              ← Homepage
│   ├── about.md
│   ├── research/
│   ├── courses/
│   ├── glossary/
│   ├── kedi/
│   ├── contact/
│   └── dharma-spirituality/
│       └── sample-article.md  ← Naya article isi tarah banao
├── layouts/                   ← HTML templates (design). Inko chhedo tabhi jab design badalna ho.
├── static/
│   ├── css/style.css          ← Saara styling (colors, fonts, spacing) yahi ek file me hai
│   └── images/                ← Hero image yahan daalo
└── .github/workflows/hugo.yml ← Auto-deploy script, isse chhedne ki zaroorat nahi
```

**Language:** Site sirf English me likhi jayegi. Header me lagi Google Translate widget visitors ko unki apni language me automatically dikha degi — tumhe kuch alag se translate karke likhne ki zaroorat nahi.

---

## 🚀 Pehli Baar Setup (One-Time)

1. **GitHub par naya repository banao** — naam kuch bhi rakh sakte ho (jaise `mkg-university`).
2. Ye saari files us repository me upload/push karo.
3. Repository ke **Settings → Pages** me jao → **Source** me "**GitHub Actions**" select karo (branch select mat karna, Actions workflow already ban chuka hai).
4. **Settings → Pages → Custom domain** me likho: `www.mkgdigitaluniversity.com`
5. Apne domain registrar (jaha domain khareeda tha) ke DNS settings me ye records add karo:
   - `CNAME` record: `www` → `<your-github-username>.github.io`
   - (Agar root domain `mkgdigitaluniversity.com` bhi chahiye bina www ke, to registrar ke docs check karo — GitHub Pages A-records bhi support karta hai)
6. Kuch minute me site live ho jayegi: `https://www.mkgdigitaluniversity.com`

Jab bhi tum `main` branch par kuch push karoge, GitHub Actions automatically site build aur deploy kar dega — tumhe kuch manually karne ki zaroorat nahi.

---

## ✍️ Naya Article Kaise Likhein

1. `content/en/dharma-spirituality/` folder me jao (ya jo bhi category ho).
2. `sample-article.md` ko copy karo, naam badlo (jaise `kaliyuga-and-satan.md`).
3. Top par ye likha hoga:
   ```yaml
   ---
   title: "Tumhara Article Title"
   date: 2026-08-26
   categories: ["Dharma & Spirituality"]
   ---
   ```
4. Iske neeche Markdown me apna content likho.
5. Commit + push karo → site automatically update ho jayegi. Translate widget khud visitor ki language handle kar legi.

---

## 💻 Local Par Preview Kaise Dekhein (Optional)

Agar apne computer par Hugo install karke changes turant dekhna chahte ho (publish karne se pehle):

```bash
hugo server
```

Fir browser me `http://localhost:1313` kholo. Ye sirf local preview hai — asli site tabhi update hogi jab GitHub par push karoge.

---

## 🔍 SEO Tip

Blogger se migrate karte waqt purane URLs (jaise `/p/about.html`) ke liye redirects zaroor banao, taaki Google search rankings na girein. `static/_redirects` ya meta-refresh pages se ye ho sakta hai — agar madad chahiye to pooch lena.
