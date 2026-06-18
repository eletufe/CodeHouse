## 2025-01-24 - [PHP 8.0 Compatibility and Memoization]
**Learning:** Found that legacy PHP code (Facebook SDK v3) used `implode($array, $glue)` which is a Fatal Error in PHP 8.0+. Also, frequent parsing of `$_SERVER` data in `getCurrentUrl()` is a significant bottleneck that can be easily solved with memoization.
**Action:** Always verify `implode` argument order when working on legacy PHP code. Use property-based caching for methods that derive data from `$_SERVER` or other immutable request-state variables.
