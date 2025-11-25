
# Secure ssh

- Change authentication method and port
```ini
# /etc/ssh/sshd_config
Port 22 # change to something else
PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM no
PubkeyAuthentication yes
```
- Generate ssh key
```sh
ssh-keygen -t ed25519 -C "mail@whatever.yolo"
# Or use old rsa system
# ssh-keygen -t rsa -b 4096 -C "mail@whatever.yolo"
```
- Use key
```sh
cd ~/.ssh
cat id_ed25519.pub >> authorized_keys
# Copy the private key to the connecting user
```

# Install fail2ban
