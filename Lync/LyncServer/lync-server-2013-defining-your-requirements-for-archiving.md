---
title: Lync Server 2013：定义存档要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21f7d374d3c4263f2341386d2c4471f50e4b719d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中定义存档要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

如果您的组织必须遵循合规性管理法规，则可以部署存档以启用对 Lync Server 2013 即时消息（IM）和会议（会议）的存档支持。 有关可存档的内容类型的详细信息，请参阅规划文档中的[Lync Server 2013 中的存档概述](lync-server-2013-overview-of-archiving.md)。

若要实现存档，您首先需要确定如何满足组织的存档要求。 这要求确定以下内容：

  - **部署存档的时间**。 您可以将存档部署为最初的 Lync Server 2013 部署的一部分，也可以将其添加到现有部署中。 通过使用拓扑生成器将存档添加到拓扑中，然后发布拓扑来部署存档。

  - **存档内部通信还是外部通信**。您可实现对内部通信（即，内部用户间的通信）、外部通信（即，至少包括内部网络之外的一个用户的通信）或二者的存档。您可为整个组织指定这些选项，也可以为特定网站和池指定它们。默认情况下，将不会启用任一选项。
    
    <div>
    

    > [!NOTE]  
    > 如果使用 Microsoft Exchange 集成来存储存档数据，则 Exchange 设置将控制是否存档 Lync 通信。 如果您的部署包含多个林，则必须在 Lync Server 和 Exchange 之间同步设置。 控制内部或外部通信的存档仅适用于 Lync 策略。 对于 Exchange 集成的存档，这两种存档都将存档或不存档。

    
    </div>

  - **为什么启用存档**。可以在全局级别对整个部署启用和禁用存档，也可以对特定网站和用户启用和禁用存档。在这些级别中的每一个级别，您可指定是否启用 IM 会话（对等）、会议（多方会话）的存档或同时启用二者的存档。默认情况下，禁用存档。

  - **存档对于组织中用户的重要性**。 如果存档在您的组织中是至关重要的，则可以指定 Lync Server 2013 在关键模式下运行，这将阻止 IM 和会议会话（如果存档失败）。 例如：
    
      - 如果存档服务临时无法向数据库队列发送消息或向数据库插入消息，则将在部署中阻止 IM 和会议功能，直到恢复存档支持。
    
      - 如果会议用户上载某个文件，但该文件无法复制到存档文件存储，则在问题解决之前，将在部署中阻止会议功能，但不会阻止 IM 功能。
    
    您可在全局级别、网站级别和池级别配置此选项。默认情况下，不会启用临界模式。

  - **是否使用 Microsoft Exchange 集成**。 此选项将存档存储与 Exchange 2013 存储集成，以便您的 Lync Server 存档数据和 Exchange 2013 存档数据将一起存储在 Exchange 中。 如果托管在 Exchange 2013 上的用户的邮箱已被置于就地保留状态，则可以使用 Microsoft Exchange 集成来存储这些数据的存档数据。 如果您没有 Exchange 2013 部署，或者您不希望将其与 exchange 2013 集成，或者如果您有任何 Lync 用户未驻留在 Exchange 上，则可以使用 SQL Server 来存储 Lync 通信中的存档数据，从而部署单独的存档数据库。 您可以在全局级别、站点级别和池级别配置 Microsoft Exchange 集成选项。 默认情况下，不会启用 Microsoft Exchange 集成。

  - **管理存档数据的方式**。 存档数据库不适用于长期保留，Lync Server 2013 不提供用于存档数据的电子发现（搜索）解决方案，因此需要将数据移动到其他存储。 Lync Server 提供了可用于导出存档数据的会话导出工具，该工具可创建存档数据的可搜索脚本。 对于全局策略以及您创建的每个网站和用户策略，可启用数据清除并指定以下选项之一：
    
      - 在特定天数之后，清除导出的存档数据和存储的存档数据。可以指定的最小天数为一天。可以指定的最大天数为 2562 天。
    
      - 仅清除导出的存档数据。此选项会清除会话导出工具已导出并标记为可安全删除的所有记录。
    
    您可在全局级别、网站级别和池级别配置此选项。默认情况下，不会启用清除。

使用以下方法控制存档：

  - **存档策略**。您可使用一个或多个存档策略启用和禁用内部和外部通信的存档。默认情况下，不会启用任何存档。您可以使用默认全局策略在部署中启用或禁用内部通信、外部通信或这二者的存档。您无法删除全局策略。您可指定一个或多个可选网站策略来启用或禁用特定网站的内部和外部通信的存档。还可指定一个或多个用户策略来启用或禁用特定用户和用户组的存档。用户级别的策略将覆盖网站策略。网站级别的策略将覆盖全局级别的策略。仅可为配置为使用用户级别的策略的特定用户实现用户级别的策略。仅当至少一个参与者的策略配置为启用存档时，才会对组即时消息和会议进行存档。
    
    <div>
    

    > [!NOTE]  
    > 如果使用 Microsoft Exchange 集成，Exchange 2013 策略将覆盖驻留在 Exchange 2013 服务器上的所有用户的 Lync Server 存档策略。

    
    </div>

  - **存档配置**。您可使用一个或多个存档配置指定本主题之前介绍过的大部分存档选项，但启用内部和外部通信的存档除外（使用存档策略配置，如上一项中所述）。存档配置包括默认的全局配置和可选的网站和池配置。您无法删除全局配置。池级别的配置将覆盖网站级别的配置。网站级别的配置将覆盖全局级别的配置。

作为需求分析的一部分，您需要确定如何配置全局存档配置和全局存档策略。您还需要确定对任何网站级别存档配置、池级别存档配置、网站级别存档策略和用户级别存档策略的要求。

如果为一个前端池或 Standard Edition 服务器部署存档，则应该为部署中的所有其他前端池和 Standard Edition 服务器启用存档。需要执行此操作的原因是，需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。如果承载该对话或会议的池上没有启用存档，则可能无法存档所有会议数据。存档对于启用存档的用户和所有 IM 消息仍然有效，但可能无法存档会议内容和事件。

<div>


> [!NOTE]  
> 若要在维护组织的安全标准的同时启用管理任务委派，Lync Server&nbsp;2013 使用基于角色的访问控制（RBAC）。 利用 RBAC，可以通过将用户分配至预定义的管理角色来授予管理特权。 若要配置 Lync 存档策略和存档配置，必须将用户分配给 CsArchivingAdministrator 角色（除非直接在部署存档的服务器上完成配置，而不是通过其他计算机远程执行）。 有关 RBAC 的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。 有关存档部署所需的用户权限、权限和角色的列表，请参阅<A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的存档的部署清单</A>，它在规划文档和部署文档中都可用。<BR>如果使用 Microsoft Exchange 集成，则 Exchange 策略的配置需要适当的管理员权限和权限。 有关详细信息，请参阅 Exchange 2013 文档。



</div>

</div>

<span> </span>

</div>

</div>

</div>

