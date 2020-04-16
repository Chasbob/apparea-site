---
title: 'Advanced usage'
weight: 3
---

## Using subdomains

As an AppArea user, you also can create arbitrary subdomains (as long as they
end in your username)!

Using the helper script, you can specify the `--subdomain` flag to specify a
subdomain of your username.

```bash
> apparea http 8000 --subdomain foo
>>> Listening on http://foo-user.apparea.dev
```

## Connecting without helper script

The helper script, while useful, may not always be available, and you may
want to connect without it sometimes.

Since the script only wraps existing SSH functionality, and all the outputs
are handled by the server, you can connect without the script without any
problems.

To cast HTTP from port 8000:

```bash
> ssh -R 0.0.0.0:80:localhost:8000 -p 21 user@apparea.dev
```

To cast TCP from port 4000:

```bash
> ssh -R 0.0.0.0:0:localhost:4000 -p 21 user@apparea.dev
```