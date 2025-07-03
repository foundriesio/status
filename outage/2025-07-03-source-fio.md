## 2025-07-03 source.foundries.io outage

Our [git service](https://source.foundries.io) was unreachable for some end users via the web portal.

## Root cause

The problem was due to new authorization code hitting a path that expected a specific piece of data to be present, in this case what teams a user belongs to.
Not all users belong to a team so this code was rectified to deal with that possibility.

### Timeline of Events

- **08:27 UTC** - It is noticed by a customer source.foundries.io web portal is not reachable
- **09:26 UTC** - Root cause identified
- **09:30 UTC** - Fix applied and deployed

## Lessons Learned

Make sure that data validation happens for all properties and assumptions about data structures are guarded for defensively.
