# GitHub Pages routing and SEO

This is a client-rendered SPA. GitHub Pages still returns HTTP 404 for a direct deep-link request, so `404.html` transports the path to `/` and `index.html` restores it with `history.replaceState` before the app boots. This fixes browser deep links and refreshes, but it cannot turn GitHub Pages' initial 404 response into HTTP 200.

For reliable indexing of internal pages, prerender static HTML per route (or move to a host with rewrite rules/SSR). Search Console should show the real limitation: rendered content may work while the initial URL remains a 404.
