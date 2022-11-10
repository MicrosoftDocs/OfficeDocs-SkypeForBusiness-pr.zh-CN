---
title: 使用应用自定义功能根据组织需求打造应用品牌
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何更改应用的元数据和外观，以重新命名它，以便在组织中更好地采用应用。
ms.openlocfilehash: 870ee97b874b2600abf136cd045d47e9fca934d3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912651"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-org-store"></a>使用应用自定义更新组织商店中应用的品牌打造

Microsoft Teams 管理员可以修改某些 Teams 应用的外观，以便为其组织的最终用户提供个性化的品牌体验。 此类修改可以增强最终用户的 Teams 应用商店体验，并帮助遵守组织的品牌。 例如，管理员可以修改应用的说明和图标。 通过自定义，最终用户可以轻松地将应用标识为内部工具、了解其组织特定的用例，并放心地使用它。 管理员通过更改应用的某些元数据或属性进行这些更新。 更改仅在其组织中可用。 此功能称为应用自定义。

仅当应用开发人员允许自定义其应用时，管理员才能自定义应用。 虽然 Teams 提供了自定义以下属性的选项，但应用开发人员可以控制任何管理员实际可以自定义的属性。

* 简短名称
* 简短说明
* 完整描述
* 隐私策略 URL
* 网站 URL
* 使用条款 URL
* 应用程序图标
* 图标的大纲颜色
* 强调色

有关其中每个属性的详细信息，请参阅 Teams 开发人员文档中的 Teams [清单架构](/microsoftteams/platform/resources/schema/manifest-schema) 。

> [!NOTE]
> 必须具有 Teams 客户端许可证才能自定义应用信息。

## <a name="verify-if-an-app-is-customizable"></a>验证应用是否可自定义

所有应用都不可自定义。 如果应用开发人员允许自定义其应用，则只有这样才能修改应用的外观。 若要验证所选应用是否可自定义，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. （可选）如果 **“可自定义** ”列不可见，请选择“编辑列” :::image type="icon" source="media/settings-icon-16px.svg"::: 并将 **“可自定义”** 选项切换为“ **开**”。

1. 使用应用名称搜索要自定义的应用。 在 **“可自定义”** 列中验证应用开发人员是否允许自定义应用。

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="屏幕截图显示管理中心中的可自定义列可帮助你验证应用是否可自定义。":::

若要查找 Teams 应用商店中的所有可自定义应用，请对 **“可自定义”** 列进行排序。

## <a name="customize-an-app"></a>自定义应用

若要更改组织的 Teams 应用商店中应用的外观，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 使用应用名称搜索要自定义的应用 [，并确保可以自定义该](#verify-if-an-app-is-customizable)应用。

1. 若要打开 UI 以自定义单个元数据字段，请执行以下步骤之一：

   * 选择应用的行，然后在“管理应用”页的工具栏中选择“**自定义**:::image type="icon" source="media/edit-pen-icon.png":::”。

   * 选择应用名称以打开应用详细信息页，然后选择“**可自定义”** 下的编辑图标:::image type="icon" source="media/edit-pen-icon.png":::。

   * 选择应用名称以打开应用详细信息页，然后选择 **“操作** > **自定义**”。

     :::image type="content" source="media/customize-action-menu.png" alt-text="屏幕截图显示了通过打开“操作”菜单并从“应用详细信息”页中选择“自定义”选项来自定义应用的选项。" lightbox="media/customize-action-menu-expanded.png":::

1. 自定义一个或多个可用字段。 仅显示这些元数据字段，并且是应用开发人员允许的可自定义字段。 有关某些字段的限制，请参阅 [可自定义字段的注意事项和限制](#considerations-and-limitations-of-app-customization)。

   :::image type="content" source="media/customize-settings.png" alt-text="屏幕截图显示自定义用户界面上的名称和说明。":::

1. 自定义应用后，选择“ **应用**”。 若要验证所做的更改，请参阅 [预览应用详细信息](#preview-app-customizations)。 若要撤消更改，请参阅 [将应用详细信息重置为默认值](#reset-app-details-to-default-values)。

1. 选择“ **发布** ”，将自定义应用发布到组织的应用商店。

应用在 **“管理应用** ”页和 Teams 应用商店和客户端 (中列出，可通过 Web、移动或桌面客户端) 更新的详细信息。 修改可能需要几个小时才能显示。

## <a name="preview-app-customizations"></a>预览应用自定义

若要在保存自定义项后查看更改，请查看应用详细信息页。

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 若要打开应用详细信息页，请选择应用名称。

1. 查看应用详细信息，包括 **来自发布者的短名称** 字段中的原始应用名称。 仅当更改了应用的短名称时，字段才可见。

   :::image type="content" source="media/original-app-version.png" alt-text="屏幕截图显示已修改的应用短名称。":::

几个小时后，Teams 用户可在其客户端的 Teams 应用商店中看到自定义应用， (Web、移动和桌面) 。

   :::image type="content" source="media/contoso-app.png" alt-text="屏幕截图显示了 Teams 客户端中的自定义应用。":::

## <a name="considerations-and-limitations-of-app-customization"></a>应用自定义的注意事项和限制

请考虑以下有关应用自定义功能的详细信息：

* 只能自定义 [第三方应用](deploy-apps-microsoft-teams-landing-page.md#third-party-apps-created-by-independent-app-developers) ，不能 [自定义应用](deploy-apps-microsoft-teams-landing-page.md#custom-apps-created-within-an-organization-for-internal-use)。

* 无法在政府社区云高 (GCCH) 和国防部 (DoD) 环境中自定义任何应用。

* 仅当应用开发人员允许时，才能自定义应用。

* 对任何应用的修改仅在组织内可用。

* 你将只有一个版本的应用，因为自定义应用详细信息不会创建应用的副本。

* 自定义应用和与应用相关的任何说明时，请确保遵循应用开发人员在其文档或使用条款中提供的准则。 使用任何第三方图像时，请遵守版权法。

* 管理员提供的自定义数据存储在最近的数据存储区域中。

* 你有责任确保指向使用条款或隐私策略的链接有效。

* 如果应用开发人员不再允许自定义字段，则应用详细信息页面上会显示一条消息，通知管理员有关此类字段的信息。 对字段所做的任何更改都将还原为原始值。

* 建议在生产环境中进行这些更改之前，先在 Teams 测试租户中测试应用自定义更改。 若要获取测试租户，请按照 [创建测试租户](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)中的说明进行操作。

* 汇报在客户端中显示所有用户和管理员帐户最多需要 24 小时。

* 若要使现有应用成为可自定义应用，开发人员可以在 Teams 应用商店中提供该应用的新版本。

* [应用使用情况报告](teams-analytics-and-reports/app-usage-report.md)显示发布者提供的应用的原始名称，即使最终用户使用自定义应用也是如此。

* Microsoft Graph 权限许可对话框显示发布者提供应用的原始名称。 它可帮助你在向应用提供权限时准确识别应用。

* 自定义应用不会更改任何应用功能。

某些可自定义字段的限制如下：

| 可自定义字段 | 考虑 |
|:---|:---|
| 任何 URL 字段 | 使用 `https`确保 URL 有效且安全。 |
| 简短说明 | 简短说明必须不到 80 个字符。 不要重复完整说明中的内容。 |
| 图标 | 采用 PNG 格式的透明边框图标，分辨率为 32x32 像素。 |
| 颜色图标 | PNG 格式的全彩图标，分辨率为 192x192 像素。 |
| 强调色 | 颜色必须与图标背景匹配。 |

## <a name="troubleshoot-app-customization"></a>排查应用自定义问题

| 错误和问题 | 可能修复或理解问题 |
| --- | --- |
| 我的更新对最终用户不可用。 | 等待几个小时，让更改传播。 |
| 我无法自定义应用。 | 交叉检查 [应用是否可自定义](#verify-if-an-app-is-customizable)。|
| 我开始自定义应用，但无法保存或应用我的更改。 | 遵守字段的限制。 在 UI 上查找错误以及 [应用自定义的限制](#considerations-and-limitations-of-app-customization)。 |
| 管理应用页面未正确加载。 不显示应用列表。 | 使用中的管理员帐户必须分配有 Teams 许可证。 |

<!--- Check ICM for error string. --->

## <a name="reset-app-details-to-default-values"></a>将应用详细信息重置为默认值

可以将应用详细信息重置为应用开发人员提供的原始值。 该选项仅适用于自定义的应用。

1. 在 Teams 管理中心，访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 若要打开应用详细信息页，请选择应用名称。

1. 在 **“操作”** 菜单中，选择“ **重置为默认值**”。

   :::image type="content" source="media/reset-app-customization.png" alt-text="屏幕截图显示了自定义应用的“重置为默认”选项。":::

## <a name="related-articles"></a>相关文章

* [自定义组织的应用商店](customize-your-app-store.md)
* [重塑应用社区帖子的品牌](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
