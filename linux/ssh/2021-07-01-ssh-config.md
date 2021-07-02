# SSH config file

SSH config file can be used to facilitate login on the remote ssh server using only one command. for eg 
```yaml
Host pi-master
    HostName 1.2.3.4
    User pi-master
    Port 22
    UseKeychain yes
    IdentitiesOnly yes
    PubKeyAuthentication yes
    IdentityFile /Users/my-user/.ssh/pi-master-private-key
```

config name is pi-master
the server I'm trying to login is at 1.2.3.4:22.
I need to use username pi-master and I'm logging in with Public key Authentication. 
IdentitiesOnly means use only the key provided and nothing else to login. 
IdentityFile is the private key for which a public key is present on the server.
Additionally, the UseKeychain command is Mac specific. It makes keychain remember private key password (if it was set when creating the key). This additional config is not required on Linux, linux remembers the key password by default.
