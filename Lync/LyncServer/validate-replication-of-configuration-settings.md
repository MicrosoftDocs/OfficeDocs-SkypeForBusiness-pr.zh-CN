---
title: 验证配置设置的复制
TOCTitle: 验证配置设置的复制
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205042(v=OCS.15)
ms:contentKeyID: 49313420
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证配置设置的复制

 

_**上一次修改主题：** 2012-10-19_

可以通过在中央管理存储所在的内部计算机（或安装 Lync Server 2013 核心组件的加入域的任何计算机）上运行 Lync Server 2013**Get-CsManagementStoreReplicationStatus** cmdlet 来验证是否已将配置信息复制到边缘服务器。

初始结果可能指示复制的状态为“False”而非“True”。如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** cmdlet 前为完成复制留出时间。

