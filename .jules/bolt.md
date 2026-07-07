## 2025-05-15 - Legacy SDK PHP 8.3 Compatibility & Memoization
**Learning:** Legacy PHP SDKs (like Facebook v3.2.2) often use `implode($array, $glue)`, which causes a fatal TypeError in PHP 8.3. Also, methods like `getCurrentUrl` that parse global `$_SERVER` state are significant bottlenecks when called repeatedly in a single request.
**Action:** Always check `implode` argument order when working with older PHP codebases. Implement property-based memoization for expensive state-parsing methods to achieve ~95% performance gains in hot paths.
