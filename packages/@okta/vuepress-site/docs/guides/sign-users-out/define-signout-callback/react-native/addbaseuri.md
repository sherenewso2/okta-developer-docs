Signing out of Okta requires the app to open a browser and navigate to the [end session endpoint](https://developer.okta.com/docs/reference/api/oidc/#logout). Okta destroys the user's session and immediately redirects back to your application. To do this, you must define a callback route for the sign-out process.

Make sure that the `endSessionRedirectUri` configured at `createConfig` is the same as the one defined in the **Logout redirect URI** section. For example if you are initializing your client via a config file:

```javascript
{
  export default {
    oidc: {
      clientId: '{clientId}',
      redirectUri: 'com.okta.example:/login',
      endSessionRedirectUri: 'com.okta.example:/logout',
      discoveryUri: 'https://com.okta.example',
      scopes: ["openid", "profile", "offline_access"],
    }
  };
}
```