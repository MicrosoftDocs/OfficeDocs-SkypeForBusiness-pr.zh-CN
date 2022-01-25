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
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192474"
---
# <a name="shifts-connectors"></a>Shifts 连接线

## <a name="overview"></a>概述

使用 Shifts 连接器，可以将 Shifts（Microsoft Teams计划管理工具）与员工管理与 WFM (集成) 系统。 设置连接后，一线员工可以从 Shifts 中无缝查看和管理 WFM 系统中日程安排。

将 WFM 系统Teams一线员工可以更有效地管理日程安排，简化日常流程，提高参与度和工作效率。 一线员工有一个地方可以安排、通信和协作，随时随地在任何设备上完成工作。

我们提供托管的开源 Shifts 连接器。 本文概述了 Shifts 连接器及其工作方式。

## <a name="how-shifts-connectors-work"></a>Shifts 连接器如何工作

连接器在 WFM 系统和 Shifts 之间同步计划数据，将组织的计划纳入Teams。 排班是一线员工参与其日程安排需求的地方。 WFM 系统是业务规则、合规性和智能的记录系统。

通过连接器的数据流这两种方式可确保计划始终为最新。 WFM 系统中计划将同步到 Shifts。 此外，Shifts 中对计划所做的更改会实时同步回 WFM 系统。 作为记录系统，所有业务规则在保存到 Shifts 之前由 WFM 系统强制实施。

## <a name="managed-shifts-connectors"></a>托管 Shifts 连接器

托管 Shifts 连接器是与合作伙伴协作开发的连接器。 托管连接器由我们或合作伙伴托管和管理。 使用托管连接器时，只需进行少量的设置。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>适用于 Microsoft Teams 的反身符 Shifts 连接器

适用于 Microsoft Teams 的反身符 Shifts 连接器由 Microsoft Teams 托管和管理。 借助此连接器，可以将 Shifts 与 Reflexis WFM 系统集成，以管理计划并使它们保持最新。

一线员工在 Teams 中的排班中有权访问其日程安排，其请求从 Shifts 同步到 RwS (工作) 。 在 RWS 中创建的请求和班次的状态将同步到 Teams。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="显示移动设备上排班列表的屏幕截图，以及一个在 Reflexis 中安排日程的屏幕截图" lightbox="../../media/shifts-connector-reflexis.png":::

一线管理员可以：

- 在"反身"中发布班次和计划，在 Shifts 中查看它们。
- 在"反身"和"Shifts"中编辑班次。
- 在"反身"和"班次"中创建、管理和分配打开的班次。
- 在"反身"和"班次"中查看和批准来自工作人员的计划请求。

一线工作者可以：

- 在 Shifts 中查看其自己的团队班次和日程安排。
- 在 Shifts 中请求请假、调班和调班。

若要了解有关详细信息，请转到 https://connect.zebra.com/microsoft-connectors 。

## <a name="open-source-shifts-connectors"></a>开源 Shifts 连接器

开源 Shifts 连接器是构建在 Shifts Graph [API 上的社区驱动的集成](/graph/api/resources/shift)。 以下开源连接器可用：

- Kronos-to-Teams WFC 本地
- 适用于 Blue Yonder Teams 2017 到 2020.2 (的 JDA 到 Shifts 连接器) 

每个连接器附带详细的部署和配置指南。 它们包括 Azure 资源管理器 (ARM) 部署脚本，用于托管所有必需的服务Microsoft Azure。 源代码和部署脚本可在 GitHub[存储库中下载](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)。 可以按需求进行部署或自定义或扩展。

有关详细信息，请参阅 [生产就绪的 Shifts 连接器](/microsoftteams/platform/samples/shifts-wfm-connectors)。

## <a name="related-articles"></a>相关文章

- [管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
