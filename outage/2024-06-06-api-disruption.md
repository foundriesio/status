## api.foundries.io disruption

We were experiencing a disruption on our resources:
* api.foundries.io was failing to serve certain requests with 500 error
* app.foundries.io was showing 500 error on some pages

The issue was investigated and fixed.

### Timeline of Events

* **18:05 UTC** - We deployed a new version of api.foundries.io containing a bug in our instrumentation (logging) code.
  This caused the API to respond with 500 error to some requests, prior to handling those requests.
  As a result, some pages on app.foundries.io were also showing 500 error.
* **18:40 UTC** - A problem was noticed in our cloud logs and investigation started.
* **19:01 UTC** - A fix was prepared, verified, and merged.
* **19:19 UTC** - A fix deployed to our servers; system is back to normal.
