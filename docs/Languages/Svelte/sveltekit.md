## What is `sveltekit`?

[`Sveltekit`](https://kit.svelte.dev/) is a build tool and framework for building web applications with Svelte, a popular JavaScript framework for building user interfaces. It provides a set of conventions and tools for building and deploying Svelte apps, making it easier for developers to get started with Svelte and to build and maintain large-scale applications. Sveltekit offers features such as automatic code splitting, server-side rendering, and optimized asset handling, all designed to help you build fast, scalable, and user-friendly web applications.
## Project Structure
```
my-project/
├ src/
│ ├ lib/
│ │ ├ server/
│ │ │ └ [your server-only lib files]
│ │ └ [your lib files]
│ ├ params/
│ │ └ [your param matchers]
│ ├ routes/
│ │ └ [your routes]
│ ├ app.html
│ ├ error.html
│ ├ hooks.client.js
│ └ hooks.server.js
├ static/
│ └ [your static assets]
├ tests/
│ └ [your tests]
├ package.json
├ svelte.config.js
├ tsconfig.json
└ vite.config.js
```

