# org-chart

## Project setup
```
yarn install
```

## Compiles and hot-reloads for development
```
yarn dev
```

## Lints and fixes files
```
yarn lint
```

### Build for production
```
yarn build
```

After running the command above, a new folder `dist` will be generated, with the compiled component bundled with Vue as `org-chart.js` and `org-chart.min.js`.

To use the component, add the following script tag:

```
<script src="path/to/org-chart(.min).js"></script>
```

Then the component can be used as a normal DOM element:

```
<org-chart url="org-data-url" />
```

> Vue is bundled with the component, so do not add a script tag for Vue.
> To avoid this behaviour, change the build script in `package.json` to `vue-cli-service build --target wc --name org-chart` (remove the `--inline-vue` option)

Refer to `dist/demo.html` for a demo (line 3 should be removed!).
