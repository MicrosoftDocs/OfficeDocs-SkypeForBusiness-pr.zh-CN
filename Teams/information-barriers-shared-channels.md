---
title: '预览版中的信息屏障 (共享) '
description: 本文介绍共享频道中Microsoft Teams屏障
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: c65da8b9b04296a7377f29aead811e1efcfb4048
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712119"
---
# <a name="information-barriers-and-shared-channels-preview"></a>预览版中的信息屏障 (共享) 

[共享频道](shared-channels.md)Microsoft Teams创建协作空间，可在其中邀请不在团队中的人员。 [信息屏障](/microsoft-365/compliance/information-barriers) 是可实施的策略，用于限制和阻止用户和组在组织内外相互通信。

默认情况下，共享通道在 Teams。 你可以选择用户能否创建共享频道、能否与组织外部人员共享，以及是否可以通过创建频道策略参与外部共享频道。 在组织中配置信息屏障策略时，在配置共享通道时执行检查，以验证没有任何现有频道成员和添加到共享频道的任何新用户违反信息屏障策略条件。

使用下表了解信息屏障策略如何影响通信，以及配置共享通道时导致特定行为：

|**应用场景**|**信息屏障行为**|
|:-----------|:--------------------------------|
| **与组织中用户共享频道** | 如果根据信息屏障策略不允许用户与共享频道成员通信，则用户不会显示在用户搜索中，并且频道不会与团队共享。 <br><br> 如果无法根据信息屏障策略添加用户，你将看到以下消息：我们 *找不到任何匹配项。与 IT 管理员联系，了解扩展搜索范围。* |
| **与你拥有的另一个团队共享组织中频道** | 如果另一个团队有根据信息屏障策略不允许与共享频道成员通信的任何用户，则频道不会与团队共享。 <br><br> 如果根据信息屏障策略不允许通信，则会看到以下消息：无法与 *此团队共享频道。选择其他团队或联系管理员了解详细信息。* |
| **与另一个您不拥有的团队共享您的组织中的频道** | 如果根据信息屏障策略，不允许团队所有者或其他团队的任何用户与共享频道成员通信，则不能与团队共享频道。 <br><br> 如果根据信息屏障策略不允许通信，则会看到以下消息：无法与 *此团队共享频道。选择其他团队或联系管理员了解详细信息。* |
| **当团队与其他团队共享频道时，将新用户添加到团队** | 如果根据信息屏障策略不允许新用户与共享频道团队成员通信，则不能将该用户添加到该团队。 将用户添加到具有六个或多个共享频道的团队时，该用户将立即添加到频道，并且支持共享。 如果发现新用户不符合信息屏障策略，可能会停止团队和以前共享频道的共享。<br><br> 如果无法根据信息屏障策略添加用户，则会看到以下消息：由于信息屏障策略 *，无法添加用户。* |
| **与外部团队共享频道** | 内部和外部租户的信息屏障策略不会限制不同租户中的用户之间的通信。 共享频道可用于与外部用户共享。 |
