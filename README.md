# Vision 2056 — PWA starter

A responsive Next.js starter for a Hindi / English / Hinglish AI assistant with robotic-bear branding, installable PWA metadata, browser voice input, local chat history, image uploads, and optional web search.

## Requirements
- Node.js 20 or newer
- An OpenAI API key with API access and billing configured

## Run locally
1. Extract this project.
2. Run `npm install`.
3. Copy `.env.example` to `.env.local` and set `OPENAI_API_KEY` and (optionally) `OPENAI_MODEL`.
4. Run `npm run dev` and open http://localhost:3000.

Never put the API key in a `NEXT_PUBLIC_` variable or commit `.env.local`.

## Deploy
1. Push the project to a private or public Git repository (do not include `.env.local`).
2. Import the repository into a Next.js-compatible host such as Vercel.
3. Add `OPENAI_API_KEY` and `OPENAI_MODEL` as server-side environment variables in the host dashboard.
4. Deploy and test the live URL over HTTPS.
5. Optionally connect a custom domain.

## PWA / install
The app includes a web app manifest and an SVG icon. Serve it over HTTPS. On supported browsers, the browser may show an install prompt; on Android Chrome, users can also use the browser menu and choose **Install app** or **Add to Home screen**. Install prompt availability depends on browser and installability rules. iOS users can use Safari's Share menu and **Add to Home Screen**. A PWA is not the same as a Play Store app.

## Important limitations / production work
- Hosting may have a free tier, but AI API calls are generally billed separately and are not guaranteed to be free.
- Chat history in this starter is saved in the current browser's localStorage only. It is not synced across devices and has no account system.
- Browser speech recognition varies by browser, OS, language, and network. This starter does not include text-to-speech.
- The image endpoint accepts JPG, PNG, WEBP, or GIF up to 5 MB. Actual image support depends on the selected model and API account.
- Web search uses the Responses API `web_search_preview` tool where available. Check current API documentation and account/model availability; adjust tool type if the API has changed.
- Before public launch, add authentication, rate limiting, abuse prevention, quotas, privacy policy, terms, monitoring, and a strategy for keeping API costs under control. Do not deploy a public endpoint with an unbounded API budget.
- `localStorage` history is not appropriate for sensitive conversations on shared devices.

## Current routes
- `/` — responsive chat interface
- `/api/chat` — server-side AI endpoint; keeps API key off the client
- `/manifest.webmanifest` — generated PWA manifest
