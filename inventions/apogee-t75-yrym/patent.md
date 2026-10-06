# Adaptive API Rate Limiting With Content Fingerprinting For Scraping Detection

## Abstract
A system for preventing unauthorized scraping and mirroring of social media posts uses adaptive rate limiting combined with per-post content fingerprinting at the API layer. Requests exceeding dynamic thresholds trigger fingerprint comparison against known mirror patterns. The invention operates in firmware on API servers to block or throttle sources without external legal action.

## Problem
Nitter and XCancel scraped and mirrored tweets at scale, bypassing static rate limits and simple IP blocks. Legal cease-and-desist letters provided only reactive shutdowns after damage occurred. No built-in mechanism detected systematic content duplication or adapted throttling based on behavioral fingerprints of requests.

## Prior art
- US11372937B1: Rate limiting for API requests; this invention differs by adding real-time content fingerprinting and adaptive thresholds tied to duplication detection rather than fixed quotas alone.
- US11783583B2: Digital fingerprinting of media content for mirror detection; this invention differs by integrating fingerprints directly into live API request handling for immediate blocking of tweet text and metadata mirrors.

## Summary of the invention
The system embeds a fingerprint generator and comparator in the API request handler. Each tweet response includes a hash computed from normalized text, timestamp, and user ID. Incoming scrapers receive fingerprints that are logged and compared. Exceeding thresholds causes source isolation via token revocation or connection reset.

## Claims
1. A method for preventing scraping comprising: receiving an API request for a post (12); computing a fingerprint (14) of the post content using SHA-256 on normalized text plus metadata; logging the fingerprint against the requester identifier (16); comparing the logged fingerprints to a mirror pattern database (18); and if matches exceed 50 within a 300-second window, applying a throttle of at most 10 requests per minute to the requester.
2. The method of claim 1, further comprising revoking the authentication token of the requester upon exceeding the match threshold.
3. The method of claim 1, wherein the fingerprint (14) normalizes whitespace and lowercases text before hashing.
4. The method of claim 1, wherein the mirror pattern database (18) stores fingerprints from known mirror sites updated every 3600 seconds.
5. The method of claim 1, further comprising resetting the connection after three consecutive throttled requests from the same IP range.
6. The method of claim 1, wherein the throttle window resets after 1800 seconds of inactivity.

## Brief description of the drawings
FIG. 1 shows the API request path with fingerprint module and comparator.

## Detailed description
An incoming GET request for post (12) arrives at API server (20). Fingerprint module (22) normalizes the post text by removing URLs and lowercasing, then computes SHA-256 hash as fingerprint (14). Requester identifier (16) is extracted from the auth token or IP subnet. Comparator (24) queries mirror pattern database (18) for prior matches. If 50 or more identical fingerprints appear from the same identifier (16) in any 300-second interval, rate limiter (26) caps the source at 10 requests per minute. Token store (28) revokes the key after three violations. Database (18) refreshes from internal crawler logs every 3600 seconds. Failure mode of hash collision is mitigated by requiring exact 256-bit match plus metadata check. Connection reset occurs via TCP RST packet from limiter (26) after sustained excess. All thresholds are configurable via firmware parameters stored in non-volatile memory on server (20). Every reference numeral appears in FIG. 1.