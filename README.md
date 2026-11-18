# Agents Demo Repo

A Turborepo-powered monorepo containing the Next.js website and its shared packages.

## Structure

```
agents-demo-repo/
├── apps/
│   └── web/          # Main website - port 3000
├── packages/
│   └── i18n/         # Shared i18n utilities and UI message catalogs (next-intl)
```

The main web app (`apps/web`) uses **Next.js App Router** with all pages under
`src/app/[locale]/`. Learn articles are MDX files in `apps/web/content/learn/<locale>/`.

## Internationalization

UI strings live in `packages/i18n/messages/web/<locale>/common.json`, one catalog per
locale, loaded by `next-intl`. English (`en`) is the source; the German catalog (`de`)
is maintained by the team. Locales are registered in `packages/i18n/src/config.ts`.
Missing translations fall back to English.

## Development

```bash
pnpm install
pnpm dev:web
```

Use Node.js 24 and pnpm 11.13.1 (`npx pnpm@11.13.1` also works).
Open `/en/learn` or `/de/learn` on the local server to compare languages.
The MDX articles are translation fixtures; this cut-down app does not render
individual article pages.

```bash
pnpm check-types
pnpm build
```

## Demo starting point

The repository deliberately starts without Lingo.dev configuration or agent
instructions. Existing German translations are retained so the setup agent can
review them before translating missing content. The English catalog and five
English MDX articles are the sources; one German article already exists.

Account sign-in, MCP authorization and GitHub App installation live outside the
repository. Use a separate macOS user and browser profile for a genuinely new-user
recording rather than removing credentials from your everyday environment.
