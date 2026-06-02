# fragment.

Standalone static Astro site for `fragment.`.

## Local Development

```sh
pnpm install
pnpm dev
```

## Checks And Build

```sh
pnpm check
pnpm build
```

The static output is generated in `dist/`.

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
