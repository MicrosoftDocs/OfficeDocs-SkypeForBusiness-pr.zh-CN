---
title: 在 Teams 中管理应用的应用策略概述
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/25/2022
search.appverid: ''
description: 了解用于管理 Microsoft Teams 中的应用的应用权限策略和设置策略。
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 8e059199d4963004e287b456c98bb80717f849b3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912431"
---
# <a name="know-about-policies-to-manage-access-and-installation-of-teams-apps"></a>了解用于管理 Teams 应用的访问和安装的策略

Microsoft Teams 使用应用策略来管理应用的访问和安装行为。 应用策略可帮助 Teams 管理员控制以下应用行为：

* 为每个用户或一组用户配置应用的访问权限。 它可帮助管理员控制每个最终用户允许的应用。

* 为最终用户固定与组织需求相关的应用。 此外，管理员无需用户干预即可为最终用户安装应用。 它可帮助最终用户轻松开始使用相关应用。

* 控制组织中的哪些开发人员可以提交自定义应用以供管理员批准。 它可帮助你控制对自定义应用上传功能的访问权限。

## <a name="app-permission-policies"></a>应用权限策略

使用应用权限策略，Teams 管理员控制组织中每个用户可用的应用。 你可以为所有用户允许几个应用，可以为特定用户组允许几个应用，也可以允许特定用户的特定应用。 应用权限策略与组织范围的设置协同工作，并允许或阻止每个应用的状态。

应用权限策略适用于 [Teams 中可用的所有类型的应用](deploy-apps-microsoft-teams-landing-page.md)。 使用应用权限策略的一些示例方案如下：

* 最初逐步向某些用户推出应用，并最终向所有用户推出应用。
* 仅允许人力资源部门成员使用自定义应用进行招聘和人才管理，并阻止所有其他组织用户。

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="应用权限策略的屏幕截图。" lightbox="media/app-permission-policy.png":::

若要了解详细信息，请参阅 [如何管理应用权限策略](teams-app-permission-policies.md)。

## <a name="app-setup-policies"></a>应用设置策略

应用设置策略允许配置应用在其 Teams 客户端中向用户提供的方式和位置。 选择要固定到 Teams 客户端中的应用栏的应用，并定义应用的显示顺序。

固定或安装应用有助于提高组织中所需应用的认知度和采用度。 这些更改适用于 Web、桌面和移动 Teams 客户端。

使用应用设置策略的一些示例方案如下：

* 为 HR 团队成员固定自定义招聘和人才管理应用。
* 使用组织用户的固定更改 [核心应用](deploy-apps-microsoft-teams-landing-page.md#core-apps) 的顺序。

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Teams 管理中心中的应用设置策略的屏幕截图。" lightbox="media/app-setup-policy.png":::

若要了解详细信息，请参阅[如何管理应用设置策略](teams-app-setup-policies.md)。

### <a name="option-to-upload-custom-apps"></a>上传自定义应用的选项

组织可以根据组织特定的要求委托创建自定义应用。 组织中的开发人员可以为组织的 Teams 内部用户生成、测试和部署自定义应用。 使用应用设置策略来控制组织中的哪些人可以上传自定义应用。 可以使用组织范围的设置来允许最终用户使用自定义应用。 使用权限策略仅允许特定最终用户使用自定义应用。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="屏幕截图显示如何在组织范围的设置面板中允许组织的自定义应用。" lightbox="media/custom-app-policy.png":::

若要了解详细信息，请参阅 [如何管理自定义应用的策略和设置](teams-custom-app-policies-and-settings.md)。

## <a name="related-articles"></a>相关文章

* [使用策略管理 Teams](manage-teams-with-policies.md)
* [管理应用权限策略](teams-app-permission-policies.md)
* [管理应用设置策略](teams-app-setup-policies.md)
* [管理自定义应用的策略和设置](teams-custom-app-policies-and-settings.md)
