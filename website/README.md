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
- The site can be hosted on any static host (S3 + CloudFront, GitHub Pages, Netlify).
