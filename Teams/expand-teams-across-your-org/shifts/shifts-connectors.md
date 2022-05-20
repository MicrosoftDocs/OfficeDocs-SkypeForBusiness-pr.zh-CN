---
title: Shifts 连接器
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
ms.openlocfilehash: a4759bc010367e6531a557e2a5ff951d1b613505
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2022
ms.locfileid: "65598355"
---
# <a name="shifts-connectors"></a>Shifts 连接器

## <a name="overview"></a>概述

使用班次连接器，可以将 Shifts（Microsoft Teams中的日程安排管理工具）与员工管理 (WFM) 系统集成。 设置连接后，一线工作人员可以从 Shifts 中无缝查看和管理 WFM 系统中的日程安排。

将 WFM 系统连接到Teams使一线员工能够更有效地管理计划，并简化日常流程，提高参与度和工作效率。 你的一线工作人员有一个位置来安排、沟通和协作，需要从任何位置、任何设备完成工作。

本文概述了 Shifts 连接器及其工作原理。

## <a name="how-shifts-connectors-work"></a>Shifts 连接器的工作原理

连接器在 WFM 系统和 Shifts 之间同步计划数据，使组织的日程安排Teams。 轮班是一线工作人员根据日程安排需求进行工作的地方。 WFM 系统是业务规则、合规性和智能记录系统。

通过连接器进行数据流，这两种方法都可确保计划始终是最新的。 WFM 系统中的计划将同步到 Shifts。 并且，对 Shifts 中的计划所做的更改将实时同步回 WFM 系统。 作为记录系统，在将数据保存到 Shifts 之前，WFM 系统会强制实施所有业务规则。

## <a name="managed-shifts-connectors"></a>托管班次连接器

托管班次连接器是与合作伙伴协作开发的连接器。 托管连接器由我们或我们的合作伙伴托管和管理。 使用托管连接器时，只需要最少的设置。

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams用于 Blue Yonder 的 Shifts 连接器
<a name="blue_yonder"> </a>

Blue Yonder 的 Teams Shifts 连接器是由 Microsoft 托管和管理的第一方产品/服务。 使用此连接器，可以将 Shifts 与 Blue Yonder Workforce Management (Blue Yonder WFM) 版本 2020.3、2021.1 或 2021.2 集成，以管理计划并使其保持最新状态。  

> [!NOTE]
> 如果有 Blue Yonder WFM 版本 2020.3 或 2021.1，请应用 2020.3.0.4 或 2021.1.0.3 修补程序。 此修补程序修复了用户在 Shifts 中收到持久性错误消息的问题。 它还修复了阻止用户在 Shifts 中更新其可用性的问题。

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="屏幕截图显示了移动设备上的 Shifts 中的交换请求、在桌面上Teams请求审批，以及 Blue Yonder WFM 中的日程安排。" lightbox="../../media/shifts-connector-blue-yonder.png":::

一线经理可以：

- 在 Blue Yonder WFM 中发布班次和计划，并在 Shifts 中查看它们。
- 在 Blue Yonder WFM 中创建、管理和分配打开的班次，并在 Shifts 中查看它们。
- 分配在 Shifts 的 Blue Yonder WFM 中创建的开放式班次。
- 在 Blue Yonder WFM 中创建、编辑和删除休假，并在 Shifts 中查看。
- 查看和批准来自 Blue Yonder WFM 和 Shifts 中工作人员的计划请求。
- 在 Blue Yonder WFM 中设置和更新辅助角色可用性，并在 Shifts 中查看。

一线工作人员可以：

- 在班次中查看他们自己和团队的班次和日程安排。
- 在 Shifts 中请求休假、打开班次和交换班次。
- 在 Shifts 中设置其可用性。

目前不支持以下操作：

- 在 Shifts 中添加、编辑、删除、保存或发布班次。
- 在 Shifts 中添加、编辑、删除、保存或发布休假。
- 在 Shifts 中添加、编辑、删除、保存或发布打开的班次。

当一线经理或辅助角色尝试在 Shifts 中执行这些操作时，他们将收到一条消息，告知他们该操作不受支持。

#### <a name="example-scenario"></a>应用场景示例

经理伊甸园在 Blue Yonder WFM 中发布计划，该计划通过连接器在Teams中同步到 Shifts。 Alex 是一名工作人员，他在移动设备上收到Teams通知，并查看他的日程安排和分配的班次。

Alex 需要请一些假，并使用 Shifts 请求休息一天。 请求通过连接器实时发送到 Blue Yonder WFM。 Blue Yonder WFM 可确保请求符合业务规则并创建请求。 伊甸园在 Blue Yonder WFM 中查看和批准请求，审批同步到Teams。  (伊甸园还可以在 Shifts) 中查看和批准请求。 Alex 在Teams收到通知，他的请求已获得批准，并查看他更新的计划。

亚历克斯想和同事交换班次。 在 Shifts 中，Alex 会看到根据 Blue Yonder WFM 中的业务规则有资格进行交换的所有班次的列表。 Alex 选择当前分配给 Gena 的班次。 Gena 在其移动设备上收到Teams通知，并接受交换请求。 伊甸园在 Shifts 中查看并批准请求，审批将同步到 Blue Yonder WFM。  (伊甸园还可以在 Blue Yonder WFM) 中查看和批准请求。 Alex 和 Gena 在 Teams 中收到通知，并查看其更新的计划。

#### <a name="set-up-a-connection"></a>设置连接

使用连接器将 Shifts 与 Blue Yonder WFM 集成只需几个步骤。 可以使用Microsoft 365 管理中心中的 Shifts 连接器向导快速设置连接。 向导根据选择和创建连接的设置配置连接器。 如果想要使用 PowerShell，我们还提供可用于连接的 PowerShell 脚本。

有关分步指南，请参阅：

- [使用 Shifts 连接器向导将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [使用 PowerShell 将班次连接到 Blue Yonder 员工管理](shifts-connector-blue-yonder-powershell-setup.md)

设置连接后，可以根据需要随时使用 PowerShell 更新和更改连接设置。 至于连接器本身，无需担心升级或维护。 我们照顾好这一点。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>用于Microsoft Teams的 Reflexis Shifts 连接器

用于Microsoft Teams的 Reflexis Shifts 连接器由 Zebra 托管和管理。 使用此连接器，可以将 Shifts 与 Reflexis WFM 系统集成，以管理计划并使计划保持最新。

一线员工可以访问他们在Teams班次中的日程安排，他们的请求从班次同步到 Reflexis 劳动力计划程序 (RWS) 。 在 RWS 中创建的请求和班次的状态将同步到 Teams 中的 Shifts。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="显示移动设备上的班次列表和 Reflexis 中的日程安排的屏幕截图。" lightbox="../../media/shifts-connector-reflexis.png":::

一线经理可以：

- 在 Reflexis 中发布班次和计划，并在 Shifts 中查看它们。
- 编辑 Reflexis 和 Shifts 中的班次。
- 在 Reflexis 和 Shifts 中创建、管理和分配打开的班次。
- 查看和批准来自 Reflexis 和 Shifts 中辅助角色的计划请求。

一线工作人员可以：

- 在班次中查看他们自己和团队的班次和日程安排。
- 在班次中请求休假、打开班次、交换和提供班次。

若要了解详细信息，请转到 https://connect.zebra.com/microsoft-connectors。

## <a name="related-articles"></a>相关文章

- [管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
