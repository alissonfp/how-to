Verificar hostname
```shell
hostname
```

Alterar hostname
```shell
hostnamectl set-hostname maat.valecard.com.br

hostnamectl set-hostname toth.valecard.com.br
```

Verificar hostname
```shell
hostname
```

Adicionar hostname ao arquivo hosts
```shell
echo "127.0.0.1 maat maat.valecard.com.br" >> /etc/hosts
echo "10.2.0.45 maat maat.valecard.com.br" >> /etc/hosts

echo "127.0.0.1 toth toth.valecard.com.br" >> /etc/hosts
echo "10.2.0.18 toth toth.valecard.com.br" >> /etc/hosts
```

Preservar alteração
```shell
sed -i 's/PRESERVE_HOSTINFO=0/PRESERVE_HOSTINFO=2/' /etc/oci-hostname.conf
init 6
```

[Wordpress](https://oraclepress.wordpress.com/2023/03/09/alterando-o-hostname-na-oci/)