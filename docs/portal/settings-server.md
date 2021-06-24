---
description: >-
  Server settings are available under
  https://YOURNAME.radius-as-a-service.com/settings/server
---

# Server Settings

![](../.gitbook/assets/image%20%2847%29.png)

Explanation of your server Settings:

* **Server IP Address** The IP Address under which your server is available. These IP Address is only providing [RadSec](../details.md#what-is-radsec)!
* **UDP Auth Port** The Port for your authentications if UDP is used
* **UDP Acc Port** The Port for your accounting if UDP is used
* **Shared Secret** Only needed if you are using UDP Proxies

### Certificates

On your **Server Settings** page you can see two tables with certificate information. Detailed information in the sections below.  
The [first table](settings-server.md#server-certificates) shows all available certificates your RADIUS server is able to use. The [second](settings-server.md#radsec-connection-certificates) is for all certificates which are allowed to establish a [RadSec](../details.md#what-is-radsec) connection. Both tables will contain at least one certificate to ensure a normal operation of your systems.  

### Server certificates

The certificate which will be created automatically on set up is a self signed end user certificate. It can cause issues on Android\(&gt;9\) because you'll not able to install those certificate as trusted CA. For this purpose you can create your own CA to allow the installation on Android. 

To create your CA follow these simple steps: 

1. Click on **Add**
2. Choose **Create your own CA**
3. Click on **Create**

![](../.gitbook/assets/image%20%2852%29.png)

After the creation you will see a new certificate available in your table. 

![](../.gitbook/assets/image%20%2846%29.png)

If you don't want the standard certificate which we're creating or want to use your own certificate you can upload up to 2 own certificates.

To upload your own certificate follow these steps:

1. Click on **Add**
2. Choose **PEM encoded Certificate**
3. Copy & Paste your certificate or use the **Browse File** option
4. Enter the password of your **Private Key** 
5. Click on **Save**

#### Activate

Certificates expire from time to time. And or you decide to use your own certificate. Therefore, it is important that you can control the certificate that your server is using. The Active column shows you which certificate your server is currently using. To change which certificate your server is using, expand the row of the certificate you want and click **Activate**. 

#### Download

To download your **Server certificate**  click on **Download** in the corresponding row.

![](../.gitbook/assets/image%20%2854%29.png)

### RadSec connection Certificates

RadSec works also with certificate authentication. Your RADIUS server has to know who is allowed to establish a valid connection. You will always see at least one certificate which is the certificate of your [RadSec proxy](settings-proxy.md)  and so cannot be deleted to ensure that your proxies can start properly and can establish a connection to your instance. 

#### Add

To allow new clients to establish a RadSec connection to your instance follow these steps:

1. Click on **Add**
2. Copy & Paste your certificate or use the **Browse File** option
3. Click on **Save**

After this you should see your imported certificate in your table.

![](../.gitbook/assets/image%20%2848%29.png)

#### Delete

To delete a certificate which should be allowed to connect. Expand the corresponding row, click on **Delete** and confirm your choice. 

![](../.gitbook/assets/image%20%2853%29.png)

