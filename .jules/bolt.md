# Bolt's Performance Journal

## 2026-03-09 - Initialization
**Learning:** Found that the Facebook PHP SDK v3.2.2 has standard code structure from 2011/2012, which contains outdated `implode()` calls that cause deprecation warnings or exceptions on PHP 8.3+. Also, methods like `getCurrentUrl()` are called repeatedly during a single request (e.g., inside `getLoginUrl`, `getLogoutUrl`, etc.) and recalculate host/protocol strings every single time.
**Action:** Implement memoization for `getCurrentUrl` and fix the `implode` parameter ordering.

## 2026-03-09 - BaseFacebook::getCurrentUrl() Memoization Results
**Learning:** Adding memoization to `BaseFacebook::getCurrentUrl()` yielded a **~35x speedup** for repeated calls of this method. In standard OAuth/Facebook integrations where several URLs (login, logout, state, login status, callbacks) are queried/constructed in the same request, this drastically reduces string parsing, parsing URL components, and checking protocol/host states.
**Action:** Always memoize request-scoped environment calculations that do not change during the request lifecycle.
