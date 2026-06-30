## 2026-01-07 - [PHP 8 Compatibility: implode() Argument Order]
**Learning:** PHP 8+ strictly requires the `($separator, $array)` argument order for `implode()`. Legacy code using the old `($array, $separator)` signature will throw a fatal `TypeError` in PHP 8.
**Action:** Always check `implode()` calls in older PHP projects when running on PHP 8+.

## 2026-01-07 - [Memoization: BaseFacebook::getCurrentUrl()]
**Learning:** `BaseFacebook::getCurrentUrl()` is called multiple times by methods like `getLoginUrl`, `getLogoutUrl`, and `getLoginStatusUrl`. In this SDK version, it doesn't cache the result, leading to redundant URL parsing and string manipulation.
**Action:** Use a simple property-based memoization to cache the result of `getCurrentUrl()` within the request lifecycle.
