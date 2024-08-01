Atualizando e limpando o SO
```bash
dnf update -y
dnf upgrade -y
dnf autoremove -y
dnf clean all
```

Instalar o repositório do Gitlab
```bash
curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
```

Instalar o repositório Epel
```bash
dnf install -y oracle-epel-release-el9
```

Instalar dependencias
```bash
sudo yum install gpgme yum-utils
```

Download do binário do Gitlab-ce e copiando para /opt
```bash
dnf install --downloadonly gitlab-ce
cp /var/cache/dnf/gitlab_gitlab-ce-b7e5fcb1998ee0fd/packages/gitlab-ce-17.2.1-ce.0.el9.x86_64.rpm /opt
```

Instalar dependencias
```bash
dnf install -y dtrace \
gcc-c++ \
libstdc++-devel \
perl \
perl-Algorithm-Diff \
perl-Archive-Tar \
perl-Archive-Zip \
perl-Attribute-Handlers \
perl-AutoSplit \
perl-Benchmark \
perl-CPAN \
perl-CPAN-Meta \
perl-CPAN-Meta-Requirements \
perl-CPAN-Meta-YAML \
perl-Compress-Bzip2 \
perl-Compress-Raw-Lzma \
perl-Config-Extensions \
perl-Config-Perl-V \
perl-DBM_Filter \
perl-DB_File \
perl-Data-OptList \
perl-Data-Section \
perl-Devel-PPPort \
perl-Devel-Peek \
perl-Devel-SelfStubber \
perl-Devel-Size \
perl-Digest-SHA1 \
perl-DirHandle \
perl-Dumpvalue \
perl-Encode-devel \
perl-English \
perl-Env \
perl-ExtUtils-CBuilder \
perl-ExtUtils-Command \
perl-ExtUtils-Constant \
perl-ExtUtils-Embed \
perl-ExtUtils-Install \
perl-ExtUtils-MM-Utils \
perl-ExtUtils-MakeMaker \
perl-ExtUtils-Manifest \
perl-ExtUtils-ParseXS \
perl-File-Compare \
perl-File-DosGlob \
perl-File-Fetch \
perl-File-HomeDir \
perl-File-Which \
perl-FileCache \
