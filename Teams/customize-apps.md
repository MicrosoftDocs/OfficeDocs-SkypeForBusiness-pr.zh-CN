---
title: 使用应用自定义为应用打造品牌，以满足组织的需求
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
description: 了解如何更改应用的元数据和外观，以重新命名应用，以便在组织中更好地采用应用。
ms.openlocfilehash: 7e2fe4545858980e3fc9d9784aea7b44256d52db
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377470"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>使用应用自定义更新组织 Teams 应用商店中的应用品牌

Microsoft Teams 管理员可以修改某些 Teams 应用的外观，为组织的最终用户提供个性化的品牌体验。 此类修改可以增强最终用户的 Teams 应用商店体验，并有助于坚持组织的品牌打造。 例如，管理员可以修改应用的说明和图标。 通过自定义，最终用户可以轻松地将应用标识为内部工具、了解其组织特定的用例，并放心地使用它。 管理员通过更改应用的某些元数据或属性来进行这些更新。 这些更改仅在其组织中可用。 此功能称为应用自定义。

仅当应用开发人员允许自定义应用时，管理员才能自定义应用。 虽然 Teams 提供了一个自定义以下属性的选项，但应用开发人员控制哪些属性实际上可以由任何管理员自定义。

* 简短名称
* 简短说明
* 完整描述
* 隐私策略 URL
* 网站 URL
* 使用条款 URL
* 应用程序图标
* 图标的大纲颜色
* 强调色

有关这些属性的详细信息，请参阅 Teams 开发人员文档中的 [Teams 清单架构](/microsoftteams/platform/resources/schema/manifest-schema) 。

> [!NOTE]
> 必须具有 Teams 客户端许可证才能自定义应用信息。

## <a name="verify-if-an-app-is-customizable"></a>验证应用是否可自定义

所有应用都不可自定义。 如果应用开发人员允许自定义其应用，则只能修改应用的外观。 若要验证所选应用是否可自定义，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. （可选）如果 **“可自定义** ”列不可见，请选择“编辑列 :::image type="icon" source="media/settings-icon-16px.svg"::: ”，并将 **可自定义** 选项切换为 **“打开**”。

1. 使用应用名称搜索要自定义的应用。 在 **“可自定义”** 列中验证应用开发人员是否允许自定义应用。

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="屏幕截图显示管理中心中的可自定义列可帮助验证应用是否可自定义。":::

若要查找 Teams 存储区中所有可自定义应用，请对 **“可自定义”** 列进行排序。

## <a name="customize-an-app"></a>自定义应用

若要更改组织 Teams 应用商店中应用的外观，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 使用应用名称搜索要自定义的应用 [，并确保可以对其进行自定义](#verify-if-an-app-is-customizable)。

1. 若要打开 UI 以自定义单个元数据字段，请执行以下步骤之一：

   * 选择应用的行，然后在“管理应用”页的工具栏中选择 **“自定义**:::image type="icon" source="media/edit-pen-icon.png":::”。

   * 选择应用名称以打开应用详细信息页，然后选择 **“可自定义”** 下的编辑图标:::image type="icon" source="media/edit-pen-icon.png":::。

   * 选择应用名称以打开应用详细信息页，然后选择“**自定义****操作** > ”。

     :::image type="content" source="media/customize-action-menu.png" alt-text="屏幕截图显示了通过打开“操作”菜单并从应用详细信息页中选择“自定义”选项来自定义应用的选项。" lightbox="media/customize-action-menu-expanded.png":::

1. 自定义一个或多个可用字段。 仅显示这些元数据字段，并且可自定义应用开发人员允许的字段。 有关某些字段的限制，请参阅 [可自定义字段的注意事项和限制](#considerations-and-limitations-of-app-customization)。

   :::image type="content" source="media/customize-settings.png" alt-text="屏幕截图显示自定义用户界面上的名称和说明。":::

1. 自定义应用后，选择“ **应用**”。 若要验证所做的更改，请参阅 [预览版应用详细信息](#preview-app-customizations)。 若要撤消更改，请参阅 [将应用详细信息重置为默认值](#reset-app-details-to-default-values)。

1. 选择 **“发布** ”，将自定义应用发布到组织的存储区。

应用列在“ **管理应用** ”页面中，在 Teams 应用商店和客户端 (通过 Web、移动或桌面客户端) 提供更新的详细信息。 修改可能需要几个小时才能显示。

## <a name="preview-app-customizations"></a>预览应用自定义项

若要在保存自定义项后查看更改，请查看应用详细信息页。

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 若要打开应用详细信息页，请选择应用名称。

1. 查看应用详细信息，包括 **发布者短名称** 字段中的原始应用名称。 仅当更改了应用的短名称时，该字段才可见。

   :::image type="content" source="media/original-app-version.png" alt-text="屏幕截图显示了应用修改后的短名称。":::

几个小时后，Teams 用户可以在其客户端 (Web、移动和桌面) 中查看 Teams 商店中的自定义应用。

   :::image type="content" source="media/contoso-app.png" alt-text="屏幕截图显示了 Teams 客户端中的自定义应用。":::

## <a name="considerations-and-limitations-of-app-customization"></a>应用自定义的注意事项和限制

请考虑以下有关应用自定义功能的详细信息：

* 只能自定义 [第三方应用](deploy-apps-microsoft-teams-landing-page.md#third-party-apps-validated-by-microsoft) ，而不能 [自定义应用](deploy-apps-microsoft-teams-landing-page.md#custom-apps)。

* 无法在政府社区云高 (GCCH) 和国防部 (DoD) 环境中自定义任何应用。

* 仅当应用开发人员允许应用时，才能自定义应用。

* 对任何应用的修改仅在组织中可用。

* 你将只有一个版本的应用，因为自定义应用详细信息不会创建应用的副本。

* 自定义应用和与应用相关的任何说明时，请确保遵循应用开发人员在其文档或使用条款中提供的准则。 使用任何第三方图像时，请遵守版权法。

* 管理员提供的自定义数据存储在最近的数据存储区域中。

* 你有责任确保使用条款或隐私策略的链接有效。

* 如果应用开发人员不再允许可自定义字段，则应用详细信息页上会显示一条消息，通知管理员有关此类字段的信息。 对字段所做的任何更改将还原为原始值。

* 建议在生产环境中进行这些更改之前，先在 Teams 测试租户中测试应用自定义更改。 若要获取测试租户，请按照 [创建测试租户](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)的说明操作。

* 汇报最多需要 24 小时才能在客户端中显示所有用户和管理员帐户。

* 对于可自定义的现有应用，开发人员可以在 Teams 应用商店中提供新版本的应用。

* [应用使用情况报表](teams-analytics-and-reports/app-usage-report.md)显示发布者提供的应用的原始名称，即使最终用户使用自定义应用。

* Microsoft Graph 权限许可对话框显示发布者提供应用的原始名称。 它可帮助你在向应用提供权限时准确识别应用。

* 自定义应用不会更改任何应用功能。

下面是某些可自定义字段的限制：

| 可自定义字段 | 考虑 |
|:---|:---|
| 任何 URL 字段 | 使用 `https`> 确保有效且安全的 URL。 |
| 简短说明 | 简短说明必须小于 80 个字符。 请勿重复完整说明中的内容。 |
| 图标 | 采用分辨率为 32x32 像素的 PNG 格式的透明轮廓图标。 |
| 颜色图标 | PNG 格式的全色图标，分辨率为 192x192 像素。 |
| 强调色 | 颜色必须与图标背景匹配。 |

## <a name="troubleshoot-app-customization"></a>排查应用自定义问题

| 错误和问题 | 可能的修复或理解问题 |
| --- | --- |
| 我的更新对最终用户不可用。 | 等待几个小时以进行更改传播。 |
| 无法自定义应用。 | 交叉检查 [应用是否可自定义](#verify-if-an-app-is-customizable)。|
| 我开始自定义应用，但无法保存或应用我的更改。 | 遵守字段的限制。 查找 UI 上的错误以及 [应用自定义的限制](#considerations-and-limitations-of-app-customization) |
| 管理应用页面未正确加载。 未显示应用列表。 | 正在使用的管理员帐户必须分配 Teams 许可证。 |

<!--- Check ICM for error string. --->

## <a name="reset-app-details-to-default-values"></a>将应用详细信息重置为默认值

可以将应用详细信息重置为应用开发人员提供的原始值。 该选项仅适用于自定义的应用。

1. 在 Teams 管理中心，访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 若要打开应用详细信息页，请选择应用名称。

1. 在 **“操作”** 菜单中，选择 **“重置为默认** 值”。

   :::image type="content" source="media/reset-app-customization.png" alt-text="屏幕截图显示了自定义应用的“重置为默认”选项。":::

## <a name="related-articles"></a>相关文章

* [自定义组织的应用商店](customize-your-app-store.md)
* [重塑应用社区帖子的品牌](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
