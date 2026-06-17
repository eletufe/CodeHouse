## 2025-01-24 - PHP 8 Compatibility: `implode()` Argument Order
**Learning:** In PHP 8.0+, the `implode()` function no longer supports passing arguments in either order. The signature must be `($separator, $array)`. Legacy code using `($array, $separator)` will trigger a `TypeError`.
**Action:** Always ensure `implode()` calls use the `($separator, $array)` order, especially when working with older codebases being run on modern PHP versions.

## 2025-01-24 - Memoization for URL Reconstruction
**Learning:** `getCurrentUrl()` in the Facebook SDK was reconstructing the URL string from `$_SERVER` and class properties on every call. In a single request, this URL is effectively constant.
**Action:** Use a protected property to cache the result of expensive string manipulations and property lookups that are known to be idempotent within a single request.
