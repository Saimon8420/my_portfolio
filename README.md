## 🛠️ Stack

- [**Astro**](https://astro.build/) - The next-gen web framework.
- [**Typescript**](https://www.typescriptlang.org/) - JavaScript with type syntax.
- [**TailwindCSS**](https://tailwindcss.com/) - Utility-first CSS framework.
- [**Iconify**](https://iconify.design/) - Icon library.
- [**FancyBox**](https://fancyapps.com/fancybox/3/) - Image viewer.
- [**Ninja Keys**](https://github.com/ssleptsov/ninja-keys) - Dropdown menu with keyboard shortcuts made in pure JavaScript.

## 🚀 Getting Started

Modify the `cv.json` file to create your own printable Portfolio/CV.

### 1. Use this Repo as an Astro Project Template

### 1-1. Clone the repo

If you don't want to use the template command, you can clone this repo and install the dependencies.

### 2. Add Your Content:

Edit the `cv.json` file to create your own printable Portfolio/CV.

### 3. Launch the Development Server:

1. Open [**http://localhost:4321**](http://localhost:4321/) in your browser to view the result 🚀

### 4. Customisable colours:
Change the data-theme of `cv.json` and choose one of the colour themes defined in theme.css, red, blue, green, cyber, pink and default, with its variants in dark mode, or create your own.

## 🧞 Commands

|     | Command         | Action                                                                       |
| :-- | :-------------- | :--------------------------------------------------------------------------- |
| ⚙️  | `dev` or `start` | Launches a local development server at `localhost:4321`.                   |
| ⚙️  | `build`         | Checks for errors and creates a production build in `./dist/`. |
| ⚙️  | `preview`       | Local preview at `localhost:4321`                                       |
| 📦  | `deploy:vercel`         | Deploy on Vercel.                           |
| 📦 | `deploy:cloudflare`       | Deploy on Cloudflare, please run `wrangler login` first.                                           |                                |

## 🟢 Live Apps (auto-showcase from Vercel)

The **Live Apps** section (`src/components/sections/LiveApps.astro`) auto-lists everything
deployed on Vercel — no editing `cv.json` for each new project.

How it works:

- At **build time** it calls the Vercel REST API (`/v9/projects`) using a server-side
  `VERCEL_TOKEN` (never exposed to the browser), keeps the public-facing apps, and renders a
  card per project with a live [thum.io](https://www.thum.io/) screenshot + link.
- **Filtering:** everything is shown except names in the `DENY` set (the portfolio itself,
  `*-server` backends, etc.) — so **future deployments appear automatically**. Edit the `DENY`
  set in `LiveApps.astro` to hide a project.
- Without a token, the section hides itself in production (and shows a small mock list in `dev`
  so the layout is previewable).

### Setup

1. Create a token: **Vercel → Account Settings → Tokens** (read access is enough).
2. Add it as an env var on the portfolio's Vercel project: `VERCEL_TOKEN`
   (and `VERCEL_TEAM_ID` only for team accounts). See `.env.example`. Redeploy.
3. **Keep it fresh** (so newly-deployed apps show up without a manual redeploy):
   create a **Deploy Hook** (Vercel → project → Settings → Git → Deploy Hooks), add its URL as
   a GitHub Actions secret `VERCEL_DEPLOY_HOOK`, and the included
   `.github/workflows/refresh-live-apps.yml` will trigger a daily rebuild.

## 📝 License

This project is [MIT](./LICENSE) licensed.

CV JSON schema from [**jsonresume.org**](https://jsonresume.org/schema/)
