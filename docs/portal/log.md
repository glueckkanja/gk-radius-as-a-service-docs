# Log

## Dashboard

To get an overview and further insights into your current connections, go to https://YOURNAME.radius-as-a-service.com/dashboard.

![](../.gitbook/assets/image%20%2832%29.png)

## Logs

To view your server logs and get a list of the authenticated users, go to https://YOURNAME.radius-as-a-service.com/logs.

To filter the connection attempts from your [Proxy](settings-proxy.md) enter the following string in your **Search.**

```text
not message : "*auth+acct*"
```

![](../.gitbook/assets/image%20%2822%29.png)

