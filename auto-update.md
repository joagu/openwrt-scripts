
# Howto

Add the following line to the file `/etc/profile`

```
alias up="opkg update && if [ $(opkg list-upgradable | wc -l) -gt 0 ]; then opkg list-upgradable | cut -f 1 -d ' ' | xargs opkg upgrade; fi"
```

Can obviously be combined with automatic cron-job if needed.
When this is added, you can log in and type `up` to check for updates and install them if any.