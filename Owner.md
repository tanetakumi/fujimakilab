# /etc/ssh/sshd_config
```
PasswordAuthentication no
...
Match Address 10.8.128.0/24
    PasswordAuthentication yes
```

# Add other users
```
sudo adduser <username>
```