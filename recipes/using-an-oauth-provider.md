# Using an OAuth Provider

{% tabs %}
{% tab title="Javascript" %}
{% code lineNumbers="true" %}
```javascript
const YourUserModel = require('server/api/models/user')

module.exports = async function Provider(auth) {
    auth.provider('custom-oauth-server');
    
    auth.on('login', async function Login(access) {
        await YourUserModel.login(access);
    });
}
```
{% endcode %}
{% endtab %}

{% tab title="Typescript" %}
{% code lineNumbers="true" %}
```typescript
import YourUserModel from 'server/api/models/user'

export default async function Provider(auth) {
    auth.provider('custom-oauth-server');
    
    auth.on('login', async function Login(access) {
        await YourUserModel.login(access);
    });
}
```
{% endcode %}
{% endtab %}
{% endtabs %}
