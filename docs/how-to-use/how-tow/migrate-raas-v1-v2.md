---
description: This page is a Step-by-Step Guide how you can migrate your v1 instance to v2
---

# Migrate RaaS v1 - v2

If you are using RADIUS-as-a-Service v1 currently, you've got the most stuff done regarding WiFi- and profile setup for your clients. We will install the same Server Certificate on the new instance which your clients already know so you don't have to redeploy any profile. 

{% hint style="info" %}
If your WiFi infrastructure supports [RadSec](../../details.md#what-is-radsec), you should consider to migrate that too. How to connect your WiFi infrastructure with your RADIUS instance is described [here](get-started.md#if-your-vendor-support-radsec) and [here](get-started.md#if-your-vendor-support-radsec-1)
{% endhint %}

If your WiFi infrastructure don't support RadSec to the following:

1. **Add** a [Proxy](../../portal/settings-proxy.md#add) to your instance
2. Tell your RADIUS Server which certificates are allowed to connect as described [here](../../portal/settings-trusted-roots/trusted-roots.md#add)
3. Set the IP address of your **Proxy**, the shared secret from your [Server Settings](../../portal/settings-server.md) page and the authentication port **1812** as primary authentication server. 

Leave the old instances as secondary and third fallback server intact so if your configuration is not valid, your clients will be able to authenticate. 

After you can see successful authentications to your instances in the [logs](../../portal/log.md#logs) disable or remove the IP addresses from your RADIUS Server lists. 

A day or week later after everything is working, please tell us, that you've successful migrated and you don't need your v1 instances anymore. If we don't see any new requests incoming to your old instances, we will than remove them. 

