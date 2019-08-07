# Инструкции

* [Как начать Git](git_quick_start.md)
* [Как начать Vagrant](vagrant_quick_start.md)

## otus-linux

Используйте этот [Vagrantfile](Vagrantfile) - для тестового стенда.

#Мои действия по обновлению ядра

vagrant up
vagrant ssh otuslinux
yum groupinstall "Development tools"
sudo yum install openssl-devel
yum install bc
yum install kernel-devel
yum install net-snmp-devel
yum update
sudo yum install wget
wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.2.4.tar.xz
cd /usr/src
tar xf ~/linux 5
ln -s /usr/src/linux-5.2.4 /usr/src/linux
cd linux
cp /boot/config-3.10.0-957.27.2.el7.x86_64 .config
make oldconfig
make modules_install
make modules
make install
reboot
grub2-set-default 0
reboot
sudo -i
uname -r
5.2.4