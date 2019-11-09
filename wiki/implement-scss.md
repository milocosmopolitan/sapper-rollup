```bash
npm i -D autoprefixer node-sass svelte-preprocess
```

svelte.config.js
```js
const sveltePreprocess = require('svelte-preprocess');

const preprocess = sveltePreprocess({
  scss: {
    includePaths: ['src'],
  },
  postcss: {
    plugins: [require('autoprefixer')],
  },
  // ...
});

```

rollup.config.js
```js
const svelteOptions = require("./svelte.config");

export default {
	client: {
    plugins: [
      svelte({
        ...svelteOptions,
        // ...
      })
    ]
  },

  server: {
    plugins: [
      svelte({
        ...svelteOptions,
        // ...
      })
    ]
  },
  // ...
}
```