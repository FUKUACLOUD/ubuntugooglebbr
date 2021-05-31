# ubuntugooglebbr

enable google bbr on ubuntu 16.04

sudo apt update

sudo apt install linux-generic-hwe-16.04

sudo shutdown -r now

sudo modprobe tcp_bbr

echo "tcp_bbr" >> /etc/modules-load.d/modules.conf

echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf

echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf

sysctl -p

sysctl net.ipv4.tcp_available_congestion_control

sysctl net.ipv4.tcp_congestion_control

lsmod | grep bbr
