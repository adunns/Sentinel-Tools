# Sentinel-Tools

Tools for Microsoft Sentinel that I've written or modified for use in a blue team.


## Ingest-CanaryTokens

Modified version of Nathan Swifts excellent implementation of a canary token logic app and sentinel analytic rule.

Blog Post: https://techcommunity.microsoft.com/t5/microsoft-sentinel-blog/how-to-setup-a-canarytoken-and-receive-incident-alerts-on-azure/ba-p/1964076

Github: https://github.com/Azure/Azure-Sentinel/blob/master/Playbooks/Ingest-CanaryTokens/readme.md

### Modifications

Logic app - Added another parsing block to correctly parse the Canary token data (such as username and machine id) so that it can be passed to Sentinel in the compose block.

Sentinel Rule - added some more entity mapping so the username and machine id show up in the alert.



