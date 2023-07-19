# 一、安装open-vm-tools

```bash
sodo pacman -S open-vm-tools
```

# 二、安装其他依赖

```bash
sudo pacman -S gtkmm gtk2 xf86-video-vmware
```

# 三、相关设置

首先vmware开启自动适应客户端分辨率

然后编辑`/etc/mkinitcpio.conf`

编辑一下内容

```bash
# /etc/mkinitcpio.conf
MODULES=(vsock vmw_vsock_vmci_transport vmw_balloon vmw_vmci vmwgfx)
```

回到终端执行

```bash
sudo mkinitcpio -p linux
```

自启动设置

```bash
sudo systemctl enable vmtoolsd
```

重启

```bash
reboot
```

