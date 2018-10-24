---
title: Lync Server 2013：将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池
TOCTitle: 将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49888381
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池

 

_**上一次修改主题：** 2012-10-05_

每个 Survivable Branch Appliance (SBA) 都与一个 前端池（充当 SBA 的备份注册器）关联。如果要将 前端池升级到 Lync Server 2013，在 前端池升级过程中必须解除 SBA 与 前端池的关联。在升级 前端池后，可将 SBA 与 前端池重新关联。这涉及到使用拓扑生成器删除拓扑中的 SBA，然后将 SBA 重新添加到拓扑生成器。在从拓扑中删除 SBA 之前，必须将驻留在 SBA 上的分支用户移动到其他 前端池。将 SBA 添加回拓扑后，可将这些用户移回 SBA。

这些步骤概括如下：

1.  将驻留在 SBA 上的用户移动到其他 前端池。

2.  从拓扑中删除 SBA 以解除作为备份注册器的现有 前端池的关联。

3.  将 前端池升级到 Microsoft Lync Server 2013。

4.  将 SBA 添加回拓扑。

5.  将新 前端池作为备份注册器与 SBA 关联。

6.  将分支用户移回 SBA。

## 本部分内容

  - [将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [将 Lync Server 2010 Survivable Branch Appliance 分支站点添加到您的拓扑](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

