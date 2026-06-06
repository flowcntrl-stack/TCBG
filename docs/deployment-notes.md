# TCBG Deployment Notes

## Commercial Video Recovery — 2026-06-05

The TCBG commercial video was restored after the previous Bunny/Mediadelivery-hosted embed became unavailable.

Current production approach:
- The optimized web video is served from the Coolify-hosted site.
- Expected public path: `/assets/TCBG-commercial-web-optimized-720p.mp4`
- The source QuickTime/iMovie `.mov` should be preserved separately as the master asset.
- The website index uses a native HTML5 `<video>` player instead of the previous Bunny iframe.

Recovery notes:
- A source QuickTime/iMovie `.mov` was uploaded and treated as the source/master.
- A web-optimized MP4 was produced for browser playback.
- The stale Bunny/Mediadelivery iframe was replaced in `index.html`.
- A 404 was traced to an asset path mismatch after deployment.
- Playback was confirmed working after the production asset was available under `/assets/`.

Pending:
- DNS control-point discovery
- Domain record swing planning
- Permanent media hosting decision if Coolify-local delivery is later replaced by CDN hosting

## DNS Migration Safety Notes

Before changing DNS records, capture the current records and nameservers.

Do not modify mail or verification records unless specifically required:
- MX
- SPF
- DKIM
- DMARC
- domain verification TXT records

Website migration should normally focus on the website-facing records only:
- root / apex A record
- `www` A or CNAME record
