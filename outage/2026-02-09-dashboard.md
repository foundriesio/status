## 2026-02-09 Foundries dashboard partially unavailable

Around 11:20 UTC, our customer dashboard experienced some disruptions.

### Timeline of Events
- **2025-02-09 11:20 UTC** – New dashboard version was deployed.
- **2025-02-09 11:28 UTC** – First reports of server errors by our users.
- **2025-02-09 12:03 UTC** – Errors found and investigation started.
- **2025-02-09 12:15 UTC** – Fix implemented and new deployment started.
- **2025-02-09 12:26 UTC** – All dashboard funcionalities restored.

### Impact
- Browsing Factories and Factories resources was impacted.
- User settings pages were not impacted.

### Root cause

In preparation for new features planned for Foundries dashboard, we deployed a new
database connection that relies on new configuration parameters.

The new configuration parameters were not deployed before the completion of the
dashboard deployment, but soon after. We also discovered that there was a typo in
one of the configuration parameter.

Once the configuration was fixed and we made sure it was correctly available to the
dashboard, we restarted the system to restore all funcionalities.

— The Foundries IO Team
