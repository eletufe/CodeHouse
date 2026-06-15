## 2025-05-14 - [PHP 8 compatibility and memoization]
**Learning:** Found that legacy PHP code often uses `implode($array, $glue)`, which is a TypeError in PHP 8+. Also, `getCurrentUrl()` type methods are frequently called but expensive due to string manipulation and superglobal access.
**Action:** Always verify `implode` argument order in PHP codebases. Memoize results of URL reconstruction methods to save ~97% of execution time on subsequent calls.
