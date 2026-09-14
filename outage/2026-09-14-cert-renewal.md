## 2026-09-14 Foundries Web Dashboard certificate failure

Certificates failed to renew on 2026-09-13 and therefore a downtime was experienced for our web dashboard and admin pages.

### Timeline of Events
- **2026-09-13 14:14 UTC** – Certificate expired.
- **2026-09-14 07:52 UTC** – First noticed certificate expired.
- **2026-09-14 08:24 UTC** – Manual fix for app.foundries.io deployed.
- **2026-09-14 09:04 UTC** – Manual fix for admin.foundries.io deployed.
- **2026-09-14 09:11 UTC** – CronJob updated to mapping extended to missing domains.

### Impact
- Web dashboard and Admin Dashboard were fully unavailable for the duration of the certificate failing.
- `fioctl login` and OAuth token refresh also failed, since fioctl authenticates against app.foundries.io.

### Root cause

When moving away from the manual certificate renewal process to an automated CronJob, an oversight occurred and some domains were left out of a mapping.
That has been rectified, and a separate alert has been created to check if the CronJob is running successfully as well.

— The Foundries IO Team
