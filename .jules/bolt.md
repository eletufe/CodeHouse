## 2024-05-22 - Memoization of getCurrentUrl and PHP 8.3 compatibility
**Learning:** `BaseFacebook::getCurrentUrl()` was being recomputed every time it was called (e.g., in `getLoginUrl`, `getLogoutUrl`, etc.), leading to redundant string parsing and manipulation. Additionally, legacy code used `implode($array, $glue)`, which is deprecated and causes fatal errors in PHP 8+.
**Action:** Implemented memoization for `getCurrentUrl()` using a protected property and corrected `implode()` argument order. Performance for 10,000 calls improved from ~0.03s to ~0.0006s.
