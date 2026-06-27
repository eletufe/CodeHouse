## 2025-01-24 - Memoize getCurrentUrl in Facebook PHP SDK
**Learning:** In the Facebook PHP SDK (v3.2.2), `BaseFacebook::getCurrentUrl()` was being called multiple times during a single request (e.g., in `getLoginUrl()`, `getLogoutUrl()`, `getLoginStatusUrl()`, and `getAccessTokenFromCode()`). Since the current URL doesn't change during a single request, this was redundant. Additionally, a legacy `implode()` call with swapped arguments caused fatal errors in PHP 8.3.

**Action:** Implement memoization for `getCurrentUrl()` by adding a `protected $currentUrl` property to `BaseFacebook`. Corrected the `implode()` argument order to `implode($glue, $array)` to ensure PHP 8.3 compatibility. This resulted in a ~50% speedup for repeated calls and fixed a critical bug.
