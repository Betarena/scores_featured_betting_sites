# scores

### Betarena Scores Platform - FEATURED BETTING SITES WIDGET

![betarena-loading-2](https://user-images.githubusercontent.com/20924663/149849423-3090443b-0bfb-4983-b06b-49c4b2b2fd95.gif)

### Features

- [x] Darkmode
- [x] Real-time Data from DB
- [x] Minimal Library Use

### About

This is a `public` repository for the `featured_match` widget for the `Betarena - Platform`.

### Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

### Building

Before creating a production version of your app, install an [adapter](https://kit.svelte.dev/docs#adapters) for your target environment. Then:

```bash
npm run build
```

> You can preview the built app with `npm run preview`, regardless of whether you installed an adapter. This should _not_ be used to serve your app in production.

### GraphQL Support

For the ability to use `GraphQL` for the Widget in Svelte, `graphql-request` was utilized - [package](https://www.npmjs.com/package/graphql-request)

`@apollo-client` does not work correctly with `sveltekit` [1](https://github.com/timhall/svelte-apollo/issues/97)
**solution**: using `graphql-request` instead.

### localStorage()

The widget stores the users `one-off` voting using the `.localStorage()` for the ability to give the user a history of past votings.

### using .env with sveltekit-vite:

[exmaple](https://dev.to/danawoodman/storing-environment-variables-in-sveltekit-2of3)

### Getting started with `sveltekit`:

Some useful links used to get familiar with `sveltekit` and the correct knownledge required for the `development`:

- [a-beginners-guide-to-sveltekit](https://www.sitepoint.com/a-beginners-guide-to-sveltekit/)
