---
title: 配置和分配存档策略
TOCTitle: 配置和分配存档策略
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205175(v=OCS.15)
ms:contentKeyID: 49313933
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置和分配存档策略

 

_**上一次修改主题：** 2012-10-01_

在 Lync Server 2013 中，可以使用策略针对驻留在 Lync Server 2013 上的用户启用和禁用内部通信和外部通信的存档。这包括以下存档策略：

  - 部署 Lync Server 2013 时默认创建的全局策略。

  - 您可以创建并用来指定如何针对特定站点或用户实施存档的可选站点级别和用户级别策略。

您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。在 Lync Server 2013 控制面板中，可以使用“存档和监控”组的“存档策略”页来管理全局级别、站点级别和用户级别的策略。

> [!NOTE]  
> 为了控制存档的实施，您必须在存档配置中指定选项，如是否存档 IM 或会议、临界模式的使用，以及清除选项。默认情况下，在全局存档配置或任何站点或池存档配置中不会启用任何选项。您应先在存档配置中指定所有适当的选项，然后再针对存档策略中的内部或外部通信启用存档。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">在 Lync Server 2013 中管理组织、站点和池的存档配置选项</a>。<br />
如果您将 Lync Server 存储与 Exchange 2013 存储进行集成，则 Exchange 用户策略的优先于 Lync Server 2013 存档策略，但是仅适用于驻留在 Exchange 2013 上并将其信箱置于就地保留状态的那些用户。



有关策略的实现方式的详细信息（包括策略的层次结构），请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。有关如何在部署后管理策略的详细信息，请参阅操作文档中的[在 Lync Server 2013 中管理内部通信和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。

## 本部分内容

  - [配置存档的全局策略](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [设置存档的站点策略](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [为用户设置存档策略](lync-server-2013-setting-up-archiving-policies-for-users.md)

