# VoirJewels

Static storefront (`index.html`) with a Decap CMS admin (`/admin/`). No build step.

## Structure
- `index.html`: the whole storefront (HTML, CSS, JS in one file)
- `data/<category>.json`: products, one file per category, edited from `/admin/`
- `admin/`: Decap CMS (`index.html` loads a pinned CMS version, `config.yml` defines the fields)
- `images/`: product photos and hero slides (`IMG_8019.PNG`, `IMG_8020.PNG`, `IMG_8021.jpeg`)
- `videos/`: `video1.mp4` to `video4.mp4` for the film player
- `_headers`, `robots.txt`: Netlify headers and crawler rules

## Adding a category
1. Add a collection in `admin/config.yml`
2. Add its name to `FILES` in `index.html`
3. Add its entry to `TM` (and `TORDER`) in `index.html`
4. Create `data/<name>.json` containing `{ "products": [] }`

## Admin access
Login is GitHub OAuth through Decap. Only people with write access to the GitHub repo can publish.
There is no password in the code. To add or remove an editor, change collaborators on the repo.
Keep two-factor authentication on for every account that has write access.

## Local admin testing
Uncomment `local_backend: true` in `admin/config.yml`, run `npx decap-server`, open `/admin/` locally.
Re-comment before pushing.
