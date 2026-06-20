## 2026-01-07 - [PHP 8 Compatibility and Memoization]
**Learning:** In PHP 8.0+, `implode()` strictly requires the `($glue, $array)` argument order. Legacy calls using `($array, $glue)` throw a `TypeError`. Additionally, `getCurrentUrl()` in the Facebook SDK was a bottleneck for repeated calls due to redundant parsing and filtering of query parameters.
**Action:** Always verify `implode()` argument order when working with legacy PHP code on PHP 8+. Apply memoization to methods that perform URL reconstruction or heavy string manipulation if they are called multiple times in a request.
