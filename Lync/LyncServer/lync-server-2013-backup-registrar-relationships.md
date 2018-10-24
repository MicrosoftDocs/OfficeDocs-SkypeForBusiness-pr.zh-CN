---
title: Lync Server 2013 备份注册器关系
TOCTitle: 备份注册器关系
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205033(v=OCS.15)
ms:contentKeyID: 49313386
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的备份注册器关系

 

_**上一次修改主题：** 2012-06-28_

除了提供灾难恢复功能外，两个配对的池彼此用作对方的备份注册器。在 Lync Server 2013 中， 前端池之间的备份注册器关系始终为 1:1 和互反的。这意味着，如果 P1 是 P2 的备份，则 P2 必须为 P1 的备份，两者均不能成为任何其他前端池的备份。这是对 Lync Server 2010 所做的更改，其中 前端池备份关系可能为多对一。

即使两个 前端池之间的备份关系必须为 1:1 和对称的，每个 前端池仍可作为任意数量的 Survivable Branch Appliance 的备份注册器，与 Lync Server 2010 中相同。

请注意， Lync Server 2013 不将灾难恢复支持扩展到驻留在 Survivable Branch Appliance 上的用户。如果用作 Survivable Branch Appliance 备份的前端池关闭，那么即使在驻留在前端池上的用户故障转移到备份 前端池之后，登录 Survivable Branch Appliance 的用户也会进入恢复能力模式。

