---
title: 'Quick setup'
weight: 2
---

AppArea is incredibly easy to get setup with! However, this is a minimal
setup, and there are more complex configurations available if you want.

To get started, download the client helper script:

```bash
> wget https://raw.githubusercontent.com/jedevc/apparea/master/scripts/apparea.py
```

This script wraps the SSH command installed on your system with all the right
options to most optimally interact with the AppArea server.

Now, you can run the script, answering some questions to configure your
global settings (to use this server, most of the defaults should be fine).

```bash
> chmod +x apparea.py
> ./apparea.py
Welcome to apparea!
Since this is your first time, this helper will get you setup.

Site [apparea.dev]: 
Port [21]: 
Username [user]: 
SSH Key [/home/user/.ssh/id_ed25519]: 

{
    "site": "apparea.dev",
    "port": 21,
    "username": "user",
    "keyfile": "/home/user/.ssh/id_ed25519"
}
Is this ok? [yes]/no: yes
Written config to /home/user/.apparea.json

Do you want to install this script to /usr/local/bin? [yes]/no: yes
$ sudo cp apparea.py /usr/local/bin/apparea
[sudo] password for user:

All done!
```

Note that the last step (installing the script to `/usr/local/bin`), is
completely optional, and you can choose to copy the script to your own
location of choice, or even not install it globally at all.

__Important!__ Make sure that you give your username and key to the
administrator of the server before your continue further, or you won't be
able to connect.

Connecting and casting a port is super easy now:

```bash
> apparea http 8000
>>> Listening on http://user.apparea.dev
```

If you visit the given URL, you should then be able to see your site that's
listening on your localhost on port 8000! You can then stop casting by
causing a keyboard interrupt by pressing `CTRL+C`.

You can also cast raw TCP ports:

```bash
> apparea tcp 4000
>>> Listening on user.apparea.dev:?????
```

This casts the localhost port 4000 to a randomized port on the AppArea
server.

Now you've properly got AppArea setup! If that's all you want it for, you're
all done, however, if you want more advanced configuration, you can continue
looking through the docs!
