# Mac

The following list and screenshot show you all necessary configurations:

Before creating the **Wi-Fi** profile, create a **Trusted root certificate** profile as described [**here**](https://glueckkanja.gitbook.io/radius-as-a-service/how-to-use/intune-wifi-deployment/windows#server-certificate). Change your **Platform** accordingly.

1. Log in to your [Azure portal](https://porta.azure.com)
2. Navigate to **Microsoft Intune\(Endpoint Manager\)** -&gt; **Devices** -&gt; **macOS** -&gt; **Configuration profiles**
3. Then click **Create Profile**
4. As **Profile type** select **Wired Network**
5. Then set your Profile **Name**
6. Choose your **Network Interface**
7. As **EAP type** choose **EAP - TLS**
8. Next, as **Certificate server names** add **radius.glueckkanja.net**
9. Select the created **Trusted root certificate** profile
10. Finally under **Client Authentication** select your certificate profile

![](../../.gitbook/assets/image%20%2820%29.png)

