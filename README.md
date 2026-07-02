# Jose Thomas — Portfolio

A single-page portfolio for a Data Scientist / ML & AI Engineer, with three **live machine-learning demos that run entirely in the browser** — no backend, no API calls, all weights embedded in the page.

## Live demos

- **Train a neural network** — a multi-layer perceptron implemented from scratch in JavaScript (forward pass, backprop, gradient descent). Pick a dataset, tune the learning rate, and watch the decision boundary form. Includes a live **network-activation visualization**: hover the canvas to push a point through the net and watch the neurons fire.
- **Handwritten-digit classifier** — a small neural net trained offline (NumPy), int8-quantized, and embedded here. Draw a digit and it classifies it in real time, showing the 28×28 image the model actually sees.
- **Language detector** — a character n-gram naive Bayes model over six languages (English, Spanish, French, German, Italian, Portuguese), trained offline and embedded. Type a sentence and it identifies the language as you go.

## Customize

Everything you need to personalize is marked with `EDIT ME` comments in `index.html`:

- Your name, headline, and bio
- Project case studies (problem / approach / results / metrics)
- Skills
- Contact links (email, GitHub, LinkedIn, Kaggle, résumé)
- The `og:url` / `og:image` / Twitter meta tags in `<head>` (point them at your live URL)

The site is a **single `index.html`** — just open it in any browser to preview locally.

## Deploy to GitHub Pages

From this folder:

```bash
git init
git add .
git commit -m "Portfolio site with live ML demos"
git branch -M main
# create an empty repo on GitHub first, then:
git remote add origin https://github.com/yourusername/portfolio.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, pick **`main`** and folder **`/ (root)`**, and save. Your site goes live at:

```
https://yourusername.github.io/portfolio/
```

> Tip: to host at `https://yourusername.github.io/` (no `/portfolio` suffix), name the repo exactly `yourusername.github.io`.

The `.nojekyll` file is included so GitHub Pages serves the files as-is without Jekyll processing.

## Alternative one-click hosts (no git)

- **Netlify Drop** — drag this folder onto <https://app.netlify.com/drop>.
- **Vercel** — `npx vercel` from this folder, or drag-and-drop in the dashboard.
- **Cloudflare Pages** — connect the repo or upload the folder.

## How the models were built

The digit and language models were trained offline in Python (NumPy + PIL), evaluated on held-out data, quantized (int8 / int16) to shrink the payload, and embedded directly in the page. The browser-side inference was verified to match the Python outputs to within rounding error. The from-scratch playground network trains live in your browser using plain JavaScript.

## License

MIT — do whatever you like with it.
