Note for [Chapter 6](https://mostly-adequate.gitbooks.io/mostly-adequate-guide/ch06.html)

- There are both pure and inpure parts in a project.

- Usage of `compose`

```JavaScript
// get "m" property from "media" property from input
const mediaUrl = compose(prop('m'), prop('media'));
```

- Curry functions with multi params from common javaScript library such as `JQuery`

```JavaScript
const getJSON = curry((callback, url) => $.getJSON(url, callback));
const setHtml = curry((sel, html) => $(sel).html(html));
```

- Optimization of `compose` and `map`

```JavaScript
// two loops in left side, one loop in right side
compose(map(f), map(g)) === map(compose(f, g));
```