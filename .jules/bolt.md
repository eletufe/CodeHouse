## 2025-01-24 - Memoization and PHP 8.3 Compatibility in Facebook SDK
**Learning:** Legacy PHP SDKs (like Facebook v3.2.2) may contain `implode()` calls with legacy argument ordering `implode($array, $glue)` which is a fatal error in PHP 8.3. Additionally, frequently called utility methods like `getCurrentUrl()` often lack memoization, leading to redundant string manipulations and URL parsing.
**Action:** Always check `implode()` argument order when working with legacy PHP code on PHP 8+. Apply memoization to idempotent methods that involve expensive string or URI processing.
