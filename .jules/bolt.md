## 2025-05-22 - Memoization of getCurrentUrl in Facebook SDK

**Learning:** `BaseFacebook::getCurrentUrl()` is used extensively throughout the SDK (login, logout, token exchange) and involves multiple `$_SERVER` lookups, `parse_url`, and string manipulations. In PHP 8.3, these operations are relatively fast but redundant when called multiple times in a single request.

**Action:** Implement memoization for `getCurrentUrl()` to ensure it only calculates the URL once per instance.
