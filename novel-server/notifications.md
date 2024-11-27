# Notifications

### Web Push

You are required to set up the following environment variables

```
VAPID_FCM_KEY=***
VAPID_PUBLIC_KEY=***
VAPID_PRIVATE_KEY=***
```

You can use the novel cli to get these via

```
novel add vapid
```

and it will walk you through the steps to get these variables



You can then use the api from your controllers via

```
import * as push from 'novel/push';

await push.web({ to: ["account_ID"] } }, { body: "Your Message" });
```

### Mail

Similarly, you can use the same api to send an email notification

```
import * as push from 'novel/push';

await push.mail({ to: ["account_ID"] } }, { body: "Your Message" });
```

You can modify the mail template under `app/templates/mail/notification/message.tsx`

