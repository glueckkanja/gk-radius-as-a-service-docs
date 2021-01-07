# Wi-Fi XML

This article describes the important parts of the XML. It also explains the parts you need to modify the XML if you do not get it from us.

### Wi-Fi XML Parts

If you want to edit the XML on your own then take care of the following sections:

* [Profile and SSID Name](wifi-xml.md#profile-and-ssid-name)
* [Server Validation](wifi-xml.md#server-validation)
* [Issuer Hashes](wifi-xml.md#issuer-hashes)

#### Profile and SSID Name

You have to customize **&lt;name&gt;** and **&lt;hex&gt;**  on your own. The **&lt;hex&gt;** value is only a string conversion of the **name** value.

```text
<name>RealmJoin WiFi</name>
<SSIDConfig>
    <SSID>
        <hex>5265616C6D4A6F696E2057694669</hex>
        <name>RealmJoin WiFi</name>
    </SSID>
		<nonBroadcast>true</nonBroadcast>
</SSIDConfig>
```

#### Server Validation

The trusted root information below is the thumbprint of the certificate which the clients get's presented from the radius server. It is needed that the client can verify the correct authentication server.

```text
<ServerValidation>
    <DisableUserPromptForServerValidation>true</DisableUserPromptForServerValidation>
    <ServerNames></ServerNames>
    <TrustedRootCA>ba b7 72 b8 7a b3 4b 21 a5 97 8d 01 10 00 b1 f9 21 74 b5 66 </TrustedRootCA>
</ServerValidation>
```

#### Issuer Hashes

The list is for the client to take the correct certificate for the authentication. The current list represents the possible authorities for the AzureAD Join and one SCEPman instance. You have to modify the values so that they fit to your root. 

```text
<CAHashList Enabled="true">
    <IssuerHash>f9 8c cd 25 b8 5a 45 62 36 36 21 07 f2 07 6e df d5 14 63 4e </IssuerHash>
    <IssuerHash>f8 4b fd 43 80 fa 64 94 3b 96 5a 9c 80 ec 1b 88 09 9f 80 6d </IssuerHash>
    <IssuerHash>b6 e2 e0 8e 32 ad 8e ca c6 5c 02 e4 5d 1b 17 e7 a9 d6 04 42 </IssuerHash>
    <IssuerHash>a1 9c 5c 5c 3f f9 53 3b 59 26 1f 0e a3 a8 5c 13 42 ef 39 1e </IssuerHash>
</CAHashList>
```

You can find the thumbprint in the certificate details.

![](../../../.gitbook/assets/image%20%2814%29.png)

### WiFi XML Content 

```text
<?xml version="1.0"?>
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
    <name>RealmJoin WiFi</name>
    <SSIDConfig>
        <SSID>
            <hex>5265616C6D4A6F696E2057694669</hex>
            <name>RealmJoin WiFi</name>
        </SSID>
		    <nonBroadcast>true</nonBroadcast>
    </SSIDConfig>
    <connectionType>ESS</connectionType>
    <connectionMode>auto</connectionMode>
    <MSM>
        <security>
            <authEncryption>
                <authentication>WPA2</authentication>
                <encryption>AES</encryption>
                <useOneX>true</useOneX>
            </authEncryption>
            <PMKCacheMode>enabled</PMKCacheMode>
            <PMKCacheTTL>720</PMKCacheTTL>
            <PMKCacheSize>128</PMKCacheSize>
            <preAuthMode>enabled</preAuthMode>
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
                <authMode>machine</authMode>
                <EAPConfig>
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                        <EapMethod>
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
                        </EapMethod>
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
                                <Type>13</Type>
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
                                    <CredentialsSource>
                                        <CertificateStore>
                                            <SimpleCertSelection>true</SimpleCertSelection>
                                        </CertificateStore>
                                    </CredentialsSource>
                                    <ServerValidation>
                                        <DisableUserPromptForServerValidation>true</DisableUserPromptForServerValidation>
                                        <ServerNames></ServerNames>
                                        <TrustedRootCA>ba b7 72 b8 7a b3 4b 21 a5 97 8d 01 10 00 b1 f9 21 74 b5 66 </TrustedRootCA>
                                    </ServerValidation>
                                    <DifferentUsername>false</DifferentUsername>
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation>
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                                    <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                                            <CAHashList Enabled="true">
                                                <IssuerHash>f9 8c cd 25 b8 5a 45 62 36 36 21 07 f2 07 6e df d5 14 63 4e </IssuerHash>
                                                <IssuerHash>f8 4b fd 43 80 fa 64 94 3b 96 5a 9c 80 ec 1b 88 09 9f 80 6d </IssuerHash>
                                                <IssuerHash>b6 e2 e0 8e 32 ad 8e ca c6 5c 02 e4 5d 1b 17 e7 a9 d6 04 42 </IssuerHash>
                                                <IssuerHash>a1 9c 5c 5c 3f f9 53 3b 59 26 1f 0e a3 a8 5c 13 42 ef 39 1e </IssuerHash>
                                            </CAHashList>
                                        </FilteringInfo>
                                    </TLSExtensions>
                                </EapType>
                            </Eap>
                        </Config>
                    </EapHostConfig>
                </EAPConfig>
            </OneX>
        </security>
    </MSM>
    <MacRandomization xmlns="http://www.microsoft.com/networking/WLAN/profile/v3">
        <enableRandomization>false</enableRandomization>
    </MacRandomization>
</WLANProfile>
```

