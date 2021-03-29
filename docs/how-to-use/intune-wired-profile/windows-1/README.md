# Windows

Before creating the **Wired Authentication** profile, create a **Trusted root certificate** profile as described [**here**](https://glueckkanja.gitbook.io/radius-as-a-service/how-to-use/intune-wifi-deployment/windows#server-certificate). Change your **Platform** accordingly.

To deploy a wired authentication profile create your XML as described [here ](wired-xml.md) and create your Intune configuration. The instructions to deploy the profile are copied from [here](https://docs.microsoft.com/en-us/microsoft-365/managed-desktop/get-ready/certs-wifi-lan?view=o365-worldwide#deploy-a-lan-profile):

1. Create a custom profile in Microsoft Intune for the LAN profile using the following settings \(see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/en-us/intune/custom-settings-windows-10)\). In **Custom OMA-URI Settings**, select **Add**, and then enter the following values:
   * Name: _Modern Workplace-Windows 10 LAN Profile_
   * Description: Enter a description that gives an overview of the setting, and any other important details.
   * OMA-URI \(case sensitive\): Enter _./Device/Vendor/MSFT/WiredNetwork/LanXML_
   * Data type: select **String \(XML file\)**.
   * Custom XML: Upload the exported XML file.

