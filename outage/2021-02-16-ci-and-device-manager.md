## CI and Device Management services offline

### Timeline of Events

* **16:30 UTC** - Notified of container publishing failure
* **17:00 UTC** - Issue traced back to internal database
* **17:40 UTC** - TUF-repo service offline
* **18:30 UTC** - Internal database restored
* **18:50 UTC** - All services restored

### What Happened

Internal database maintenance caused the cluster size to be reduced.  Because of this the database ran out of
storage space and started to refuse connections from customer facing applications.  The database was restarted,
checked for integrity, and brought back online.  Other services were enabled and connected properly.
