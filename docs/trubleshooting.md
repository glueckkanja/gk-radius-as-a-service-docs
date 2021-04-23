# Troubleshooting

If you have problems to authenticate correctly, there are some possible reasons: 

1. Wrong WiFi profile config or not the correct certificate taken by the client 
2. CA is not enabled in your RADIUS settings
3. Wrong username or password

### 1.

![](.gitbook/assets/image%20%2828%29.png)

Check that your client has a certificate to authenticate.

### 2.

Add your CA as [Trusted Root](azure/trusted-root.md#to-add-a-trusted-root-profile-for-your-clients).

### 3. 

![](.gitbook/assets/image%20%2831%29.png)

Check your [Logs](portal/log.md#logs). There is a detailed description of the error.

