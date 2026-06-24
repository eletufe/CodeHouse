## 2024-05-23 - Memoization of getCurrentUrl in BaseFacebook
**Learning:** `getCurrentUrl()` performs multiple expensive operations (`getHttpProtocol`, `getHttpHost`, `parse_url`, and string reconstruction). In a single request lifecycle, this value is constant. Memoizing it provides a ~30x speed boost for repeated calls. However, in long-running PHP environments (Swoole/RoadRunner), this could lead to stale data if the instance is reused across requests.
**Action:** Use memoization for request-constant values in legacy PHP SDKs, but be mindful of persistent process environments.
>>>>>>> REPLACE
<<<<<<< SEARCH
## 2024-05-23 - PHP 8.3 `implode()` Argument Order
**Learning:** PHP 8.0+ enforces `($glue, $array)` order for `implode()`. Legacy code using `($array, $glue)` will throw a `TypeError`.
**Action:** Always verify `implode()` calls when working in PHP 8+ environments.
>>>>>>> REPLACE
