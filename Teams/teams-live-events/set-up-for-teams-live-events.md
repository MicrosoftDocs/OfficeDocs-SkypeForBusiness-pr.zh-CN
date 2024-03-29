---
title: 在 Microsoft Teams 中为实时事件进行设置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: 在 Teams 中设置实时事件，包括设置网络、分配许可证、启用实时事件功能和日程安排以及视频分发解决方案。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cf3d364ce01ea80892dc929102c96a7fab5a74bc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767583"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中为实时事件进行设置

为实时事件进行设置时，必须执行几个步骤。

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>第 1 步：在 Teams 中为实时事件设置网络

在 Teams 中制作的实时事件要求你[为 Teams 准备贵组织的网络](../prepare-network.md)。  

## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证

请确保为[可以创建和安排实时事件的用户](plan-for-teams-live-events.md#who-can-attend-create-and-schedule-live-events)以及[可以观看实时事件的用户](plan-for-teams-live-events.md#who-can-watch-live-events)分配正确的许可证。

## <a name="step-3-set-up-live-events-policies"></a>第 3 步：设置实时事件策略

实时事件策略用于控制组织中的哪些人员可以主持实时事件，以及其创建的事件中的可用功能。 可使用默认策略或创建一个或多个自定义实时事件策略。 创建自定义策略后，将其分配给组织中的一个或多个用户组。

> [!NOTE]
> 除非创建并分配自定义策略，否则组织中的用户将获得组织范围的全局 (默认) 策略。 默认情况下，在全局策略中，已为 Teams 用户启用实时事件安排，已关闭实时辅助字幕与字幕（转录），组织中的每个人都可以加入实时事件，并且录制设置已设置为“始终录制”。

### <a name="create-or-edit-a-live-events-policy"></a>创建或编辑实时事件策略

<a name="bkcreatepolicy"> </a>

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **“会议** > **实时事件策略** > **”“管理策略** ”选项卡。
2. 执行以下选项之一：

    - 如果要编辑现有默认策略，请选择“**全局(默认为组织范围)**”。
    - 如果要创建新的自定义策略，请选择“ **+添加**”。
    - 如果要编辑自定义策略，请选择该策略，然后选择“**编辑**”。

    可更改以下设置以满足组织的需求。

    ![实时事件策略设置的屏幕截图。](../media/teams-live-events-policies-new.png "Microsoft Teams 管理中心中的实时事件策略设置屏幕截图")

|设置  |说明  |
|---------|---------|
|**标题**     |这是显示在实时事件策略页面上的策略标题。 它不能超过 64 个字符或包含任何特殊字符。          |
|**说明**    |使用它为策略添加友好说明。         |
|**实时事件计划**     |启用此设置可让组织中的用户在 Teams 中创建和安排实时事件。     |
|**与会者听录** |此设置仅适用于在 Teams 中制作的事件。 启用此设置后，实时事件参与者可在事件期间查看实时辅助字幕与字幕。         |
|**可以加入已计划实时事件的用户**    |选择以下选项之一。<br><br>**任何人** 用户可以创建允许任何人（包括组织外部的人员）参与的实时事件。 当用户安排实时事件时，此设置将在 Teams 中启用 **公共** 权限类型。<br> **组织中的所有人** 用户可以创建允许组织内的人员（包括添加到组织的 [来宾用户](../add-guests.md)）参与的实时事件。 用户不能创建由匿名用户参与的实时事件。 当用户安排实时事件时，此设置将在 Teams 中启用 **组织范围** 权限类型。<br> **特定用户或组** 用户可以创建只允许组织内的特定用户或组参与的实时事件。 用户不能创建由组织内的任何人或匿名用户参与的实时事件。 当用户安排实时事件时，此设置将在 Teams 中启用 **人员和组** 权限类型。       |
|**录制设置**  <br>     | 此设置仅适用于在 Teams 中制作的事件。 选择以下选项之一。 <br><br> **始终录制** 始终录制由用户创建的实时事件。 事件结束后，事件团队成员可以下载录制内容，并且参加者可以观看该事件。 <br> **从不录制** 从不录制由用户创建的实时事件。 <br>**组织者可以录制或不录制** 用户可以决定是否录制实时事件。 如果已录制，则事件结束后，事件团队成员可以下载录制内容，并且参加者可以观看该事件。

也可以使用 Windows PowerShell 执行此操作，目前 GCC High 和 DoD 客户必须使用此方法。 有关详细信息，请参阅[使用 PowerShell 在 Teams 中设置实时事件策略](set-teams-live-events-policies-using-powershell.md)。

### <a name="assign-a-live-events-policy-to-users"></a>向用户分配实时事件策略

如果你已创建自定义实时事件策略，请将其分配给用户，以使该策略生效。 <br><br>[!INCLUDE [assign-policy](../includes/assign-policy.md)]

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>第 4 步：在 Teams 中为实时事件设置视频分发解决方案

实时事件视频的播放使用自适应比特率流 (ABR)，但它是单播流，这意味着每个观看者都将从 Internet 上获取自己的视频流。 对于发送到组织内的大部分用户的实时事件或视频，观看者可能会消耗大量 Internet 带宽。 对于想要减少实时活动的 Internet 流量的组织，Microsoft 提供了第一方解决方案 [Microsoft eCDN](/ecdn) (企业内容分发网络) 。 直播活动解决方案还与 Microsoft 受信任的视频交付合作伙伴集成，提供软件定义的网络 (SDN) 或 eCDN。 这些 SDN/eCDN 平台使组织能够在不牺牲最终用户查看体验的情况下优化网络带宽。 这些解决方案有助于在整个企业网络中实现更具可缩放性和更高效的视频分发。

- **Microsoft eCDN** Microsoft eCDN 已集成到 Teams 中，还与 Stream 和 Yammer 兼容。 它在企业网络中采用对等技术，从 WAN 连接卸载带宽。

- **在 Teams 之外购买和设置你的解决方案** 通过 Microsoft 值得信赖的视频交付合作伙伴，在扩展视频交付方面获得专家帮助。 

以下 SDN/eCDN 解决方案已预先集成，可以设置为与 Teams 流式处理配合使用：

- **Hive Streaming** 为直播和点播企业视频分发提供了简单而强大的解决方案。 Hive 是一种基于软件的解决方案，它不需要其他硬件或带宽，并且提供了一种安全的方式来允许数千个观看者同时观看视频，而不会影响你的网络。 对于希望在购买 SDN/eCDN 解决方案之前了解视频对其网络的影响的客户，Hive Streaming 还为 Microsoft 客户提供了基于浏览器的分析解决方案。 [了解详细信息](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。

- **Kollective** 是基于云的智能对等互连分发平台，它利用现有网络基础结构以多种形式交付内容， (实时流式处理视频、点播视频、软件更新、安全修补程序等) 更快、更可靠、带宽更少。 我们的安全平台深受全球最大金融机构的信任，无需额外的硬件，安装和维护都非常简单。 [了解详细信息](https://kollective.com/microsoft-pilot/)。

- **Ramp OmniCache** 提供下一代网络分发，并确保跨全球 WAN 的视频内容无缝交付，从而帮助事件制作者优化网络带宽并支持成功的实时事件广播和点播流。 即将对在 Teams 中制作的实时事件提供 OmniCache 支持。 [了解详细信息](https://rampecdn.com)。

- **Riverbed** 是网络优化方面的行业标准，它正在将其加速解决方案扩展到 Microsoft Teams。 现在，Microsoft 365 客户可以放心地加速 365 流量（包括 Teams）以及大量其他领先的企业 SaaS 服务，从而随时随地提高员工工作效率。 可以通过轻松的设置启用 Teams 加速，该设置附带对 Riverbed 的世界级支持和持续投资的所有保证。

> [!NOTE]
> 如果选择第三方 SDN 或 eCDN 解决方案，它将受所选 **第三方提供商的服务条款和隐私策略** 的约束，该条款将控制你对提供商解决方案的使用。 你对提供商解决方案的使用将不受 Microsoft 批量许可条款或联机服务条款的约束。 如果你不同意 **第三方提供商的条款**，则不要在 Teams 中启用该解决方案。

设置 SDN 或 eCDN 解决方案后，即可在 Teams 中配置实时事件的提供商。

## <a name="next-steps"></a>后续步骤

转到[配置 Teams 实时事件设置](configure-teams-live-events.md)。

### <a name="related-topics"></a>相关主题

- [什么是 Teams 实时活动?](what-are-teams-live-events.md)
- [规划 Teams 直播活动](plan-for-teams-live-events.md)
- [配置 Teams 实时事件设置](configure-teams-live-events.md)
