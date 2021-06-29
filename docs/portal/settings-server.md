---
description: >-
  Server settings are available under
  https://YOURNAME.radius-as-a-service.com/settings/server
---

# Server Settings

![Exemplary Server Settings](../.gitbook/assets/image%20%2847%29.png)

Explanation of your Server Settings:

* **Server IP Address** The IP Address at which your server is available. This IP Address only speaks [RadSec](../details.md#what-is-radsec)!
* **UDP Auth Port** The RADIUS authentication port in case UDP is used
* **UDP Acc Port** The RADIUS accounting port in case UDP is used
* **Shared Secret** Only required if you use UDP proxies

## Certificates

On your **Server Settings** page there are two tables with certificate information. Both tables will contain at least one certificate to ensure a normal operation of your systems.  

#### List of all available Server Certificates

The [first table](settings-server.md#server-certificates) shows all available certificates your RADIUS server is able to use. 

#### List of allowed RadSec Connection Certificates

The [second table](settings-server.md#radsec-connection-certificates) contains all certificates that are allowed to establish a [RadSec](../details.md#what-is-radsec) connection. 

### Server Certificates

#### Default Certificate

The certificate which will be created automatically during set up of your RADIUSaaS instance is a self-signed end user certificate. 

#### Custom CAs

{% hint style="warning" %}
A custom CA is required if you are planning to authenticate Android devices.
{% endhint %}

In same cases, you might be required to create your own custom CA. For example, Android devices \(version &gt; Android 9\) will not allow to install the auto-generated certificate as trusted CA. 

To create your custom CA, follow these simple steps: 

1. Click **Add**
2. Choose **Create your own CA**
3. Click on **Create**

![](../.gitbook/assets/image%20%2852%29.png)

After the creation, you will see a new certificate available in your table:

![](../.gitbook/assets/image%20%2846%29.png)

In case you do not want to use any of the standard certificates which we are providing you can upload up to two of your own certificates.

To upload your own certificate, follow these steps:

1. Click **Add**
2. Choose **PEM encoded Certificate**
3. Copy & Paste your certificate or use the **Browse File** option
4. Enter the password of your **Private Key** 
5. Click **Save**

#### Certificate Activation

As certificates expire from time to time or your preference on which certificates you would like to use change, it is important that you can control the certificate that your server is using. The **Active** column shows you the certificate your server is currently using. To change the certificate your server is using, expand the row of the certificate you would like to choose and click **Activate**. 

#### Download

To download your **Server Certificate**  click **Download** in the corresponding row.

![](../.gitbook/assets/image%20%2854%29.png)

### RadSec Connection Certificates

RadSec itself works with certificate authentication as well. Hence, your RADIUS server has to know who is allowed to establish a valid RadSec connection. Due to this requirement, you will always see at least one certificate in this table, which is the one related to your [RadSec proxy](settings-proxy.md). To ensure that your proxies are able to start up properly and are able to establish a connection to your instance, you cannot delete it. 

#### Add

To allow new clients to establish a RadSec connection to your instance, follow these steps:

1. Click **Add**
2. Copy & Paste your certificate or use the **Browse File** option
3. Click **Save**

After this you should see your imported certificate in your table.

![](../.gitbook/assets/image%20%2848%29.png)

#### Delete

To delete a certificate, expand the corresponding row, click **Delete** and confirm your choice. 

![](../.gitbook/assets/image%20%2853%29.png)

