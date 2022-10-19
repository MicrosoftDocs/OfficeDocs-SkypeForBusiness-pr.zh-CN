---
title: Microsoft Teams 会议室规划
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Teams_ITAdmin_Rooms
- highpri
description: 本文介绍部署下一代 Skype 会议室系统Microsoft Teams 会议室的相关规划注意事项。
ms.openlocfilehash: 0e6e3d53928a1a28572a8ea0a038ea772c934e7b
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584443"
---
# <a name="plan-microsoft-teams-rooms"></a>规划Microsoft Teams 会议室

本文介绍一种端到端方法，用于规划、交付和操作Microsoft Teams 会议室作为整个会议室策略的一部分。

你将找到下面的规划信息，这些信息涵盖了建议的方法和需要做出的关键决策，并提供了支持技术信息的链接。 建议查看“计划”、“部署和管理”部分，即使已完全部署。

## <a name="overview-of-microsoft-teams-rooms"></a>Microsoft Teams 会议室概述

Microsoft Teams 会议室提供完整的会议体验，可将高清视频、音频和内容共享引入各种规模的会议，从小型拥挤区域到大型会议室。

![用户点击Teams 会议室控制台，并在后台显示。](../media/room-systems-image1.jpg "用户点击Teams 会议室控制台，后台显示")

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)是一个很好的资源，可详细了解Microsoft Teams 会议室以及如何在部署过程中增加价值。

## <a name="microsoft-teams-rooms-components"></a>Microsoft Teams 会议室组件

Microsoft Teams 会议室包含以下关键组件，可提供出色的用户体验：

- 触摸屏控制台
- 计算模块
- Microsoft Teams 会议室应用程序
- 相机、麦克风、扬声器)  (外围设备
- 外部屏幕最多 (两个) 
- HDMI 输入

可以从许多供应商处采购这些组件作为预安装捆绑包，也可以按照 [本文中所述的要求](requirements.md)单独购买受支持的组件。

## <a name="teams-rooms-licensing"></a>Teams 会议室许可

每个会议室设备（如Teams 会议室控制台、Surface Hub 和 Teams 面板）都需要Teams 会议室许可证。 Teams 为Teams 会议室提供两个许可证：Microsoft Teams 会议室专业版和基本Microsoft Teams 会议室。

Microsoft Teams 会议室专业版非常适合具有 25 个或更多会议室设备的组织，或者想要最全面的会议和设备管理体验的组织。 混合 Teams 会议更身临其境，具有 Front 行、内容相机、AI 支持的干扰抑制等功能，以及Microsoft Teams 会议室专业版可用的其他功能。 Teams 会议室管理员可以从 Teams 管理中心集中管理所有经过认证的Teams 会议室设备，从配置条件访问策略到分析有关设备运行状况和会议质量的丰富遥测数据。

Microsoft Teams 会议室基本版适用于仅具有少数会议室设备且仅需要基本会议和管理功能的组织。 Microsoft Teams 会议室基本版允许你加入会议、共享内容和实时视频、使用 Direct Guest Join 加入 Zoom 和 Webex 会议，并在 Teams 管理中心执行基本设备清单和监视。

在使用会议室设备之前，需要为其分配许可证。 有关详细信息，请参阅[Microsoft Teams 会议室许可证](rooms-licensing.md)。

[!INCLUDE [mtr-user-licensing](../includes/mtr-user-licensing.md)]

| &nbsp;   |  &nbsp;   |
|-----------|------------|
|![决定部署。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>是否会在组织中部署Microsoft Teams 会议室？ </li><li>如何采购Microsoft Teams 会议室系统？</li></ul> |
| ![标识活动。](../media/audio_conferencing_image9.png)<br/>后续步骤 | <ul><li>确定谁将在整个部署中执行关键活动。</li><li>查看已 (的会议室，并计划设置) ，了解要在何处部署Microsoft Teams 会议室以及适合会议室大小的外围设备。</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>确定谁将在整个部署中执行关键活动

使用下面所示的方法指导你完成部署，并根据需要自定义为组织提供的示例输出。

首先了解你拥有哪些会议室，并设想将来最适合你的会议室，然后通过选择和采购所需的设备、准备站点、配置和部署服务、管理更改和用户采用以及开发运营和维护过程来着手。

![首先了解你所拥有的内容并设想最适合你的内容，然后逐步选择和采购所需的设备、准备站点、配置和部署服务、管理更改和用户采用，以及开发操作和维护过程。](../media/room-systems-image2.png "首先了解你所拥有的内容并设想最适合你的内容，然后逐步选择和采购所需的设备、准备站点、配置和部署服务、管理更改和用户采用，以及开发操作和维护过程。")

可能需要跨多个团队协调这些活动。 我们提供应涵盖的主要活动的高级视图，并为通常参与部署和管理会议室系统的团队提供建议，以帮助你决定需要与谁合作。

| 任务                       | 谁可以执行该任务           | 分配到 | 指向此内容的链接 |
|----------------------------|----------------------------------------|-------------|-----------------------|
| 清单会议室            | 设施/AV 团队/IT 项目团队 |             | [会议室清单和功能规划](#room-inventory-and-capability-planning) |
| 规划功能          | IT 项目团队                        |             | [会议室清单和功能规划](#room-inventory-and-capability-planning) |
| 设备选择           | IT 项目团队/AV 团队              |             | [设备选择](#device-selection) |
| 采购                | IT 项目团队/AV 团队              |             | [采购](#procurement) |
| 网站就绪             | 设施/AV 团队/IT 项目团队 |             | [网站就绪](rooms-deploy.md#site-readiness) |
| 服务就绪          | IT 项目团队                        |             | [服务就绪](rooms-deploy.md#service-readiness) |
| 配置              | IT 项目团队                        |             | [配置和部署](rooms-deploy.md#configuration-and-deployment) |
| 部署                 | 设施/AV 团队/IT 项目团队 |             | [部署清单](console.md#microsoft-teams-rooms-deployment-checklist) |
| 采用                   | 设施/AV 团队/IT 项目团队 |             | [采用](#plan-for-adoption-and-change-management) |
| 维护和操作 | AV 团队/IT 项目团队              |             | [管理概述](rooms-manage.md) |

## <a name="room-inventory-and-capability-planning"></a>会议室清单和功能规划

第一步是清点组织现有的会议空间和会议室，以了解其环境、会议室大小、布局和用途。 然后，可以确定希望每个房间具有的功能，如智能相机、白板、内容相机等。

在每个现有会议室中创建设备和功能清单后，你对该会议室源的要求将纳入设备选择计划，以创建丰富的会议解决方案。 除了房间大小和用途外，每个房间所需的音频、视频)  (方式在决定哪个解决方案最适合每个房间方面都起着重要作用。

作为发现的一部分，考虑房间音响效果和布局是关键。 例如，检查会议室中的椅子不会阻止相机视图。 验证房间没有过多的回显或嘈杂的空调，并且它确实有足够的电源用于屏幕和Microsoft Teams 会议室。 有许多因素需要考虑，你的视听 (AV) 团队或合作伙伴将能够提供建议。

| &nbsp;   | &nbsp;    |
|-----------|------------|
| ![deplyment 会议室。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>查看范围内的会议室，并为其定义Microsoft Teams 会议室配置。</li></ul>|

_示例会议室/会议室清单_

| 站点      | 会议室名称 | 会议室类型 | 人数 | 在范围中？ | 当前房间功能           | 未来会议室容量 |
|-----------|-----------|-----------|------------------|-----------|-------------------------------------|--------------------------|
| 伦敦总部 | Curie     | 中型    | 6&ndash;12       | 是       | 扬声器                        | 1 个屏幕、音频和视频以及演示文稿<br>PSTN 访问 |
| 悉尼总部 | Hill      | 大型     | 12&ndash;16      | 是       | 旧版 AV 单元、1 个屏幕和相机 | 2 个屏幕、音频和视频以及演示文稿<br>PSTN 访问 |

## <a name="device-selection"></a>设备选择

根据所需空间的未来功能，评估哪个Microsoft Teams 会议室解决方案最适合每个会议室。 根据房间大小和布局确定最适合的 AV 外围设备。

有关系统和外围设备类型（按房间类型和大小）的指导，请参阅[Microsoft Teams 会议室要求](requirements.md)文章。

根据你喜欢的供应商，使用要求文章中提供的信息来定义每个房间类型的Microsoft Teams 会议室和支持的外围设备配置，并将其用作部署的模板。

**专业提示** - 某些房间类型可能不适用于你的部署。

| &nbsp; | &nbsp; |
|---|---|
| ![范围中的会议室。](../media/audio_conferencing_image7.png) <br/>决策点 | <ul><li>从清单中，哪些类型的会议室在部署范围内？</li><li>将为每个房间类型部署哪些系统？</li></ul> |
| ![收集材料。](../media/audio_conferencing_image9.png)<br/>后续步骤 | <ul><li>开始收集所选系统的关键操作材料，并与采购团队联系。</li></ul> |

_组织Microsoft Teams 会议室部署模板示例_

| 会议室类型/大小     | 人数 | Microsoft Teams 会议室系统 | 外围设备 | 显示 (的)       |
|--------------------|------------------|------------------------------|--------------------|-----------------|
| 焦点 10' by 9'    | 2&ndash;4        |                              |                    |                 |
| 小 16' 由 16'   | 4&ndash;6        |                              |                    |                 |
| 中等 18' 到 20'  | 6&ndash;12       |                              |                    |                 |
| 大 15' 由 32'   | 12&ndash;16      |                              |                    |                 |

**专业提示 -** 现在是开始收集有关所选Microsoft Teams 会议室解决方案的信息的好时机。

## <a name="procurement"></a>采购

可以通过设备合作伙伴以捆绑包或集成解决方案方式采购所选系统。

可以从要求[文章](requirements.md)中列出的多个合作伙伴获取Microsoft Teams 会议室。 请访问合作伙伴的网站，详细了解这些解决方案和采购选项。

根据部署规模和方法，你可能决定将Microsoft Teams 会议室和支持的外围设备运到中心位置进行初始配置和分配。 对于跨多个站点分阶段推出而言，这可能是一种不错的方法。 或者，可以选择将捆绑包直接寄送到站点。

| &nbsp; | &nbsp; |
|---|---|
| ![寄送组件。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>是将组件直接寄送到站点还是临时设施？</li><li>如果你决定使用一个) ，谁将管理过渡设施 (？</li></ul> |
| ![计划操作。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>规划操作。</li><li>规划采用和更改管理。</li></ul> |

## <a name="plan-for-operations"></a>规划操作

你的组织必须持续执行监视、管理和管理任务，并且必须同意谁将在部署早期执行这些任务。

许多组织都有一个 AV 团队或合作伙伴来管理其会议室和设备。 或者，可以通过利用Microsoft Teams 会议室专业版让 Microsoft 帮助管理Teams 会议室。 确定谁将管理Microsoft Teams 会议室设备，以监视性能以及部署软件更新和修补程序。

考虑要将Microsoft Teams 会议室相关调用路由到的帮助台队列，并向支持人员团队提供常见问题解答，以便他们更好地了解如何使用Microsoft Teams 会议室以及可以采取的关键故障排除步骤。 此常见问题解答的一个好起点是 [用户帮助](https://support.microsoft.com/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 和 [已知问题](known-issues.md)。

| &nbsp; | &nbsp; |
|---|---|
| ![选择管理器。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定谁将管理Microsoft Teams 会议室。</li><li>确定要将Microsoft Teams 会议室相关调用路由到的帮助台队列。</li></ul> |
| ![准备主机帐户。](../media/audio_conferencing_image9.png)<br/>后续步骤 |<ul><li>准备托管帐户。</li></ul> |

## <a name="plan-for-adoption-and-change-management"></a>规划采用和更改管理

Microsoft Teams 会议室系统为用户引入了新功能。 请务必认识到，这将会对用户造成更改，并且应确保内部营销活动确定新系统将为用户带来的好处，以及潜在客户可用于与其团队讨论的关键谈话要点。

请考虑在每个站点上安排显示和讲述事件和海报投递，以通知用户新功能。 还可以创建室内“快速入门指南”。 请考虑在每个站点找到一个会议冠军，帮助其他人提高速度并开始使用设备。
