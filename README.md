# PND // Party Never Dies

A brutalist, monochrome website for the PND collective — a multidisciplinary network of artists, engineers, filmmakers, designers, coders, sound people and visual creators operating between Berlin and London.

## What's Inside

Static HTML/CSS/JS website, ready for GitHub Pages. No build tools, no dependencies.

```
/
  index.html          Homepage — title page with full brutalist hero
  projects.html       Project grid with status tags
  collective.html     Member directory
  chris-mansouri.html Founder profile page
  rob-handyside.html  Founder profile page
  about.html          Collective explanation
  contact.html        Contact information
  assets/
    css/
      style.css       All styles (single file)
    js/
      main.js         Mobile menu + navigation (single file)
    img/
      tunnel.jpg      Industrial tunnel photo
      og-image.png    Social sharing image
      favicon-*.png   Favicon files
  README.md           This file
```

## How to Upload to GitHub Pages

1. Create a new repository on GitHub (e.g., `pnd-collective`)
2. Upload all files from this folder to the repository root
3. Go to **Settings > Pages** in your repository
4. Under "Source", select **Deploy from a branch**
5. Select the `main` branch and `/` (root) folder
6. Click **Save**
7. Your site will be live at `https://yourusername.github.io/pnd-collective/`

### Alternative: Git command line

```bash
git init
git add .
git commit -m "Initial PND website"
git remote add origin https://github.com/YOURUSERNAME/pnd-collective.git
git push -u origin main
```

## How to Edit Projects

Open `projects.html`. Each project is an `<article class="card">` element. To add a new project, copy an existing card and modify:

```html
<article class="card">
  <div class="card__header">
    <span class="card__category">YOUR CATEGORY</span>
    <span class="status-tag status-tag--active">YOUR STATUS</span>
  </div>
  <h2 class="card__title">Your Project Name</h2>
  <p class="card__description">Your project description here.</p>
  <span class="card__link">&rarr;</span>
</article>
```

**Status options:**
- `status-tag--active` — White border, solid
- `status-tag--research` — Gray border, solid
- `status-tag--archive` — Dark gray border, solid
- `status-tag--concept` — Dark gray border, dashed

## How to Edit Collective Members

Open `collective.html`. Each member is an `<article class="card member-card">`. Founder cards can link to internal profile pages such as `chris-mansouri.html` and `rob-handyside.html`. To add a new member, copy an existing card:

```html
<article class="card member-card">
  <h2 class="card__title">Member Name</h2>
  <p class="member-card__role">Role / Discipline</p>
  <p class="card__description">Short bio here.</p>
  <div class="member-card__links">
    <a href="https://member-website.com" target="_blank" rel="noopener noreferrer">Website</a> /
    <a href="https://instagram.com/handle" target="_blank" rel="noopener noreferrer">Instagram</a> /
    <a href="https://member-portfolio.com" target="_blank" rel="noopener noreferrer">Portfolio</a>
  </div>
</article>
```

Replace `#` in existing links with real URLs. Remove any link you don't need.

## Where to Change Colours and Text

All visual settings are CSS custom properties at the top of `assets/css/style.css`:

```css
:root {
  /* Colors */
  --color-black: #000000;
  --color-white: #FFFFFF;
  --color-gray-1: #888888;
  --color-gray-2: #444444;
  --color-gray-3: #1A1A1A;

  /* Typography Scale */
  --text-display-xl: clamp(80px, 18vw, 280px);
  --text-display-lg: clamp(32px, 5vw, 64px);
  /* ... etc */
}
```

- **Change the black background:** Modify `--color-black`
- **Change text color:** Modify `--color-white`
- **Change gray tones:** Modify `--color-gray-*` values
- **Change font sizes:** Adjust the clamp() values
- **All pages use the same CSS file** — one change applies everywhere

## How to Connect a Custom Domain

1. In your repository, create a file named `CNAME` (no extension) in the root
2. Inside `CNAME`, write your domain: `pnd.collective`
3. Commit and push the file
4. Go to **Settings > Pages** and enter your custom domain
5. At your domain registrar, add these DNS records:

   **For apex domain (pnd.collective):**
   ```
   A record → 185.199.108.153
   A record → 185.199.109.153
   A record → 185.199.110.153
   A record → 185.199.111.153
   ```

   **For www subdomain (www.pnd.collective):**
   ```
   CNAME record → yourusername.github.io
   ```

6. Wait for DNS propagation (up to 24 hours)
7. GitHub will automatically provision an SSL certificate

## Technical Notes

- **Zero external dependencies** — no fonts, no CDN, no frameworks
- **System font stack** — uses fonts already on the user's device
- **Mobile responsive** — adapts from desktop to mobile with hamburger menu
- **Accessibility** — semantic HTML, focus states, skip link, screen-reader friendly
- **SEO ready** — meta descriptions, Open Graph tags, Twitter Cards
- **GitHub Pages compatible** — static files only, no server-side processing needed

## Credits

Design and development by PND.
Technical systems and research supported by [Event Tech Research](https://eventtechresearch.org).


## Included people pages

This build includes profile pages for:

- `chris-mansouri.html` — Founder profile
- `rob-handyside.html` — Founder profile
- `ed.html` — Cinematographer profile

The Collective page links to each profile first. External links are placeholders marked with `#` and can be replaced with real websites, portfolios, Instagram pages or LinkedIn profiles.

## Visual style

The build uses the supplied PND black-and-white brutalist key art as `assets/img/pnd-key-art.png` and the Open Graph preview image.


## V2 collective updates

This build includes profile pages for:
- Chris Mansouri — Founder / Technical Director
- Rob Handyside — Founder / Director
- Ed Stone — Cinematographer
- Roberto Pellegrino — Bespoke Sound Systems & Video

Roberto's profile links to Roots Sensation Sound System:
https://www.soundsystem.world/soundsystems/roots-sensation-sound-system/
