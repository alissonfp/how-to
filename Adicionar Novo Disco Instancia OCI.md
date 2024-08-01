Adicionar repositório
```bash
dnf config-manager --enable ol8_oci_included
dnf config-manager --enable ol8_developer
```

Instalar pacotes da OCI
```bash
dnf install python36-oci-sdk python36-oci-cli oci-utils
```

Habilitar serviço ocid
```bash
systemctl enable --now ocid.service && systemctl status ocid.service
```

Verificar volumes
```bash
oci-iscsi-config show
```

Adicionar volume
```bash
oci-iscsi-config create --size 512 --volume-name=ol-gitlab --attach-volume
```

Verificar volumes
```bash
oci-iscsi-config show
```

Criar physical volume
```bash
pvs
pvcreate /dev/sdb
pvs
```

Criar volume group
```bash
vgs
vgcreate gitlab /dev/sdb
vgs
```

Criar logical volume
```bash
lvs
lvcreate -n opt-gitlab -L 32G gitlab
lvcreate -n var-opt-gitlab -L 320G gitlab
lvs
```

Formatar volumes
```bash
mkfs.xfs /dev/mapper/gitlab-opt-gitlab
mkfs.xfs /dev/mapper/gitlab-var-opt-gitlab
```

Montar volumes
```bash
df -h
mkdir /opt/gitlab
echo -e '/dev/mapper/gitlab-opt-gitlab\t/opt/gitlab\txfs\tdefaults\t0 0' >> /etc/fstab
mkdir /var/opt/gitlab
echo -e '/dev/mapper/gitlab-var-opt-gitlab\t/var/opt/gitlab\txfs\tdefaults\t0 0' >> /etc/fstab
mount -a
df -h
```

[Youtube](https://www.youtube.com/watch?v=ubJP56xgpB0)
