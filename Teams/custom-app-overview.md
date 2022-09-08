---
title: 管理自定义和旁加载应用
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解什么是 Microsoft Teams 中的自定义应用和旁加载应用，并管理应用以控制其行为、推出和权限。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: d7c23b424db102b21e88944e2ab55d8a2fe98c08
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299292"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>了解和管理自定义和旁加载应用

Microsoft Teams 允许组织内的开发人员为组织的内部用户生成、测试和部署自定义应用。 此类应用称为自定义应用或业务线应用。 组织可以根据组织特定的要求委托创建自定义应用。

作为管理员，你可以控制整个组织或特定用户允许或阻止此类应用。 组织中的开发人员可以通过使用 Teams 与 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 集成，快速构建自定义低代码解决方案。

开发人员可以通过 Teams 提交自定义应用以获得管理员批准。可以使用应用设置策略来控制自定义应用的推出、分发和权限。

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="显示如何在组织范围内的设置面板中允许自定义应用的屏幕截图。" lightbox="media/custom-app-policy.png":::

允许使用自定义应用后，最终用户可以通过在 Teams 应用商店的左侧导航中选择 **“为组织生成** ”来找到它。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 桌面应用中 Teams 应用商店中自定义应用的屏幕截图。" lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>了解自定义应用的旁加载

开发自定义应用时，以及在将这些应用分发给最终用户之前，开发人员通过将其添加到 Teams 应用商店进行测试来测试应用。 开发人员可以自行或使用指定的用户组进行测试，但该应用无法通过应用商店提供给组织中的其他最终用户。 此方法称为应用旁加载，仅适用于自定义应用。

开发人员可以旁加载应用，使其可供特定团队的成员使用，通常用于测试开发不足的应用。 以这种方式使用应用会将其使用限制为应用开发人员，并且只要管理员允许在 Teams 中旁加载，就不需要管理员批准。

开发人员可以与特定团队共享旁加载的应用，而无需将其提交到 Teams 应用目录。 它使旁加载的自定义应用可供有限的最终用户组使用，但在组织的所有最终用户的应用存储中不可用。

作为管理员，你可以禁止为所有开发人员旁加载应用。 如果不允许旁加载，开发人员仍可以通过 [创建单独的测试租户](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant) 来测试其应用。 自定义应用开发完成后，开发人员会请求管理员将其自定义应用分发给最终用户。 有关详细信息，请参阅 [如何发布自定义应用](/microsoftteams/upload-custom-apps)。 作为管理员，可以允许或禁止对特定用户使用自定义应用。

## <a name="allow-developers-to-upload-custom-apps"></a>允许开发人员上传自定义应用

你可以创建自定义策略或编辑全局策略，以根据组织的需要允许或阻止自定义应用。 若要创建允许组织开发人员上传自定义应用的自定义策略，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[设置策略](https://admin.teams.microsoft.com/policies/app-setup)**。

1. 选择“**添加**”。

1. 提供策略的名称和说明。

1. 打开或关闭 **上传自定义应用**。

> [!NOTE]
> 若要更改此设置，请允许租户的 [组织范围应用设置](manage-apps.md#manage-org-wide-app-settings)中的第三方应用。

## <a name="related-articles"></a>相关文章

* [管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)
* [了解管理应用的策略](app-policies.md)
* [了解第三方应用](overview-third-party-apps.md)