---

copyright:
  years: 2014, 2018
lastupdated: "2018-08-17"

---
{:new_window: target="_blank"}
{:pre: .pre}

# 在 Linux 上安装 {{site.data.keyword.filestorage_short}}

首先，确保通过 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 对要访问 {{site.data.keyword.filestorage_full}} 卷的主机授权。

1. 在 {{site.data.keyword.filestorage_short}} 列表页面中，单击与新共享关联的**操作**，然后单击**授权主机**。
2. 从列表中选择一个或多个主机，然后单击**提交**。此操作将授权主机访问共享。

## 安装 {{site.data.keyword.filestorage_short}} 共享

使用以下指示信息将基于 Linux 的 {{site.data.keyword.BluSoftlayer_full}} 计算实例连接到网络文件系统 (NFS) 共享。示例基于 Red Hat Enterprise Linux 6。对于其他 Linux 分发版，可以根据相应操作系统 (OS) 供应商文档来调整这些步骤。

>**注** - 可以在 {{site.data.keyword.filestorage_short}} 列表页面中或通过以下 API 调用来获取文件存储器实例的安装点：`SoftLayer_Network_Storage::getNetworkMountAddress()`。

1. 安装必需的软件包/工具。
   ```
   # yum -y install nfs-utils nfs-utils-lib
   ```
   {:pre}
    
2. 安装远程共享。
   ```
   # mount -t "nfs version" -o "options" <mount_point> /mnt
   ```
       
   示例
   ```
   # mount -t nfs4 -o hard,intr
   nfsdal0501a.service.softlayer.com:/IBM01SV278685_7 /mnt
   ```
 
3. 验证安装是否成功。
   ```
   # df -h
   Filesystem Size Used Avail Use% Mounted on
   /dev/xvda2 25G 1.4G 22G 6% /
   tmpfs 1.9G 0 1.9G 0% /dev/shm
   /dev/xvda1 97M 51M 42M 55%
   ```
    
4. 转至安装点并读/写文件。
   ```
   # touch /mnt/test
   # ls -la /mnt
   total 12
   drwxr-xr-x 2 nobody nobody 4096 Sep 8 15:52 .
   dr-xr-xr-x. 22 root root 4096 Sep 8 14:30 ..
   -rw-r--r-- 1 nobody nobody 0 Sep 8 15:52 test
   ```

   >**注** - 由 root 用户创建的文件将具有所有权 `nobody:nobody`。为了正确显示所有权，`idmapd.conf` 需要使用正确的域设置进行更新。请参阅**如何对 NFS 实施 no_root_squash** 部分。
    
5. 在启动时安装远程共享。为了完成设置，请编辑文件系统表 (`/etc/fstab`) 以将远程共享添加到将在启动时自动安装的条目的列表：

   ```
   (hostname):/(username) /mnt "nfs version" "options" 0 0
   ```
    
   示例
    
   ```
   nfsdal0501a.service.softlayer.com:/IBM01SV278685_7 /mnt nfs4 defaults,hard,intr 0 0
   ```
    
6. 验证配置文件是否没有任何错误。

   ```
   # mount -fav
   ```
   {:pre}
    
   如果此命令完成且未发生任何错误，那么设置完成。

   >**注** - 如果使用的是 NFS 4.1，请将 `sec=sys` 添加到 mount 命令以防止文件所有权问题。

 
## 如何对 NFS 实施 `no_root_squash`（可选）

通过配置 `no_root_squash`，root 用户客户机可以保留对 NFS 共享的 root 用户许可权。 
- 对于 NFS V3，客户机无需执行任何操作；`no_root_squash` 会正常运作。
- 对于 NFS V4，您需要将 nfsv4 域设置为 `slnfsv4.com`，并启动 `rpcidmapd` 或操作系统使用的类似服务。

示例

1. 在主机中的 `/etc/idmapd.conf` 中设置域设置。

   ```
   #vi /etc/idmapd.conf
   [General]
   #Verbosity = 0
   #以下内容应设置为本地 NFS V4 域名
   #缺省值为主机的 DNS 域名。
   Domain = slnfsv4.com
   [Mapping]
   Nobody-User = nobody
   Nobody-Group = nobody
   ```
    
2. 运行 `nfsidmap -c`。
3. 启动 `rpcidmapd`。
   ```
   # /etc/init.d/rpcidmapd start
   Starting RPC idmapd: [ OK ]
   ```
