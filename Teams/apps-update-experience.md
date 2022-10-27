---
title: Microsoft Teams 中的应用更新体验
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 本文介绍如何更新 Microsoft Teams 中的 Microsoft 应用、自定义应用和第三方应用，以及管理员如何为其提供便利。
ms.openlocfilehash: 0f5631abcd773f09c5a926bf3459d56e8f9f92bf
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738608"
---
# <a name="teams-app-updates-and-admin-role"></a>Teams 应用更新和管理员角色

Teams 管理员可以帮助最终用户获取最新版本的应用。 为此，他们完成以下一项或两项任务：

* 当应用开发人员或供应商提供新版本时，更新 Teams 应用商店中可用的[第三方](#updates-to-third-party-apps)应用。
* 更新仅在开发人员提交新版本时在组织中可用的[自定义应用](#updates-to-custom-apps)。

## <a name="updates-to-third-party-apps"></a>汇报到第三方应用

对于安装和使用应用的用户，他们必须向应用授予访问所需服务和信息的权限。 在大多数情况下，当已安装应用的新版本在 Teams 应用商店中可用时，该应用会自动为所有用户更新。 但是，新版本应用中的一些特定更改需要再次用户权限。 这种重复的用户接受可确保了解更改，例如功能或访问个人信息。 Teams 管理员可以 [代表用户向应用提供权限](app-permissions-admin-center.md)。

如果应用开发人员对其应用进行了以下一项或多项更改，则最终用户必须批准应用的更新。

* 添加机器人。 使用 `botId` 属性更改机器人的 ID。
* `isNotificationOnly`更改可能更改机器人通知的现有机器人的属性。
* 更改 `SupportsCalling`现有机器人的 、 `SupportsVideo`和 `SupportsFiles` 属性，以添加调用、播放视频以及上传或下载文件的功能。
* 在授权中添加或删除权限。
* 添加或删除消息传递扩展、添加组选项卡、添加连接器或添加频道。
* [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo)更改清单文件中的参数。

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>汇报自定义应用

在组织中创建和部署的自定义应用可供租户或组织中的用户使用。 Teams 管理员将自定义应用更新为组织内开发人员提供的新版本。 有关详细信息，请参阅 [管理员如何管理自定义应用](custom-app-overview.md)。

## <a name="related-article"></a>相关文章

* [了解应用中完成的更新的清单架构](/microsoftteams/platform/resources/schema/manifest-schema)。
* [了解自定义应用管理](custom-app-overview.md)。
