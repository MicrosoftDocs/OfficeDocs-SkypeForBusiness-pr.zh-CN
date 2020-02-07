---
title: 规划 Microsoft 团队聊天室
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 本文介绍了部署 Microsoft 团队聊天室的相关规划注意事项，以及下一代 Skype 会议室系统。
ms.openlocfilehash: 1d5236c522a0f3da6f2c2686e34db9d665a93d15
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825890"
---
# <a name="plan-microsoft-teams-rooms"></a>规划 Microsoft 团队聊天室

本文介绍了在整个会议和会议室策略中规划、提供和操作 Microsoft 团队会议室的端到端方法。

您将在下面的规划信息中介绍所需的建议做法和关键决策，以及指向支持技术信息的链接。 我们建议你查看 "计划"、"部署" 和 "管理" 部分，即使你已完全部署。

## <a name="overview-of-microsoft-teams-rooms"></a>Microsoft 团队聊天室概述

Microsoft 团队聊天室提供了一项完整的会议体验，可为所有规模的会议（从小型 huddle 区域到大型会议室）提供高清视频、音频和内容共享。

![在会议室墙上安装的控制台、麦克风和大型屏幕阐释了 Microsoft 团队会议室设置示例的元素。](../media/room-systems-image1.png "在会议室墙上安装的控制台、麦克风和大型屏幕阐释了 Microsoft 团队会议室设置示例的元素。")

[Microsoft 团队会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)是一个非常好的资源，可了解有关 Microsoft 团队聊天室的详细信息，以及如何将值添加为部署的一部分。 此外，我们还建议观看此[概述视频](https://youtu.be/tNey5KZVCl0)。 

## <a name="microsoft-teams-rooms-components"></a>Microsoft 团队聊天室组件

Microsoft 团队聊天室包含以下关键组件，可提供出色的用户体验：

- 触摸屏控制面板
- 计算
- Microsoft 团队聊天室应用程序
- 停靠/扩展器
- 外围设备（相机、麦克风、扬声器）
- 外部屏幕（最多两个）
- HDMI 输入

你可以将这些组件作为预装的供应商捆绑购买，也可以按照[本文中记录的要求](requirements.md)逐个购买受支持的组件。

除了 Surface Pro/dock 组合外，你还可以通过触摸屏控制面板、计算、停靠和关键外围设备（集成）购买 Microsoft 团队聊天室。 

通常情况下，捆绑和集成设备包括预安装软件，而如果您为 Surface Pro 系统单独购买支持的组件，则需要安装软件。 有关说明，请参阅[本文了解如何在设备上安装软件](rooms-scale.md)。 

你可以通过 Microsoft 团队、Skype for business Online 或 Skype for business 混合或内部部署部署 Microsoft 团队聊天室。  有关所需许可证的信息，请参阅[团队会议会议室授权更新](rooms-licensing.md)。

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>是否将在你的组织中部署 Microsoft 团队聊天室？ </li><li>如何购买 Microsoft 团队房间系统-捆绑、作为单独的组件或作为集成单元？</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤 | <ul><li>确定将在整个部署中执行关键活动的人员。</li><li>查看你拥有的会议室（并计划设置），了解你希望在何处部署 Microsoft 团队聊天室以及适合会议室大小的外围设备。</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>确定在整个部署过程中谁将承担关键活动

使用下面所示的方法指导你完成部署，并根据组织的需要自定义本文中提供的示例输出。

首先了解你拥有哪些会议室，构思未来最适合你的内容，然后通过选择和 procuring 所需的设备、管理你的网站、配置和部署你的服务、管理更改和用户采纳以及开发操作和维护过程。

![首先了解你拥有的内容和展望最适合你的内容，然后通过选择和 procuring 所需的设备、管理你的网站、配置和部署你的服务、管理更改和用户采纳以及开发操作和维护过程。](../media/room-systems-image2.png "首先了解你拥有的内容和展望最适合你的内容，然后通过选择和 procuring 所需的设备、管理你的网站、配置和部署你的服务、管理更改和用户采纳以及开发操作和维护过程。")

你可能需要跨多个团队协调这些活动。 我们提供了你应涵盖的主要活动的高级视图，还提供了有关团队（通常涉及到部署和管理会议室系统）的建议，可帮助你确定需要使用的人员。

| 任务                       | 可能执行任务的人员           | 分配对象 | 指向此内容的链接 |
|----------------------------|----------------------------------------|-------------|-----------------------|
| 库存会议室            | 设施/AV 团队/IT 项目团队 |             | [会议室库存和功能规划](#room-inventory-and-capability-planning)        |
| 计划功能          | IT 项目团队                        |             | [会议室库存和功能规划](#room-inventory-and-capability-planning)                       |
| 设备选择           | IT 项目团队/AV 团队              |             | [设备选择](#device-selection)                      |
| 无论                | IT 项目团队/AV 团队              |             | [无论](#procurement)                      |
| 网站准备情况             | 设施/AV 团队/IT 项目团队 |             | [网站准备情况](rooms-deploy.md#site-readiness)                      |
| 服务就绪          | IT 项目团队                        |             | [服务就绪](rooms-deploy.md#service-readiness)                      |
| 配置              | IT 项目团队                        |             | [配置和部署](rooms-deploy.md#configuration-and-deployment)                      |
| 部署                 | 设施/AV 团队/IT 项目团队 |             | [部署清单](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| 采用                   | 设施/AV 团队/IT 项目团队 |             | [采用](#plan-for-adoption-and-change-management)                      |
| 维护和操作 | AV 团队/IT 项目团队              |             | [管理概述](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>会议室库存和功能规划

第一步是清点组织的现有会议和会议室，以了解其环境、空间大小、布局和用途，并确定你希望未来范围内的每个房间的功能，例如，哪些功能更丰富将在聊天室中启用协作功能。 

在每个现有房间内创建设备和功能的库存后，您对设备选择计划的要求将置于您的设备选择计划中，以便创建富会议解决方案。 每个房间所需的形式（音频、视频），除了空间大小和用途之外，在确定哪种解决方案最适合每个房间时，所有功能都扮演着重要的角色。 

作为你的发现的一部分，它是考虑房间噪声和布局的关键。 例如，检查房间中的椅子是否不会阻止相机视图。 验证会议室没有过度的回声或嘈杂的空调，并且为屏幕和 Microsoft 团队机房提供充足的电力。 有许多因素可让你的音频视觉（AV）团队或合作伙伴能够提出建议。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>此部署的范围内有哪些聊天室？</li><li>部署范围内有哪些网站？</li><li>谁将承担会议室库存？</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>查看范围中的聊天室，并为其定义 Microsoft 团队会议室配置。</li></ul>|

_会议/会议室库存示例_

| 站点  | 聊天室名称 | 会议室类型 | 人数  | 在范围内？ | 当前房间功能       | 未来的会议室功能     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| 伦敦总部 | Curie         | 中        | 6&ndash;12                  | 是          | 话筒                        | 1屏幕，音频和视频以及演示文稿<br>PSTN 访问 |
| 悉尼总部 | 山          | 大         | 12&ndash;16                 | 是          | 旧式 AV 设备、1屏幕和照相机 | 2屏、音频和视频以及演示文稿<br>PSTN 访问 |

## <a name="device-selection"></a>设备选择 

根据你希望的会议室的未来功能，评估哪些 Microsoft 团队聊天室解决方案最适合于每个房间。 根据空间大小和布局，确定哪些 AV 外围设备最合适。 

有关系统和外围设备的类型、房间类型和大小的指南，请参阅[Microsoft 团队会议室需求](requirements.md)文章。 

根据您喜欢的供应商，使用 "要求" 文章中提供的信息来定义 Microsoft 团队聊天室和每个会议室类型支持的外围设备配置，并将其用作部署模板。 

**Pro 提示**-某些会议室类型可能不适用于你的部署。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>从你的库存中，你的部署在范围内的会议室有哪些类型？</li><li>将为每个房间类型部署哪些系统？</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始为所选系统收集关键的操作资料，并与您的采购团队进行沟通。</li></ul>|

_适用于你的组织的 Microsoft 团队聊天室部署模板示例_

| **房间类型/大小** | **人数**  | **Microsoft 团队会议室系统** | **外围设备**  | **显示（s）** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| 焦点 10 "按 9"      | 2&ndash;4                   |                                  |                         |                 |
| 小写 16 "x 16"     | 4&ndash;6                   |                                  |                         |                 |
| 中等深浅 18 "x 20"    | 6&ndash;12                  |                                  |                         |                 |
| 大 15 "x 32"     | 12&ndash;16                 |                                  |                         |                 |

**Pro 提示-** 现在是开始收集有关您所选的 Microsoft 团队聊天室解决方案的信息的好时机。

## <a name="procurement"></a>无论 

你可以通过设备合作伙伴购买所选系统作为捆绑包或集成解决方案。 你还可以通过使用 Surface Pro 设备和现有的_受支持_的 AV 外围设备来获取合作伙伴设备停靠和准备自己的 Microsoft 团队聊天室解决方案。 

你可以从 "[需求" 文章](requirements.md)中列出的许多合作伙伴那里获取 Microsoft 团队聊天室。 请访问合作伙伴的网站，了解有关这些解决方案和购买选项的详细信息。 

根据你的部署规模和方法，你可能决定将 Microsoft 团队聊天室和受支持的外围设备运送到一个中心位置，以便进行初始配置和作业。 这可能是在多个网站上进行分步推出的好方法。 或者，您可以选择将捆绑包直接发运到您的网站。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>是将组件直接发运到站点还是转移到暂存设备？</li><li>谁将管理临时设施（如果你决定使用其中一个）？</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>计划操作。</li><li>规划采纳和更改管理。</li></ul>|

## <a name="plan-for-operations"></a>计划操作 

你的组织必须定期执行监视、管理和管理任务，并且它是在你的部署早期接受这些任务的关键。 

许多组织拥有一个 AV 团队或管理其会议室和设备的合作伙伴。 此团队应参与同意负责管理 Microsoft 团队聊天室设备以监控性能、部署软件更新和修补程序的人员。 

考虑哪些 "帮助台" 队列你将向 Microsoft 团队 Rooms֪提供相关呼叫，并向帮助台团队提供常见问题，以便他们能够更好地了解如何使用 Microsoft 团队聊天室和他们可以执行的关键疑难解答步骤。 此常见问题的一个良好起点是[用户帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)和[已知问题列表](known-issues.md)。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定谁将管理 Microsoft 团队聊天室。</li><li>确定要向哪些帮助台队列传送 Microsoft 团队聊天室-相关呼叫。</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备主机帐户。 </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>规划采纳和更改管理

Microsoft 团队会议室系统向你的用户推出新功能。 请注意，这将是你的用户的更改，你应该确保你的市场活动能够确定新系统为你的用户带来的好处，并且谈话要点的销售人员可以使用它们与他们的团队进行讨论。 

请考虑安排在每个网站上显示的 "显示" 和 "通知" 事件和海报删除，以通知用户新功能。 您也可以创建房间内 "快速入门指南"。 请考虑在每个网站上查找可帮助他人提高速度和开始使用设备的会议。
