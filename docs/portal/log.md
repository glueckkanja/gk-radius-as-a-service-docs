# Log

## Dashboard

To get a overview of your current connections go to https://YOURNAME.radius-as-a-service.com/dashboard to get statistics of your client authentications.

![](../.gitbook/assets/image%20%2832%29.png)

## Logs

To view your server logs and get a list of the authenticated users go to https://YOURNAME.radius-as-a-service.com/logs.

To not see the connection attempts from your [Proxy](settings-proxy.md) enter the following in your **Search.**

```text
not message : "*auth+acct*"
```

![](../.gitbook/assets/image%20%2822%29.png)

