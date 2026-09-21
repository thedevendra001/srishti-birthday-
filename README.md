# Srishti's Birthday Surprise 🎂

A mobile-first interactive birthday microsite. Plain HTML + CSS + JavaScript, no build step, no frameworks.

## Folder structure

```
srishti-birthday/
├── index.html
├── README.md
├── css/
│   └── style.css
├── js/
│   └── script.js          ← captions + file names live at the top
└── assets/
    ├── photos/            ← put photo-01 … photo-05 here
    └── audio/             ← put birthday-song.mp3 here
```

## 1. Photos (already added ✅)

Srishti's 5 photos are already in `assets/photos/` (trimmed, resized and renamed). To swap any of them, replace the file and keep the same name. Details:

Put 5 photos in `assets/photos/` and name them exactly:

```
photo-01.jpg   (PHOTO_01)
photo-02.jpg   (PHOTO_02)
photo-03.jpg   (PHOTO_03)
photo-04.jpg   (PHOTO_04)
photo-05.jpg   (PHOTO_05)
```

- `.jpg`, `.jpeg`, `.png` and `.webp` all work. Just keep the `photo-0X` part.
- Any shape works. Portrait, landscape or square photos keep their real proportions, so faces are never stretched.
- **Shrink them first.** Phone photos are 3–8 MB each and will load slowly on mobile data. Aim for about 1200 px on the long side and under 400 KB each (squoosh.app is free and takes a minute).
- `photo-01` is also the big circular photo in the "dreams" scene, so pick your favourite as number 1.
- Missing photos show a pink "PHOTO_0X" placeholder, so you can test before you have them.
- To change the handwritten caption under each polaroid, edit `CONFIG.photos` at the top of `js/script.js`.

## 2. Music (already added ✅)

`assets/audio/birthday-song.mp3` is an original, copyright-free music-box arrangement of the traditional "Happy Birthday" tune (about 1 minute, loops). To use a different song instead, replace that file. Details:

1. Choose a song you have the right to use (your own recording, a royalty-free track, or a licensed one). Nothing copyrighted is included.
2. Rename it **`birthday-song.mp3`** and put it in `assets/audio/`.
3. Keep it under about 5 MB (128 kbps is plenty).

Music starts when she taps **OPEN IT**. It dips during the emotional message, swells through the countdown and peaks at the reveal. She can mute it with the speaker button (top right).

If no MP3 is found, a soft built-in music-box loop plays instead. If you want a different file name, change `CONFIG.music` in `js/script.js`.

## 3. Run it locally

**Quickest:** double-click `index.html`. It opens in your browser.

**Better (also lets you test on your phone):**

```bash
cd srishti-birthday
python3 -m http.server 8000
```

Then open `http://localhost:8000`. To test on your phone, join the same Wi-Fi and open `http://<your-computer-IP>:8000`. (VS Code's "Live Server" extension works too.)

**Jump to any scene while testing:** add `?scene=1` to `9` to the address, for example `http://localhost:8000/?scene=5` for the photos.

## 4. Put it online and send her the link

The whole folder is a static site, so any static host works. The easiest options:

**Netlify Drop (about 1 minute, no account needed to start)**
1. Go to **app.netlify.com/drop**.
2. Drag the whole `srishti-birthday` folder onto the page.
3. You get a link like `random-name.netlify.app`. In Site settings you can rename it to something like `srishti-birthday`.

**GitHub Pages (free)**
1. Create a new public repository and upload everything in the folder, with `index.html` at the top level.
2. Go to Settings → Pages → Deploy from a branch → `main` / root → Save.
3. After a minute your link is `https://<username>.github.io/<repo-name>/`.

**Cloudflare Pages or Vercel:** create a project, upload the folder, and deploy. No build command is needed and the output directory is the root.

**Before you send it:**
- Open the live link on your own phone once and tap through it with sound on.
- Send the link on WhatsApp or Instagram and ask her to open it on her phone with sound on. The link preview only says "You have a new notification 🔔", so the surprise stays intact.
- The music won't play if her iPhone is on silent mode with some browsers. The opening screen asks her to turn her sound on.

## Customising

| What | Where |
|---|---|
| Photo captions, photo file names, music file name | top of `js/script.js` (`CONFIG`) |
| Any on-screen wording | `index.html` |
| Colours, fonts | top of `css/style.css` (`:root`) |
| Timing of a scene | the `wait(...)` numbers inside that scene's function in `js/script.js` |

## Notes

- Works on current Android Chrome, iPhone Safari and desktop browsers. On desktop it shows inside a phone-shaped frame.
- Fonts (Bricolage Grotesque and Instrument Serif) load from Google Fonts. Offline, it falls back to system fonts.
- It respects "reduce motion" settings and uses only lightweight animation.
- Tapping empty space anywhere sends up a few little hearts. 💖
