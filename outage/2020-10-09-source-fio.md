## source.foundries.io Disruption

### Timeline of Events

* **09:27 UTC** - Monitroing system reported about the issue
* **09:35 UTC** - Engineering team started verificatio and investigation
* **09:45 UTC** - Cloud-provider support acknowledged hypervisor issues
* **09:55 UTC** - Instance migration started
* **10:33 UTC** - Instance migrated, service returned back

### What Happened

During cloud-provider maintenance, hypervisor become stuck or unresponsive and all instances on it were affected.
We contacted support and kept the issue on track.

During outage, source codes of factories weren't accessible for read/write operations. Builds weren't affected.

To prevent such kind of issues we have already planned some improvements and will apply them soon.
