Adicionar o hostname no arquivo hosts para o loopback
```bash
sudo vi /etc/hosts
```
~~~vim
127.0.0.1   fedorasrv fedorasrv.home.afp  
~~~

Instalar pacotes
```bash
sudo yum install -y realmd sssd krb5-workstation krb5-libs oddjob oddjob-mkhomedir samba-common-tools
```

Descobrir o domínio
```bash
sudo realm discover HOME.AFP
```

Inicializar o kerberos
```bash
sudo kinit administrator@HOME.AFP
```

Ingressar ao domínio
```bash
sudo realm join --verbose HOME.AFP -U 'administrator@HOME.AFP'
```

Permitir autenticação por senha no SSH
```bash
sudo vi /etc/ssh/sshd_config
```
~~~vim
PasswordAuthentication yes  
~~~
```bash
sudo systemctl restart sshd
```

Conceder privilégio de sudo
```bash
sudo visudo
```
~~~vim
# Add 'AAD DC Administrators' group members as admins.
%AAD\ DC\ Administrators@home.afp ALL=(ALL) NOPASSWD:ALL
~~~

Testar login
```bash
ssh -l alisson@HOME.AFP fedorasrv.home.afp

pwd

id
```

Testar comando
```bash
sudo yum update -y
```

[Microsoft](https://learn.microsoft.com/pt-br/entra/identity/domain-services/join-rhel-linux-vm?tabs=rhel7)