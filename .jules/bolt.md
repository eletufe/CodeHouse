# Bolt's Performance Journal

## 2026-06-15 - Facebook SDK URL Reconstruction Bottleneck
**Learning:** `BaseFacebook::getCurrentUrl()` is called multiple times during login, logout, and status URL generation, but it parses the protocol, host, and query parameters on every single invocation. This can be significantly optimized with request-level memoization. Additionally, legacy calls to `implode()` with backwards-ordered arguments causes fatal errors on PHP 8+.
**Action:** Always memoize `getCurrentUrl()` and correct PHP 8+ argument ordering for string utilities.
