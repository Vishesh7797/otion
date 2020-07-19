# react-otion

Server-side React bindings for otion, the atomic CSS-in-JS library.

## Usage

Install the library and its bindings with a package manager of choice, e.g.:

```shell
npm install otion react-otion
```

### Server-side rendering

A special renderer is available for instantiating `<style>` JSX elements on the server, as seen in the [Next.js example](https://github.com/kripod/otion/tree/main/packages/example-nextjs):

```js
import { setup } from "otion";
import { getStyleElement, VirtualInjector } from "react-otion/server";

const injector = VirtualInjector();
setup({ ...sharedOptions, injector });

// The resulting HTML code could be used for critical CSS extraction
renderToString(rootElement);

const styleElement = getStyleElement(injector);
setHeadComponents(styleElement);
```

All [methods of `otion/server`](https://github.com/kripod/otion/tree/main/packages/otion#server-side-rendering) are re-exported for convenience, as seen in the previous snippet.

### Single-page applications

This package is not necessary for single page React applications, e.g. those built with [Create React App](https://github.com/facebook/create-react-app).
