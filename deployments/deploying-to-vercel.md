# Deploying to Vercel

There are two ways to deploy novel web in vercel. This assumes that you have the novel server set up in a different location.

1. proxy mode - use rewrites in next.config.js to proxy all routes from /api /admin /auth /docs into novel server (warning, this may be costly as you scale)
2. standalone mode - recommended. configure novel server to proxy pages and \_next from the novel server location into vercel.

It is up to your preference and comfor where you want to stage your UI and server. The mode you pick now can be changed in the future based on your need.



### Proxy Mode

You can run&#x20;

```sh
novel web use proxy
```

and it will add the relevant rewrites into your next.config.js

If you want to do it manually, the rewrites applied are below

```json
{
    "rewrites": [
    
    ]
}
```

{% hint style="warning" %}
Remember to add your custom endpoints if you have any. for example, api/v1 is available by default and if you want to add private-api/v1 into it, you need to add \[$$ $$$$$$ $$]
{% endhint %}



