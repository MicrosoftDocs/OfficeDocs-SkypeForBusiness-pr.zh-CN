---
title: 配置将受监控的 Lync Server 计算机
TOCTitle: 配置将受监控的 Lync Server 计算机
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205118(v=OCS.15)
ms:contentKeyID: 49313766
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置将受监控的 Lync Server 计算机

 

_**上一次修改主题：** 2012-10-20_

由于 Lync Server 2013 不使用在 Microsoft Lync Server 2010 中使用的中央恢复过程，因此要监控的每台 Lync Server 2013 计算机必须能够自行向管理服务器报告其存在。为此，您必须在要监控的每台计算机上安装 Operations Manager 代理文件。在安装这些代理文件后，您必须对计算机进行配置，以将其用作 System Center 代理。请注意，您应先在这些计算机上安装并配置 Lync Server，然后再执行这些过程。

