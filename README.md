<div align="center">

# 🎂 The Memory Vault

### A cinematic, five-act interactive birthday experience

Beautiful enough for a premiere, personal enough to feel hand-made. Guests arrive at a moody hero screen, solve a passphrase to unlock the vault, and uncover one heartfelt message after another — ending in a confetti-lit finale.

**React 19 · Framer Motion · Tailwind CSS** — no backend, no database, no accounts. Just one file to edit and a story to tell.

</div>

---

## ✨ Highlights

- 🎬 **Five cinematic acts** — Arrival → Vault → Countdown → Inbox → Finale
- 🔐 **Passphrase gate** — a soft, blurred lock screen that shakes on a wrong guess
- 💬 **Typewriter wishes** — each message reveals itself letter by letter, Apple-style shared layout transforms, live unread counter
- 🎆 **Canvas confetti** — 260 multi-shape particles with gravity and rotation
- ☁️ **Cloud diffusion & ambient motes** — drifting blurred layers throughout every scene
- 🔊 **Cinematic sound design** — unlock, whoosh, chime, boom, ambient bed (mute toggle included)
- 🖼️ **Photo-ready** — drop in a photo per well-wisher or use the elegant placeholder cards
- 📱 **Fully responsive** — separate portrait/landscape hero art, tuned for phones
- ⚙️ **One-file config** — reskin the whole thing for anyone, in minutes

---

## 🎬 The Journey

| Act | Scene | What happens |
| --- | --- | --- |
| **I** | **Arrival** | Ken-burns hero shot, ambient motes, layered serif title reveal |
| **II** | **Vault** | A blurred password panel emerges from the dark — wrong guesses shake |
| **III** | **Countdown** | Giant serif numerals 3 · 2 · 1 dissolve into a shimmering *"Nineteen."* |
| **IV** | **Inbox** | Notifications cascade in; each wish opens a shared-layout message viewer |
| **V** | **Finale** | *"19 Years." → "Countless Memories." → "Happy Birthday…"* then back home |

---

## 🚀 Quick Start

> Uses [yarn 1](https://classic.yarnpkg.com) — the lockfile includes a package that `npm` refuses, so yarn is required.

```bash
cd frontend
yarn install
yarn start
```

Open **[http://localhost:3000](http://localhost:3000)** — it hot-reloads as you customize.

Production build:

```bash
yarn build
```

---

## 🎨 Make It Yours

Everything worth editing lives in **`frontend/src/config.js`**. Save → the page reloads.

```js
export const HERO_NAME = "Racksheetth";          // name in the hero + finale
export const AGE       = 19;                     // "19 Years." in the finale

export const HERO_IMAGE        = "/assets/hero-horizontal.png";   // desktop hero
export const HERO_IMAGE_MOBILE = "/assets/hero-vertical.png";     // phone / portrait

export const PASSWORD = "GEBURTSTAG";            // vault passphrase
export const HINT     = "Birthday in German";    // hint shown on the lock screen

export const WISHES = [
  {
    senderName: "Wisher One",
    body: `Replace this with the first wish.\n\nBlank lines make new paragraphs.`,
    photo: null,                                  // or "/assets/wishers/wisher1.jpg"
  },
  // ... add as many as you like
];
```

### Step by step

1. **Say whose birthday** — set `HERO_NAME` and `AGE`.
2. **Drop in hero art** — replace `public/assets/hero-horizontal.png` (landscape) and `hero-vertical.png` (portrait).
3. **Pick a passphrase** — set `PASSWORD` (case-insensitive) and a `HINT`.
4. **Add well-wishers** — one `WISHES` entry each. Paste a photo in `public/assets/wishers/` and point `photo` at it, or set `photo: null` for the placeholder card.
5. **Tune the audio** — files live in `public/assets/audio/`:
   - `unlock.mp3` — vault unlock
   - `whoosh.mp3` — scene transitions
   - `chime.mp3` — new wish
   - `boom.mp3` — countdown beat
   - `celebrate.mp3` — finale burst
   - `ambient.mp3` — inbox ambience

> Want the credit line in the corner changed? It reads *"created by Caleb EJ"* and lives in `frontend/src/components/Hero.jsx`.

---

## 🗂 Project Structure

```
frontend/
├── public/
│   ├── index.html              # app shell
│   └── assets/
│       ├── hero-horizontal.png # desktop hero art
│       ├── hero-vertical.png   # mobile hero art
│       └── audio/              # unlock, whoosh, chime, boom, celebrate, ambient
└── src/
    ├── App.js                  # act state machine (5 acts)
    ├── config.js               # ⭐ edit this to reskin the experience
    ├── data/wishes.js          # derives wishes from config
    ├── lib/
    │   ├── sound.js            # minimal fade/loop audio engine
    │   └── numberToWords.js    # "Nineteen" for the finale
    └── components/
        ├── Hero.jsx            # Act I — arrival
        ├── Vault.jsx           # Act II — passphrase gate
        ├── Countdown.jsx       # Act III — 3…2…1
        ├── Inbox.jsx           # Act IV — notification center
        ├── MessageViewer.jsx   # Act IV — shared-layout wish viewer
        ├── Finale.jsx          # Act V — "19 Years."
        ├── Clouds.jsx          # drifting diffusion layers
        ├── Particles.jsx       # ambient motes
        ├── Confetti.jsx        # canvas confetti burst
        ├── UnreadCapsule.jsx   # the capsule you click to begin
        └── MuteToggle.jsx      # sound on/off
```

---

## 🛠 Tech Stack

| | |
| --- | --- |
| ⚛️ **React 19** | UI library |
| 🎞 **Framer Motion** | layout + entrance animations |
| 💨 **Tailwind CSS 3** | styling, via CRACO |
| ⛓ **TanStack Query** | query client (ready for real data) |
| ⚙️ **CRACO** | build configuration on Create React App |

---

## ☁️ Deploy

It's a fully static build — host it anywhere.

```bash
yarn build   # outputs to frontend/build
```

Upload that folder to **Netlify**, **Vercel**, **GitHub Pages**, or your own server. No env vars, no backend, no database required.

---

## 📄 License

No License for this...but please don't plagiarize this
