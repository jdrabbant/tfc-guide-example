# Cloud Pro Serv website

Static marketing site for Cloud Pro Serv — plain HTML, CSS and JavaScript with no build step.

- `index.html` — page content (services, process, why us, FAQ, contact)
- `styles.css` — styles, including responsive layout and automatic dark mode
- `script.js` — mobile menu, scroll animations and contact-form validation

## Preview locally

```sh
cd website
python3 -m http.server 8000
# open http://localhost:8000
```

## Notes

- The contact form validates input in the browser but does not send messages yet.
  Connect the submit handler in `script.js` to a form backend (an API endpoint,
  Formspree, AWS Lambda, etc.) before going live.

## Hosting (GitHub Pages)

`.github/workflows/pages.yml` deploys this folder to GitHub Pages on every push to
`master` that touches `website/` (it can also be run manually from the Actions tab).

One-time setup:

1. **Settings → Pages → Build and deployment → Source:** choose **GitHub Actions**.
2. **Settings → Pages → Custom domain:** enter `cloudproserv.com` and save.
3. In **Wix → Domains → cloudproserv.com → Manage DNS Records**, set:

   | Type  | Host                | Value                    |
   |-------|---------------------|--------------------------|
   | A     | cloudproserv.com    | 185.199.108.153          |
   | A     | cloudproserv.com    | 185.199.109.153          |
   | A     | cloudproserv.com    | 185.199.110.153          |
   | A     | cloudproserv.com    | 185.199.111.153          |
   | CNAME | www                 | jdrabbant.github.io      |

   Remove any other A or CNAME records for the root and `www` (for example ones
   pointing at Wix).
4. Once DNS has propagated and GitHub shows the domain check passing, tick
   **Enforce HTTPS** on the Pages settings page.
