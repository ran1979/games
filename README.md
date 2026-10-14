# Games

Static showcase of Godot games exported for the web. Each game is a card with a thumbnail and title; clicking opens the game in a new tab.

## Add a game

Games are not hosted here. Each game is published from its own repo to its own GitHub Pages site, and this page links to it.

1. Publish the game's Web export to its own GitHub Pages site (e.g. `https://<user>.github.io/<repo>/`).
2. Add a cover image as `games/<slug>/thumbnail.png` (16:9 works best). Without it, the card shows a blank placeholder.
3. Add an entry to `games.json`:

   ```json
   [
     { "slug": "space-dodge", "title": "Space Dodge", "url": "https://user.github.io/space-dodge/" }
   ]
   ```

Order in `games.json` is the order on the page.

## Notes

- Threaded Godot web exports need cross-origin isolation headers, which GitHub Pages cannot send. Export such games without thread support.

## Preview locally

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000. (Opening `index.html` directly from disk will not load `games.json`.)

## Deploy to GitHub Pages

Repo → Settings → Pages → deploy from the `main` branch, root folder. The site is then served at `https://<user>.github.io/<repo>/`.
