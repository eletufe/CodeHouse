## 2025-01-24 - Memoizing getCurrentUrl in BaseFacebook
**Learning:** In the Facebook PHP SDK, `getCurrentUrl()` is called frequently (e.g., in `getLoginUrl()`, `getLogoutUrl()`, `getLoginStatusUrl()`, and `getAccessTokenFromCode()`). This method performs several expensive operations including `parse_url()`, string manipulations, and multiple helper method calls. Memoizing the result within the request lifecycle significantly reduces redundant processing.
**Action:** Always check for frequently called utility methods that derive state from superglobals or environment variables which are unlikely to change during a single request.

## 2025-01-24 - PHP 8 Compatibility: implode() Argument Order
**Learning:** PHP 8+ is strict about the argument order for `implode()`. The legacy `implode($array, $glue)` format now throws a `TypeError`. The SDK was using the old format in `getCurrentUrl()`, causing crashes in PHP 8.3.6.
**Action:** When working with older PHP codebases on modern PHP runtimes, proactively check `implode()` and `explode()` calls for argument order and type compatibility.
