---
title: Lync Server 2013：对池进行故障回复
TOCTitle: 对池进行故障回复
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204945(v=OCS.15)
ms:contentKeyID: 49313040
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中对池进行故障回复

 

_**上一次修改主题：** 2012-11-01_

在经历灾难的池恢复联机（即此示例中的 Pool1）后，执行以下步骤来使部署恢复常规工作状态。

请注意，故障回复过程需要几分钟时间才能完成。一个 20,000 个用户的池需要占用 60 分钟的时间，可以此为参考。

1.  通过键入以下 cmdlet 返回到最初驻留在 Pool1 中并已故障转移到 Pool2 的用户：
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

无需执行其他步骤。如果故障转移 中央管理服务器，则可将其保留在 Pool2 中。

