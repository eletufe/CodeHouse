## 2025-05-15 - [Facebook SDK PHP 8.3 compatibility and memoization]
**Learning:** Legacy PHP code (Facebook SDK v3.2.2) often uses `implode($array, $glue)` which is deprecated and throws a Fatal Error in PHP 8.3+. Methods like `getCurrentUrl()` are called multiple times (e.g., for login, logout, and status URLs) and benefit significantly from memoization.
**Action:** Always check `implode` argument order when working with older PHP codebases and apply memoization to shared utility methods that perform redundant string/URL parsing.
