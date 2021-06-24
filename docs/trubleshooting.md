# Troubleshooting

If you have problems to authenticate correctly, there are some possible reasons: 

1. CA is not enabled in your RADIUS settings
2. Wrong username or password

### Wrong XML 

![](.gitbook/assets/image%20%2828%29.png)

Check that your client has a certificate to authenticate. And you're using the correct [XML](portal/settings-trusted-roots/xml.md#wifi)

### Trusted Root issues 

![](.gitbook/assets/image%20%2831%29.png)

Check that you've done the following: 

* Told your RADIUS Server which certificates are allowed to connect as described [here](portal/settings-trusted-roots/trusted-roots.md#add)
* Imported the active RADIUS Server certificate as trusted root on your client as described [here](azure/trusted-root.md#to-add-a-trusted-root-profile-for-your-clients)

Also check your [Logs](portal/log.md#logs). There is a detailed description of the error. May it's [this](trubleshooting.md#fatal-decrypt-error) issue.

### Fatal decrypt error

If you can see something like this in your [Logs](portal/log.md#logs):

```text
Wed Apr  7 08:14:39 2021 : Auth: (312) Login incorrect (eap_tls: TLS Alert write:fatal:decrypt error): [host/00128t09-cbna-469c-9768-2783d28eikl9/<via Auth-Type = eap>] (from client cygate-se port 1 cli 84-FD-D1-8C-0E-33)
Wed Apr  7 08:14:41 2021 : ERROR: (320) eap_tls: ERROR: TLS Alert write:fatal:decrypt error
Wed Apr  7 08:14:41 2021 : Error: tls: TLS_accept: Error in error
```

Than it's a bug of the TPM software on your Windows machines. More information can be found in the [SCEPman documentation](https://docs.scepman.com/certificate-deployment/microsoft-intune/windows-10)

{% hint style="warning" %}
The setting Key Storage Provider \(KSP\) determines the storage location of the private key for the end-user certificates. Storage in the TPM is more secure than software storage, because the TPM provides an additional layer of security to prevent key theft. However, there is **a bug in some older TPM firmware versions** that invalidates some signatures created with a TPM-backed private key. In such cases, the certificate cannot be used for EAP authentication as it is common for Wi-Fi and VPN connections. Affected TPM firmware versions include:

* STMicroelectronics: 71.12, 73.4.17568.4452
* Intel: 11.8.50.3399, 2.0.0.2060
* Infineon: 7.63.3353.0

If you use TPM with this firmware, either update your firmware to a newer version or select "Software KSP" as key storage provider.
{% endhint %}

