**Archived**

Redirect: Please go to https://github.com/claudepache/es-legacy-function-reflection

## Motivation

This code is evaluated differently in Chrome, Safari, Firefox and Edge.

```js
function getOwnPropertyDescriptor() {
  console.log("caller", getOwnPropertyDescriptor.caller);
}

var p = new Proxy({ a: "test" }, { getOwnPropertyDescriptor });

function test() {
  "use strict";
  return Reflect.getOwnPropertyDescriptor(p, "a");
}

test();
```

<details>
<summary>Evaluation result</summary>

Chrome and Safari: <img src="./chrome.png" /><br />
Firefox: <img src="./firefox.png" /><br />
Edge: <img src="./edge.png" /><br />

</details>
