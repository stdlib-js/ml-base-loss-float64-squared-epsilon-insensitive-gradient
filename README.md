<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# squaredEpsilonInsensitiveGradient

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Compute the squared epsilon insensitive loss gradient with respect to a model parameter.

<section class="intro">

The squared epsilon insensitive loss gradient is defined as

<!-- <equation class="equation" label="eq:squared_epsilon_insensitive_loss_gradient" align="center" raw="\frac{\partial \ell}{\partial w_i} = \begin{cases} -2((y - p) - \epsilon)x_i & \text{if } y - p > \epsilon, \\2((p - y) - \epsilon)x_i & \text{if } p - y > \epsilon, \\0 & \text{otherwise.}\end{cases}" alt="Equation for the squared epsilon insensitive loss gradient."> -->

```math
\frac{\partial \ell}{\partial w_i} =
\begin{cases}
-2((y - p) - \epsilon)x_i & \text{if } y - p > \epsilon, \\
2((p - y) - \epsilon)x_i & \text{if } p - y > \epsilon, \\
0 & \text{otherwise.}
\end{cases}
```

<!-- </equation> -->

</section>

<!-- /.intro -->



<section class="usage">

## Usage

<!-- eslint-disable id-length -->

```javascript
import squaredEpsilonInsensitiveGradient from 'https://cdn.jsdelivr.net/gh/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient@esm/index.mjs';
```

#### squaredEpsilonInsensitiveGradient( x, e, y, p )

Computes the squared epsilon insensitive loss gradient with respect to a model parameter.

<!-- eslint-disable id-length -->

```javascript
var v = squaredEpsilonInsensitiveGradient( 3.0, 5.0, 10.2, 0.782 );
// returns ~-26.508

v = squaredEpsilonInsensitiveGradient( -1.3, 1.0, 23.2, -0.999 );
// returns ~60.317
```

The function accepts the following arguments:

-   **x**: input value.
-   **e**: insensitivity parameter.
-   **y**: true target value.
-   **p**: predicted value.

If any argument is `NaN`, the function returns `NaN`.

<!-- eslint-disable id-length -->

```javascript
var v = squaredEpsilonInsensitiveGradient( NaN, 1.0, 1.0, 0.782 );
// returns NaN

v = squaredEpsilonInsensitiveGradient( 1.0, 1.0, NaN, 0.782 );
// returns NaN

v = squaredEpsilonInsensitiveGradient( NaN, NaN, 1.0, 0.782 );
// returns NaN

v = squaredEpsilonInsensitiveGradient( NaN, NaN, NaN, NaN );
// returns NaN
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint-disable id-length -->

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="module">

import uniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-array-uniform@esm/index.mjs';
import logEachMap from 'https://cdn.jsdelivr.net/gh/stdlib-js/console-log-each-map@esm/index.mjs';
import squaredEpsilonInsensitiveGradient from 'https://cdn.jsdelivr.net/gh/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient@esm/index.mjs';

var x = uniform( 100, -100.0, 100.0, {
    'dtype': 'float64'
});
var e = uniform( 100, 0.0, 5.0, {
    'dtype': 'float64'
});
var y = uniform( 100, -100.0, 100.0, {
    'dtype': 'float64'
});
var p = uniform( 100, -5.0, 5.0, {
    'dtype': 'float64'
});

logEachMap( 'squaredEpsilonInsensitiveGradient(%0.4f, %0.4f, %0.4f, %0.4f) = %0.4f', x, e, y, p, squaredEpsilonInsensitiveGradient );

</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->



<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ml-base-loss-float64-squared-epsilon-insensitive-gradient.svg
[npm-url]: https://npmjs.org/package/@stdlib/ml-base-loss-float64-squared-epsilon-insensitive-gradient

[test-image]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/tree/deno
[deno-readme]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/tree/umd
[umd-readme]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/tree/esm
[esm-readme]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ml-base-loss-float64-squared-epsilon-insensitive-gradient/main/LICENSE

</section>

<!-- /.links -->
