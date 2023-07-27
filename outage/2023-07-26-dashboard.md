## Foundries.io dashboard and resources not available

We are experiencing on outage on our resources:
* app.foundries.io is not available
* docs.foundries.io is not available
  
Our internal user management database is not reachable and this might cause disruptions on other resources as well.

We are investigating and monitoring the issue.

### Timeline of Events

* **14:48 UTC** - Our monitoring system reported an issue with app.foundries.io not being reachable.
* **15:06 UTC** - Our resources are back online, we are still investigating the origin of the outage.

### What Happened

Our organization experienced an incident related to Google Compute Engine (GCE) resources exhaustion in the us-central region.
The incident resulted in increased resource utilization and degraded performance for our services hosted on the affected virtual machines (VMs).

However, the situation was resolved through an automatic self-recovery process initiated by Google Cloud Platform (GCP) services.
