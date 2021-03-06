Whitelists are used to control access to your environments.

Each whitelist defines a set of IP address ranges which are permitted to access an environment.

By default a whitelist named 'allow-all' is created. This whitelist permits all traffic, and should generally be used for your production environment.

Creating a new whitelist
----

```
$ fleet whitelist create <whitelist_name>
Created whitelist <whitelist_name>

```

Listing existing whitelists
----

```
$ fleet whitelist list
name           rules    in use    read only
---------      -------  --------  -----------
allow-all      2/50     no        yes
whitelist_name 0/50     no        no
```

Adding an address range to a whitelist
----

```
$ fleet whitelist allow whitelist_name 10.0.0.0/8
```

Showing ranges allowed by a whitelist
----
```
$ fleet whitelist describe whitelist_name
 - 10.0.0.0/8
```

Revoking access to a range from a whitelist
----
```
$ fleet whitelist revoke whitelist_name 10.0.0.0/8
```

Deleting a whitelist
---

If a whitelist is no longer needed, you can remove it. You cannot remove a whitelist if it is being used by an environment.

```
$ fleet whitelist destroy whitelist_name
Destroyed whitelist whitelist_name
```
