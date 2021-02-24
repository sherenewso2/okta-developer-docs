### Clear the Okta session

Clear the browser session and clear the app session (stored tokens) in memory. Fires an event once a user successfully logs out.

Note: This method apply for browser-sign-in scenario only. Use a combination of revokeToken (optional) and clearTokens methods to signOut when use custom-sign-in.

browser-sign-in example:

```javascript
import { signOit } from '@okta/okta-react-native';

signOut();
```

custom-sign-in example:

```javascript
await revokeAccessToken(); // optional
await revokeIdToken(); // optional
clearTokens()
    .then(() => { })
    .catch(e => { });
```