---
title: 为 Lync Server 存档设置用户策略
TOCTitle: 为 Lync Server 存档设置用户策略
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204742(v=OCS.15)
ms:contentKeyID: 49312247
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 存档设置用户策略

 

_**上一次修改主题：** 2012-10-10_

为驻留在 Lync Server 2013 上的特定用户启用或禁用存档需要创建和配置一个或多个用户策略，然后将相应的策略应用于特定用户或用户组。用户策略将覆盖站点策略和全局策略，但仅针对驻留在 Lync Server 2013 上的用户。

用户始终驻留在 Lync Server 中。如果启用 Microsoft Exchange 集成，则其邮箱位于 Microsoft Exchange Server 2013 中的用户无需管理其 Lync Server 中的存档策略。这些用户及存档将由 Exchange 就地保留来管理。

有关存档策略的工作方式的详细信息（包括全局、站点和用户策略的层次结构），请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 如果为部署启用 Microsoft Exchange 集成，Exchange 就地保留策略将控制是否为驻留在 Exchange 2013 上的用户启用存档。为这些用户启用存档要求他们将其邮箱置于就地保留状态。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。<br />
您应在存档配置中指定所有适当的选项，然后再启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-archiving-options.md">配置存档选项</a>。



## 本部分内容

  - [在 Lync Server 中创建和配置存档的用户策略](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [将 Lync Server 存档策略应用于用户](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

