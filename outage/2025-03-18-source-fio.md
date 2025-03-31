## source.foundries.io Disruption

### Timeline of Events

- **15:59 UTC** - Colleague notices system is unresponsive
- **16:09 UTC** - Engineering team started verification and investigation
- **16:14 UTC** - Other customers are reporting issues
- **16:26 UTC** - The root cause is known
- **16:54 UTC** - First workaround is implemented to alleviate pressure
- **17:23 UTC** - Second workaround is implemented and verified to be working
- **19:51 UTC** - Permanent solution is in place in the form of Google Cloud Armor

### What Happened

There was an automatic vulnerability scanner of unknown origin, trying to see if there was a Cisco related vulnerability.
The automated scanner tool was getting 302 HTTP status response codes, and that did not make it stop.
It only kept trying, the assumption is the tool in question does not register a 302 as an error condition.

The specific path of the HTTP request was isolated and added to a Web Application Firewall (WAF) ruleset to deny the request
before it reaches the service in question. This ruleset can be used for all services.
