---
title: 在 Teams 中管理应用的应用策略概述
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
search.appverid: ''
description: 了解用于在 Microsoft Teams 中管理应用的应用权限策略、应用设置策略和自定义应用策略。
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: ad7e99d10ebf53c7a85394edda84061f6caf0d29
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837562"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>用于管理应用访问权限的应用策略概述

Microsoft Teams 使用策略来控制访问和安装行为。 策略可帮助 Teams 管理员控制以下应用行为：

* 在粒度级别为用户配置应用访问权限。 它可帮助每个最终用户仅使用管理员允许的应用。

* 为特定用户固定相关应用。 它可帮助最终用户轻松入门并快速访问相关应用，因为固定的应用无需干预即可自动安装。

## <a name="app-permission-policies"></a>应用权限策略

利用应用权限策略，Teams 管理员可以控制组织中的哪些特定用户可以使用哪些应用。 可以定义应用和用户之间的确切访问映射，也可以定义这两者的任意组合。 例如，可以为所有用户允许一些应用，可以为特定用户组允许一些应用，也可以为特定用户允许特定应用。

应用权限策略适用于 Teams 中可用的所有应用类型。 例如，可以使用应用权限策略逐步推出第三方应用或自定义应用，对特定用户允许该应用。

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="应用权限策略的屏幕截图。" lightbox="media/app-permission-policy.png":::

若要了解详细信息，请参阅[如何管理自定义应用策略和设置](teams-app-permission-policies.md)。

## <a name="app-setup-policies"></a>应用设置策略

应用设置策略允许你为用户自定义应用体验。 选择要固定到 Teams 客户端中应用栏的应用，以及这些应用在 Web、桌面和移动客户端上的显示顺序。

下面是一些有关如何使用应用设置策略的示例：

* 在其个人 Teams 环境中为最终用户安装应用。 它有助于提高对所需应用的认知和采用。 例如，为人力资源团队成员固定自定义招聘和人才管理应用。
* 选择性地固定核心应用，如“聊天”、“团队”和“通话”。

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Teams 管理中心中的应用设置策略的屏幕截图。" lightbox="media/app-setup-policy.png":::

若要了解详细信息，请参阅[如何管理应用设置策略](teams-app-setup-policies.md)。

## <a name="custom-app-policies"></a>自定义应用策略

Teams 允许组织内的开发人员为组织的内部用户生成、测试和部署自定义应用。 开发人员可以通过 Teams 提交其自定义应用，以供 Teams 管理员批准。 可以使用应用设置策略来控制组织中谁可以上传自定义应用。 管理员可以使用组织范围的应用设置允许其组织的最终用户使用自定义应用，并允许开发人员上传自定义应用。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="屏幕截图显示如何在组织范围的设置面板中允许组织的自定义应用。" lightbox="media/custom-app-policy.png":::

若要了解详细信息，请参阅[如何管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。

## <a name="related-articles"></a>相关文章

* [使用策略管理 Teams](manage-teams-with-policies.md)
