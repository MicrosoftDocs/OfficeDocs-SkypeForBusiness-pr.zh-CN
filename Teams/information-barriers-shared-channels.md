---
title: 预览)  (信息屏障和共享通道
description: 本文介绍 Microsoft Teams 中的信息障碍如何支持共享频道
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: 5b214a4c60df7b50f508fec7985c6f38b65985e6
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047212"
---
# <a name="information-barriers-and-shared-channels-preview"></a>预览)  (信息屏障和共享通道

Microsoft Teams 中的[共享频道](shared-channels.md)创建协作空间，可在其中邀请不在团队中的人员。 [Microsoft Purview 信息屏障](/microsoft-365/compliance/information-barriers) 是可以实施的策略，用于限制和防止用户和组在组织内外相互通信。

默认情况下，在 Teams 中启用共享通道。 你可以选择用户是否可以创建共享频道、他们是否可以与组织外部的人员共享该频道，以及他们是否可以通过 创建频道策略 来参与外部共享频道。 在组织中配置信息屏障策略时，在配置共享通道以验证现有频道成员和添加到共享通道的任何新用户是否违反信息屏障策略条件时，将执行检查。

使用下表了解信息屏障策略在配置共享通道时如何影响通信并导致特定行为：

|**应用场景**|**信息屏障行为**|
|:-----------|:--------------------------------|
| **与组织中的用户共享频道** | 如果不允许用户根据信息屏障策略与共享频道成员通信，则用户不会显示在用户搜索中，并且频道不会与团队共享。 <br><br> 如果无法根据信息屏障策略添加用户，你将看到以下消息： *我们未找到任何匹配项。与 IT 管理员讨论如何扩展搜索范围。* |
| **与你拥有的另一个团队共享组织中的频道** | 如果其他团队有任何用户不允许根据信息屏障策略与共享频道成员进行通信，则不会与团队共享该频道。 <br><br> 如果每个信息屏障策略不允许通信，你将看到以下消息： *无法与此团队共享该频道。选择另一个团队或与管理员联系以获取详细信息。* |
| **与你不拥有的另一个团队共享组织中的频道** | 如果不允许团队所有者或其他团队的任何用户根据信息屏障策略与共享频道成员通信，则无法与团队共享该频道。 <br><br> 如果每个信息屏障策略不允许通信，你将看到以下消息： *无法与此团队共享该频道。选择另一个团队或与管理员联系以获取详细信息。* |
| **当团队与其他团队共享频道时，向团队添加新用户** | 如果不允许新用户根据信息屏障策略与共享频道团队的成员通信，则无法将该用户添加到团队中。 将用户添加到具有六个或更多共享频道的团队时，会立即将用户添加到频道，并支持共享。 如果发现新用户不符合信息屏障策略，则可能会停止对团队和以前共享的频道的共享。<br><br> 如果无法根据信息屏障策略添加用户，你将看到以下消息： *由于信息屏障策略，无法添加用户。* |
| **与外部团队共享频道** | 内部和外部租户的信息屏障策略不会限制来自不同租户的用户之间的通信。 共享通道可用于与外部用户共享。 |
