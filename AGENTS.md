# Development environment

- This repository is a static, multi-page site, not a backend application. It requires no database, migrations, secrets, or external API credentials; Maps, WhatsApp, and Instagram are ordinary outbound links.
- Base44 uses Vite only as a development server. The existing HTML, CSS, JavaScript, and `IMAGENES/` assets are served directly from the bind-mounted checkout; do not replace them with a prebuilt site image.
- Start with `docker compose -f docker-compose.base44.yml up -d --build`. Startup runs `npm ci` using the committed lockfile into a dedicated dependency volume before starting the live-reload server on port 3000.
- The bare `__VITE_ADDITIONAL_SERVER_ALLOWED_HOSTS` environment entry passes through the platform host allowance. Keep it environment-driven rather than hardcoding a sandbox hostname.
- Verify `/`, `/completos.html`, `/sandwiches.html`, `/especiales.html`, `/styles.css`, `/app.js`, and the referenced image files respond successfully. The served homepage should include `/@vite/client`, confirming the live source server is active.
- There is no automated test suite. Browser checks should confirm the homepage, loaded images, active navigation, and mobile menu, with no console errors or failed asset requests.
