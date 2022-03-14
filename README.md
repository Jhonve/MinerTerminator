# MinerTerminator
Defend server from miner attack

### Base

**Using [fail2ban](https://www.fail2ban.org/)**

*How to Install*

```shell
sudo apt-get install fail2ban
```

*How to configure*

```shell
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.conf.backup # backup
sudo vim /etc/fail2ban/jail.conf
```

```
bantime = 3d # recommended modification
maxretry = 3 # recommended modification
```

*How to start*

```shell
sudo systemctl start fail2ban
sudo systemctl status fail2ban.service # check status
sudo fail2ban-client status # check status
```



*How to unban an IP from jail manually*

```shell
# check if IP is blocked
sudo iptables -n -L
# check Fail2ban log
sudo cat /var/log/fail2ban.log
# Get the jail name of the blocked IP, default is 'sshd'
sudo fail2ban-clinet status
# Unban the IP
sudo fail2ban-client set jail_name unbanip ip_address
```

*How to block an IP manually*

```shell
sudo fail2ban-client set jail_name banip ip_address
```



### If you are attacked

- Find the PID of the miner process.

- Find the program.

  ```
  sudo cd /proc/miner_pid
  
  ```

- 



### Solution 1 -- Using 'ssh-copy-id'

Suppose your server is attacked by hackers repeatedly with the correct username and password. You can disable ssh password login and use 'ssh-copy-id' instead.

Waiting for update...



### Solution 2 -- Waiting for Update

