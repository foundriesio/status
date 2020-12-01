## source.foundries.io Disruption

### Timeline of Events

* **06:48 UTC** - Monitroing system reported about the issue
* **06:57 UTC** - Engineering team started verification and investigation
* **07:13 UTC** - The root of the issue identified
* **07:27 UTC** - Service returned back

### What Happened

Automatic upgrade of operating system and its components caused container daemon shutdown.
The daemon wasn't started after upgrade.

During the outage, source codes of factories weren't accessible for read/write operations. Builds weren't affected.

To prevent such kind of issues we'll change system settings and setup additional moniroting checks.
