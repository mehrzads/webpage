# How to Update YouTube Videos

The website shows your 6 latest YouTube videos as click-to-play cards (thumbnail loads instantly; the YouTube player is only embedded when a visitor clicks play).

## Quick Steps

1. **Get the Video ID** from your new YouTube video URL
   - URL format: `https://www.youtube.com/watch?v=VIDEO_ID_HERE`
   - Example: `https://www.youtube.com/watch?v=3JyKypJsFCc` → Video ID is `3JyKypJsFCc`

2. **Edit `index.html`**
   - Find the videos section (search for `TO UPDATE VIDEOS`)
   - Each video is one `<article class="video-card">` block. To add a new video, copy the first card, paste it at the top of the grid, and delete the last (oldest) card.
   - In the new card, replace the video ID in **three** places:
     - `data-id="VIDEO_ID"` on the `<button class="video-frame">`
     - both thumbnail URLs: `https://i.ytimg.com/vi/VIDEO_ID/maxresdefault.jpg` and `.../VIDEO_ID/hqdefault.jpg`
   - Update the `<h3>` title, the `aria-label` on the button, and the date in `<p class="video-meta">`.

3. **Commit and Push**
   ```bash
   git add index.html
   git commit -m "Update YouTube videos"
   git push
   ```

4. **Wait 1-2 minutes** for GitHub Pages to rebuild.

## Example card

```html
<article class="video-card reveal">
  <button class="video-frame" data-id="3JyKypJsFCc" aria-label="Play video: Open Knowledge Format by Amir Hormati">
    <img src="https://i.ytimg.com/vi/3JyKypJsFCc/maxresdefault.jpg"
         onerror="this.onerror=null;this.src='https://i.ytimg.com/vi/3JyKypJsFCc/hqdefault.jpg'"
         alt="" loading="lazy">
    <span class="play-badge" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg></span>
  </button>
  <div class="video-body">
    <h3>38. Open Knowledge Format by Amir Hormati</h3>
    <p class="video-meta">July 2026 &middot; Persian</p>
  </div>
</article>
```

The podcast section (`id="podcasts"`) uses the same card structure — update it the same way.

Tip: you can get a video's exact title with
`curl "https://www.youtube.com/oembed?url=https://www.youtube.com/watch?v=VIDEO_ID&format=json"`
