Verificar versão atual
```shell
cat /etc/os-release | grep -i pret
```

Verificar portas abertas
```shell
netstat -tunpl
```

Verificar serviços ativos
```shell
systemctl list-unit-files --state=enabled
```

Verificar Secure Boot
```shell
bootctl status
mokutil --sb-state
```

Verificar idioma
```shell
cat /etc/locale.conf
```

Verificar pontos de montagem
```shell
cat /etc/fstab
```

Verificar Package Locked
```shell
dnf versionlock list
dnf versionlock clear
```

Verificar proxy yum
```shell
cat /etc/yum.conf
```

Desinstalar kernel antigo
```shell
uname -r
dnf list installed kernel*
dnf repoquery --installonly --latest-limit 2 -q
sed -i 's/installonly_limit=3/installonly_limit=2/' /etc/dnf/dnf.conf
dnf config-manager --setopt=installonly_limit=2 --save
dnf remove $(rpm -qa | grep -i kernel | grep 4.18)
dnf remove $(rpm -qa | grep -i kernel | grep 203.146)
dnf autoremove -y
```

Atualizar e reiniciar
```shell
dnf update -y
init 6
```

Instalar pacotes de atualização
```shell
dnf install -y leapp leapp-deps leapp-repository leapp-upgrade-el8toel9 leapp-upgrade-el8toel9-deps
```

Checar dependencias de upgrade
```shell
leapp preupgrade --oraclelinux
```

OL Report Overview

Resolver dependencias de upgrade
```shell
dnf install -y vdo
rpm -qa | grep -i oswatcher
rpm -e oswatcher-9.0.0-5.el8.noarch
systemctl | grep -i oracle-cloud-agent
systemctl stop oracle-cloud-agent*
systemctl disable oracle-cloud-agent
sed -i s/^AllowZoneDrifting=.*/AllowZoneDrifting=no/ /etc/firewalld/firewalld.conf
leapp answer --section remove_pam_pkcs11_module_check.confirm=True
leapp answer --section check_vdo.confirm=True
```

Checar dependencias de upgrade
```shell
leapp preupgrade --oci
```

OCI Report Overview

Realizar upgrade
```shell
leapp upgrade --oci --verbose
```

UP OCI Report Overview

Reiniciar
```shell
init 6
```

Done Report Overview

Verificar e concluir
```shell
cat /etc/os-release
dnf clean all
systemctl enable oracle-cloud-agent
systemctl start oracle-cloud-agent
sed -i s/^"PermitRootLogin yes"/"PermitRootLogin no"/ /etc/ssh/sshd_config
systemctl restart sshd
dnf update -y
dnf autoremove -y
init 6
```

[Oracle](https://blogs.oracle.com/linux/post/upgrade-oracle-linux-8-to-oracle-linux-9-using-leapp)