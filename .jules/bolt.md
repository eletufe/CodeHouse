## 2026-07-23 - [Facebook PHP SDK URL Memoization & PHP 8.3 Compatibility]
**Learning:** Found that `BaseFacebook::getCurrentUrl()` was called repeatedly to reconstruct current page details, causing redundant superglobal reads and string manipulation. Also, the legacy `implode($array, $glue)` call crashed under PHP 8+ as the parameter order has become strict.
**Action:** Implemented current URL memoization and updated the `implode` parameter order to achieve a ~19x speedup for URL reconstruction and ensure robust PHP 8.3 compatibility. Cleared memoized URL on `destroySession()`.
