## 2025-01-24 - PHP 8.3 `implode()` Compatibility and Memoization in Facebook SDK
**Learning:** In PHP 8.3, `implode($array, $glue)` throws a TypeError. It must be `implode($glue, $array)`. Also, `BaseFacebook::getCurrentUrl()` is called multiple times per request (e.g., in `getLoginStatusUrl`), making it a good candidate for memoization.
**Action:** Fix `implode()` calls and add a protected property to cache the result of `getCurrentUrl()`.
