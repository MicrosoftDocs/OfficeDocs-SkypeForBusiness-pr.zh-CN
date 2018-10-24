---
title: Lync Server 2013：验证内部服务器与边缘服务器之间的连接
TOCTitle: 验证内部服务器与边缘服务器之间的连接
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398292(v=OCS.15)
ms:contentKeyID: 49312232
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中验证内部服务器与边缘服务器之间的连接

 

_**上一次修改主题：** 2012-09-08_

在 Lync Server 2013 中，提供了一个单独的验证向导来帮助验证边缘服务器与内部服务器之间的连接。在 Lync Server 2013 中，安装边缘服务器时将自动完成连接验证。

可以通过在 中央管理存储所在的内部计算机（或安装 Lync Server 2013 核心组件 (OcsCore.msi) 的加入域的任何计算机）上运行 Windows PowerShell**Get-CsManagementStoreReplicationStatus** cmdlet 来验证是否已将配置信息复制到边缘。初始结果可能指示复制的状态为“False”而非“True”。如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。

可以单独验证外部用户连接，包括使用 Office Communications Server 远程连接分析器验证远程用户连接。有关详细信息，请参阅 [在 Lync Server 2013 中验证外部用户连接](lync-server-2013-verify-connectivity-for-external-users.md)。

