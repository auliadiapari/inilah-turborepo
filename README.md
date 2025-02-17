# Inilah Monorepo Assigments

This is an official starter Turborepo.

## To run the applications

Run the following command to install the node_modules:

```sh
pnpm install
```

Edit TURBO_TEAM & TURBO TOKEN to enable remote caching in docker-compose.yaml:

```sh
TURBO_TEAM: <TURBO_TEAM>
TURBO_TOKEN: <TURBO_TOKEN>
```

Run the following command to run the application using docker-compose:

```sh
docker compose up -d
```

Run the following command to run the application using docker-compose:

```sh
localhost: 3000 for web
localhost: 3001 for docs
```

## What's inside?

This Turborepo includes the following packages/apps:

### Apps and Packages

- `docs`: a [Next.js](https://nextjs.org/) app
- `web`: another [Next.js](https://nextjs.org/) app
- `@repo/ui`: a stub React component library shared by both `web` and `docs` applications
- `@repo/eslint-config`: `eslint` configurations (includes `eslint-config-next` and `eslint-config-prettier`)
- `@repo/typescript-config`: `tsconfig.json`s used throughout the monorepo

Each package/app is 100% [TypeScript](https://www.typescriptlang.org/).