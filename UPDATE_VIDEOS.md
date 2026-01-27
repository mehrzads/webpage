# How to Update YouTube Videos

Your website displays your 5 latest YouTube videos. To update them:

## Quick Steps

1. **Get the Video ID** from your new YouTube video URL
   - URL format: `https://www.youtube.com/watch?v=VIDEO_ID_HERE`
   - Example: `https://www.youtube.com/watch?v=WuqWQ4jRaP8` → Video ID is `WuqWQ4jRaP8`

2. **Edit `index.html`**
   - Find the YouTube section (search for "TO UPDATE VIDEOS")
   - Replace the oldest video's iframe URL with your new video ID
   - Change: `https://www.youtube.com/embed/OLD_VIDEO_ID`
   - To: `https://www.youtube.com/embed/NEW_VIDEO_ID`

3. **Update the title** (optional)
   - Change the text in the `<h3>` tag below the video to match your new video title

4. **Commit and Push**
   ```bash
   git add index.html
   git commit -m "Update YouTube video"
   git push
   ```

5. **Wait 1-2 minutes** for GitHub Pages to rebuild

## Example

If your new video is at `https://www.youtube.com/watch?v=ABC123XYZ`, replace:

```html
<iframe class="..." src="https://www.youtube.com/embed/WuqWQ4jRaP8" ...></iframe>
```

With:

```html
<iframe class="..." src="https://www.youtube.com/embed/ABC123XYZ" ...></iframe>
```

That's it! Your website will update automatically.
