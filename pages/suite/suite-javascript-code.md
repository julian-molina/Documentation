---
title:  JavaScript Code
summary: "The system runs code through the eval() function and does not impose any constraints."
sidebar: suite_sidebar
permalink: suite-javascript-code.html
---

You may use any valid piece of JavaScript code for your conditions and formulas. The system imposses no contraints whatsoever. The code on conditions and formulas is run through the ```eval()``` function, as follows:

```js
try {
    let code = node.code
    value = eval(code);
    addCodeToSnapshot(code)
}
```

{% include tip.html content="Remember that all conditions must evaluate to ```true``` or ```false``` and that formulas must evaluate to a number." %}