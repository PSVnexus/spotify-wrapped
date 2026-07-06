# Nexus Wrapped

**Live title on the site: "My 2025 Wrapped"**

A personal, interactive recap of my 2025 in music (and, as a bonus, my 2025 on Discord) —
built as a front-end project rather than pulled from any official Wrapped generator.

## Why I built this

I wanted a portfolio piece that actually showed something about *me*, not another to-do list
app or weather widget. Spotify Wrapped only sticks around for a few weeks every December, so I
rebuilt the idea as a site I control — real data, own design, and I can add to it whenever I
want (new year, new stats, no redeploying someone else's template).

It also gave me an excuse to build a few things I hadn't done from scratch before:

- A canvas particle background that reacts to the cursor
- A scroll-driven timeline with a progress rail
- A flip-card grid with real `<audio>` playback (only one track plays at a time)
- A tap-to-pause, Instagram-style story/slideshow overlay
- A tiny Web Audio synthesizer, just because it was fun to build

## What I learned

- How much cleaner a page gets when content lives in one config object (`wrappedData` in
  `script.js`) instead of being scattered across the HTML. Updating a stat is now a one-line
  change instead of a find-and-replace across three files.
- `IntersectionObserver` is the right tool for scroll reveals and count-up animations — no
  scroll-event math needed.
- Getting audio autoplay right in the browser means always handling the rejected `play()`
  promise (Chrome/Safari block unmuted autoplay without a user gesture).
- CSS custom properties make a full re-theme (accent color, in this case) a five-minute job
  instead of a find-and-replace nightmare.

## Tech used

Plain HTML, CSS, and vanilla JavaScript — no build step, no framework, no dependencies.
Fonts are loaded from Google Fonts (Space Grotesk + Plus Jakarta Sans). Everything else,
including the particle background and the little synth toy in the Sound Lab section, is
hand-rolled Canvas/Web Audio API code.

## Structure

```
index.html          Markup and section layout
style.css            Design system (CSS variables, glassmorphism, animations)
script.js            wrappedData config object + all interactivity
assets/music/        Drop mp3 clips here to enable playlist previews (see its README)
```



## Credits

Built by PSV — [github.com/PSVnexus](https://github.com/PSVnexus)
