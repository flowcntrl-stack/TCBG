# The Creative Business Group Website

This repository contains the approved production website for The Creative Business Group.

## Current Status

The site has moved from mock/development status to an approved production client website.

The client approved the current website and requested that the primary domain point to this Coolify-hosted version.

## Live Domains

- Primary domain: https://thecreativebusinessgroup.com
- WWW domain: https://www.thecreativebusinessgroup.com
- Coolify staging/origin domain: https://tcbg.creativeflow.one

## Repository

- Repository: `flowcntrl-stack/TCBG`
- Branch: `main`
- Main entry file: `index.html`
- Site type: static HTML/CSS/JS
- Deployment target: Coolify

## Deployment Notes

The production site is deployed through Coolify on the CreativeFlow infrastructure.

Coolify app domains should include:

```text
https://tcbg.creativeflow.one
https://thecreativebusinessgroup.com
https://www.thecreativebusinessgroup.com
```

The TCBG domain is managed through Genesis / DomainControl DNS.

Current DNS authority was verified in the Genesis DNS management console. The domain uses DomainControl nameservers:

```text
ns13.domaincontrol.com
ns14.domaincontrol.com
```

The domain cutover was completed by pointing the web records toward the Coolify-hosted site while preserving Microsoft 365 mail records.

## DNS Safeguards

Do not remove or modify Microsoft 365 records unless intentionally changing email services.

Preserve records related to:

- MX
- TXT / SPF
- autodiscover
- msoid
- lyncdiscover
- sip
- SRV records

Only web records should be adjusted for hosting changes, such as:

- root / `@`
- `www`

## Recent Production Updates

- Client approved the current website.
- Domain authority was verified through Genesis / DomainControl.
- The primary domain was pointed to the Coolify-hosted site.
- SSL/domain configuration was validated enough for the site to load live.
- Footer credit was added:
  - Site designed by CreativeFlow.One.
  - Business logic engineered by Batch One Processing.

Latest relevant footer commit:

```text
d0cb169be6bef61cec40e23fb567df042e8b0adb
```

## Known Deployment Note

A later Coolify redeploy attempt encountered a Git fetch/clone transport failure before build completion. The failure appeared to be a Coolify/GitHub transfer issue, not an HTML/footer-code issue.

Observed error pattern:

```text
RPC failed / unexpected disconnect / early EOF
```

The running production app was not intentionally stopped during that failure.

If this occurs again:

1. Do not stop the running app.
2. Confirm the app still shows Running.
3. Wait for the failed deployment to settle.
4. Retry redeploy once later.
5. If repeated, troubleshoot Coolify Git fetch, GitHub connectivity, helper container state, or repository size/assets.

## Content Features

The website includes:

- Hero section
- Slideshow imagery
- TCBG Method video section
- About / purpose section
- Services cards
- Audience cards
- Process section
- Payment portal link
- Contact section
- Footer credit for CreativeFlow.One and Batch One Processing

## Footer Credit

Client footer should remain tasteful and minimal:

```text
Site designed by CreativeFlow.One. Business logic engineered by Batch One Processing.
```

Do not add CreativeFlow or Batch One email addresses to the client footer unless specifically approved. Provider contact details should live on the provider websites, not the client site.

## Maintenance Checklist

Before marking production updates complete:

- [ ] Confirm `thecreativebusinessgroup.com` loads
- [ ] Confirm `www.thecreativebusinessgroup.com` loads
- [ ] Confirm SSL lock is present
- [ ] Confirm images load
- [ ] Confirm video section loads
- [ ] Confirm payment link opens
- [ ] Confirm contact section displays correctly
- [ ] Confirm footer credit appears
- [ ] Confirm Microsoft 365 email records remain intact

## Related Ecosystem

- CreativeFlow.One: https://www.creativeflow.one
- Batch One Processing: https://batchoneprocessing.com
- The Level Standard Industrial Collective: pending TLS landing page
