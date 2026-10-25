# Mind Hub Gemini setup

1. In the same folder as `server.js` and `package.json`, create a file named `.env` (not `.env.txt`).
2. Copy the lines from `.env.example` into `.env`. Replace the placeholder with your Google AI Studio Gemini API key.
3. Keep `.env` private and never commit it to GitHub.
4. In VS Code terminal, stop the running server with Ctrl+C, then run `npm start`.
5. Open http://localhost:3000/ai-chat.html, enable **Allow remote AI**, and choose **Server proxy**.

The server uses Google's recommended Gemini Interactions API endpoint (`/v1beta/interactions`) with `gemini-3.8-flash`. It sends the recent conversation transcript and Mind Hub's wellness instructions, and uses `store: false` so interactions are not stored server-side by the API. The API key stays on the server and is not embedded in browser JavaScript.

If the terminal says the API key is missing, confirm `.env` is beside `server.js` and contains `GEMINI_API_KEY=...`. If the API returns a quota or access error, check the key's project and limits in Google AI Studio.
