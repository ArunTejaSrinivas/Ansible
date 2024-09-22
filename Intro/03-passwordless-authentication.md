# How to setup Passwordless Authentication 

## EC2 Instances

### Using Public Key

## when you are in local
```
ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
```

- ssh-copy-id: This is the command used to copy your public key to a remote machine.
- -f: This flag forces the copying of keys, which can be useful if you have keys already set up and want to overwrite them.
- "-o IdentityFile <PATH TO PEM FILE>": This option specifies the identity file (private key) to use for the connection. The -o flag passes this option to the underlying ssh command.
- ubuntu@<INSTANCE-IP>: This is the username (ubuntu) and the IP address of the remote server you want to access.

### Using Password 

- Go to the file `/etc/ssh/sshd_config.d/60-cloudimg-settings.conf`
- Update `PasswordAuthentication yes`
- Restart SSH -> `sudo systemctl restart ssh`
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## If you are using WSL or EC2 Instance 
* run the commange in control node`ssh-keygen` to get public and praivate keys if you are using wsl or ec2 instance we can take public key and we have to add that into manage node exactly in authorization_keys where we can find this means we have run the command called ssh-keygen in manage node too..

