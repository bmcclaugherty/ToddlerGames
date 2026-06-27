# 🚗 Tappy Town — Toddler Touch Games

A collection of **14 touchscreen games** for toddlers, built as a single self-contained `index.html`. No build step, no external files, no internet required once loaded. Designed to run great on a **Tesla center touchscreen** (or any tablet/phone/browser).

All sounds are synthesized in-browser (Web Audio API) and all icons are emoji, so the whole thing is one file with zero assets to host.

## 🎮 The games

| | Game | What it does | Score? |
|---|------|--------------|:---:|
| 🫧 | Bubble Pop | Tap drifting bubbles to pop them | ✅ |
| 🎈 | Balloon Pop | Pop balloons floating up the screen | ✅ |
| 🐹 | Whack-a-Critter | Tap critters as they peek out | ✅ |
| ⭐ | Star Catcher | Catch falling stars | ✅ |
| 🎆 | Fireworks | Tap anywhere to launch fireworks | — |
| 🎹 | Piano | Pentatonic keys — every tap sounds nice | — |
| 🎨 | Finger Paint | Multi-touch painting, colors + rainbow + eraser | — |
| 🧠 | Memory Match | Flip-and-match pairs | ✅ |
| 🔷 | Shape Match | Tap the shape that matches | ✅ |
| 🌈 | Color Match | Tap the matching color | ✅ |
| 🔢 | Counting Fun | Count the items, hear the number | ✅ |
| 🐮 | Animal Friends | Tap an animal, hear its sound | — |
| 🟦 | Bubble Wrap | Endless poppable bubble wrap | ✅ |
| 👾 | Feed the Monster | Tap food to fly it into the monster | ✅ |

### Toddler-friendly touches
- **Hold-to-exit** 🏠 Home button (must press and hold ~¾ second, with a visible fill ring) so little hands can't accidentally leave a game.
- **No fail states, no scary sounds** — nothing punishes a mistake.
- **Big targets**, gentle audio, ⛶ fullscreen and 🔇 mute always in the header.

## 🌐 Deploy with GitHub Pages

1. Create a new GitHub repository (e.g. `tappy-town`).
2. Upload **`index.html`** and the empty **`.nojekyll`** file to the repo root.
   - `.nojekyll` tells GitHub not to run Jekyll, which can interfere with plain static files.
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source = Deploy from a branch**, **Branch = `main`** (or `master`), folder **`/ (root)`**, then **Save**.
5. Wait ~1 minute. Your game is live at:
   ```
   https://<your-username>.github.io/<repo-name>/
   ```

That URL is what you'll open on the Tesla.

> Tip: any static host works too (Netlify, Cloudflare Pages, Vercel) — just drop in `index.html`.

## 🚙 Using it on the Tesla

- The car must be **in Park** for the browser to be usable.
- Open the Tesla browser → go to your GitHub Pages URL.
- **Tap the screen once** when it loads — browsers block audio until the first touch, so the first tap "turns on" the sound.
- Tap **⛶** (top right) for **fullscreen**.
- To leave a game, **press and hold 🏠** until the ring fills.
- Add the URL to the Tesla browser **favorites** so it's one tap next time.

Works offline once the page has loaded (it's a single file with no network calls), but the Tesla browser may re-fetch it between sessions, so a quick reconnect to load it is ideal.

## 🛠️ Customizing

Everything lives in `index.html`. Each game is registered with a `defGame({...})` call inside the `<script>` block — search for `defGame(` to find them. To add a game, copy an existing block and supply your own `id`, `name`, `emoji`, `color`, optional `score: true` / `reset: true`, and a `mount(stage, api)` function. The shared helpers (`runCanvas`, `quizGame`, the `SFX` sound bank, and the `FX` particle overlay) are defined just above the games and are reusable.

Enjoy! 🎉
