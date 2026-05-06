# Vansh Gokhale Portfolio

A cinematic single-page portfolio for Vansh Gokhale, built as a dark Imperial command-terminal experience with a Darth Vader inspired visual language. The site is intentionally immersive: full-screen space, Sith red highlights, theatrical typography, animated starfields, drifting TIE silhouettes, and editorial sections that feel closer to a premium sci-fi dossier than a generic developer portfolio.

The entire project is contained in one file: `index.html`.

## Preview

Open `index.html` directly in a browser, or serve it locally:

```bash
python3 -m http.server 8765
```

Then visit:

```text
http://127.0.0.1:8765/
```

## Project Goals

This portfolio was designed to feel like an intercepted Imperial archive for a software engineer. The visual direction follows a cinematic, editorial, full-bleed style: very dark backgrounds, large display typography, sparse composition, and controlled red glow moments.

The main priorities are:

- Strong first impression on desktop and mobile.
- Single-page smooth-scroll portfolio flow.
- Pure HTML, CSS, and vanilla JavaScript.
- No frameworks, build tools, or external JavaScript libraries.
- Fully self-contained layout and animation logic.
- Responsive smartphone layout using flexbox stacks.
- Accessible semantic structure with headings, nav, sections, articles, and labels.

## Tech Stack

- HTML5 for structure.
- CSS custom properties for theme control.
- CSS animations for glow, scanlines, hover states, mobile menu, and silhouettes.
- Flexbox and CSS Grid for responsive layout.
- Vanilla JavaScript for canvas animation, typewriter text, menu state, and IntersectionObserver reveals.
- Google Fonts:
  - `Cinzel` for cinematic display typography.
  - `Rajdhani` for body and interface text.
  - `Share Tech Mono` for terminal/data readouts.

## File Structure

```text
.
|-- index.html
`-- README.md
```

Everything needed for the website lives inside `index.html`:

- Markup
- Styles
- Inline SVG icons and atmospheric objects
- Canvas starfield JavaScript
- Typewriter animation
- Scroll reveal behavior
- Mobile navigation behavior

## Sections

### 1. Hero

The opening section is a full-viewport cinematic introduction. It includes:

- Animated Imperial crest.
- Massive `VANSH GOKHALE` title.
- Typewriter subtitle cycling through professional roles.
- Sith red horizontal ignition line.
- Terminal-style CTA buttons.
- Pulsing down-scroll cue.
- Parallax-style fade and scale effect on supported browsers.

### 2. Intercepted Transmission

The about section is styled like a classified transmission panel:

- Split layout on desktop.
- Red vertical signal bar.
- Rotated transmission label.
- Scanline texture.
- Profile summary.
- Four status chips for degree, graduation year, location, and current academic year.

### 3. The Armory

The technical skills section presents tools and concepts as an equipment grid:

- Languages
- Backend systems
- Frontend interface
- Data vaults
- Cloud and deployment
- Core protocols

Each card has inline SVG iconography, red borders, hover glow, and skill pills.

### 4. Field Missions

The experience section uses a vertical timeline:

- Glowing red center line on desktop.
- Left-aligned mobile timeline.
- Rhombus mission nodes.
- Date chips.
- Alternating desktop cards.
- Single-column flexbox layout on smartphones.

### 5. Operations Log

The projects section uses a magazine-style layout:

- Featured project card for the AI Job Automation Pipeline.
- Two stacked supporting project cards.
- Holographic scanline animation.
- Tech stack pills.
- Terminal-style initiate buttons.

On smartphones, the project layout becomes a clean flexbox column so every card reads naturally without horizontal overflow.

### 6. Imperial Clearance

The certifications section uses credential chips:

- HackerRank problem solving.
- Goldman Sachs virtual experience.
- AWS Cloud Technical Essentials.
- Java certification.
- CSS certification.

### 7. Open Transmission

The final contact section acts as the closing command prompt:

- Large `SEND A TRANSMISSION` headline.
- Contact links for email, LinkedIn, GitHub, and portfolio.
- Red underline hover animation.
- Footer identity line.

## Visual System

### Colors

The palette is intentionally strict and minimal:

```css
--bg: #000000;
--bg-alt: #0A0A0F;
--accent: #CC0000;
--accent-deep: #8B0000;
--panel: #1C1C2E;
--text: #FFFFFF;
--text-muted: #A0A0B0;
--highlight: #FF4444;
```

### Typography

Only the requested type families are used:

- `Cinzel`
- `Rajdhani`
- `Share Tech Mono`

There are no Inter, Roboto, Arial, or system-font declarations in the CSS.

## Animation System

The site includes several coordinated motion layers:

- Canvas starfield with 300 drifting stars.
- Randomized star twinkle using `requestAnimationFrame`.
- CSS animated TIE fighter silhouettes.
- Faint Death Star atmosphere in the upper-right viewport.
- Hero staggered entrance animation.
- Typewriter role cycle.
- Scroll-triggered reveals through `IntersectionObserver`.
- Timeline line draw animation.
- Project holographic scanline sweep.
- CTA fill sweep hover effect.
- Contact underline slide animation.
- Mobile menu stagger entrance.

Motion is reduced for users who prefer reduced motion through the `prefers-reduced-motion` media query.

## Responsive Design

The page includes breakpoints at:

- `1200px`
- `768px`
- `480px`

Desktop uses a mix of CSS Grid and flexbox to preserve the editorial layout. Smartphone views use flexbox-focused stacks for consistency and readability:

- Hero buttons stack vertically.
- About content becomes a vertical flex layout.
- Stat chips wrap, then stack on very small screens.
- Skill cards become a single flex column.
- Timeline entries become a single readable column.
- Project cards become a vertical flex stack.
- Contact links and footer spacing are tuned for 320px screens.

Extra safeguards such as `min-width: 0`, `overflow-wrap: anywhere`, reduced mobile letter-spacing, and smaller contact footer tracking help prevent clipping on narrow devices.

## Accessibility

The page uses:

- Semantic landmarks: `nav`, `main`, `section`, `article`, and `footer`.
- Proper heading hierarchy.
- `aria-label` on navigation and icon-only controls.
- `aria-live` for the typewriter role text.
- `inert` for the closed mobile menu to keep hidden links out of the focus order.
- `prefers-reduced-motion` support.

## How To Customize

### Update Profile Text

Edit the about paragraph inside:

```html
<section class="about" id="about">
```

### Update Skills

Edit the cards inside:

```html
<section class="armory" id="armory">
```

Each skill is a `.pill` element.

### Update Experience

Edit timeline entries inside:

```html
<section class="missions" id="missions">
```

Each entry is an `.timeline-item`.

### Update Projects

Edit project cards inside:

```html
<section class="operations" id="operations">
```

The featured project uses:

```html
<article class="project-card featured">
```

### Update Contact Links

Edit links inside:

```html
<section class="contact" id="transmission">
```

## Deployment

Because this is a static one-file website, it can be deployed anywhere that serves static HTML:

- GitHub Pages
- Netlify
- Vercel
- Cloudflare Pages
- Any static web host

No build command is required. The deploy output is simply the project folder containing `index.html`.

## Verification

The page has been checked with:

```bash
npx --yes html-validate index.html
```

And the inline JavaScript has been syntax-checked with Node.

Mobile screenshots were also reviewed at narrow smartphone widths, including 390px and 320px viewports, to confirm that the layout remains readable and does not clip key content.

## Notes

This is a fan-inspired sci-fi aesthetic portfolio and is not affiliated with Lucasfilm, Disney, or the Star Wars franchise. The design uses original inline SVG shapes and CSS effects to evoke an Imperial command-terminal mood without relying on external image assets or JavaScript libraries.
