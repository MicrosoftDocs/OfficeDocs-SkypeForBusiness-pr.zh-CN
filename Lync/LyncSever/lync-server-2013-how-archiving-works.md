---
title: Lync Server 2013 的存档工作原理
TOCTitle: Lync Server 2013 的存档工作原理
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204900(v=OCS.15)
ms:contentKeyID: 49312861
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的存档工作原理

 

_**上一次修改主题：** 2014-02-04_

Lync Server 2013 存档功能可提供帮助您满足合规性要求的选项。要以符合贵组织要求的最高效方式实现和维护该功能，您应该了解：

  - 可以存档的信息。

  - 如何在您的部署中启用和禁用存档。

  - 可以配置以控制如何实现存档的存档选项。

## 可以存档哪些信息？

可以存档以下类型的内容：

  - 对等即时消息

  - 多方即时消息的会议

  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）

  - 会议期间共享的白板和投票

不存档以下类型的内容：

  - 对等文件传输

  - 对等即时消息和会议的音频/视频

  - 对等即时消息和会议的桌面和应用程序共享

Lync Server 也不存档持久聊天对话。要存档持久聊天对话，必须启用和配置合规性服务，该服务是一个可以使用 Microsoft Lync Server 2013持久聊天服务器部署的组件。有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

## 如何开始使用存档？

部署每台前端服务器时将自动在该服务器上安装存档，但存档在您配置之前不会启用。配置存档的方式由存档的部署方式决定：

  - **使用 Microsoft Exchange 集成的存档。** 如果您的用户驻留在 Exchange 2013 上，并且其邮箱已被置于就地保留状态，则可以选择此选项以将 Lync Server 2013 存储与 Exchange 存储集成。如果您选择 Microsoft Exchange 集成选项，则可使用 Exchange 2013 策略和配置来控制这些用户的 Lync Server 2013 数据存档。

  - **使用 Lync Server 存档数据库的存档。** 如果您的用户未驻留在 Exchange 2013 上或其邮箱未被置于就地保留状态，或者您不希望对部署中的任意或所有用户使用 Microsoft Exchange 集成，则可使用 SQL Server 部署 Lync Server 存档数据库来存储这些用户的存档数据。在此情况下，Lync Server 2013 存档策略和配置将决定是否启用存档及其实现方式。若要使用 Lync Server 2013，则必须向您的拓扑添加适当的 SQL Server 数据库并发布该拓扑。

## 使用 Microsoft Exchange 集成时存档设置

如果您的用户驻留在 Exchange 2013 上，并且其邮箱已被置于就地保留状态，则可选择“Microsoft Exchange 集成”选项（如本节后面所述）以便为这些用户存档 Lync Server 2013，然后您可通过指定 Exchange 就地保留策略和设置来控制这些用户的存档，并指定 Lync Server 配置来控制以下内容：

  - 是否存档 IM、会议或二者。

  - 是否为 Lync Server 部署实现关键模式。

  - 选择 Microsoft Exchange 集成选项以使用 Exchange 2013 存储已存档的数据。

本节后面将介绍这些 Lync Server 2013 存档配置选项。有关如何配置 Exchange 就地保留策略和设置以支持存档的信息，请参阅 Exchange 2013 产品文档。

## 使用 Lync Server 存档数据库存储时存档设置

若要使用 Lync Server 存档数据库（使用 SQL Server 数据库）为部署中的任何用户存档数据，您可以配置 Lync Server 存档策略以控制是否为这些用户启用存档。在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：

  - 内部通信

  - 外部通信

默认情况下，任何 Lync Server 存档策略都不会对内部通信或外部通信启用存档。可使用 Lync Server 2013 控制面板或使用 Lync Server 2013 命令行管理程序中的 cmdlet 启用和禁用通信。

Lync Server 2013 存档策略包括以下内容：

  - **全局存档策略**。这是默认存档策略，适用于您的整个部署。该策略是在您部署 Lync Server 2013 时创建的，并且默认情况下，同时针对内部和外部通信禁用存档。您无法删除此策略。如果您选择删除选项，那么全局策略将重置为默认设置。

  - **站点存档策略**。（可选）您可以通过为一个或多个特定站点创建和配置站点级别存档策略，来对该站点启用或禁用存档。当您创建站点级别存档策略时，默认情况下不启用存档。您可以删除任何您所创建的站点级别存档策略。站点级别存档策略会覆盖全局策略，但仅针对策略中指定的站点。例如，如果在全局策略中对内部和外部通信启用存档，并创建了一个对外部通信禁用存档的站点策略，则只能针对该站点存档内部通信。

  - **用户存档策略**。（可选）您可以通过为一个或多个指定用户和用户组创建、配置和应用用户级别存档策略，来为这些特定用户和用户组启用或禁用存档。当您创建用户级别存档策略时，默认情况下不启用存档。您可以删除任何您所创建的用户级别存档策略，并且可以更改应用存档策略的用户和用户组。用户级别存档策略会覆盖全局策略和任何站点策略，但仅针对应用策略的用户和用户组。例如，如果在全局策略中对内部和外部通信禁用存档，并创建了一个对内部和外部通信启用存档的站点级别策略，然后创建了一个对外部通信禁用存档的用户级别策略，那么将为所有站点用户存档外部和内部通信，但是不包括那些应用了用户级别策略的用户，将仅为这些用户存档内部通信。

有关在部署存档时如何设置初始存档策略的详细信息，请参阅部署文档中的[配置和分配存档策略](lync-server-2013-configuring-and-assigning-archiving-policies.md)。有关部署后使用存档策略启用和禁用通信的详细信息，请参阅操作文档中的[在 Lync Server 2013 中管理内部通信和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。

> [!NOTE]  
> 如果您实现这两个 Lync Server 2013 存档数据库并启用 Microsoft Exchange 集成，则 Exchange 2013 策略将重写 Lync Server 存档策略，但仅针对驻留在 Exchange 2013 上且其邮箱已被置于就地保留状态的用户执行此操作。Lync 存档仅取决于 Microsoft Exchange 就地保留策略。



## 有哪些可供选择的配置存档选项？

除了使用策略启用和禁用存档以外，您还可以选择可针对整个部署（或针对特定站点和池）配置的其他存档选项。使用 Lync Server 2013 控制面板中的一个或多个存档配置可控制大多数存档选项，但还有一个选项仅适用于使用 Lync Server 2013 命令行管理程序的配置。

## Lync Server 2013 控制面板中提供的存档配置选项

每个存档配置提供以下选项。

在部署存档时自动创建全局配置，可以对全局配置进行配置，但不能删除它。如果您选择删除全局配置，那么设置将重置为默认值。您可以创建多个站点和池配置，与全局配置一起控制存档设置。对于全局配置和每个站点及池配置，您可以选择以下选项：

  - 禁用存档、仅针对即时消息 (IM) 启用存档或同时针对 IM 和会议启用存档。

  - 配置关键模式，以便在 Lync Server 发生故障时阻止 IM 和会议会话。故障包括以下几种类型：
    
      - **IM**。Lync Server 存储设备出现问题。在此情况下，为启用存档的用户阻止 IM。
    
      - **会议**。故障可能是文件共享不可用或存储服务出现问题。在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。

  - 指定通过 Microsoft Exchange Server 2013 集成使用 Exchange 2013 存储存档数据，而不设置单独的 SQL Server 数据库来存储 Lync Server 2013 存档数据。

  - 配置存档数据的清除选项。这包括指定何时清除存档数据，可以是以下任意时间：
    
      - 在您指定的特定天数之后
    
      - 在导出存档数据（如果启用 Microsoft Exchange 集成，还包括上载到 Exchange 的数据）后。
    
    > [!NOTE]  
    > 如果您启用 Microsoft Exchange 集成，则清除驻留在 Exchange 2013 上的用户及其处于就地保留状态的邮箱的过程由 Exchange 进行控制。该唯一限制针对存储在 Lync Server 文件共享中的会议文件。如果您选择在已导出存档数据后，或者选择在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。
    


默认情况下不启用任何存档选项。您可以使用 Lync Server 2013 控制面板管理存档配置。

您可以指定以下存档配置：

  - **全局存档配置**。这是默认存档配置，并且适用于您的整个部署。该配置是在部署 Lync Server 2013 时创建的，并且默认情况下不启用存档功能。可以修改全局配置，但无法删除它。如果您为配置选择删除选项，则全局配置将重置为默认设置。

  - **站点存档配置**。（可选）您可以通过为单个站点创建和配置站点级别存档配置来为一个或多个特定站点配置存档。站点级别存档配置仅在您创建它后才会存在。您可以修改或删除任何站点级别存档配置。站点级别存档配置会覆盖全局配置，但仅针对站点级别配置中指定的站点。例如，如果您在全局配置中仅为 IM 启用存档，并创建了一个同时为 IM 和会议启用存档的站点配置，那么仅会为该站点存档会议，而不会为组织的其他站点存档会议。

  - **池存档配置**。（可选）您可以通过为单个池创建和配置池级别配置来为一个或多个特定池指定存档设置。池级别存档配置仅在您创建它后才会存在。您可以修改或删除任何池级别存档配置。池级别存档配置会覆盖全局配置和您可能已创建的任何站点存档配置。例如，如果您在全局配置中仅为 IM 启用存档，并创建了一个同时为站点的 IM 和会议启用存档的站点配置，然后创建了一个仅为 IM 启用存档的池级别配置，那么将为该站点的所有用户存档 IM 和会议通信，但是不包括那些驻留在池级别配置中指定的池中的用户。对于贵组织中的所有其他用户，仅针对 IM 启用存档。

有关部署存档时如何设置初始存档配置的详细信息，请参阅部署文档中的[配置存档选项](lync-server-2013-configuring-archiving-options.md)。有关部署后使用存档策略启用和禁用通信的详细信息，请参阅操作文档中的[在 Lync Server 2013 中管理组织、站点和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)。

## 仅在 Windows PowerShell 中可用的存档选项

通过 Lync Server 2013 命令行管理程序，您可以使用 cmdlet 实现 Lync Server 2013 控制面板中未提供的选项。这些选项包括：

  - **存档重复消息**。有关详细信息，请参阅操作文档中的 [New-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingConfiguration) 和 [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration)。

  - **导出存档数据**。有关详细信息，请参阅 [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)

## 如何访问存档数据？

存档数据的访问取决于数据的存储位置：

  - **Microsoft Exchange存储**。如果您选择 Exchange 集成选项，则 Lync Server 会为驻留在 Exchange 2013 上且其邮箱已被置于就地保留状态的所有用户将存档内容存放在 Exchange 2013 存储中。存档数据将存储在用户邮箱的可恢复项文件夹中，该文件夹通常对用户可见且仅可供具有 Exchange**Discovery Management** 角色的用户搜索。Exchange 允许与 SharePoint（如果已部署）进行联盟搜索和发现。有关存储、保留和发现存储在 Exchange 中的数据的详细信息，请参阅 Exchange 2013 和 SharePoint 文档。

  - **Lync Server 存储**。如果您设置 Lync Server 2013 存档数据库来存储 Lync Server 数据，则 Lync Server 会为未驻留在 Exchange 2013 上且其邮箱已被置于就地保留状态的任何用户将存档内容存放在 Lync Server 存档数据库（SQL Server 数据库）中。虽然此数据是不可搜索的，但可以采用可通过其他工具搜索的格式导出此数据。有关导出存储在存档数据库中的数据的详细信息，请参阅操作文档中的[在 Lync Server 2013 中导出存档数据](lync-server-2013-exporting-archived-data.md)。

有关如何结合使用 Lync Server 2013 和 Exchange 2013 的更多详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md)。

