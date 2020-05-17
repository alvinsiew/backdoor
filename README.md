# backdoor

backdoor allow you to execute any command as root in linux machine with authorize group.

## How to setup

### First compile into a binary

```bash
env GOOS=linux GOARCH=amd64 go build -o backdoor main.go
```

### setuid for backdoor binary and permission for group execution only

```bash
chmod 4710 backdoor
```

### set owner of binary to root and group to desire group

```bash
chown root:group backdoor
```

Setup is now completed. Verify by executing below command with user belong to group set above.

```bash
backdoor whoami
```

User should return root.
