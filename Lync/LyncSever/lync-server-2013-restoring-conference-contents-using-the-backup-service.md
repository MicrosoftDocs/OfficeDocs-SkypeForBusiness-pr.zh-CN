---
title: Lync Server 2013：使用备份服务还原会议内容
TOCTitle: 使用备份服务还原会议内容
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49888383
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中使用备份服务还原会议内容

 

_**上一次修改主题：** 2012-11-01_

如果存储在前端池的文件存储中的会议信息变得不可用，则您必须还原此信息，以便驻留在池中的用户能够保留其会议数据。如果丢失了会议数据的前端池与另一个前端池配对，您可以使用备份服务还原数据。

此外，如果整个池已失败并且您必须将其用户故障转移到备份池，则也必须执行此任务。在将这些用户故障转移回其原始池时，您也必须使用此过程将其会议内容复制回其原始池。

假定将 Pool1 与 Pool2 配对且 Pool1 中的会议数据已丢失。您可以使用以下 cmdlet 调用备份服务来还原内容：

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

还原会议内容可能需要一些时间，具体取决于该内容的大小。您可以使用以下 cmdlet 检查过程状态：

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

当此 cmdlet 为数据会议模块返回值“稳定状态”时，表示此过程已完成。

