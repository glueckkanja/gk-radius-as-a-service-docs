# MikroTik

Due to establish a valid TLS connection, your client have to know the RADIUS Server certificate and your RADIUS Server needs to know your client certificate. To import your Server certificate, follow these steps: 

* Download your RADIUS [Server certificate](../../../portal/settings-server.md#server-certificate)
* Import it to your Mikrotik client:
  * Upload the certificate with the files section
  * switch to your WebFig and enter

```text
/certificate import filename=yournameServercertificate.cer
```

If you not already have a certificate for your router generate one as described [here](https://wiki.mikrotik.com/wiki/Manual:Create_Certificates). 

Example: 

```text
/certificate add name=ca-template common-name=myCa key-usage=key-cert-sign,crl-sign
/certificate add name=mikrotik-client common-name=mikrotik-client
/certificate sign mikrotik-client ca=myCa name=mikrotik-client
```

Export your generated certificate:

```text
/certificate export-certificate mikrotik-client
```

Upload the file to your RADIUS instance as [trusted root](../../../portal/settings-trusted-roots/trusted-roots.md#add).

Switch back to your WebFig, add a new RADIUS profile and enter the following information:

* use the IP address from your [Server Settings ](../../../portal/settings-server.md)page
* **Protocol:** radsec
* **Secret:** radsec
* **Authentication Port:** 2083
* **Accounting Port:** 2083
* **Certificate:** the generated before 

![](../../../.gitbook/assets/image%20%2821%29.png)

Go to **Wireless** add a new **Security Profile** and enter the following information: 

* **Name:** on your behalf
* **Mode:** dynamic keys
* **EAP Methods:** passthrough
* **TLS Mode:** verify certificate
* **TLS Certificate:** the imported RADIUS Server certificate

![](../../../.gitbook/assets/image%20%2834%29.png)



Switch to your **WiFi Interfaces** and apply your **Security Profile** to the interface.

![](../../../.gitbook/assets/image%20%2840%29.png)

