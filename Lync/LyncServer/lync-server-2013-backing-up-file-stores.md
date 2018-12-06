---
title: 备份文件存储
TOCTitle: 备份文件存储
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202167(v=OCS.15)
ms:contentKeyID: 52060970
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 备份文件存储

 

_**上一次修改主题：** 2013-02-17_

备份 Lync Server 文件存储包括 Lync Server 组件使用的所有文件和文件夹。

## 备份文件存储

1.  若要查找 Lync Server 文件存储的特定位置，请打开拓扑生成器，并查看“文件存储”节点。

2.  使用 Robocopy 或其他文件系统管理工具将每个文件存储复制到 $Backup\\filestore。

