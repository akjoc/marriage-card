# 💌 Animesh & Dakshita — Interactive Wedding Invitation

An elegant, mobile-first digital wedding invitation web application featuring royal Indian aesthetics, fluid animations, ambient music, an interactive scratch-to-reveal card, and a real-time countdown timer.

Built purely with vanilla **HTML5**, **CSS3**, and **JavaScript** — lightweight, fast, zero runtime dependencies, and fully responsive across smartphones, tablets, and desktop displays.

---

## ✨ Features

- **💌 Interactive Envelope Opening:**
  - Realistic 3D-style folded envelope with wax seal (`A+D`).
  - Smooth flap unseal animation that unlocks the invitation and scroll controls.
  - User gesture triggers background audio playback seamlessly in compliance with browser autoplay policies.

- **🎵 Ambient Background Music:**
  - Plays traditional celebratory music (*Din Shagna Da*).
  - Floating, non-intrusive audio control button with pulse animation and dynamic play/pause icons.

- **✨ Interactive Gold Scratch Card:**
  - HTML5 Canvas-powered interactive scratch-off gold foil texture with metallic sheen and shimmer animation.
  - Scratching reveals the wedding ceremony date.
  - Automatically completes revelation when over 50% is scratched.
  - Accessible fallback reveal button for convenience.

- **⏳ Real-Time Countdown Timer:**
  - Dynamically calculates remaining Days, Hours, Minutes, and Seconds until the main wedding auspicious moment.
  - Gracefully slides into view once the date is revealed.

- **🌸 Ambient Petal Fall Animation:**
  - Lightweight DOM-based falling rose and marigold petals drifting gently across the screen with randomized trajectories and speeds.

- **📜 Illustrated Celebration Timeline ("A Week of Joy"):**
  - Themed cards for each ceremony: **Haldi**, **Sangeet**, **Gaudev**, **Saptapadi**, and **Varmala**.
  - Custom inline SVG illustrations with adaptable palettes for groom and bride attire matching the mood of each ceremony.
  - Event details including dates, timings, venues, and descriptions.

- **📍 Venue & Navigation:**
  - Responsive Google Maps embed for The Sage & Marigold Estate, Amer Road, Jaipur.
  - One-click **"Get Directions"** button linking directly to Google Maps turn-by-turn navigation.

- **♿ Accessibility & Performance:**
  - Full respect for `prefers-reduced-motion` (disables heavy particle effects and auto-reveals hidden scratch content).
  - Semantic HTML tags, clear ARIA labels (`aria-pressed`, `aria-label`), and visible focus rings.
  - Zero heavy external libraries or frameworks — loads instantaneously.

---

## 🎨 Color Palette & Typography

### Design Tokens

| Variable | Color Name | Hex Code | Purpose |
| :--- | :--- | :--- | :--- |
| `--sindoor` | Sindoor Red | `#A23B4E` | Primary accent, headings, badges |
| `--marigold` | Marigold Gold | `#E3A039` | Haldi accents, envelope seal, CTA buttons |
| `--sage` | Sage Green | `#DCE7D6` | Ambient stage backdrop, serene secondary tone |
| `--sage-deep`| Deep Sage | `#AFC6A5` | Envelope gradients, foliage ornaments |
| `--ivory` | Warm Ivory | `#FBF5EC` | Invitation card background, clean paper texture |
| `--blush` | Soft Blush | `#F3C6CE` | Falling petals, ambient radial accents |
| `--ink` | Deep Sepia Ink| `#3A2E26` | High-contrast readable body typography |

### Typography

- **Display / Headings:** [Fraunces](https://fonts.google.com/specimen/Fraunces) (Sophisticated high-contrast variable serif)
- **Calligraphy / Script:** [WindSong](https://fonts.google.com/specimen/WindSong) (Expressive cursive script for couple names & accents)
- **Body & Metadata:** [Jost](https://fonts.google.com/specimen/Jost) (Clean, modern geometric sans-serif)

---

## 📂 Project Structure

```text
public_html/
├── index.html               # Main invitation page (markup, CSS styles, & JS logic)
├── music/
│   └── din-shagna-da.mp3    # Background audio track
└── README.md                # Project documentation
```

---

## 🚀 Getting Started

No compilation, transpilation, or package installation is required.

### 1. View Directly in Browser
Simply double-click [`index.html`](file:///c:/Users/Aman/Downloads/public_html/index.html) or right-click and choose **Open With > Google Chrome / Safari / Edge / Firefox**.

### 2. Run with a Local Web Server (Recommended)
Running through an HTTP server ensures audio files, external fonts, and iframe embeds load without local file restriction warnings.

#### Using Python (built-in):
```bash
# Python 3.x
python -m http.server 8000
```
Then visit: `http://localhost:8000`

#### Using Node.js:
```bash
npx serve .
# or
npx http-server .
```

#### Using VS Code:
Install the **Live Server** extension, right-click [`index.html`](file:///c:/Users/Aman/Downloads/public_html/index.html), and select **"Open with Live Server"**.

---

## 🛠️ Customization Guide

All configuration resides in [`index.html`](file:///c:/Users/Aman/Downloads/public_html/index.html). Here is how to personalize it:

### 1. Couple & Family Names
Search for `.names` and `.parents` around line 429:
```html
<h1 class="names">Animesh<span class="amp">&amp;</span>Dakshita</h1>
<p class="parents">
  S/o Mr. [Groom's Father] &amp; Mrs. [Groom's Mother]<br>
  D/o Mr. [Bride's Father] &amp; Mrs. [Bride's Mother]
</p>
```
Also update the envelope monogram seal (line 402):
```html
<div class="envelope-seal">A+D</div>
```

### 2. Wedding Date & Countdown Target
- **Scratch Card Date Display** (line 441):
  ```html
  <span class="scratch-value">20th November 2026</span>
  ```
- **Countdown JavaScript Target** (line 670):
  ```javascript
  // Set in ISO 8601 format with timezone offset:
  const target = new Date('2026-11-20T10:00:00+05:30').getTime();
  ```

### 3. Events & Schedule
Ceremony cards are structured inside `<section class="panel panel--events">`. You can edit dates, timings, venues, and descriptions for each:
- `Haldi` (line 461)
- `Sangeet` (line 485)
- `Gaudev` (line 511)
- `Saptapadi` (line 532)
- `Varmala` (line 556)

### 4. Venue & Directions Link
Update the Google Maps iframe source and directions link around line 602:
```html
<div class="map-embed">
  <iframe title="Venue location map" src="https://www.google.com/maps?q=YOUR_VENUE_LOCATION&output=embed"></iframe>
</div>
<a class="btn-directions" href="https://www.google.com/maps/dir/?api=1&destination=YOUR_VENUE_LOCATION" target="_blank" rel="noopener">
  Get Directions
</a>
```

### 5. Background Audio
Replace `music/din-shagna-da.mp3` with your preferred `.mp3` track, or change the `<source>` tag in `index.html`:
```html
<audio id="bgMusic" loop preload="none">
  <source src="music/your-audio-track.mp3" type="audio/mpeg">
</audio>
```

### 6. Event Hashtag & Footer Note
Modify the footer tags around line 609:
```html
<p class="footer-hash">#ANIDAKSHI2026</p>
<p class="footer-note">Made with love, for the ones we love most.</p>
```

---

## 🌐 Deployment

Because this is a completely static project, it can be hosted anywhere for free in seconds:

### GitHub Pages
1. Push this repository to GitHub.
2. In the repository settings, navigate to **Settings > Pages**.
3. Under **Build and deployment > Branch**, select `main` and root `/`.
4. Click **Save**. Your site will be live at `https://<username>.github.io/<repo-name>/`.

### Vercel / Netlify / Cloudflare Pages
- Connect the Git repository and deploy with default static settings (no build command, output directory `.`).

### Traditional Web Hosting (cPanel / Apache / Nginx)
- Upload all files into your server's `public_html` directory.

---

## 📱 Browser Compatibility

- **Chrome / Edge / Chromium:** Full support (Desktop & Mobile)
- **Safari / iOS Safari:** Full support (including touch canvas scratch interactions and audio toggle)
- **Firefox:** Full support

---

## 📄 License

This project is open for personal use and customization for your special celebrations.
