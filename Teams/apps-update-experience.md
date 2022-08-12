---
title: Microsoft Teams 中的应用更新体验
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 本文介绍如何更新 Microsoft Teams 中的 Microsoft 应用、自定义应用和第三方应用，以及管理员如何为其提供便利。
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299041"
---
# <a name="update-apps-in-microsoft-teams"></a>在 Microsoft Teams 中更新应用

大多数情况下，当 Teams 应用商店中有新版本的应用可用时，系统会自动为用户更新该应用。 但是，新应用版本中的一些特定更改需要用户接受才能更新应用。 用户接受可确保了解功能或访问权限等更改。 如果应用开发人员对 Microsoft Teams 应用进行了以下特定更改，则最终用户必须批准应用更新：

* 添加了机器人。
* 现有机器人的 `botId` 属性或 `isNotificationOnly` 属性已更改。
* 为机器人添加了 `SupportsCalling`、`SupportsVideo` 和 `SupportsFiles` 功能。
* 添加了消息传递扩展。
* 添加或更改了授权中的权限。
* `Id` 或 `ApplicationPermissionsHash` 或两者都在 `webApplicationInfo` 内进行了更改。

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>相关文章

* [了解应用中完成的更新的清单架构](/microsoftteams/platform/resources/schema/manifest-schema)。
