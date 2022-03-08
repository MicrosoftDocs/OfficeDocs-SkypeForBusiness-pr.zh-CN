---
title: Microsoft Teams 中适用于应用的管理设置
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: 了解可用于管理组织中应用的策略和设置，Microsoft Teams。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44c46df2e25473b72af8e97a02d941eed50d9897
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070251"
---
# <a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams 中适用于应用的管理设置

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

应用为组织提供开箱即用的工具，以进一Teams。 这些应用结合了由 Microsoft 提供的选项卡、消息传送扩展、连接器和机器人的功能，由第三方构建，或由组织中的开发人员提供。

在管理中心内为Teams **管理** 应用。  (请参阅使用 Teams 管理员角色管理 [Teams](./using-admin-roles.md) 以阅读有关获取管理员角色和权限的信息。) 例如，可以在组织级别允许或阻止应用，设置策略来控制哪些应用可供 Teams 用户使用，以及通过固定对用户最重要的应用来自定义 Teams。

我们正在不断改进应用体验，Teams添加特性和功能。 随着时间的推移，我们将构建其他应用管理功能，因此请返回查看有关应用策略最新信息。

## <a name="manage-apps"></a>管理应用

使用 **"管理应用**"页查看和管理Teams应用程序目录中的所有应用。 可以在组织级别查看应用的状态和属性、在组织级别阻止或允许应用、将新的自定义应用上传到租户目录，以及管理组织范围内的应用设置。

" **管理应用** "页提供了租户目录中所有可用应用的视图，为你提供确定允许或阻止整个组织哪些应用时需要的信息。 然后，可以使用 [应用权限策略](#app-permission-policies)、 [应用设置](#app-setup-policies)策略、自定义应用策略 [和](#custom-app-policies-and-settings) 设置为组织中特定用户配置应用体验。

有关详细信息，请参阅在应用程序中[管理Teams](manage-apps.md)。

## <a name="app-permission-policies"></a>应用权限策略

使用应用权限策略，可以控制哪些应用可供组织的特定用户使用。 你可以允许或阻止 Microsoft、第三方和你的组织发布的所有应用或特定应用。

例如，可以使用应用权限策略来：

- 逐渐向特定用户推出新的第三方或自定义生成应用。
- 简化用户体验，尤其是在开始在整个组织中推出Teams时。

有关详细信息，请转到在应用中[管理应用权限Teams](teams-app-permission-policies.md)。

## <a name="app-setup-policies"></a>应用设置策略

应用设置策略允许为用户自定义应用体验。 在 Web 客户端、桌面客户端和移动Teams，选择要固定到应用栏的应用及其显示顺序。

下面是一些如何使用应用设置策略的示例：

- 促进核心应用的认知和采用。 例如，为 HR 团队中的用户固定自定义招聘和才能管理应用。
- 选择性地固定Teams聊天、聊天和Teams等功能。 这样做有助于确保用户参与特定活动Teams。

有关详细信息，请查看在应用中[管理应用设置Teams](teams-app-setup-policies.md)。

## <a name="custom-app-policies-and-settings"></a>自定义应用策略和设置

Teams允许组织中开发人员生成、测试自定义应用，以及将自定义应用部署到其他用户。 可以将自定义应用添加到Teams将应用包上传到 .zip 文件，直接上传到团队或个人上下文中。 可以使用应用设置策略来控制组织中哪些人可以上传自定义应用。 还可以设置组织范围的设置，以控制用户是否可以与特定的自定义应用交互。

有关详细信息，请转到管理应用中[的自定义应用策略和Teams](teams-custom-app-policies-and-settings.md)。