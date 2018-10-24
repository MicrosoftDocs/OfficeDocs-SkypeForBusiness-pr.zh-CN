---
title: "从 Office Communications Server 2007 R2 群聊或 Lync Server 2010 群聊迁移到 2013 持久聊天服务器"
TOCtitle: "从 Office Communications Server 2007 R2 群聊或 Lync Server 2010 群聊迁移到 2013 持久聊天服务器"
ms:assetid: 5b4d3db1-6eba-4932-b49c-f60bcf9488f9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615442(v=OCS.15)
ms:contentKeyID: 49312960
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器

 

_**上一次修改主题：** 2012-10-06_

本节中的主题引导您完成将 Lync Server 2010 群聊或 Office Communications Server 2007 R2群聊迁移到 Lync Server 2013持久聊天服务器的过程。如果计划使 Lync Server 2013持久聊天服务器部署与 Lync Server 2010 群聊或 Office Communications Server 2007 R2群聊部署共存，本指南还包含一些用于在此混合环境中进行操作的重要信息。本指南重点说明 持久聊天服务器的数据迁移。对于从旧版 Lync Server 迁移到 Lync Server 2013 的用户，请参阅 [从 Lync Server 2010 迁移到 Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) 和 [从 Office Communications Server 2007 R2 迁移至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。

> [!IMPORTANT]
> 本主题假定您已安装 Lync Server 2013 以与 Lync Server 2010 或 Office Communications Server 2007 R2 共存。


> [!IMPORTANT]
> 本指南介绍完成迁移的每个阶段通常需要执行的步骤。它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。本指南还提供了验证步骤的示例。提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。可根据您的特定迁移过程修改这些验证步骤。


本指南提供专用于升级现有部署的信息。它未解释如何更改现有拓扑。本指南不涉及新功能的实现。如果本指南中的某个过程已在其他文档中得到详细说明，本指南将为您指出相应的文档名称或文档章节。

在本文档中，术语的定义如以下列表所示。

  - *迁移*   
    将部署从 持久聊天服务器的早期版本（以前称为 群聊服务器）移至 Lync Server 2013持久聊天服务器。

<!-- end list -->

  - *升级*   
    在服务器或客户端计算机上安装软件的更高版本。

<!-- end list -->

  - *共存*   
    在迁移期间存在的临时环境，其中部分功能已迁移至 Lync Server 2013持久聊天服务器并且其他功能仍保留在 群聊服务器的早期版本中。

持久聊天服务器是 Lync Server 2013 基础结构的扩展。根据所用拓扑，可以将 Lync Server 2010 群聊或 Office Communications Server 2007 R2群聊迁移到 Lync Server 2013持久聊天服务器。有关可用拓扑以及迁移 群聊服务器的技术和软件要求的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

如果您的组织需要合规性支持，则它现在会自动与每个 持久聊天服务器一起安装。合规性不再需要单独的服务器。

> [!IMPORTANT]
> 持久聊天服务器必须安装在 Windows NT 文件系统上才能帮助强制执行文件系统安全性。FAT32 是 持久聊天服务器不支持的文件系统。<br />
> 如果您的组织需要合规性支持，则它现在会自动与每个 持久聊天服务器一起安装。合规性不再需要单独的服务器。有关 Lync Server 2013持久聊天服务器中的更改的详细信息，请参阅入门文档中的 <a href="lync-server-2013-new-persistent-chat-server-features.md">Lync Server 2013 中新的持久聊天服务器功能</a>。


## 本节内容

  - [标准迁移方案 - 高级别](standard-migration-scenario-high-level.md)

  - [迁移过程 - 详细信息](migration-process-details.md)

  - [共存注意事项](coexistence-considerations.md)

