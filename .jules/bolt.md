## 2026-01-20 - Memoization and PHP 8 compatibility in Facebook SDK
**Learning:** The Facebook PHP SDK (v3.2.2) uses legacy PHP patterns (like incorrect `implode()` argument order) that cause fatal errors in PHP 8.3. Additionally, `getCurrentUrl()` is a redundant bottleneck called by multiple URL generation methods.
**Action:** Always verify library compatibility when running in modern PHP environments. Use memoization for expensive URL/environment-based computations that don't change during a request.
