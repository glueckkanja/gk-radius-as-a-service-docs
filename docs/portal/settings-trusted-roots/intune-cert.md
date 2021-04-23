---
description: >-
  It's also possible to use the certificate which every Windows 10 get's when
  joining your Azure Active directory
---

# Intune Certificate

### Intune IDs

{% hint style="danger" %}
Use this setting with care. One of the following IDs **must** exist in the certificate extension 1.2.840.113556.5.14. All other certificates will **rejected**.
{% endhint %}

To get your Intune Tenant ID follow these steps: 

* Press **Windows + R** and enter **certlm.msc**
* Go to your personal certificates. There will be a certificate from one of the following issuers
  * SC Online Issuing
  * MDM Device Authority 
* Open this certificate, go to **Details** and search for the extension 

  1.2.840.113556.5.14

* The printed HEX value is your Intune Tenant ID. 

#### Example:

The tenant ID of the following certificate is: **bb4397cb6891c64db17f766487518a6a**

![](../../.gitbook/assets/image%20%2841%29.png)

