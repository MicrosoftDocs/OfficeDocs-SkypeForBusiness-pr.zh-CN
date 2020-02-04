---
title: Lync Server 2013：存档的工作原理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca026dcfb9b994353de139b6e10ecd419c9dd165
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>在 Lync Server 2013 中存档的工作方式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-04_

Lync Server 2013 存档提供的选项可帮助你满足合规性需求。 若要以最有效地满足组织要求的方式实施和维护它，应了解以下事项：

  - 可以存档哪些信息。

  - 如何在部署中启用和禁用存档。

  - 可配置的存档选项，用于控制实施存档的方式。

<div>

## <a name="what-information-can-be-archived"></a>哪些信息可以存档？

可存档以下类型的内容：

  - 对等即时消息

  - 多方即时消息的会议

  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）

  - 会议期间共享的白板和投票

以下类型的内容未存档：

  - 对等文件传输

  - 对等即时消息和会议的音频/视频

  - 对等即时消息和会议的桌面和应用程序共享

Lync 服务器也不会存档持久聊天对话。 若要存档持久聊天对话，您必须启用和配置合规性服务，该服务是可以使用 Microsoft Lync Server 2013、持久聊天服务器部署的组件。 有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>如何开始使用存档？

部署服务器时，会自动在每台前端服务器上安装存档，但除非配置存档，否则不会启用存档。 配置方式取决于部署存档的方式：

  - **使用 Microsoft Exchange 集成进行存档。** 如果您有托管在 Exchange 2013 上的用户，并且其邮箱已放在原地保留，则您可以选择将 Lync Server 2013 存储与 Exchange 存储集成的选项。 如果你选择 "Microsoft Exchange 集成" 选项，则使用 Exchange 2013 策略和配置来控制这些用户的 Lync Server 2013 数据的存档。

  - **使用 Lync Server 存档数据库进行存档。** 如果你的用户未托管在 Exchange 2013 上或未将其邮箱放置在原地保留中，或者如果你不希望对部署中的任何用户或所有用户使用 Microsoft Exchange 集成，则可以使用 SQL Server 部署 Lync Server 存档数据库 存储这些用户的存档数据。 在这种情况下，Lync Server 2013 存档策略和配置确定是否已启用存档以及如何实现存档。 若要使用 Lync Server 2013，必须向拓扑中添加相应的 SQL Server 数据库并发布拓扑。

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>使用 Microsoft Exchange 集成时的存档设置

如果你的用户托管在 Exchange 2013 上，并且其邮箱已放在原地保留中，你可以选择 " **Microsoft Exchange 集成**" 选项（如本节稍后部分所述），为这些用户存档 Lync Server 2013，然后通过指定 Exchange 就地保留策略和设置来控制这些用户的存档，以及控制以下各项的 lync server 配置：

  - 是存档 IM、会议还是同时存档两者。

  - 是否为 Lync Server 部署实现关键模式。

  - 选择 "Microsoft Exchange 集成" 选项以使用 Exchange 2013 存储存档数据。

本部分后面将介绍这些 Lync Server 2013 存档配置选项。 有关如何配置 Exchange 就地保留策略和设置以支持存档的信息，请参阅 Exchange 2013 产品文档。

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>使用 Lync Server 存档数据库存储时的存档设置

如果要使用 Lync Server 存档数据库（使用 SQL Server 数据库）对部署中任何用户的数据进行存档，则可以配置 Lync Server 存档策略来控制是否为这些用户启用存档。 在每个存档策略中，可以启用或禁用以下任一或全部的存档：

  - 内部通信

  - 外部通信

默认情况下，不会为任何 Lync Server 存档策略中的内部通信或外部通信启用存档。 使用 Lync Server 2013 控制面板或在 Lync Server 2013 管理外壳程序中使用 cmdlet 启用和禁用通信。

Lync Server 2013 存档策略包括以下内容：

  - **全局存档策略**。 这是默认存档策略，适用于整个部署。 它是在你部署 Lync Server 2013 时创建的，并且默认情况下，将禁用内部和外部通信的存档。 您不能删除此策略。 如果你选择 "删除" 选项，则全局策略将重置为默认设置。

  - **网站存档策略**。 或者，你可以通过为网站创建和配置网站级别的存档策略来启用或禁用一个或多个特定网站的存档。 创建网站级存档策略时，默认情况下不会启用存档。 你可以删除你创建的任何网站级存档策略。 网站级别的存档策略会覆盖全局策略，但仅适用于策略中指定的网站。 例如，如果在全局策略中启用了内部和外部通信的存档，并创建了一个网站策略，在其中禁用外部通信的存档，则仅为该网站存档内部通信。

  - **用户存档策略**。 或者，你可以通过为指定的用户和用户组创建、配置和应用用户级存档策略，为一个或多个特定用户和用户组启用或禁用存档。 创建用户级存档策略时，默认情况下不启用存档。 你可以删除你创建的任何用户级存档策略，也可以更改存档策略应用于的用户和用户组。 用户级存档策略将覆盖全局策略和任何网站策略，但仅适用于要对其应用该策略的用户和用户组。 例如，如果您在全局策略中禁用了内部和外部通信的存档，请创建一个网站级策略，在其中启用内部和外部通信的存档，然后创建禁用的用户级策略存档对于外部通信，将对所有网站用户的外部通信和内部通信同时进行通信，但对于应用用户级策略的用户而言，只会存档内部通信。

有关如何在部署存档时设置初始存档策略的详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置和分配存档策略](lync-server-2013-configuring-and-assigning-archiving-policies.md)"。 有关在部署后使用存档策略启用和禁用通信的详细信息，请参阅在操作文档中[管理 Lync Server 2013 中的内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。

<div>


> [!NOTE]  
> 如果你实现 Lync Server 2013 存档数据库并启用 Microsoft Exchange 集成，Exchange 2013 策略将覆盖 Lync Server 存档策略，但仅适用于托管在 Exchange 2013 并已将其邮箱置于原地保留的用户. Lync 存档仅取决于 Microsoft Exchange 就地保留策略。



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>我有哪些选项用于配置存档？

除了使用策略和启用和禁用存档，还可以为整个部署配置其他存档选项，还可以针对特定网站和池进行配置。 你可以通过使用一个或多个存档配置来控制大多数存档选项，这些配置在 Lync Server 2013 控制面板中可用，但也有另一个仅适用于使用 Lync Server 2013 管理外壳程序配置的选项。

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>"Lync Server 2013 控制面板" 中可用的存档配置选项

每个存档配置均提供以下选项：

全局级别配置在部署存档时自动创建，并且可以配置但不能删除。 如果选择删除全局配置的选项，则设置将重置为默认值。 你可以创建多个网站和池配置以及全局配置，控制存档设置。 对于全局配置以及每个网站和池配置，您可以使用以下选项：

  - 禁用存档，仅为即时消息（IM）启用存档，或者启用即时消息和会议的存档。

  - 配置关键模式以在 Lync 服务器出现故障时阻止 IM 和会议会话。 失败包括以下几项：
    
      - **即时消息**。 Lync Server 存储服务出现问题。 在此情况下，将阻止为存档启用的用户使用 IM。
    
      - **会议**。 故障可能是文件共享不可用或存储服务出现问题。 在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。

  - 指定使用 Microsoft Exchange Server 2013 集成以使用 Exchange 2013 存储存档数据，而不是设置单独的 SQL Server 数据库以存储 Lync Server 2013 存档数据。

  - 配置存档数据的清除选项。 这包括指定何时清除已存档的数据，这可能是下列情况之一：
    
      - 指定天数后的特定天数
    
      - 导出存档数据后（包括已上载到 Exchange 的数据）（如果启用 Microsoft Exchange 集成）。
    
    <div>
    

    > [!NOTE]  
    > 如果启用 Microsoft Exchange 集成，请清除托管在 Exchange 2013 上的用户，并将其邮箱置于就地保留状态由 Exchange 控制。 仅适用于会议文件的资格，这些文件存储在 Lync Server 文件共享中。 如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。

    
    </div>

默认情况下，不启用任何存档选项。 你可以使用 Lync Server 2013 控制面板管理存档配置。

你可以指定以下存档配置：

  - **全局存档配置**。 这是默认存档配置，适用于整个部署。 它是在部署 Lync Server 2013 时创建的，默认情况下，它不启用存档功能。 您可以修改全局配置，但不能将其删除。 如果为配置选择 "删除" 选项，则全局配置将重置为默认设置。

  - **网站存档配置**。 或者，你可以通过为单个网站创建和配置网站级别的存档配置，为一个或多个特定网站配置存档。 网站级别的存档配置仅在创建时才存在。 你可以修改或删除任何网站级存档配置。 网站级别的存档配置将覆盖全局配置，但仅适用于网站级配置中指定的网站。 例如，如果仅为全局配置中的 IM 启用存档，并创建可在其中为 IM 和会议同时启用存档的网站配置，则仅为网站存档会议，而不是组织的其余部分。

  - **池存档配置**。 或者，你可以通过为单个池创建和配置池级配置来指定一个或多个特定池的存档设置。 池级别的存档配置仅在创建时才存在。 你可以修改和删除任何池级别的存档配置。 池级别的存档配置覆盖你可能已创建的全局配置和任何网站存档配置。 例如，如果仅为全局配置中的 IM 启用存档，请创建网站级配置，在该配置中，你可以为网站的 IM 和会议启用存档，然后创建池级别配置，仅在其中启用存档IM，将为网站的所有用户（驻留在池级配置中指定的池中的用户除外）的 IM 和会议存档通信。 对于组织中的所有其他用户，将仅为 IM 启用存档。

有关如何在部署存档时设置初始存档配置的详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置存档选项](lync-server-2013-configuring-archiving-options.md)"。 有关在部署后使用存档策略启用和禁用通信的详细信息，请参阅操作文档中的 "[管理 Lync Server 2013 中的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)"。

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>仅在 Windows PowerShell 中可用的存档选项

使用 Lync Server 2013 命令行管理程序，你可以使用 cmdlet 来实现 Lync Server 2013 控制面板中不可用的选项。 这些选项包括以下内容：

  - **存档重复邮件**。 有关详细信息，请参阅操作文档中的 "[新建-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) " 和 "[设置 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) "。

  - **导出已存档的数据**。 有关详细信息，请参阅[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>如何访问已存档的数据？

存档数据的访问取决于数据的存储位置：

  - **Microsoft Exchange 存储**。 如果你选择 "Exchange 集成" 选项，Lync Server 将为托管在 Exchange 2013 上的所有用户在 Exchange 2013 存储中的存档内容，并将其邮箱放在原地保留中。 已存档的数据存储在用户邮箱 "可恢复的项目" 文件夹中，该文件夹通常对用户不可见，并且只能由具有 Exchange**发现管理**角色的用户搜索。 如果部署了，Exchange 将启用联合搜索和发现，以及 SharePoint。 有关存储在 Exchange 中的数据的存储、保留和发现的更多详细信息，请参阅 Exchange 2013 和 SharePoint 文档。

  - **Lync 服务器存储**。 如果将 Lync server 2013 存档数据库设置为存储 Lync Server 数据，Lync Server 将把存档内容放在 Lync Server 存档数据库（SQL Server 数据库）中，用于任何未驻留在 Exchange 2013 的用户，并且未将其邮箱放在就地保留。 This data is not searchable, but it can be exported to formats that are searchable using other tools. 有关导出存储在存档数据库中的数据的详细信息，请参阅在操作文档中[导出 Lync Server 2013 中的存档数据](lync-server-2013-exporting-archived-data.md)。

有关 Lync Server 2013 和 Exchange 2013 如何协同工作的更多详细信息，请参阅支持文档中[Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

