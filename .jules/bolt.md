## 2025-05-15 - [Memoization and PHP 8 Compatibility]
**Learning:** Found that `BaseFacebook::getCurrentUrl()` was a hotspot as it was called multiple times per request to reconstruct the current URL from `$_SERVER`. Also discovered that PHP 8+ is strict about `implode()` argument order, which was causing crashes in this legacy codebase.
**Action:** Implemented memoization for `getCurrentUrl()` and fixed the `implode()` argument order. Always verify legacy PHP code with modern PHP runtimes as some previously deprecated behaviors are now fatal errors.
