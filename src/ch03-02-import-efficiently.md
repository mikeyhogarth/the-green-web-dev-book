# Import efficiently

Ensure that you're importing modules efficiently. You might be unknowingly increasing your build times and serving your users a ton of JavaScript that will never be executed, increasing the energy footprint of your website.

## Example: Importing Lodash

[Lodash](https://lodash.com/) is a popular utility library which provides a collection of useful functions for working with JavaScript. You would be correct in thinking that the following import strategy would be wasteful because it would import the whole Lodash library, even if you are only using a small part of it:

```
import _ from "lodash";
console.log(_.capitalize("hello world"));
```

Where many people go wrong though, is in the belief that the following code solves this problem;

```
import { capitalize } from "lodash";
console.log(capitalize("hello world"));
```

In fact, **this is not true**. Both of the above two imports will result in the entire `lodash` library being imported into your bundle and served to the user. It is possible for bundlers such as webpack to [use tree-shaking to throw away dead code](https://webpack.js.org/configuration/optimization/), however this feature is normally turned off by default (the reason being that the module may have side-effects that run on import, so it's not safe just to throw code away without asking!).

So what is the solution? In the case of Lodash, the developers have split their functionality up into _categories_ and you can reduce your bundle size by importing only from the category you are using:

```
import { capitalize } from "lodash/string";
```

Alternatively for an even smaller bundle you can import only the particular function you are using:

```
import capitalize from "lodash/capitalize";
```

## Prevention

Whilst the above example is lodash-specific, the principle of importing efficiently holds true for any module you import. Unfortunately there is no "one size fits all" strategy for dealing with this issue as it depends very much on the implementation of the module you are importing - popular UI component library [MUI](https://mui.com/), for example, has [a completely different approach to minimizing bundle sizes](https://mui.com/guides/minimizing-bundle-size/).

There is therefore no single thing you can do which will cover off all of your imports, but one thing you _can_ do is ensure that you are no longer making assumptions about what does/doesn't make things more efficient through the use of **tools**.

One such tool is the [Import Cost VSCode extension](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost) by Wix. Install this into your editor and it will display the import cost for each module in your codebase. This means you will never make assumptions about what is/isn't an efficient import ever again!

## Relevant Links

- [MDN pages covering ES6 imports](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [Google article about Tree Shaking](https://developers.google.com/web/fundamentals/performance/optimizing-javascript/tree-shaking)
