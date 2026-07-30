# NewAPI Model Routing

Load `.env` without printing its values.

```dotenv
NEW_API_URL=https://llmapi.lovbrowser.com/v1
NEW_API_KEY=<secret>
AI_TEXT_MODEL=gpt-5.6-sol
AI_IMAGE_MODEL=gpt-image-2
AI_VIDEO_MODEL=doubao-seedance-2-0-260128
```

## Roles

- `AI_TEXT_MODEL`: research synthesis, writing, Humanizer pass, visual review reasoning.
- `AI_IMAGE_MODEL`: cover and illustration assets.
- `AI_VIDEO_MODEL`: future motion/video work only; exclude from the default static pipeline.

## Preflight

1. Check all five variables exist.
2. Call `${NEW_API_URL}/models` with the bearer token without logging the token.
3. Confirm the configured model IDs are present.
4. Record model IDs in `manifest.md`.
5. If auth or availability fails, mark the stage `blocked` and report the failing role.

All downstream inference goes through `NEW_API_URL`. Keep provider-specific credentials and direct vendor endpoints outside this project.
