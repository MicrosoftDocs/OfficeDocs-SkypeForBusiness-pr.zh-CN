---
title: Shifts 连接线
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解 Shifts 连接器以及如何使用它们将 Shifts 连接到员工管理系统。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592887"
---
# <a name="shifts-connectors"></a>Shifts 连接线

## <a name="overview"></a>概述

使用 Shifts 连接器，可以将 Shifts（Microsoft Teams计划管理工具）与 WFM (系统) 集成。 设置连接后，一线员工可以从 Shifts 中无缝查看和管理 WFM 系统中日程安排。

将 WFM 系统Teams一线员工可以更有效地管理计划，简化日常流程，提高参与度和工作效率。 一线员工有一个地方可以安排、通信和协作，随时随地在任何设备上完成工作。

我们提供托管的开源 Shifts 连接器。 本文概述了 Shifts 连接器及其工作方式。

## <a name="how-shifts-connectors-work"></a>Shifts 连接器如何工作

连接器在 WFM 系统和 Shifts 之间同步计划数据，将组织的计划纳入Teams。 排班是一线员工参与其日程安排需求的地方。 WFM 系统是业务规则、合规性和智能的记录系统。

通过连接器的数据流这两种方式可确保计划始终为最新。 WFM 系统中计划将同步到 Shifts。 此外，Shifts 中对计划所做的更改会实时同步回 WFM 系统。 作为记录系统，所有业务规则在保存到 Shifts 之前由 WFM 系统强制实施。

## <a name="managed-shifts-connectors"></a>托管 Shifts 连接器

托管 Shifts 连接器是与合作伙伴协作开发的连接器。 托管连接器由我们或合作伙伴托管和管理。 使用托管连接器时，只需进行少量的设置。

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams Blue Yonder 的 Shifts 连接器
<a name="blue_yonder"> </a>

Blue Yonder Teams Shifts 连接器是由 Microsoft 托管和管理的第一方产品/服务。 借助此连接器，可以将 Shifts 与 Blue Yonder Workforce Management (Blue Yonder WFM) 版本 2020.3、2021.1 或 2021.2 集成，以管理计划并保持其最新。  

> [!NOTE]
> 如果具有 Blue Yonder WFM 版本 2020.3 或 2021.1，请应用 2020.3.0.4 或 2021.1.0.3 修补程序。 此修补程序修复了用户在 Shifts 中收到持久错误消息的问题。 它还修复了阻止用户在 Shifts 中更新其可用性的问题。

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="屏幕截图显示移动设备上的 Shifts 中的交换请求、在桌面上Teams请求审批，以及 Blue Yonder WFM 中的计划。" lightbox="../../media/shifts-connector-blue-yonder.png":::

一线管理员可以：

- 在 Blue Yonder WFM 中发布班次和计划，在 Shifts 中查看。
- 在 Blue Yonder WFM 中创建、管理和分配打开的班次，在 Shifts 中查看它们。
- 分配在 Shifts 中的 Blue Yonder WFM 中创建的未分配班次。
- 在 Blue Yonder WFM 中创建、编辑和删除请假，在 Shifts 中查看。
- 查看和批准 Blue Yonder WFM 和 Shifts 中工作人员的计划请求。
- 在 Blue Yonder WFM 中设置和更新辅助角色可用性，在 Shifts 中查看。

一线工作者可以：

- 在 Shifts 中查看其自己的团队班次和日程安排。
- 在 Shifts 中请求请假、调班和调班。
- 在 Shifts 中设置其可用性。

目前不支持以下操作：

- 在 Shifts 中添加、编辑、删除、保存或发布班次。
- 在 Shifts 中添加、编辑、删除、保存或发布假。
- 在 Shifts 中添加、编辑、删除、保存或发布打开的班次。

当一线经理或工作人员尝试在 Shifts 中执行上述任何操作时，他们将收到一条消息，告知他们不支持该操作。

#### <a name="example-scenario"></a>应用场景示例

经理 Eden 在 Blue Yonder WFM 中发布计划，通过连接器Teams Shifts。 Alex（一名职员）在移动设备上Teams通知，并查看他的日程安排和分配班次。

Alex 需要休息一段时间，然后使用 Shifts 请求休息一天。 请求通过连接器实时发送到 Blue Yonder WFM。 Blue Yonder WFM 确保请求符合业务规则并创建请求。 Eden 在 Blue Yonder WFM 中查看并批准请求，审批将同步到Teams。  (Eden 还可以在 Shifts) 中查看和批准) 。 Alex 收到通知Teams批准他的请求，并查看他更新的计划。

Alex 想要与同事调班。 在 Shifts 中，Alex 根据 Blue Yonder WFM 中的业务规则查看符合调班条件的所有班次的列表。 Alex 选择当前分配给 Gena 的班次。 Gena 在Teams接收通知并接受交换请求。 Eden 在 Shifts 中查看并批准请求，审批将同步到 Blue Yonder WFM。  (Eden 还可以在 Blue Yonder WFM) 中查看和批准) 。 Alex 和 Gena 在Teams通知，并查看其更新的计划。

#### <a name="set-up-a-connection"></a>设置连接

使用连接器将 Shifts 与 Blue Yonder WFM 集成只需几个步骤。 可以使用向导中的 Shifts 连接器Microsoft 365 管理中心快速设置连接。 向导将基于你选择的设置配置连接器并创建连接。 如果希望使用 PowerShell，我们还会提供可用于连接的 PowerShell 脚本。

有关分步指南，请参阅：

- [使用 Shifts 连接器向导将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [使用 PowerShell 将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)

设置连接后，可以使用 PowerShell 根据需要随时更新和更改连接设置。 对于连接器本身，无需担心升级或维护。 我们将处理好这一问题。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>适用于 Microsoft Teams 的 Reflexis Shifts 连接器

适用于 Microsoft Teams 的反身符 Shifts 连接器由 Microsoft Teams 托管。 借助此连接器，可以将 Shifts 与 Reflexis WFM 系统集成，以管理计划并使它们保持最新。

一线员工在 Teams 中的班次中有权访问其计划，其请求从 Shifts 同步到"反身员工计划程序" (RWS) 。 在 RWS 中创建的请求和班次的状态将同步到 Teams。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="屏幕截图显示移动设备上的排班列表，以及一个在"反身"中的日程安排。" lightbox="../../media/shifts-connector-reflexis.png":::

一线管理员可以：

- 在"反身"中发布班次和计划，在 Shifts 中查看它们。
- 在"反身"和"Shifts"中编辑班次。
- 在"反身"和"班次"中创建、管理和分配打开的班次。
- 在"反身"和"班次"中查看和批准来自工作人员的计划请求。

一线工作者可以：

- 在 Shifts 中查看其自己的团队班次和日程安排。
- 在 Shifts 中请求请假、调班和调班。

若要了解有关详细信息，请转到 https://connect.zebra.com/microsoft-connectors。

## <a name="open-source-shifts-connectors"></a>开源 Shifts 连接器

开源 Shifts 连接器是构建在 [Shifts Graph API 上的社区驱动的集成](/graph/api/resources/shift)。 以下开源连接器可用：

- Kronos-to-Teams WFC 本地
- 适用于 Blue Yonder (2017 到 2020.2) 的 JDA 到 Teams Shifts 连接器) 

每个连接器附带详细的部署和配置指南。 它们包括 Azure 资源管理器 (ARM) 部署脚本，用于将所有必要的服务托管在 Microsoft Azure。 源代码和部署脚本可在 GitHub[存储库中下载](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)。 可以按需求进行部署或自定义或扩展。

有关详细信息，请参阅 [生产就绪的 Shifts 连接器](/microsoftteams/platform/samples/shifts-wfm-connectors)。

## <a name="related-articles"></a>相关文章

- [管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
