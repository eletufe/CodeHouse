## 2025-05-15 - [PHP 8.3 Compatibility & Memoization]
**Learning:** PHP 8.3+ strictly requires `implode($glue, $array)` argument order. Legacy PHP allowed `implode($array, $glue)`. Also, `BaseFacebook::getCurrentUrl()` is called multiple times (e.g., in `getLoginStatusUrl`), making it a prime candidate for memoization.
**Action:** Always check `implode()` calls in legacy PHP codebases. Use memoization for expensive URL reconstruction methods that depend on static request data.
