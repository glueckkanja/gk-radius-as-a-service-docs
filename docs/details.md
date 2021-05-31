# Details

## What is RADIUS

Whenever large companies need network authentication, [RADIUS ](https://tools.ietf.org/html/rfc2865)is the protocol of choice. RADIUS is a AAA protocol which stands for **authentication, authorization and accounting**. It is therefore best suited for controlling access to a network\(Wi-Fi, Wired or VPN\). The protocol was developed by Livingston Enterprises, Inc. in 1991 and is now one of the IETF standards.

## What is RadSec

RADIUS is a good protocol for authentication which uses the UDP transport protocol. Nonetheless, some traffic will not be encrypted during transport. This can be avoided by using [RadSec](https://tools.ietf.org/html/rfc6614) which is transported over TCP and completely encapsulated within a TLS  tunnel. 

### Which certificates can be used?

The easiest solution to authenticate your clients is [SCEPman](https://glueckkanja.gitbook.io/scepman/index), which only requires a Azure Key Vault for storage and allows you to block access of specific clients by disabling them in Azure.  
  
But if you want to use your own on-premise PKI or need a migration phase for both worlds, you can also enter any other Root-CA to verify your clients.

### OCSP

To work with revocation of certificates our RADIUS system can also work with OSCP. A certificate revocation list is currently not supported. 

## Our Service

Each customer has access to their own personal instance through our portal, which can be used for tasks such as [creating Users](portal/users.md#add), changing your [allowed certificates](portal/settings-trusted-roots/), [adding proxies](portal/settings-proxy.md) and viewing your server [logs](portal/log.md). 

Our RADIUS server only allows [RadSec](details.md#what-is-radsec) connections. If your WiFi infrastructure doesn't support RadSec, you can add a [Proxy](portal/settings-proxy.md) to your instance, which will establish a secure tunnel allowing you to use our service with traditional UDP.

### Guests and IOT devices 

Some devices will not receive any certificates. Rather they are not managed by any policy provider or they simply don't have the opportunity to get one.   
In cases like this or Guests scenarios you can [add users](portal/users.md#add) to your instances and restrict the access to a specific time frame if needed, which allows you to authenticate printers, TV's or other devices with the same instance.



 

