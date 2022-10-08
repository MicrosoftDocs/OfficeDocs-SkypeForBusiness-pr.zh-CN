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
ms.date: 09/04/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 本文介绍如何更新 Microsoft Teams 中的 Microsoft 应用、自定义应用和第三方应用，以及管理员如何为其提供便利。
ms.openlocfilehash: 14c327c2a24536f5441b318767e301ffe9a3196d
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2022
ms.locfileid: "68376810"
---
# <a name="teams-app-updates-and-admin-role"></a>Teams 应用更新和管理角色

Teams 管理员可以帮助最终用户获取最新版本的应用。 为此，他们完成以下一项或两项任务：

* 当应用开发人员或供应商提供新版本时，更新 Teams 应用商店中可用的第[三方应用](#updates-to-third-party-apps)。
* 更新仅在开发人员提交新版本时在组织中可用的[自定义应用](#updates-to-custom-apps)。

## <a name="updates-to-third-party-apps"></a>汇报到第三方应用

用户若要安装和使用应用，必须向应用授予访问所需服务和信息的权限。 在大多数情况下，当 Teams 应用商店中提供了已安装应用的新版本时，系统会自动为所有用户更新该应用。 但是，新版本应用中的一些特定更改需要再次获得用户权限。 此重复用户接受可确保了解更改，例如功能或访问个人信息。 Teams 管理员可以 [代表用户向应用提供权限](app-permissions-admin-center.md)。

如果应用开发人员对其应用进行了以下一项或多项更改，则最终用户必须批准应用的更新。

* 添加或删除机器人。 使用属性更改机器人的 `botId` ID。
* `isNotificationOnly`更改可能更改机器人通知的现有机器人的属性。
* `SupportsVideo`更改`SupportsCalling`现有机器人的属性，`SupportsFiles`以添加调用、播放视频以及上传或下载文件的功能。
* 在授权中添加或删除权限。
* 添加或删除消息传递扩展、添加组选项卡、添加连接器或添加通道。
* 更改清单文件中的 [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) 参数。

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>汇报自定义应用

在组织内创建和部署的自定义应用可供租户或组织上的用户使用。 Teams 管理员将自定义应用更新到组织内开发人员提供的新版本。 有关详细信息，请参阅 [管理员如何管理自定义应用](custom-app-overview.md)。

## <a name="related-article"></a>相关文章

* [了解应用中完成的更新的清单架构](/microsoftteams/platform/resources/schema/manifest-schema)。
* [了解自定义应用管理](custom-app-overview.md)。
