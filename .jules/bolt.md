## 2026-01-08 - Memoize getCurrentUrl and fix PHP 8 compatibility
**Learning:** Found that `BaseFacebook::getCurrentUrl()` is called multiple times per request but performs the same expensive URL parsing and rebuilding each time. Also discovered a PHP 8 compatibility issue where `implode()` arguments were in the legacy order, causing fatal errors.
**Action:** Implement memoization for `getCurrentUrl()` and correct the `implode()` argument order.
