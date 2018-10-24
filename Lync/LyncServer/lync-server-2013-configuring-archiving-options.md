---
title: 配置存档选项
TOCTitle: 配置存档选项
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205182(v=OCS.15)
ms:contentKeyID: 49313969
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置存档选项

 

_**上一次修改主题：** 2012-10-10_

在 Lync Server 2013 控制面板中，可以使用存档配置指定如何实施存档。这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

您最初是在部署存档时设置存档配置，但您可以在部署后更改、添加和删除配置。在 Lync Server 2013 控制面板中，可以使用 **Archiving and Monitoring** 组的“存档配置”页来管理全局级别、站点级别和池级别的配置。有关如何实现存档配置（包括可指定的选项以及存档配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。有关如何在部署后管理配置的详细信息，请参阅操作文档中的[在 Lync Server 2013 中管理组织、站点和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)。

> [!NOTE]  
> 要使用存档，则必须配置存档策略以指定是对内部通信、外部通信还是驻留在 Lync Server 2013 上的用户启用存档策略。默认情况下，不会为内部或外部通信启用存档。在任何策略中启用存档之前，您应为您的部署以及（可选）特定站点和池指定相应的存档配置，如本节所述。有关启用存档的详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配存档策略</a>。<br />
如果您没有在部署中针对所有用户使用 Microsoft Exchange 集成，则必须配置存档策略以指定是对内部通信、外部通信还是同时对这两者启用存档。默认情况下，不会为内部或外部通信启用存档，以在使用 Lync Server 2013 存档数据库时存档数据。在任何策略中启用存档之前，应为您的部署以及（可选）特定站点和池指定相应的存档配置，如本节中所述。有关启用存档以与 Lync Server 2013 存档数据库结合使用的详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配存档策略</a>。



## 本部分内容

  - [配置全局级别的存档选项](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [配置站点的存档选项](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [配置池的存档选项](lync-server-2013-configuring-archiving-options-for-a-pool.md)

