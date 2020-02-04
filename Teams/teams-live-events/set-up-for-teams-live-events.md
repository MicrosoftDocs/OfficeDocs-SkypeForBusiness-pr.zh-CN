---
title: 在 Microsoft Teams 中为实时事件进行设置
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 了解在团队中设置事件的活动的步骤，包括准备网络、分配许可证、使用策略为用户启用实时事件功能和计划以及设置第三方分发提供商。
f1.keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebc72d8238e5551c7a09cae3d617e8f6a187befb
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708328"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中为实时事件进行设置

当您正在设置实时事件时，必须执行几个步骤。

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>步骤1：为团队中的实时事件设置网络
在团队中生成的实时事件要求你为[团队准备组织的网络](https://docs.microsoft.com/microsoftteams/prepare-network)。  

## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
请确保你对[可以创建和安排实时事件](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events)以及[可以观看实时事件](plan-for-teams-live-events.md#who-can-watch-live-events)的人员拥有正确的许可证分配。

## <a name="step-3-set-up-live-events-policies"></a>步骤3：设置实时事件策略
实时事件策略用于控制你的组织中的哪些人可以保存实时事件以及他们创建的事件中可用的功能。 你可以使用默认策略或创建一个或多个自定义实时事件策略。 创建自定义策略后，将其分配给组织中的一个或多个用户组。

> [!NOTE]
> 除非你创建并分配自定义策略，否则你组织中的用户将获取全局策略。 默认情况下，全局策略会为团队用户启用实时事件计划，并且实时标题和字幕（脚本）已关闭，组织中的每个人都可以加入实时事件，并且录制设置将设置为 "始终录制"。 

### <a name="create-or-edit-a-live-events-policy"></a>创建或编辑实时事件策略
<a name="bkcreatepolicy"> </a>

**![使用 Microsoft 团队管理中心显示 Microsoft 团队](../media/teams-logo-30x30.png)徽标的图标**

1. 在左侧导航中，转到 "**会议** > **实时事件策略**"。 
2. 请执行下列操作之一：
- 如果要编辑现有的默认策略，请选择 "**全局（组织范围默认）**"。 
- 如果要创建新的自定义策略，请选择 "**新建策略**"。 
- 如果要编辑自定义策略，请选择该策略，然后选择 "**编辑**"。 

    你可以更改这些设置以满足组织的需求。

    ![实时事件策略设置的屏幕截图](../media/teams-live-events-policies.png "Microsoft 团队管理中心中的实时事件策略设置的屏幕截图") 

|设置  |说明  |
|---------|---------|
|**标题**     |这是 "实时事件策略" 页面上显示的策略的标题。 它不能超过64个字符，也不能包含任何特殊字符。          |
|**说明**    |使用此设置添加策略的友好描述。         |
|**允许计划**     |打开此功能后，您的组织中的用户可以创建和安排团队中的实时事件。 请务必知道，如果你希望用户安排使用外部应用或设备生成的实时事件，则必须执行其他步骤。 若要了解详细信息，请参阅[使用户能够计划使用外部应用或设备生成的事件](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。     |
|**允许对与会者进行脚本输入** |此设置仅可应用于团队中产生的事件。 启用此功能将使实时事件参与者可以在事件期间查看实时字幕和字幕。         |
|**哪些人可以加入计划的实时事件**    |选择下列操作之一。<br><br>**所有人**用户可以创建实时事件，每个人（包括组织外部的人员）都可以参加。 当用户安排实时事件时，此设置将启用团队中的**公共**权限类型。<br> **组织中的每个人**用户可以创建你的组织中的人员（包括添加到你的组织的[来宾用户](../add-guests.md)）可以参加的实时事件。 用户无法创建由匿名用户参与的实时事件。 当用户安排实时事件时，此设置将启用团队中的**组织范围**权限类型。<br> **特定用户或组**用户可以创建仅限组织中的特定用户或组可以参加的实时事件。 用户无法创建由组织中的所有人或匿名用户出席的实时事件。 当用户安排实时事件时，此设置将启用团队中的 "**人员和组**" 权限类型。       |
|**录制设置**  <br>     | 此设置仅可应用于团队中产生的事件。 选择下列操作之一。 <br><br> **始终录制**始终记录用户创建的实时事件。 在事件结束后，事件团队成员可以下载录制，与会者可以观看事件。 <br> **从不录制**不会记录用户创建的实时事件。 <br>**组织者可以录制**用户可以决定是否录制实时事件。 如果它已录制，事件结束后，事件团队成员可以下载录制，并且与会者可以观看该事件。      

也可以使用 Windows PowerShell 执行此操作。 有关详细信息，请参阅[使用 PowerShell 设置团队中的实时事件策略](set-teams-live-events-policies-using-powershell.md)。 

### <a name="assign-a-live-events-policy-to-users"></a>将实时事件策略分配给用户 

如果你创建了自定义实时事件策略，请将其分配给用户以使策略处于活动状态。 

![显示 Microsoft 团队徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 在左侧导航中，转到 "**用户**"，然后选择用户。
2. 在 "**分配的策略**" 旁边，选择 "**编辑**"。 
3. 选择要分配的实时事件策略，然后选择 "**保存**"。 

你还可以将实时事件策略分配给一个或多个用户，如下所示：

![显示 Microsoft 团队徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 转到 "**会议** > **实时事件策略**"。
2. 通过单击策略名称的左侧，选择策略。
3. 选择 "**管理用户**"。
4. 在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。 对要添加的每个用户重复此步骤。
5. 完成添加用户后，请选择 "**保存**"。
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>允许用户计划使用外部应用或设备生成的事件

若要让用户计划使用外部应用或设备生成的事件，还必须执行以下操作：

1. 为你的组织中的用户启用 Microsoft Stream。 流作为符合条件的 Office 365 订阅的一部分或作为独立服务提供。 Business Essentials 或 Business Premium 计划中未包含流。 有关详细信息，请参阅[流许可概述](https://docs.microsoft.com/stream/license-overview)。

      深入了解如何[向 Office 365 中的用户分配许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问流。 确保对于[本文](https://docs.microsoft.com/stream/disable-user-organization)中定义的用户，流未被阻止。

2. 确保用户在流中具有实时事件创建权限。 默认情况下，管理员可以使用外部应用或设备创建事件。 流管理员可以[为流中的实时事件创建启用其他用户](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)。  

3. 确保实时事件组织者已同意由流管理员设置的公司策略。如果流管理员已[设置公司指南策略](https://docs.microsoft.com/stream/company-policy-and-consent)并要求员工在保存内容之前接受此策略，则用户必须先执行此操作，然后才能在团队中创建实时事件（使用外部应用或设备）。 在组织中推出 "实时事件" 功能之前，请确保将创建这些实时事件的用户同意该策略。 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>步骤4：为团队中的实时事件设置视频分发解决方案
实时事件视频的播放使用自适应比特率流（ABR），但它是单播流，这意味着每个查看器都从 internet 获取自己的视频流。 对于发送给组织中的大部分内容的实时事件或视频，查看者可能会使用大量的 internet 带宽。 对于希望减少实时事件的 internet 流量的组织，实时事件解决方案与 Microsoft 的受信任的视频交付合作伙伴（提供软件定义的网络（SDNs）或企业内容交付网络（eCDNs）集成。 这些 SDN/eCDN 平台使组织能够在不影响最终用户查看体验的情况下优化网络带宽。 我们的合作伙伴可以帮助您在企业网络中实现更具伸缩性和更高效的视频分发。

在**团队外购买和设置您的解决方案**利用 Microsoft 的受信任的视频交付合作伙伴，获取有关缩放视频传递的专家帮助。 在你可以启用要与团队一起使用的视频交付提供商之前，你必须在外购买和设置 SDN/eCDN 解决方案，并将其与团队分开。

以下 SDN/eCDN 解决方案是预集成的，可以设置为与 Stream 一起使用。

- **配置单元流**为实时和点播的企业视频分发提供了一个简单且功能强大的解决方案。 Hive 是基于软件的解决方案，无需额外的硬件或带宽，也可提供一种安全的方法来启用数以千计的同时视频查看器，而不影响你的网络。 对于希望在购买 SDN/eCDN 解决方案之前了解视频影响的客户在其网络上的影响，蜂巢流还为 Microsoft 客户提供了基于浏览器的分析解决方案。 [了解详细信息](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。
 
- **Kollective**是一种基于云的智能对等分发平台，可利用你的现有网络基础结构，以更快、更可靠的方式以及更低的带宽提供内容（实时流视频、按需视频、软件更新、安全修补程序等）。 我们的安全平台受世界上最大的金融机构的信任，没有其他硬件、设置和维护非常简单。 [了解详细信息](https://kollective.com/microsoft-pilot/)。
 
- **斜 OmniCache**提供下一代网络分发，确保跨全球 wan 的视频内容无缝传递，帮助事件发生器优化网络带宽并支持成功的实时事件广播和按需流。 即将推出针对团队中产生的实时事件的快速起步 OmniCache 支持。 [了解详细信息](http://www.ramp.com)。 
 
> [!NOTE] 
> 所选的 SDN 或 eCDN 解决方案须遵守所选的**第三方提供商的服务条款和隐私策略**，这些条款将控制提供商的解决方案的使用。 您对提供商的解决方案的使用将不受 Microsoft 批量许可条款或在线服务条款的制约。 如果您不同意**第三方提供商的条款**，则不要在团队中启用该解决方案。 

设置 SDN 或 eCDN 解决方案之后，你可以为团队中的实时事件配置提供程序。 

## <a name="next-steps"></a>后续步骤
转到["配置团队中的实时事件设置"](configure-teams-live-events.md)。

### <a name="related-topics"></a>相关主题
- [什么是 Teams 实时事件？](what-are-teams-live-events.md)
- [规划 Teams 实时事件](plan-for-teams-live-events.md)
- [配置团队中的实时事件设置](configure-teams-live-events.md)

