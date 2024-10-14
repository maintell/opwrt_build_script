# opwrt_build_script    

### 基于 Linux 6.12 固件下载：

x86_64: https://github.com/JohnsonRan/opwrt_build_script/releases

```
【首次登陆】
地址：172.16.1.1（默认）
用户：root
密码：空

【分区挂载】
系统 -> 磁盘管理 -> 磁盘 -> 编辑
系统 -> 挂载点
```

---------------

- 优化系统内核
  - [x] Full Cone NAT
  - [x] TCP BBRv3
  - [x] TCP Brutal
  - [x] eBPF
  - [x] Shortcut-FE
  - [x] RTC 时钟
  - [x] O3、LTO、MOLD、LRNG

| ⚓ 服务 |  🩺 网络  |
|  :----  | :----  |
| Watchcat | 网速测试 |
| MihomoTProxy | WireGuard |
| | UPnP |

------
### DDNS
固件内置 [kkkgo/UE-DDNS](https://github.com/kkkgo/UE-DDNS)   
- 只需要在终端输入 `ue-ddns` 即可快速配置DDNS脚本，并支持hotplug接口（可实现网卡IP变动时，自动执行脚本）
- 支持消息通知，具体请查看 [官方文档](https://blog.03k.org/post/ue-ddns.html#%E8%87%AA%E5%AE%9A%E4%B9%89%E9%80%89%E9%A1%B9%E5%92%8C%E6%B6%88%E6%81%AF%E9%80%9A%E7%9F%A5)

### RTC 硬件时钟

**本固件支持 RTC 硬件时钟读取/同步，当设备断电时，重新通电启动系统时间不会错乱** *（注意：设备需要安装 RTC 电池后使用）*

**首次安装 RTC 电池写入时间命令**

```shell
hwclock -w -f /dev/rtc0
```

**测试时间读取（返回当前时间表示正常）**

```shell
hwclock -f /dev/rtc0
```