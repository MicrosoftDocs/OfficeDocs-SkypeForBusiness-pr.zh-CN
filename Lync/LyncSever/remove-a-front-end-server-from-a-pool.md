---
title: 从池删除前端服务器
TOCTitle: 从池删除前端服务器
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49888466
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从池删除前端服务器

 

_**上一次修改主题：** 2012-10-04_

Microsoft Lync Server 2010 Enterprise Edition 前端服务器无法作为独立计算机存在。它必须定义为 前端池，即使池中只有一台计算机也是如此。

本主题指导您完成从现有 前端池中删除单个 前端服务器的过程。如果 前端服务器是池中仅有的服务器或者要完全删除池，请参阅 [删除前端池或 Standard Edition 服务器](remove-front-end-pool-or-standard-edition-server.md)。在删除 前端池之前，无需删除单个 前端服务器。在删除池时，将删除每台 前端服务器。

## 从池中删除前端服务器

1.  打开 Lync Server 2013 前端服务器，然后打开拓扑生成器。

2.  导航到 Lync Server 2010 节点。

3.  展开“Enterprise Edition 前端池”，展开具有要删除的前端服务器的前端池，右键单击要删除的前端服务器，然后单击“删除”。

