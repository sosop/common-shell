# linux上常用shell命令

## 硬件查询

```shell l
# 查看所有硬件信息
dmidecode
dmidecode -q

# 查看bios相关硬件
dmidecode -t bios
# 查看系统相关硬件
dmidecode -t system
# 查看主板相关硬件
dmidecode -t baseboard 
# 查看机箱相关硬件
dmidecode -t chassis
# 查看处理器相关硬件
dmidecode -t processor
cat /proc/cpuinfo
lscpu
# 查看内存相关硬件
dmidecode -t memory
cat /proc/meminfo

# 查看帮助信息
dmidecode -h
```

## 操作系统相关

```shell
# 查看内核/操作系统/CPU信息的linux系统信息
uname -a
cat /proc/version
# 查看操作系统版本
head -n 1 /etc/issue
# 列出所有PCI设备
lspci -tv
# 列出所有USB设备
lsusb
# 列出加载的内核模块
lsmod
# 查看环境变量
env
```



## 磁盘相关

```shell
# 查看硬盘和分区
lsblk
fdisk -l
# 查看挂接的分区状态
mount | column -t
# 查看挂接的分区状态
swapon -s
# 查看硬盘使用情况
df -hT
# 硬盘检测命令smartctl
smartctl -a /dev/sda
# 磁盘类型
cat /sys/block/sda/queue/rotational # 0:ssd 1 sata
# 查看是硬盘还是U盘
cat /sys/block/sda/removable # 0 主板硬盘 1 usb外界硬盘
# 获取磁盘SN号
lsblk -d -no serial /dev/sda
```

## 网卡

```shell
# 查看网卡信息
dmesg | grep -i Ethernet
lspci | grep -i 'eth'
# 所有网络接口
ifconfig -a
ip link show
ls /sys/class/net/
# 某个网络接口的详细信息
ethtool wlp3s0
# 查看虚拟网卡
ls /sys/devices/virtual/net/

```

