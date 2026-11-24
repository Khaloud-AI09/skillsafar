# SkillSafar — Advanced AI Career Companion

SkillSafar compares a resume with a job description and returns evidence-led career guidance.

## Features
- Botanical journal-inspired responsive interface
- Resume PDF text extraction in the browser (PDF.js)
- AI analysis through a server-side Vercel function
- Estimated role-match score, strengths, matched terms, gaps, improvements and prioritized next steps
- Optional Safar Journal stored locally on the current device (summary only; no resume text)
- Print / Save PDF and copy report summary
- Input validation, loading states and user-friendly errors

## Requirements
- Node.js 20+
- A Gemini API key from Google AI Studio
- Vercel account for deployment

## Run locally
1. Open this folder in VS Code.
2. Open a terminal in this folder and run:

   ```powershell
   npm install
   ```
3. Create a file named `.env.local` in the project root:

   ```env
   GEMINI_API_KEY=PASTE_YOUR_KEY_HERE
   GEMINI_MODEL=gemini-3.8-flash
   ```
4. Run:

   ```powershell
   npx vercel dev
   ```
5. Open the local URL printed in the terminal.

Do not paste your API key into `index.html`, GitHub, screenshots, or chat.

## Deploy to Vercel
1. Push this project to a private or public GitHub repository (never commit `.env.local`).
2. Import the repository into Vercel.
3. In Vercel Project Settings → Environment Variables, add:
   - `GEMINI_API_KEY` = your Gemini API key
   - `GEMINI_MODEL` = `gemini-3.8-flash` (or another model available to your API key)
4. Redeploy after adding environment variables.

## Privacy notes
- The resume and job description are sent to the server endpoint for the requested AI analysis.
- PDF text extraction happens in the browser before the extracted text is submitted.
- The Safar Journal is opt-in and stores only the report score, role title, date and short summary in browser localStorage.
- Clearing browser site data may clear the journal. The journal is not synced across devices.
- Do not use real sensitive personal information while testing a public demo. Consider adding authentication, rate limiting and abuse protection before opening the app widely.

## Product limitations
- The match score is an AI-generated estimate, not a verified ATS score or probability of getting hired.
- Scanned/image-only PDFs may not contain selectable text and will need OCR (not included).
- This starter does not include user accounts or cloud-synced report history.
