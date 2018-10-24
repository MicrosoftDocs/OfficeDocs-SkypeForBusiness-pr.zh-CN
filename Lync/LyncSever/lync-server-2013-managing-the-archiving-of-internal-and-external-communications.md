---
title: 在 Lync Server 2013 中管理内部通信和外部通信的存档
TOCTitle: 在 Lync Server 2013 中管理内部通信和外部通信的存档
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204977(v=OCS.15)
ms:contentKeyID: 49313166
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中管理内部通信和外部通信的存档

 

_**上一次修改主题：** 2012-10-09_

在 Lync Server 2013 中，如果未使用 Microsoft Exchange 集成或您的用户未驻留在 Exchange 2013 上且其邮箱已被置于就地保留状态，则可使用存档策略为内部通信和外部通信启用和禁用存档。这包括以下存档策略：

  - 在部署 Lync Server 2013 时默认创建的全局策略。

  - 可创建并用于指定为特定站点或用户实现存档的方式的可选站点级和用户级策略。

您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。在 Lync Server 2013 控制面板中，可以使用“存档和监控”组的“存档策略”页来管理全局级、站点级和用户级的策略。如果将 Lync Server 存储与 Exchange 2013 存储集成，则 Exchange 用户策略将优先于 Lync Server 2013 存档策略。

有关策略如何实现的详细信息（包括策略的层次结构），请参见规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 若要控制存档的实现，您必须在存档配置中指定选项，例如，是否存档 IM 或会议、关键模式的用法和清除选项。默认情况下，在全局存档配置或任意站点或池存档配置中未启用任何选项。您应在存档配置中指定所有适当的选项，然后在存档策略中为内部或外部通信启用存档。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">在 Lync Server 2013 中管理组织、站点和池的存档配置选项</a>。<br />
如果为部署启用 Microsoft Exchange 集成，则 Exchange 策略可控制是否为驻留在 Exchange 2013 上且其邮箱处于就地保留状态的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。



## 本部分内容

  - [创建存档策略以启用或禁用特定站点或用户的内部或外部通信的存档](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [更改存档策略以启用或禁用组织、站点或用户的内部或外部通信的存档](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [将存档策略应用于用户](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [使用 Exchange 服务器集成设置存档的策略](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [删除存档策略](lync-server-2013-deleting-an-archiving-policy.md)

