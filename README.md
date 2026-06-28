# Graph Background

Customize the background of Obsidian's **global** and **local** graph views — solid color, gradient, or image — all from the plugin's settings page. No theme switching, no manual CSS snippets.

## Install (manual)

1. In your vault, go to `.obsidian/plugins/` (create the `plugins` folder if it doesn't exist).
2. Create a new folder inside it called `graph-background`.
3. Copy `main.js`, `manifest.json`, and `styles.css` into that folder.
4. In Obsidian: **Settings → Community plugins**, make sure "Restricted mode" is off, then refresh the list and toggle **Graph Background** on.
5. Go to **Settings → Graph Background** to configure it.

Your folder should look like:

```
.obsidian/
  plugins/
    graph-background/
      main.js
      manifest.json
      styles.css
```

## How it works

- **Background type**: pick None, Solid color, Gradient (linear or radial), or Image.
- **Image source**: either pick a file already in your vault, or paste an external image URL.
- **Fit**: cover / contain / repeat (tile) / center, for images.
- **Apply to**: choose whether it affects the global graph, the local graph, or both.
- **Readability overlay**: a Dim slider and a Blur slider — these only affect the background layer, never the actual graph nodes/links/labels, so your notes stay easy to read on top of busy images.

Changes apply live — no need to reopen the graph view or restart Obsidian.

## Notes

- This relies on the documented Obsidian "CSS bridge" classes for the graph view (`.graph-view.color-fill`), which Obsidian itself provides specifically so themes/snippets can recolor the graph's WebGL canvas. The plugin uses this to make the canvas's own background transparent, then layers your chosen background behind it.
- Because this depends on Obsidian's internal graph view markup, a future Obsidian update could in theory change those class names and require an update to this plugin. It's been built against current (mid-2026) Obsidian releases.
- Works on desktop and mobile.
