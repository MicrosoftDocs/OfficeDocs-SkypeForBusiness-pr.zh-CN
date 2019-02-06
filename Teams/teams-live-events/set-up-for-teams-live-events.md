---
title: 在 Microsoft Teams 中为实时事件进行设置
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: 了解 live 团队，包括网络准备、 分配许可证、 使用策略来启用 live 事件功能和计划的用户，以及设置分发第三方提供程序中的事件的设置的步骤。
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 078374652325d177e30db1d320f22e5d814ac548
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754781"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中为实时事件进行设置

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

时您 live 事件的设置，有以下几个您必须采取的步骤：

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>步骤 1： 设置您的网络中的 Microsoft 团队的实时事件
快速入门 live 事件要求您[准备贵组织的网络中的 Microsoft 团队](https://docs.microsoft.com/microsoftteams/prepare-network)。  

## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
确保您具有正确的许可证分配[谁可以创建和安排 live 事件](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events)和[谁可以观看 live 事件](plan-for-teams-live-events.md#who-can-watch-live-events)。

## <a name="step-3-set-up-live-events-policies"></a>步骤 3： 为实时事件策略设置
实时的事件使用策略来控制您的组织中的谁可以保留 live 事件和他们创建的事件中可用的功能。 您可以使用默认策略或创建一个或多自定义 live 事件策略。 创建自定义策略后，请将其分配给用户或您的组织中的用户组。

> [!NOTE]
> 您的组织中的用户将获得全局策略，除非您创建和分配自定义策略。 默认情况下，在全局策略中，为团队用户启用了 live 事件调度、 转录处于关闭、 组织中的所有人都可以加入 live 事件和录制设置设为始终记录。 

### <a name="create-or-edit-a-live-events-policy"></a>创建或编辑 live 事件策略

**![团队-徽标-30x30.png](../media/teams-logo-30x30.png)使用的 Microsoft 团队管理中心**

1. 在左侧导航窗格中，转到**会议** > **Live 事件策略**。 
2. 请执行下列操作之一：
- 如果您想要编辑现有的默认策略，则选择**全局 （组织范围内默认值）**。 
- 如果您希望创建新的自定义策略，请选择**新建策略**。 
- 如果您想要编辑的自定义策略，选择策略，，然后选择**编辑**。 

    以下是您可以更改以适合您组织的需要的设置。

    ![屏幕截图 live 事件策略设置](../media/teams-live-events-policies.png "屏幕截图 live 事件的 Microsoft 团队管理中心中的策略设置") 

|设置  |说明  |
|---------|---------|
|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。     |这是策略的显示在 live 事件策略页的名称。 它不能超过 64 个字符或具有任何特殊字符。          |
|**说明**    |用于添加策略的友好说明。         |
|**允许计划**     |打开这允许用户在组织中创建和安排团队中的实时事件。 务必要了解您希望用户能够安排外部编码器 live 事件，是否有，您必须执行其他步骤。 若要了解详细信息，请参阅[使用户能够安排外部编码器事件](#enable-users-to-schedule-external-encoder-events)。     |
|**允许转录的与会者**（即将推出） |此设置可以仅应用于快速入门事件。 打开启用 live 事件与会者查看实时标题和事件期间的转换。         |
|**谁可以加入计划的 live 事件**    |选择下列选项之一。<br> <br> **所有人**用户可以创建任何人，包括组织外部的人员可以参加的实时事件。 <br> **组织中所有人**用户可以创建仅在组织中的人员可以参加的实时事件。 用户无法创建由匿名用户参加的实时事件。 <br> **特定用户或组**用户可以创建 live 事件，仅限特定用户或可参加在您的组织中的组。 用户无法创建通过您的组织中的每个人或匿名用户参加的实时事件。        |
|**录制设置**  <br>     | 此设置可以仅应用于快速入门事件。 选择下列选项之一。 <br><br> **始终记录**始终记录由用户创建的实时事件。 该事件是通过后，事件工作组成员可以下载录制，与会者可以观看事件。 <br> **从不记录**从不记录由用户创建的实时事件。 <br>**组织者可以记录或不**用户可以决定是否记录 live 事件。 如果它记录的事件是通过后，事件工作组成员可以下载录制并与会者可以观看事件。      

您也可以使用 Windows PowerShell 执行此操作。 有关详细信息，请参阅[使用 PowerShell，可以设置团队中的实时事件策略](set-teams-live-events-policies-using-powershell.md)。 

### <a name="assign-a-live-events-policy-to-users"></a>将实时事件策略分配给用户 

如果您创建的自定义的实时事件策略，则将其分配给用户的策略处于活动状态。 

![团队-徽标-30x30.png](../media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 在左侧导航窗格中，转到**用户**，，然后选择用户。
2. 旁边**分配策略**，选择**编辑**。 
3. 选择要分配的实时事件策略，然后选择**保存**。 

### <a name="enable-users-to-schedule-external-encoder-events"></a>使用户能够安排外部编码器事件

用户安排外部编码器事件，则任务组还必须执行以下任务：

1. 为在组织中的用户启用 Microsoft 流。 Microsoft 流是可用的合格的 Office 365 订阅一部分或作为独立的服务。 Microsoft 流未包含在业务 Essentials 或企业高级版计划。 有关详细信息，请参阅[流许可概述](https://docs.microsoft.com/stream/license-overview)。

      了解有关如何可以[分配给 Office 365 中的用户的许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问 Microsoft 流。 确保 Microsoft 流不阻止用户，如[本文](https://docs.microsoft.com/stream/disable-user-organization)中所定义。

2. 确保用户具有 Microsoft 流中的实时事件创建权限。 默认情况下，管理员可以创建外部编码器 live 事件。 Microsoft 流管理员可以流中[启用 live 事件创建的其他用户](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)。  

3. 确保组织者同意流管理员设置的公司策略的实时事件如果 Microsoft 流管理员[设置的公司准则策略](https://docs.microsoft.com/stream/company-policy-and-consent)并要求员工保存内容之前接受此策略，然后用户必须这样做团队在创建 （具有外部编码器生产） 的实时事件之前。 推出组织中的实时事件功能之前，请确保将创建这些 live 事件的用户同意策略。 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>步骤 4： 设置的团队中的实时事件的视频分布解决方案
Live 事件视频播放使用流式处理 (ABR) 的自适应比特率，但它并单播流，这意味着每个查看器从 internet 获取其自己的视频流。 对于 live 事件或发送到您的组织的大部分内容的视频，可能有大量的 internet 带宽使用查看器。 对于希望减少 live 事件此 internet 通信的组织，与 Microsoft 的集成解决方案的实时事件受信任提供软件的视频传送合作伙伴定义网络 (SDNs) 或企业内容交付网络 (eCDNs)。 这些 SDN/eCDN 平台启用组织牺牲最终用户查看体验的情况下优化网络带宽。 我们的合作伙伴可帮助您在企业网络中启用多可扩展且高效的视频分布。

**购买和设置您的解决方案团队之外**获取与通过利用 Microsoft 的受信任的视频传送合作伙伴缩放视频传递专家的帮助。 启用与团队一起使用的视频传输提供程序之前必须购买和外部和分开团队设置 SDN/eCDN 解决方案。

以下 SDN/eCDN 解决方案前集成，可以设置与 Microsoft 流一起使用。

- **配置单元流式处理**提供 live 和点播企业视频分布的简单且强大的解决方案。 配置单元是一种基于软件的解决方案，不需要额外的硬件或带宽，并提供了一种启用数千个并发视频查看器，而不会影响您的网络安全方法。 对于希望了解影响视频具有其购买 SDN/eCDN 解决方案之前的网络上的客户，配置单元流还提供基于浏览器的分析解决方案的 Microsoft 客户。 [了解更多](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。
 
- **Kollective**是一个基于云的、 智能对等分发平台，利用您现有的网络基础结构来提供多个窗体中的内容，、 (live 视频流，按需视频、 软件更新、 安全修补程序，等等) 更快、 更多可靠地及较少的带宽。 我们安全平台是受信任的世界最大金融机构及任何其他硬件、 设置和维护很容易。 [了解更多](http://www.kollective.com)。
 
- **提升 OmniCache**提供下一代网络通讯组和跨全局 Wan 确保视频内容的无缝传递，帮助事件生产者优化网络带宽和支持成功 live 事件广播和按需流式处理。 快速入门 live 事件提升 OmniCache 支持即将提供。  [了解更多](http://www.ramp.com)。 
 
> [!NOTE] 
> 您选择的 SDN 或 eCDN 解决方案受制于所选**的服务和隐私策略的第三方提供程序的条款**，哪些将控制提供程序的解决方案的使用。 您使用提供程序的解决方案不会受到的 Microsoft 批量许可条款或联机服务条款。 如果您不同意**第三方提供程序的术语**，然后不启用团队中的解决方案。 

设置 SDN 或 eCDN 解决方案后，您已准备好在团队中配置的实时事件提供程序。 

## <a name="next-steps"></a>后续步骤
转到[配置 live 团队中的事件设置](configure-teams-live-events.md)。

### <a name="related-topics"></a>相关主题
- [什么是团队 live 事件？](what-are-teams-live-events.md)
- [规划团队 live 事件](plan-for-teams-live-events.md)
- [在工作组中配置 live 事件设置](configure-teams-live-events.md)

