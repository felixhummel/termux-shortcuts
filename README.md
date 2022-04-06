# Preamble
- mobile phone called `sx` (hostname set via Android system settings)
- rsync/sftp server called `r`


# SSH Config
For `r`:
```
Host r
  Hostname example.com
  User rsync
  Port 12345
```


# Markor
https://github.com/gsantner/markor
```
ln -s markor /data/data/com.termux/files/home/storage/shared/Documents/markor/
```


# ~/storage
https://wiki.termux.com/wiki/Termux-setup-storage


# more...
- `tasks/` discontinued; see https://wiki.termux.com/wiki/Termux:Tasker


# burn-battery
Stop Wi-Fi going to sleep to improve interactive SSH experience by reducing
lag.

Install:
```
cat <<'EOF' > ~/burn-battery
#!/data/data/com.termux/files/usr/bin/bash
while true; do
  sleep 0.1
  date
done
EOF

chmod +x burn-battery
```

Run it in some background terminal:
```
ssh sx ./burn-battery
```
