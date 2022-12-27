---
title: Microsoft Teams 中的自定义会议模板概述
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
appliesto:
- Microsoft Teams
description: 了解 Microsoft Teams Premium 中的自定义会议模板。
ms.openlocfilehash: 0ed766141e09b9c26d8e8c6f5e8fdd12195ddb78
ms.sourcegitcommit: 4fdbd93aacb52a4fca68e31eb04d0495d4e27a10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/27/2022
ms.locfileid: "69672912"
---
# <a name="overview-of-custom-meeting-templates-in-microsoft-teams"></a>Microsoft Teams 中的自定义会议模板概述

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Microsoft Teams Premium 包括创建自定义会议模板的功能。 会议模板可用于控制会议组织者通常控制的会议设置。 使用模板，可以在组织中创建一致的会议体验，并帮助强制实施合规性要求和业务规则。

会议模板可用于强制设置或设置默认值。 可以锁定每个模板设置，以便会议组织者无法更改它，或者可以根据需要解锁会议组织者进行更改。

可以使用会议模板控制以下会议设置：

|设置|说明|
|:------|:----------|
|聊天|指定会议聊天是否可用。 还可用于在会议前后阻止聊天。|
|端到端加密|指定会议是否加密。|
|大堂|指定谁可以绕过大厅并直接加入会议。|
|管理与会者看到的内容|指定会议组织者是否可以在其他会议参与者看到内容之前预览和批准在屏幕上共享的内容。|
|与会者的麦克风和摄像头|指定与会者是否可以取消静音并使用其相机。|
|呼叫者加入和离开时发出通知|指定当通过电话呼叫加入或离开会议时是否播放声音。|
|Q&A|指定与会者是否可以在会议期间使用 Q&A 功能提问。|
|反应|指定与会者是否可以在会议中使用反应或举手。|
|录制|指定谁可以录制以及是否自动录制会议。|
|敏感度标签|指定要用于会议的敏感度标签。|
|水印|指定是否对会议屏幕上共享的相机源和内容使用水印。|

模板何时有用的一些示例包括：

- 为某些类型的会议强制执行自动会议录制。
- 限制聊天和与会者相机和音频，并使用 Q&A 功能进行演示式会议。
- 对可以绕过大厅的人员使用更严格的默认值，但允许会议组织者根据需要更改设置。

若要了解如何创建会议模板，请参阅[在 Microsoft Teams 中创建自定义会议模板](create-custom-meeting-template.md)。

## <a name="templates-with-sensitivity-labels"></a>具有敏感度标签的模板

模板可以选择指定敏感度标签。 标签也可以直接应用于会议，独立于模板。 敏感度标签可以控制一些与模板相同的设置：

- 端到端加密
- 会议聊天
- 自动录制
- 谁可以绕过大厅
- 谁可以演示
- 谁可以录制
- 水印

如果在标签中配置了这些设置中的任何一个，它们将在模板中替代这些设置。

## <a name="templates-included-with-teams"></a>Teams 附带的模板

Teams Premium 包括多个可提供给用户的默认会议模板：

- 大型会议
- 受保护的会议
- 大会堂
- [虚拟约会](virtual-appointment-meeting-template.md)
- 网络研讨会

此外，Teams 教育版中提供了这些模板：

- 类
- 讨论组
- 演讲
- 家长会议

如果需要，可以更新这些模板上的设置。

## <a name="related-topics"></a>相关主题

[使用三层保护配置 Teams 会议](configure-meetings-three-tiers-protection.md)

[将 Teams 会议模板、敏感度标签和管理策略结合使用](meeting-templates-sensitivity-labels-policies.md)
