# Sessions

## Cookie Session

Available under

```typescript
export default function Route(instance) {
    instance.authenticated();
    instance.get('/your/route', handler);
    
    async function handler () {
        reply.send('ONLY FOR AUTHENTICATED USERS');
    }
}
```

also available under request via

```
await request.authenticated();
```

you can also provide an array of roles where the endpoint only responds to the session if they have the role.

## API Session

When using an API key, you can respond to requests and scope routes under

```typescript
export default function Route(instance) {
    instance.authorized();
    instance.get('/your/route', handler);
    
    async function handler () {
        reply.send('ONLY FOR AUTHENTICATED API KEYS');
    }
}
```

also available under request via

```
await request.authorized();
```

You can provide an array of scopes specific to the key if you need to have a more granular control.



### Allowed Roles

```
instance.allows('admin')
```

responds to the current session's role and available under the instance definition

### CASL

Available under the request handler

```
request.allows('write', request.org.id);
// is equal to
request.can('write', request.org.id);
```

you can also use `request.cannot(...)`



### Verified

Check if a user is verified by checking

```
export default function Route(instance) {
    instance.verified();
    instance.get('/your/route', handler);
    
    async function handler () {
        reply.send('ONLY FOR AUTHENTICATED API KEYS');
    }
}
```

or inside request as

```
await request.verified();
```







