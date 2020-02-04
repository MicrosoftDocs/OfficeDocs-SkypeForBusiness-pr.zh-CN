---
title: Lync Server 2013：定义组织的存档要求
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
ms.openlocfilehash: a3cee7269620a9525456e40604ae3f1d1c2cf33d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中定义组织的存档要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-09_

如果你的组织必须遵循合规性规定，你可以部署存档以启用对 Lync Server 2013 即时消息（IM）和会议（会议）的存档支持。 有关可存档的内容类型的详细信息，请参阅规划文档中[Lync Server 2013 中的存档概述](lync-server-2013-overview-of-archiving.md)。

若要实现存档，首先需要确定如何满足组织对存档的要求。 这需要确定以下内容：

  - **何时部署存档**。 你可以将存档部署为你的初始 Lync Server 2013 部署的一部分，也可以将其添加到现有部署。 通过使用拓扑生成器将其添加到拓扑，然后发布拓扑来部署存档。

  - **存档内部通信还是外部通信**。您可实现对内部通信（即，内部用户间的通信）、外部通信（即，至少包括内部网络之外的一个用户的通信）或二者的存档。您可为整个组织指定这些选项，也可以为特定网站和池指定它们。默认情况下，将不会启用任一选项。
    
    <div>
    

    > [!NOTE]  
    > 如果你使用 Microsoft Exchange 集成来存储存档的数据，Exchange 设置将控制是否存档 Lync 通信。 如果你的部署包含多个林，则必须在 Lync Server 和 Exchange 之间同步设置。 仅适用于 Lync 策略控制内部或外部通信的存档。 对于 Exchange 集成的存档，这两个都将存档或不存档。

    
    </div>

  - **为什么要启用存档**。 你可以在全局级别为整个部署启用和禁用存档，并且你可以启用和禁用特定网站和用户的存档。 在每个级别，指定是否启用 IM 会话（对等）、会议（这是多方会话）的存档。 默认情况下，禁用存档。

  - **您的组织中的用户的重要存档方式**。 如果存档在你的组织中是任务关键型的，则可以指定 Lync Server 2013 在 "关键" 模式下运行，这将在存档失败时阻止 IM 和会议会话。 例如：
    
      - 如果存档服务暂时无法将消息发送到数据库队列或将消息插入到数据库中，则将在部署中阻止 IM 和会议功能，直到还原存档支持。
    
      - 如果会议用户上载文件，但无法将文件复制到存档文件存储，则在部署中将阻止会议功能，直到问题得到解决，但不阻止 IM 功能。
    
    你可以在全局级别、网站级别和池级别配置此选项。 默认情况下，不启用关键模式。

  - **是否使用 Microsoft Exchange 集成**。 此选项将存档存储与 Exchange 2013 存储集成，以便您的 Lync 服务器存档数据和 Exchange 2013 存档数据将一起存储在 Exchange 中。 你可以使用 Microsoft Exchange 集成来存储托管在 Exchange 2013 上的用户的存档数据（如果其邮箱已放在原地保留）。 如果您没有 Exchange 2013 部署，或者如果您不希望与之集成，或者如果您有任何 Lync 用户未托管在 Exchange 2013 上，则可以通过使用 SQL Server 从 Lync 通信存储已存档的数据来部署单独的存档数据库。 你可以在全局级别、网站级别和池级别配置 Microsoft Exchange 集成选项。 默认情况下，不启用 Microsoft Exchange 集成。

  - **如何管理存档数据**。 存档数据库不适用于长期保留，并且 Lync Server 2013 不会为存档的数据提供电子发现（搜索）解决方案，因此需要将数据移动到其他存储。 Lync Server 提供了一种会话导出工具，可用于导出已存档的数据，这将创建已存档数据的可搜索脚本。 对于全局策略以及你创建的每个网站和用户策略，你可以启用数据清除并指定下列选项之一：
    
      - 在特定天数后清除导出的存档数据并存储存档数据。 您可以指定的最少天数是一天。 可以指定的最大天数为2562天。
    
      - 仅清除导出的存档数据。 此选项清除由会话导出工具导出并标记为可安全删除的所有记录。
    
    你可以在全局级别、网站级别和池级别配置此选项。 默认情况下，不启用清除。

你可以使用以下方法控制存档：

  - **存档策略**。 使用一个或多个存档策略启用和禁用内部和外部通信的存档。 默认情况下，不启用任何存档。 你可以使用默认全局策略在部署中启用或禁用内部通信、外部通信或两者的存档。 您不能删除全局策略。 你可以指定一个或多个可选的网站策略，以便为特定网站启用或禁用内部和外部通信的存档。 你还可以指定一个或多个用户策略来启用或禁用特定用户和用户组的存档。 用户级策略替代网站策略。 网站级别策略替代全局级别策略。 用户级策略仅针对配置为使用该策略的特定用户执行。 只有当至少一个参与者的策略配置为启用存档时，才会存档组即时消息和会议。
    
    <div>
    

    > [!NOTE]  
    > 如果使用 Microsoft Exchange 集成，Exchange 2013 策略将覆盖驻留在 Exchange 2013 服务器上的所有用户的 Lync Server 存档策略。

    
    </div>

  - **存档配置**。 你可以使用一个或多个存档配置来指定本主题前面所述的大部分存档选项，除了允许存档内部和外部通信（使用存档策略进行配置），如本文中所述。上一个项目符号）。 存档配置包括默认全局配置和可选网站和池配置。 您不能删除全局配置。 池级配置替代网站级别的配置。 网站级配置替代全局级别配置。

作为需求分析的一部分，你需要确定如何配置全局存档配置和全局存档策略。 你还需要确定任何网站级存档配置、池级存档配置、网站级存档策略和用户级存档策略的要求。

如果你为一个前端池或标准版服务器部署存档，则应该为部署中的所有其他前端池和标准版服务器启用它。 你需要执行此操作，因为需要存档其通信的用户可以被邀请到其他池中托管的组 IM 对话或会议。 如果在托管对话或会议的池上未启用存档，则可能不会存档所有会议数据。 存档仍将适用于启用存档的用户和所有 IM 消息，但会议内容和事件可能不会存档。

<div>


> [!NOTE]  
> 若要在维护组织的安全标准的同时启用管理任务委派，Lync Server&nbsp;2013 使用基于角色的访问控制（RBAC）。 利用 RBAC，可以通过将用户分配至预定义的管理角色来授予管理特权。 若要配置 Lync 存档策略和存档配置，必须将用户分配给 CsArchivingAdministrator 角色（除非直接在部署存档的服务器上执行配置，而不是从另一台计算机远程执行配置）。 有关 RBAC 的详细信息，请参阅规划文档中<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的 "规划基于角色的访问控制</A>"。 有关存档部署所需的用户权利、权限和角色的列表，请参阅<A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中存档的部署清单</A>，该清单可在 "规划文档" 和 "部署" 文档中提供。<BR>如果你使用 Microsoft Exchange 集成，则 Exchange 策略的配置需要相应的管理员权限。 有关详细信息，请参阅 Exchange 2013 文档。



</div>

</div>

<span> </span>

</div>

</div>

</div>

