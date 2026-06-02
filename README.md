# fragment.

Standalone static Astro site for `fragment.`.

## Local Development

```sh
bun install
bun run dev
```

## Checks And Build

```sh
bun run check
bun run build
```

The static output is generated in `dist/`.

## Pre-Commit

This repo includes `.pre-commit-config.yaml` with:

- standard file hygiene checks
- `actionlint` for GitHub Actions syntax and semantics
- `zizmor` for GitHub Actions security analysis
- Renovate config validation
- Mergify config validation

Install and run locally:

```sh
pipx install pre-commit
pre-commit install
pre-commit run --all-files
```

The `Checks` GitHub Actions workflow also runs pre-commit, `bun run check`, and `bun run build` on pushes to `main` and pull requests.

## Dependency Updates

This repo includes `.github/renovate.json` for Renovate Bot. It tracks Bun dependencies, GitHub Actions, pre-commit hooks, and mise-managed tools.

## Copy And Brand Settings

- Main page: `src/pages/index.astro`
- Brand config: `src/brand/fragment.ts`
- Shared visual tokens: `src/brand/tokens.css`
- Components: `src/components/`
- Layouts: `src/layouts/`
- Logo: `public/logos/fragment-logo.png`

Current contact email:

```txt
contact@fragment.sh
```

## GitHub Pages

This repo includes `.github/workflows/deploy.yml` for GitHub Pages.

In GitHub:

1. Go to repository settings.
2. Open `Pages`.
3. Set source to `GitHub Actions`.
4. Push to `main`.

## Custom Domain With Route 53

For an apex domain such as `fragment.sh`, keep Route 53 as DNS and create GitHub Pages apex `A` records:

```txt
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Optional IPv6 `AAAA` records:

```txt
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

For `www`, create a CNAME to the GitHub Pages hostname, usually:

```txt
www -> <github-namespace>.github.io
```

After setting the custom domain in GitHub Pages, GitHub may create a `CNAME` file. If you prefer to version it, add `public/CNAME` containing only the domain name.
