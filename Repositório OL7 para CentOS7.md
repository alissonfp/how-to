~~~shell
mkdir -p ~/backup/repos

mv /etc/yum.repos.d/* ~/backup/repos

wget https://yum.oracle.com/public-yum-ol7.repo -O /etc/yum.repos.d/public-yum-ol7.repo

wget https://yum.oracle.com/RPM-GPG-KEY-oracle-ol7 -O /etc/pki/rpm-gpg/RPM-GPG-KEY-oracle

gpg --quiet --with-fingerprint /etc/pki/rpm-gpg/RPM-GPG-KEY-oracle

rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-oracle

dnf clean all

dnf update -y
