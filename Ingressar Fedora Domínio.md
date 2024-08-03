```bash
sudo vi /etc/hosts
```
127.0.0.1   fedorasrv fedorasrv.home.afp  

```bash
sudo yum install -y realmd sssd krb5-workstation krb5-libs oddjob oddjob-mkhomedir samba-common-tools

sudo realm discover HOME.AFP

sudo kinit administrator@HOME.AFP

sudo realm join --verbose HOME.AFP -U 'administrator@HOME.AFP'
```

```bash
sudo vi /etc/ssh/sshd_config
```
PasswordAuthentication yes  

```bash
sudo systemctl restart sshd
```

```bash
sudo visudo
```
%AAD\ DC\ Administrators@aaddscontoso.com ALL=(ALL) NOPASSWD:ALL

```bash
ssh -l alisson@HOME.AFP fedorasrv.home.afp

pwd

id
```

```bash
sudo yum update -y
```
