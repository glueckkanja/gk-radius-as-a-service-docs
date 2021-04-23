# Android

During a update from Android 11 the WiFi profile setting is functional broken. If your clients are using Android 10 you can use the following configuration: 

Android version 10 and higher does not allow to add a user certificate - which your radius server certificate is - as Certificate Authority. Therefore let the section **Root certificate for server validation** untouched.

The following list and screenshot show you all necessary configurations:

1. Log in to your [Azure portal](https://porta.azure.com/)​
2. Navigate to **Microsoft Intune\(Endpoint Manager\)** -&gt; **Devices** -&gt; **Android** -&gt; **Configuration profiles**
3. Then click **Create Profile**
4. As **Platform** select **Android Enterprise**
5. As **Profile type** select **Wi-Fi**
6. Then as **Wi-Fi type** choose **Enterprise**
7. As **EAP type** choose **EAP - TLS**
8. Finally select your certificate profile under **Client Authentication**

![](https://gblobscdn.gitbook.com/assets%2F-Lzl3JXanfpvdg6pLlGg%2F-MRzTCnyTXIc508RLjzv%2F-MRzWMMOFKRnAWGMCG10%2Fandroid-enterprise-eap-tls-settings.png?alt=media&token=c08d2827-cf3a-42ae-ac45-54764d8d581f)

