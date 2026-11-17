# Scrubbr

Public static, manifest-driven YouTube player. Scrubbr is the open playback frontend; Rizzr is a separate, future MCP service that will store manifests and return shareable player URLs.

## Try it
Use **Use example JSON** then **Play pasted manifest**, or paste your own JSON and play. You can load a hosted manifest by URL (same-origin or CORS-enabled HTTPS). The app needs no API key, OAuth token, backend or video publishing quota.

## Example manifest
```json
{
  "version": 1,
  "title": "Scrubbr playback smoke test",
  "description": "Two videos for testing queue navigation and automatic advancement in the official YouTube player.",
  "items": [
    {
      "videoId": "M7lc1UVf-VE",
      "title": "YouTube IFrame API demonstration",
      "note": "Official player test video"
    },
    {
      "videoId": "jNQXAC9IVRw",
      "title": "Me at the zoo",
      "note": "Second entry for queue switching; embedding availability may vary"
    }
  ]
}
```

## GitHub Pages
The workflow in `.github/workflows/pages.yml` publishes the repository root on pushes to `main`.
In **Settings → Pages → Build and deployment**, select **GitHub Actions**.
Once enabled and deployed, the site should be at https://qbob1.github.io/scrubbr/ .

## Limits
Browser autoplay may require tapping Play. Some YouTube videos disallow embedding. YouTube embedded-player policy prohibits background/audio-only playback. Segment timestamps and chapters are not yet supported. Manual JSON stays in the browser session; a shareable playlist requires a hosted manifest.
