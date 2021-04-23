# Details

## What is RADIUS

Whenever large companies need network authentication, [RADIUS ](https://tools.ietf.org/html/rfc2865)is the protocol of choice. RADIUS is a AAA protocol which means **authentication, authorization and accounting** and therefore best suited for logging into Wi-Fi, Wired or VPN. The protocol was developed by Livingston Enterprises, Inc. in 1991 and is now one of the IETF standards.

## What is RadSec

RADIUS is a good protocol for authentication which uses the UDP transport protocol. Nonetheless will some traffic not encrypted during transport. To avoid this it's possible to use [RadSec](https://tools.ietf.org/html/rfc6614) which is transported over TCP and completely encapsulated within a TLS  tunnel. 

### Which certificates can be used?

The easiest solution to authenticate your clients is [SCEPman](https://glueckkanja.gitbook.io/scepman/index) which has the benefit to disallow the access of your clients by disabling the device in Azure.   
  
But if you want to use your own on-premise PKI or need a migration phase for both worlds, you can also enter any other Root-CA to verify your clients.

### OCSP

To work with revocation of certificates our RADIUS system can also work with OSCP. A certificate revocation list is currently not supported. 

## Our Service

Each Customer will get their own Website to manage his instance. This portal allows you to [create Users](portal/users.md#add), control your [allowed certificates](portal/settings-trusted-roots/), [add proxies](portal/settings-proxy.md) and view your server [logs](portal/log.md). 

Our RADIUS server only allow [RadSec](details.md#what-is-radsec) connections. If your WiFi infrastructure don't support RadSec, you can add a [Proxy](portal/settings-proxy.md) to your instance, which will establish a secured tunnel and allows you to use our service with traditional UDP. 

### Guests and IOT devices 

Some devices will not receive any certificates. Rather they are not managed by any policy provider or they simply don't have the opportunity to get one.   
In cases like this or Guests scenarios you can [add users](portal/users.md#add) to your instances and restrict the access to a specific time frame if needed, which allows you to authenticate printers, TV's or other devices with the same instance.



 

