---
title: 配置用于迁移的客户端
TOCTitle: 配置用于迁移的客户端
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49888508
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置用于迁移的客户端

 

_**上一次修改主题：** 2016-12-08_

本主题包含在迁移到 Lync Server 2013 之前应采取的推荐客户端部署步骤。这些配置更改应在 Office Communications Server 2007 R2 上进行。在迁移之前必须执行这些步骤，这一点非常重要。有关详细信息，请参阅 [规划 Lync Server 2013 中的客户端和设备](lync-server-2013-planning-for-clients-and-devices.md)。

## 在迁移之前配置客户端

1.  部署最新的 Office Communications Server 2007 R2 服务器、客户端和设备更新（修补程序）：
    
      - [应用 Office Communications Server 2007 R2 更新](apply-office-communications-server-2007-r2-updates.md)
    
      - [Communicator 2007 R2 的累积更新程序包描述](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [获取设备的软件更新](http://go.microsoft.com/fwlink/?linkid=335809)

2.  在 Office Communications Server 2007 R2 上，使用客户端版本筛选以便仅允许安装了最新更新的 Office Communications Server 2007 R2 客户端登录。

3.  在 Office Communications Server 2007 R2 上，使用客户端版本筛选来阻止 Lync Server 2013 客户端登录。按照 [http://go.microsoft.com/fwlink/?linkid=202488\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=202488%26clcid=0x804) 上的“配置客户端版本筛选”中所述的步骤添加下表中列出的版本筛选器。为每个版本筛选器分配“阻止”操作。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>客户端</th>
    <th>用户代理标头</th>
    <th>版本</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*.*</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*.*</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*.*</p></td>
    </tr>
    </tbody>
    </table>

