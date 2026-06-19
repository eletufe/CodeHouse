## 2025-01-24 - [Memoization & PHP 8 Compatibility]
**Learning:** In PHP 8+, `implode()` strictly requires the `($glue, $array)` argument order; the legacy `($array, $glue)` order now throws a `TypeError`. Additionally, `BaseFacebook::getCurrentUrl()` is a high-traffic method involving string parsing and array filtering, making it an ideal candidate for memoization within the request lifecycle.
**Action:** Always check `implode` calls when modernizing legacy PHP code and apply memoization to deterministic URL-rebuilding logic that is called multiple times per request.
