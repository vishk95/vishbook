# Personal Technical Notebook

Source files are under `Vishbook 2.0/`.

## Local preview

```bash
python -m venv .venv
pip install -r requirements.txt
zensical serve
```

## Production verification

```bash
zensical build --clean --strict
python -m http.server 8000 --directory site
```

The site is published from `main` to https://vishk95.github.io/vishbook/. On GitHub, set Settings → Pages → Build and deployment → Source to GitHub Actions.
