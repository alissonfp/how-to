Verificar hostname
```shell
hostname
```

Alterar hostname
```shell
hostnamectl set-hostname fedorasrv.home.afp

hostnamectl set-hostname olsrv.home.afp
```

Verificar hostname
```shell
hostname
```

Adicionar hostname ao arquivo hosts
```shell
echo "127.0.0.1 fedorasrv fedorasrv.home.afp" >> /etc/hosts
echo "10.0.12.11 fedorasrv fedorasrv.home.afp" >> /etc/hosts

echo "127.0.0.1 olsrv olsrv.home.afp" >> /etc/hosts
echo "10.0.11.11 olsrv olsrv.home.afp" >> /etc/hosts
```

Preservar alteração
```shell
sed -i 's/PRESERVE_HOSTINFO=0/PRESERVE_HOSTINFO=2/' /etc/oci-hostname.conf
init 6
```

[Wordpress](https://oraclepress.wordpress.com/2023/03/09/alterando-o-hostname-na-oci/)