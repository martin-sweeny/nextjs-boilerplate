# Next.js App

## Development

This is repo is based off of the [Next.js typescript template](https://github.com/vercel/next.js/tree/master/packages/create-next-app/templates/typescript) and the [Next.js Typescript with SSR example](https://github.com/vercel/next.js/tree/master/examples/custom-server-typescript). It is designed to be run with [Lando](https://lando.dev) (a tool to give Docker Compose superpowers), but you can run this without that, and just use Docker Compose.

[pnpm](https://pnpm.io) is used, since it's faster and more strict about dependency linking.

Code linting is enforced and opinionated, mostly to reduce polluted PR diffs.

### With Lando (preferred)

Required:

- [Docker](https://docker.com)
- [Lando](https://lando.dev)

Start up the container with:
```bash
lando start
```

Then, to begin development, run:
```bash
lando dev
```

### Tooling

Some tooling is built-in:

-
    **Upgrade dependencies**

    ```bash
    lando update-deps
    ```

    This will use [`npm-check-updates`](https://www.npmjs.com/package/npm-check-updates) to get the latest versions of the project's deps, then will install them.
-
    **Clean out the project**

    ```bash
    lando cleanup
    ```

    Removes the `.next`, `.pnpm-store`, `cache`, and `node_modules` directories from the project root. It's generally a good idea rebuild your containers after this.

-
    **Linting**

    ```bash
    lando lint
    ```

    This will run `prettier --write` on the `pages`, and `server` directories