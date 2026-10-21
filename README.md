# supercomp-redirect

This repository only serves a Vercel edge redirect to the current site:

- `/ambassadors` → `https://supercomp.bucis.org/ambassador` (HTTP 308 permanent redirect)
- `/:path*` → `https://supercomp.bucis.org/:path*` (HTTP 308 permanent redirect)

## SEO behavior

- Redirect responses include `X-Robots-Tag: noindex, follow` so crawlers should not keep indexing this redirect host with stale snippets/titles.
- The visible search title for users is ultimately controlled by the destination site metadata, not this redirect repository.
- Because this is a permanent redirect, Google may still need re-crawling/re-indexing time before stale labels (such as old event names) disappear.

If search results still show outdated text, request re-indexing in Google Search Console for both the redirect URL and destination URL.
