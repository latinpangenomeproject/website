# LatinGenomes website (Quarto)

A Quarto website for LatinGenomes: The Latin American Alliance for Genomic Diversity.
It needs **no R or Python**: the interactive map, cohort table and timeline use
Observable JS, which Quarto runs in the browser.

## Run it locally

1. Install Quarto (1.6 or newer): https://quarto.org/docs/get-started/
2. From this folder:

   ```bash
   quarto preview      # live-reloading local site
   quarto render       # builds the static site into _site/
   ```

## Structure

| File | What it is |
|------|------------|
| `_quarto.yml` | Site settings, navbar, footer, themes |
| `index.qmd` | Home page (hero, genome band, aims, facts, latest news) |
| `research.qmd` | Aims 1–4 with figures from the proposal |
| `cohorts.qmd` | Interactive map and searchable cohort table (reads `data/cohorts.csv`) |
| `data.qmd` | Data sharing strategy (EGA, CELLxGENE, portal) |
| `timeline.qmd` | Five-year Gantt chart |
| `training.qmd` | CABANAnet workshops and community engagement |
| `team.qmd` | Collaborators by country |
| `news/` | Blog-style news; one folder per post in `news/posts/` |
| `styles/` | Light/dark SCSS themes and `extra.css` (country colors live here) |
| `data/` | `cohorts.csv` (Table 1) and `countries.csv` (map positions and colors) |

## Common edits

- **Update cohort numbers:** edit `data/cohorts.csv`; the map and table update automatically.
  The home-page genome band is hand-written HTML in `index.qmd`; update its numbers too.
- **Add a news post:** copy `news/posts/2026-09-welcome/`, rename, edit.
- **Replace placeholders:** search the project for `TODO` (domain, GitHub org, contact email, EGA accessions).
- **Add a Spanish/Portuguese version:** the simplest route is a parallel `es/` folder with translated `.qmd` files and a navbar language menu.

## Publish on GitHub Pages

1. Push this folder to a GitHub repository.
2. Run `quarto publish gh-pages` once locally.
3. After that, `.github/workflows/publish.yml` re-publishes on every push to `main`.

Netlify, Quarto Pub, or your institution's web server (upload `_site/`) also work.

## Credits

Figures 1–5 are taken from the Discovery Award application. Figure 2 data: Homburger, Moreno-Estrada et al. 2015, *PLOS Genetics*.
Figure 5: Lorenzo Bermejo et al. 2017. Check reuse permissions before public launch.
