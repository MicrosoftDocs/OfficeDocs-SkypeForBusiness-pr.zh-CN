---
title: 在 Microsoft Teams 中为实时事件进行设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 在 Teams 中为实时事件进行设置，包括设置网络、分配许可证、启用实时事件功能和安排以及视频分发解决方案。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ae30fdb824c62027d1a704435e80df2a9abf1f85
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140561"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中为实时事件进行设置

为实时事件进行设置时，必须执行几个步骤。

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>第 1 步：在 Teams 中为实时事件设置网络
在 Teams 中制作的实时事件要求你[为 Teams 准备贵组织的网络](https://docs.microsoft.com/microsoftteams/prepare-network)。  

## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
请确保为[可以创建和安排实时事件的用户](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events)以及[可以观看实时事件的用户](plan-for-teams-live-events.md#who-can-watch-live-events)分配正确的许可证。

## <a name="step-3-set-up-live-events-policies"></a>第 3 步：设置实时事件策略
实时事件策略用于控制组织中的哪些人员可以主持实时事件，以及其创建的事件中的可用功能。 可使用默认策略或创建一个或多个自定义实时事件策略。 创建自定义策略后，将其分配给组织中的一个或多个用户组。

> [!NOTE]
> 除非你创建并分配了自定义策略，你组织中的用户将获取全局策略。 默认情况下，在全局策略中，已为 Teams 用户启用实时事件安排，已关闭实时辅助字幕与字幕（转录），组织中的每个人都可以加入实时事件，并且录制设置已设置为“始终录制”。 

### <a name="create-or-edit-a-live-events-policy"></a>创建或编辑实时事件策略
<a name="bkcreatepolicy"> </a>

**![显示 Microsoft Teams 徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft Teams 管理中心**

1. 在左侧导航中，转到“**会议**” > “**实时事件策略**”。 
2. 执行下列操作之一：
- 如果要编辑现有默认策略，请选择“**全局(默认为组织范围)**”。 
- 如果要创建新的自定义策略，请选择“**新建策略**”。 
- 如果要编辑自定义策略，请选择该策略，然后选择“**编辑**”。 

    可更改以下设置以满足组织的需求。

    ![实时事件策略设置的屏幕截图](../media/teams-live-events-policies.png "Microsoft Teams 管理中心中的实时事件策略设置屏幕截图") 

|设置  |说明  |
|---------|---------|
|**标题**     |这是显示在实时事件策略页面上的策略标题。 它不能超过 64 个字符或包含任何特殊字符。          |
|**说明**    |使用它为策略添加友好说明。         |
|**允许安排**     |启用此设置可让组织中的用户在 Teams 中创建和安排实时事件。 请务必注意，如果希望用户安排使用外部应用或设备制作的实时事件，则必须执行其他步骤。 若要了解详细信息，请参阅[允许用户安排使用外部应用或设备制作的事件](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。     |
|**允许与会者转录** |此设置仅适用于在 Teams 中制作的事件。 启用此设置后，实时事件参与者可在事件期间查看实时辅助字幕与字幕。         |
|**可以加入已计划实时事件的用户**    |选择以下选项之一。<br><br>**任何人** 用户可以创建允许任何人（包括组织外部的人员）参与的实时事件。 当用户安排实时事件时，此设置将在 Teams 中启用**公共**权限类型。<br> **组织中的所有人** 用户可以创建允许组织内的人员（包括添加到组织的[来宾用户](../add-guests.md)）参与的实时事件。 用户不能创建由匿名用户参与的实时事件。 当用户安排实时事件时，此设置将在 Teams 中启用**组织范围**权限类型。<br> **特定用户或组** 用户可以创建只允许组织内的特定用户或组参与的实时事件。 用户不能创建由组织内的任何人或匿名用户参与的实时事件。 当用户安排实时事件时，此设置将在 Teams 中启用**人员和组**权限类型。       |
|**录制设置**  <br>     | 此设置仅适用于在 Teams 中制作的事件。 选择以下选项之一。 <br><br> **始终录制** 始终录制由用户创建的实时事件。 事件结束后，事件团队成员可以下载录制内容，并且参加者可以观看该事件。 <br> **从不录制** 从不录制由用户创建的实时事件。 <br>**组织者可以录制或不录制** 用户可以决定是否录制实时事件。 如果已录制，则事件结束后，事件团队成员可以下载录制内容，并且参加者可以观看该事件。      

你可以使用 Windows PowerShell 来执行此操作。 有关详细信息，请参阅[使用 PowerShell 在 Teams 中设置实时事件策略](set-teams-live-events-policies-using-powershell.md)。 

### <a name="assign-a-live-events-policy-to-users"></a>向用户分配实时事件策略 

如果你已创建自定义实时事件策略，请将其分配给用户，以使该策略生效。 

![显示 Microsoft Teams 徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft Teams 管理中心

1. 在左侧导航中，转到“**用户**”，然后选择用户。
2. 在“**已分配的策略**”旁，选择“**编辑**”。 
3. 选择要分配的实时事件策略，然后选择“**保存**”。 

你还可以将实时事件策略分配给一个或多个用户，如下所示：

![显示 Microsoft Teams 徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft Teams 管理中心

1. 转到“**会议**” > “**实时事件策略**”。
2. 单击策略名称的左侧以选择该策略。
3. 选择“管理用户”****。
4. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。
5. 完成添加用户后，选择“**保存**”。
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>允许用户安排使用外部应用或设备制作的事件

为了让用户安排使用外部应用或设备制作的事件，你还必须执行以下操作：

1. 为组织中的用户启用 Microsoft Stream。 Stream 可作为符合条件的 Office 365 订阅的一部分或作为独立服务提供。 Stream 未包含在商业协作版或商业高级版计划中。 有关详细信息，请参阅 [Stream 许可概述](https://docs.microsoft.com/stream/license-overview)。

      深入了解如何[将许可证分配给 Office 365 中的用户](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问 Stream。 请确保不会阻止用户使用 Stream，正如[此文](https://docs.microsoft.com/stream/disable-user-organization)中所述。

2. 确保用户在 Stream 中具有实时事件创建权限。 默认情况下，管理员可以使用外部应用或设备创建事件。 Stream 管理员可以在 Stream 中[允许其他用户创建实时事件](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)。  

3. 确保实时事件组织者已同意由 Stream 管理员设置的公司策略。如果 Stream 管理员已[设置公司准则策略](https://docs.microsoft.com/stream/company-policy-and-consent)，并要求员工在保存内容之前接受此策略，则用户在 Teams 中创建实时事件（使用外部应用或设备）之前必须这样做。 在组织中推出实时事件功能之前，请确保将要创建这些实时事件的用户已同意该策略。 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>第 4 步：在 Teams 中为实时事件设置视频分发解决方案
实时事件视频的播放使用自适应比特率流 (ABR)，但它是单播流，这意味着每个观看者都将从 Internet 上获取自己的视频流。 对于发送到组织内的大部分用户的实时事件或视频，观看者可能会消耗大量 Internet 带宽。 对于希望减少实时事件的 Internet 流量的组织，可将实时事件解决方案与 Microsoft 值得信赖的视频交付合作伙伴提供的软件定义的网络 (SDN) 或企业内容交付网络 (eCDN) 相集成。 这些 SDN/eCDN 平台使组织能够在不牺牲最终用户观看体验的情况下优化网络带宽。 我们的合作伙伴可帮助你在整个企业网络中实现更具可扩展性且高效的视频分发。

**在 Teams 之外购买和设置你的解决方案** 通过 Microsoft 值得信赖的视频交付合作伙伴，在扩展视频交付方面获得专家帮助。 在将视频交付提供程序与 Teams 一起使用之前，你必须购买并在 Teams 外部单独设置 SDN/eCDN 解决方案。

以下 SDN/eCDN 解决方案已预集成，可设置为与 Stream 一起使用。

- **Hive Streaming** 为直播和点播企业视频分发提供了简单而强大的解决方案。 Hive 是一种基于软件的解决方案，它不需要其他硬件或带宽，并且提供了一种安全的方式来允许数千个观看者同时观看视频，而不会影响你的网络。 对于希望在购买 SDN/eCDN 解决方案之前了解视频对其网络的影响的客户，Hive Streaming 还为 Microsoft 客户提供了基于浏览器的分析解决方案。 [了解详细信息](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。
 
- **Kollective** 是一种基于云的智能对等分发平台，它利用你现有的网络基础结构，以多种形式（实时流视频、点播视频、软件更新、安全修补程序等）更快、更可靠地交付内容，并且所需带宽更少。 我们的安全平台深受全球最大金融机构的信任，无需额外的硬件，安装和维护都非常简单。 [了解详细信息](https://kollective.com/microsoft-pilot/)。
 
- **Ramp OmniCache** 提供下一代网络分发，并确保跨全球 WAN 的视频内容无缝交付，从而帮助事件制作者优化网络带宽并支持成功的实时事件广播和点播流。 即将对在 Teams 中制作的实时事件提供 OmniCache 支持。 [了解详细信息](http://www.ramp.com)。 
 
> [!NOTE] 
> 你选择的 SDN 或 eCDN 解决方案受所选**第三方提供商的服务条款和隐私策略**的约束，这将制约你对提供商解决方案的使用。 你对提供商解决方案的使用将不受 Microsoft 批量许可条款或联机服务条款的约束。 如果你不同意**第三方提供商的条款**，则不要在 Teams 中启用该解决方案。 

设置 SDN 或 eCDN 解决方案后，即可在 Teams 中配置实时事件的提供商。 

## <a name="next-steps"></a>后续步骤
转到[配置 Teams 实时事件设置](configure-teams-live-events.md)。

### <a name="related-topics"></a>相关主题
- [什么是 Teams 实时事件？](what-are-teams-live-events.md)
- [规划 Teams 实时事件](plan-for-teams-live-events.md)
- [配置 Teams 实时事件设置](configure-teams-live-events.md)
