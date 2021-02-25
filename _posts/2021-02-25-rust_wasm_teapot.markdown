---
layout: post
title:  "Rust -> WebAssembly"
date:   2021-02-25 08:01:44 -0400
categories: jekyll update
---
OK, time for another teapot. This one is a combination of the two in
[this earlier post](https://rustytriangles.github.io/jekyll/update/2020/05/01/teapots.html). The code
which creates the geometry of the teapot is copied from the Rust example, and the code which does the
rendering is copied from the WebGL example.

But how do they work together? Rust compiles to native, and WebGL is only available in a browser or in
something like [electron](https://www.electronjs.org/). The trick is something calle [wasm-pack](https://rustwasm.github.io/wasm-pack/book/). This compiles the Rust code to WebAssembly. Then you can use that as
a module you can call from JavaScript.

![Teapot]({{site.baseurl}}/images/rust_wasm_teapot_screenshot.png)

Connecting the two is surprisingly simple. You just mark the functions and types you want to
expose to javascript with the `wasm_bindgen` macro and then you can `import` them in your JS code.

The source is [here](https://github.com/rustytriangles/rust-wasm-teapot). You can run it from [github pages](https://rustytriangles.github.io/rust-wasm-teapot/).
