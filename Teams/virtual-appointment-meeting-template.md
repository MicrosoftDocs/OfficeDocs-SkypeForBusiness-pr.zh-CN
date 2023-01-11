---
title: Microsoft Teams 中的虚拟约会会议模板
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
audience: admin
description: 了解如何管理组织中 Teams 用户的虚拟约会会议模板。
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0d93bb05a6456499ab1c0c16070149d8cdfd949
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767623"
---
# <a name="virtual-appointment-meeting-template-in-microsoft-teams"></a>Microsoft Teams 中的虚拟约会会议模板

![信息图标](media/info.png) **本文中所述的某些功能需要 [Teams 高级版](teams-add-on-licensing/licensing-enhance-teams.md) (预览版)**。

## <a name="overview"></a>概述

虚拟约会模板是 Microsoft Teams 中的一个默认会议模板，用户可以使用该模板来安排与组织外部的客户、客户端和其他人员进行虚拟约会。 例如，使用它来安排和进行面试、指导会议、财务咨询、虚拟购物体验等。

该模板允许指定会议组织者通常控制的会议设置的值。 它使你能够灵活地应用默认设置并强制实施设置。 可以选择锁定设置，以便会议组织者在使用模板时无法更改这些设置。

使用此模板，可以在整个组织中为 Teams 中安排的虚拟约会启用一致的体验，并帮助强制实施合规性要求。

本文概述了如何在 Teams 管理中心查看和管理虚拟约会会议模板。

## <a name="view-or-change-virtual-appointment-meeting-template-settings"></a>查看或更改虚拟约会会议模板设置

1. 在 Teams 管理中心的左侧导航栏中，转到 **“会议”“** > **会议模板**”。
1. 选择 **“虚拟约会**”，然后选择“ **编辑**”。
1. 若要进行更改，请选择一个选项，然后配置所需的设置。 对于每个选项，可以定义以下设置：
    - **默认值**：使用模板时应用于虚拟约会的值。
    - **可见性**：选择 **“隐藏”** 或“ **显示”** 以指定选项是否对 Teams 会议选项中的会议组织者可见。
    - **锁定状态**：若要防止会议组织者更改设置的值，请选择“ **锁定**”。 若要允许会议组织者更改设置的值，请选择“ **解锁**”。
1. 查看更改，然后选择“ **保存**”。

## <a name="manage-the-virtual-appointment-meeting-template"></a>管理虚拟约会会议模板

可以使用 Teams 管理中心中的会议模板策略来控制组织中的用户可以使用哪些会议模板。 默认情况下，全局策略允许用户查看和使用所有会议模板，包括虚拟约会模板和你创建的任何自定义模板。

如果要使虚拟约会模板可供组织中的特定用户或用户组使用，可以创建自定义会议模板策略，然后将其分配给这些用户或组。

若要了解详细信息，请参阅 [在 Teams 中管理会议模板](manage-meeting-templates.md)。

## <a name="user-experience"></a>用户体验

当组织中的用户使用会议模板安排虚拟约会时，组织外部的人员 (外部来宾) 获取定制的会议邀请，其中包括“ **作为来宾加入约会** ”按钮和其他约会详细信息。 他们可以使用此按钮从任何设备轻松加入，而无需下载和安装 Teams。

请记住，某些 Teams 会议选项可能不适用于外部来宾或使用“ **作为来宾加入约会** ”按钮加入的任何人员。 来宾加入支持以下会议选项：

- **谁可以绕过大厅**： **“每个人** ”设置允许外部来宾绕过大厅。
- **选择共同组织者**
- **自动录制**
- **允许会议聊天**：如果要在会议之前、会议期间和会议后阻止会议聊天，则设置为 **“已禁用** ”。

组织内的人员收到会议邀请，约会将显示在其 Teams 和 Outlook 日历中，他们可以像在任何其他 Teams 会议中一样轻松加入会议。 所有 Teams 会议选项都适用于使用会议邀请中的 Teams 会议链接或者从 Teams 或 Outlook 日历加入的与会者。

若要详细了解如何使用虚拟约会会议模板和用户体验，请参阅 [使用 Teams 会议模板创建虚拟约会](https://support.microsoft.com/office/6a9e8cbb-c0ed-4598-851e-3b1750a4a747)。

## <a name="related-articles"></a>相关文章

- [Teams 中的自定义会议模板概述](custom-meeting-templates-overview.md)
