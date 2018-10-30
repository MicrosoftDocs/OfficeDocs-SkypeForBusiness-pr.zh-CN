---
title: Lync Server 2013：存档概述
TOCTitle: 存档概述
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204729(v=OCS.15)
ms:contentKeyID: 49312190
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的存档概述

 

_**上一次修改主题：** 2013-09-30_

Lync Server 2013 中的存档功能可向您提供一种存档通过 Lync Server 2013 发送的通信的方法。

可在初始 Lync Server 2013 部署期间实施存档，或将其添加到现有部署中。若要使用 Lync Server 2013 存档数据库（ SQL Server 数据库）存储存档数据，可使用 拓扑生成器将数据库添加到拓扑中，然后再次发布该拓扑。如果所有用户都托管在 Exchange 2013 中并且其邮箱处于就地保留状态，则不必更新拓扑，而只需启用 Microsoft Exchange 集成，以便在 Exchange 2013 中存储存档的数据。

实施存档时，需要配置存档以指定要存档的内容。默认情况下，不对任何内容存档。可以使用 Lync Server 2013 控制面板配置和管理存档。可以针对内部通信和/或外部通信实施存档。可以为您的整个组织和（可选）特定站点、特定池以及特定用户和用户组配置存档设置。有关确定适合您的组织的选项的详细信息，请参阅规划文档中的[在 Lync Server 2013 中定义组织的存档要求](lync-server-2013-defining-your-requirements-for-archiving.md)。有关如何实施存档策略和配置的详细信息以及可以或不能存档哪些信息的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

