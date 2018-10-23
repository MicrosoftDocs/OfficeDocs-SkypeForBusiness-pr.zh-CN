---
title: 验证配置设置
TOCTitle: 验证配置设置
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204885(v=OCS.15)
ms:contentKeyID: 49312845
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证配置设置

 

_**上一次修改主题：** 2012-09-06_

可以通过在 中央管理存储所在的内部计算机上，或在安装 Lync Server 2013 核心组件 (OcsCore.msi) 的加入域的任何计算机上运行 Lync Server 2013**Get-CsManagementStoreReplicationStatus** cmdlet 来验证是否已将配置信息复制到边缘服务器。

初始结果可能指示复制的状态为“False”而非“True”。如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。

