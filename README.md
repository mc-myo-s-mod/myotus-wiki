# Myotus Wiki

An Astro + Starlight documentation site with a JRip-derived light/dark theme.

**Site:** https://mc-myo-s-mod.github.io/myotus-wiki/

## Local development

Use Node.js 24 and npm.

```sh
npm ci
npm run dev
```

Open the local URL printed by Astro, including `/myotus-wiki/`.

```sh
npm run check
npm run build
npx playwright install chromium
npm test
```

Search is generated at build time. Test search with `npm run preview`, not only the development server. Browser tests build on the production output and start their own preview server.

## Content

- Edit Markdown/MDX in `src/content/docs/`.
- Add navigation entries in `astro.config.mjs`.
- JRip colors, geometry, and responsive adjustments are in `src/styles/theme.css`.
- All internal links include the GitHub Pages base path `/myotus-wiki/`.
- Do not copy uncommitted Myotus API changes into these docs as stable contracts. The initial source snapshot is `e7cfa3aaed345a351ab5d468f7d5f0f8b0e40b51`; update source references and the scope notice together when migrating to a newer revision.

The source documents remain in the mod repository; this site maintains a reviewed copy. It is not automatically synchronized with local worktrees.

## GitHub Pages

In repository Settings > Pages, choose **GitHub Actions** as the source. The deployment workflow checks types, builds the static site, runs browser checks, uploads `dist`, and deploys pushes to `main`. Pull requests run the same validation without deploying. No external hosting secret is needed.

The existing `wiki.myogoo.me` domain is not changed or claimed by this repository. To use a custom domain later, configure it in Pages, update `site` and `base`, and migrate the internal links deliberately.

See [NOTICE.md](NOTICE.md) for content, design, and font attribution.
