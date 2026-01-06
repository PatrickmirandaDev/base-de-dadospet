<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://github.com/user-attachments/assets/0aa67016-6eaf-458a-adb2-6e31a0763ed6" />
</div>

# Run and deploy your AI Studio app

This contains everything you need to run your app locally.

View your app in AI Studio: https://ai.studio/apps/drive/1VIQBxERGxdubwh6bp9yQ8rgsujGzeytr

## Run Locally

**Prerequisites:**  Node.js

1. Install dependencies:
   `npm install`
2. Set the `GEMINI_API_KEY` in [.env.local](.env.local) to your Gemini API key
3. Run the app:
   `npm run dev`

---

## Deploying / Running

These instructions help you run the project locally and deploy a test instance using bolt.new or Vercel.

### Run locally

1. Install dependencies:

   npm install

2. Start the dev server:

   npm run dev

3. Open http://localhost:3000 in your browser.

Notes: The project uses Vite. The importmap that previously pointed to CDN React versions was removed so the app uses local dependencies installed from package.json. Tailwind is still loaded via CDN in index.html for convenience; for a production build you may want to integrate Tailwind properly via PostCSS or the Tailwind CLI.

### Deploy to bolt.new (quick test)

1. Go to https://bolt.new and connect your GitHub account.
2. Import the `patrickmirandadev/base-de-dadospet` repository and choose the `main` branch.
3. Configure the build command and output directory if needed:

   - Build command: `npm run build`
   - Output directory: `dist`

4. If you need environment variables (the repo contains a placeholder `.env.local`), you can add them in bolt.new UI.
5. Deploy and wait for the build to finish. Open the provided URL to test the app.

### Deploy to Vercel

1. Go to https://vercel.com and import the repository.
2. Set the framework to "Other" or detect Vite automatically. Use the following settings if prompted:

   - Build command: `npm run build`
   - Output directory: `dist`

3. Add any environment variables in the Vercel project settings if necessary.
4. Deploy and open the generated URL.

### Notes and fixes applied

- Removed the importmap from `index.html` so the app loads React and other dependencies from the local node_modules through Vite; this avoids version mismatches between CDN and package.json.
- Added a minimal `index.css` (importing Inter font and setting root height) and referenced it from `index.html` so preview servers serve a real stylesheet.
- If you prefer to bundle Tailwind instead of using the CDN, I can add a proper Tailwind setup (postcss + tailwind.config) and adjust the build scripts.

If you want, I can also add a simple GitHub Action or Vercel configuration file to automate deployments.

---

End of update.
