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
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 本文介绍部署 Microsoft Teams 会议室（下一代 Skype 会议室系统）的相关规划注意事项。
ms.openlocfilehash: ccc24aea1a45d2aa75c3b1a5de668b520483c2bd
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662467"
---
# <a name="plan-microsoft-teams-rooms"></a>规划 Microsoft Teams 会议室

本文介绍一种端到端的方法来规划、交付和操作 Microsoft Teams 会议室，作为总体会议与会议室策略的一部分。

下面列出了规划信息，涵盖了建议的方法和需要做出的关键决策，并提供了支持技术信息的链接。 建议即使已完全部署，也查看"计划、部署和管理"部分。

## <a name="overview-of-microsoft-teams-rooms"></a>Microsoft Teams 会议室概述

Microsoft Teams 会议室提供完整的会议体验，将 HD 视频、音频和内容共享引入各种规模的会议，范围从小而多的区域到大型会议室。

![会议室墙壁上装载的主机、麦克风和大屏幕演示了 Microsoft Teams 会议室设置示例的元素。](../media/room-systems-image1.png "会议室墙壁上装载的主机、麦克风和大屏幕演示了 Microsoft Teams 会议室设置示例的元素。")

[Microsoft Teams 会议室是](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 一个很好的资源，可以了解有关 Microsoft Teams 会议室以及如何在部署中添加价值。 此外，我们建议观看此 [概述视频](https://youtu.be/tNey5KZVCl0)。 

## <a name="microsoft-teams-rooms-components"></a>Microsoft Teams 会议室组件

Microsoft Teams 会议室包含以下关键组件，可提供出色的用户体验：

- 触摸屏控制面板
- 计算
- Microsoft Teams 会议室应用程序
- Dock/扩展程序
- 外围设备 (、麦克风、扬声器) 
- 外部屏幕 (最多两) 
- HDMI 输入

你可以从许多供应商购买这些组件作为预安装捆绑包，也可以按照本文中介绍的要求单独购买 [支持的组件](requirements.md)。

除了 Surface Pro/Dock 组合外，还可以购买集成了触摸屏控制面板、计算、扩展坞和关键外围设备的 Microsoft Teams 会议室。 

通常，捆绑包和集成单元包括预安装的软件，而如果你单独购买 Surface Pro 系统支持的组件，则需要安装该软件。 有关说明， [请参阅有关在设备上安装软件的文章](rooms-scale.md)。 

可以使用 Microsoft Teams、Skype for Business Online 或 Skype for Business 混合部署或本地部署部署 Microsoft Teams 会议室。  有关所需 [许可证的信息，](rooms-licensing.md) 请参阅 Teams 会议室许可更新。

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>你将在组织中部署 Microsoft Teams 会议室吗？ </li><li>如何采购 Microsoft Teams 会议室系统（作为独立组件捆绑的或作为集成单元购买）？</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤 | <ul><li>确定谁将在整个部署中执行关键活动。</li><li>查看已 (并计划设置) ，以了解要在何处部署 Microsoft Teams 会议室以及适合会议室大小的外围设备。</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>确定谁将在整个部署中执行关键活动

使用下面所示的方法指导完成部署，并根据需要为组织自定义这些文章中提供的示例输出。

首先了解您拥有哪些会议室并构想将来最适合您的会议室，然后继续选择和采购所需的设备、准备网站、配置和部署服务、管理更改和用户采用，以及制定操作和维护过程。

![首先了解你拥有的内容并构想最适合你的设备，然后开始选择和采购所需的设备、准备站点、配置和部署服务、管理更改和用户采用，以及制定操作和维护过程。](../media/room-systems-image2.png "首先了解你拥有的内容并构想最适合你的设备，然后开始选择和采购所需的设备、准备站点、配置和部署服务、管理更改和用户采用，以及制定操作和维护过程。")

可能需要跨多个团队协调这些活动。 我们提供了应涵盖的主要活动的高级别视图，并为通常参与部署和管理会议室系统的团队提供建议，以帮助你决定需要与谁合作。

| 任务                       | 谁可能执行该任务           | 已分配到 | 指向此内容的链接 |
|----------------------------|----------------------------------------|-------------|-----------------------|
| 库存室            | 设施/AV 团队/IT 项目团队 |             | [房间库存和容量规划](#room-inventory-and-capability-planning)        |
| 计划功能          | IT 项目团队                        |             | [房间库存和容量规划](#room-inventory-and-capability-planning)                       |
| 设备选择           | IT 项目团队/AV 团队              |             | [设备选择](#device-selection)                      |
| 采购                | IT 项目团队/AV 团队              |             | [采购](#procurement)                      |
| 网站就绪性             | 设施/AV 团队/IT 项目团队 |             | [网站就绪性](rooms-deploy.md#site-readiness)                      |
| 服务就绪          | IT 项目团队                        |             | [服务就绪](rooms-deploy.md#service-readiness)                      |
| 配置              | IT 项目团队                        |             | [配置和部署](rooms-deploy.md#configuration-and-deployment)                      |
| 部署                 | 设施/AV 团队/IT 项目团队 |             | [部署清单](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| 采用                   | 设施/AV 团队/IT 项目团队 |             | [采用](#plan-for-adoption-and-change-management)                      |
| 维护和操作 | AV 团队/IT 项目团队              |             | [管理概述](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>房间库存和容量规划

第一步是盘点组织的现有会议室，以了解其环境、会议室大小、布局和用途，并确定您希望范围内每个会议室在将来拥有的功能，例如将在会议室中启用哪些更丰富的协作功能。 

在每个现有房间创建设备和功能的清单后，你需要将房间馈送到你的设备选择规划中，以创建丰富的会议解决方案。 每个 (所需的) 、音频、视频等形式（除了房间大小和用途）在决定最适合每个房间的解决方案方面都扮演了重要角色。 

作为发现的一部分，考虑房间音响效果和布局是关键。 例如，检查房间中的桌子是否不会阻止相机视图。 确认房间没有过多的回声或嘈杂的空调，并且是否有足够的电源供屏幕和 Microsoft Teams 会议室使用。 有许多因素需要考虑，你的音频- (AV) 团队或合作伙伴能够提供建议。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>哪些聊天室在此部署范围内？</li><li>哪些站点在部署范围内？</li><li>谁将负责会议室清单？</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>查看范围中的聊天室，并定义这些聊天室的 Microsoft Teams 会议室配置。</li></ul>|

_示例会议/会议室清单_

| 站点  | 聊天室名称 | 房间类型 | 人员数  | 在范围内？ | 当前房间功能       | 未来房间功能     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| 伦敦总部 | Curie         | 中        | 6 &ndash; 12                  | 是          | 免提电话                        | 1 个屏幕、音频和视频以及演示文稿<br>PSTN 访问 |
| 悉尼总部 | 山          | 大         | 12 &ndash; 16                 | 是          | 旧版 AV 单元，1 个屏幕和摄像头 | 2 个屏幕，音频和视频以及演示文稿<br>PSTN 访问 |

## <a name="device-selection"></a>设备选择 

根据聊天室的未来功能，评估最适合每个聊天室的 Microsoft Teams 会议室解决方案。 根据房间大小和布局，确定最适合的 AV 外围设备。 

有关按房间类型和大小表示的系统类型和外围设备类型的指南，请参阅 [Microsoft Teams 会议室要求](requirements.md) 一文。 

根据你喜欢的供应商，使用要求文章中提供的信息为每个聊天室类型定义 Microsoft Teams 会议室和支持的外围设备配置，并使用此模板进行部署。 

**专业提示** - 某些聊天室类型可能不适用于部署。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>从清单中，哪些类型的会议室在部署范围内？</li><li>将针对每种聊天室类型部署哪些系统？</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始收集所选系统的关键操作材料，并吸引采购团队参与。</li></ul>|

_适用于组织的 Microsoft Teams 会议室部署模板示例_

| **房间类型/大小** | **人员数**  | **Microsoft Teams 会议室系统** | **外围设备**  | **显示 ()** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| 焦点为 10' by 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| 小 16' by 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| 中等 18' by 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| 大 15' by 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**专业提示 -** 现在，可以开始收集有关所选 Microsoft Teams 会议室解决方案的信息。

## <a name="procurement"></a>采购 

可以通过设备合作伙伴购买所选系统作为捆绑包或集成解决方案。 还可使用 Surface Pro 设备和现有的受支持的 _AV_ 外围设备获取合作伙伴设备扩展坞并准备自己的 Microsoft Teams 会议室解决方案。 

可以从要求一文中列出的许多合作伙伴获取 Microsoft Teams [会议室](requirements.md)。 请访问合作伙伴的网站，了解有关这些解决方案和采购选项的详细信息。 

根据部署规模和方式，可能决定将 Microsoft Teams 会议室和支持的外围设备运送到中心位置进行初始配置和分配。 对于跨多个站点进行分步推出，这可能是一个不错的方法。 或者，您可以选择将捆绑包直接发运到网站。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>是否直接将组件运送到站点或过渡设施？</li><li>如果你决定使用一个 (，由谁管理暂存) ？</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>规划操作。</li><li>规划采用和变更管理。</li></ul>|

## <a name="plan-for-operations"></a>计划操作 

组织必须持续执行监视、管理和管理任务，并且必须同意谁在部署早期执行这些任务。 

许多组织都有一个 AV 团队或合作伙伴，负责管理其会议室和设备。 此团队应参与同意谁将管理 Microsoft Teams 会议室设备，以监视性能以及部署软件更新和修补程序。 

请考虑将 Microsoft Teams Rooms֪ 相关呼叫路由到哪个支持人员队列，并为支持人员团队提供常见问题解答，以便他们更好地了解如何使用 Microsoft Teams 会议室以及可采取的主要故障排除步骤。 此常见问题解答的一个好起点[是用户帮助和](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)[已知问题](known-issues.md)。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定谁将管理 Microsoft Teams 会议室。</li><li>确定将 Microsoft Teams 会议室相关呼叫路由到哪个支持人员队列。</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备托管帐户。 </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>规划采用和变更管理

Microsoft Teams 会议室系统为用户引入了新功能。 必须认识到，这会为用户带来改变，并且应确保营销活动确定新系统将为用户带来的好处，以及潜在顾客可用于与团队讨论的关键讨论点。 

考虑在每个网站上安排展示和告知事件和海报删除，以通知用户新功能。 还可以在房间内创建"快速入门指南"。 考虑在每个网站上查找会议得主，以帮助其他人快速开始使用设备。
