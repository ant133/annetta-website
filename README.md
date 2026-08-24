# Annetta's portfolio

An interactive portfolio for Annetta, built as a static site with HTML, CSS,
JavaScript, and Three.js. It is designed to be hosted at
[annetta.dev](https://annetta.dev/) using GitHub Pages.

## Local development

Run the site from a local web server because the Three.js ES modules do not run
reliably from `file://` URLs:

```sh
python3 -m http.server 8000
```

Then visit `http://localhost:8000`. Visual and physics parameters live in the
`config` object near the top of `main.js`.

## Deployment

The site has no build step. Publish the repository root with GitHub Pages. The
`CNAME` file configures the custom domain, and `.nojekyll` tells Pages to serve
the static files without Jekyll processing.
