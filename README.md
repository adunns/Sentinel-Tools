# Sentinel-Tools

Tools for Microsoft Sentinel that I've written or modified for use in a blue team.


## Ingest-CanaryTokens

Modified version of Nathan Swifts excellent implementation of a canary token logic app and sentinel analytic rule.

Blog Post: https://techcommunity.microsoft.com/t5/microsoft-sentinel-blog/how-to-setup-a-canarytoken-and-receive-incident-alerts-on-azure/ba-p/1964076<br />
Github: https://github.com/Azure/Azure-Sentinel/blob/master/Playbooks/Ingest-CanaryTokens/readme.md

### Modifications

**Logic app** - Added another parsing block to correctly parse the Canary token data (such as username and machine id) so that it can be passed to Sentinel in the compose block. Removed GeoIP block as the data is the same in the canary token details once parsed properly. Only parse the latest instance of the canary token fire as we are running a NRT rule on the sentinel side. <br />
**Sentinel Analytics Rule** - added some more entity mapping so the username and machine id (and any other details) show up in the alert. Added Mitre Attack techniques. Changed rule to be a NRT (Near Real Time) rule as opposed to running on a 15min schedule.



