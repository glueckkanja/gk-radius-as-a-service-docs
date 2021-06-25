---
description: >-
  This page is a Step-by-Step Guide on how you can migrate your V1 instance to
  V2
---

# Migrating from RADIUSaaS V1 to V2

If you are using RADIUS-as-a-Service V1 currently, you have got the most stuff done regarding WiFi- and profile setup for your clients. We will install the same Server Certificate on the new instance which your clients already know so you do not have to redeploy any new profiles. 

{% hint style="info" %}
If your WiFi infrastructure supports [RadSec](../../details.md#what-is-radsec), you should consider to migrate that too. How to connect your WiFi infrastructure with your RADIUS instance is described [here](get-started.md#if-your-vendor-support-radsec) and [here](get-started.md#if-your-vendor-support-radsec-1)
{% endhint %}

If your WiFi infrastructure does not support RadSec to the following:

1. **Add** a [Proxy](../../portal/settings-proxy.md#add) to your instance
2. Tell your RADIUS Server which certificates are allowed to connect as described [here](../../portal/settings-trusted-roots/trusted-roots.md#add)
3. Set the IP address of your **Proxy**, the shared secret from your [Server Settings](../../portal/settings-server.md) page and the authentication port **1812** as primary authentication server. 

Leave the old instances as secondary and third fallback server intact, so if your configuration does not work initially, your clients will still be able to authenticate. 

One you are able to see successful authentications to your V2 instance in the [logs](../../portal/log.md#logs), disable or remove the IP addresses from your RADIUS Server lists. 

A day or week later, after everything is working stable, please inform us, that you have successfully migrated and that you do not need your V1 instance anymore so we can start  disenrolling it. If we do not see any new incoming requests to your old instances for a certain period, we will then finally disable it. 

