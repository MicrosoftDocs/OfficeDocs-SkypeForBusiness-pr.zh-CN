---
title: 使用应用自定义为应用打造品牌，以满足组织的需求
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
description: 了解如何更改应用的元数据和外观，以重新命名应用，以便在组织中更好地采用应用。
ms.openlocfilehash: 0a1ae462933768e0c5a53db6c7379e5cd8b9bf05
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647476"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>使用应用自定义更新组织 Teams 应用商店中的应用品牌

Microsoft Teams 管理员可以修改某些 Teams 应用的外观，为组织的最终用户提供个性化的品牌体验。 此类修改可以增强最终用户的 Teams 应用商店体验，并有助于坚持组织的品牌打造。 例如，管理员可以修改应用的说明和图标，以便其组织最终用户更轻松地识别应用、了解应用的使用情况，以及提高其突出程度。 管理员通过更改应用的某些元数据或属性进行这些更改。 这些更改仅在其组织中可用。 此功能称为应用自定义。

仅当应用开发人员允许自定义应用时，管理员才能自定义应用。 虽然 Teams 提供了一个自定义几个属性的选项，但应用开发人员控制任何管理员实际上可以自定义的属性。

作为管理员，可以自定义以下属性。

* 简短名称
* 简短说明
* 完整描述
* 隐私策略 URL
* 网站 URL
* 使用条款 URL
* 应用程序图标
* 图标的大纲颜色
* 强调色

有关这些元数据字段的详细信息，请参阅 Teams 开发人员文档中的 [Teams 清单架构](/microsoftteams/platform/resources/schema/manifest-schema) 。

> [!NOTE]
> 应用自定义功能不适用于自定义应用。 管理员无法在政府社区云高 (GCCH) 和国防部 (DoD) 环境中自定义任何应用。

## <a name="verify-if-an-app-is-customizable"></a>验证应用是否可自定义

所有应用都不可自定义。 如果应用开发人员允许你自定义其应用，则只能使用应用自定义功能来修改应用的外观。 若要验证所选应用是否可自定义，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 使用应用名称搜索要自定义的应用。 在 **“可自定义”** 列中验证应用开发人员是否允许自定义应用。 如果列不可见，请选择“编辑列 :::image type="icon" source="media/settings-icon-16px.svg"::: ”，并将 **“可自定义”** 选项切换为 **“打开**”。

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="屏幕截图显示管理中心中的可自定义列可帮助验证应用是否可自定义。":::

若要查找 Teams 存储区中所有可自定义应用，请对“可自定义”列进行排序。

## <a name="customize-the-details-of-an-app"></a>自定义应用的详细信息

若要更改应用在组织的 Teams 应用商店中显示的外观，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 使用应用名称搜索要自定义的应用，并确保可以对其进行自定义。

1. 若要打开 UI 以自定义单个元数据字段，请执行以下步骤之一：

   * 选择应用的行，然后在“管理应用”页的工具栏中选择 **“自定义**:::image type="icon" source="media/edit-pen-icon.png":::”。

   * 选择应用名称以打开应用详细信息页，然后选择 **“可自定义”** 下的编辑图标:::image type="icon" source="media/edit-pen-icon.png":::。

   * 选择应用名称，选择 **“操作**”，然后选择 **“自定义**”。

     :::image type="content" source="media/customize-action-menu.png" alt-text="屏幕截图显示了通过打开“操作”菜单并从应用详细信息页中选择“自定义”选项来自定义应用的选项。" lightbox="media/customize-action-menu-expanded.png":::

1. 自定义一个或多个可用字段。 应用开发人员可能只允许自定义几个元数据字段。 请参阅 [可自定义字段的注意事项和限制](#considerations-and-limitations-of-app-customization)。

   :::image type="content" source="media/customize-settings.png" alt-text="屏幕截图显示自定义用户界面上的名称和说明。":::

1. 自定义应用后，选择“ **应用**”。 若要验证所做的更改，请参阅 [预览版应用详细信息](#preview-app-details)。 若要撤消更改，请参阅 [将应用详细信息重置为默认值](#reset-app-details-to-default-values)。

1. 选择 **“发布** ”以发布自定义应用，并查看“ **管理应用** ”页中列出的应用。

<!---
   :::image type="content" source="media/customize-app-colors.png" alt-text="Screenshot showing the icon color options that can be customized.":::
--->

## <a name="preview-app-details"></a>预览应用详细信息

若要在保存自定义项后查看更改，请查看应用详细信息页。

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 若要打开应用详细信息页，请选择应用名称。

1. 查看应用详细信息，包括 **发布者短名称** 字段中的原始应用名称。 仅当更改了应用的短名称时，该字段才可见。

   :::image type="content" source="media/original-app-version.png" alt-text="屏幕截图显示了应用修改后的短名称。":::

Teams 用户可以在其客户端的 Teams 应用商店中看到自定义应用。

   :::image type="content" source="media/contoso-app.png" alt-text="屏幕截图显示了 Teams 客户端中的自定义应用。":::

## <a name="considerations-and-limitations-of-app-customization"></a>应用自定义的注意事项和限制

请考虑以下有关应用自定义功能的详细信息：

* 只有一个版本的应用，因为自定义应用功能不会创建应用的副本。

* 自定义应用和与应用相关的任何说明时，请确保遵循应用开发人员在其文档或使用条款中提供的准则。 使用任何第三方图像时，请遵守版权法。

* 管理员提供的自定义数据存储在最近的区域中。

* 你有责任确保使用条款或隐私策略的链接有效。

* 如果应用开发人员不再允许自定义字段，则应用详细信息页上会显示一条消息，通知管理员无法再自定义的字段。 对该字段所做的所有更改都将还原为原始值。

* 建议在生产环境中进行这些更改之前，先在 Teams 测试租户中测试应用自定义更改。 若要获取测试租户，请按照 [创建测试租户](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)的说明操作。

* 更改最多需要 24 小时才能传播到所有用户。

* 若要使应用可自定义，开发人员可以提供新版本的应用。 上传新版本并删除以前版本的应用。 如果已自定义应用并将其发布，则使用应用自定义功能自定义的新应用将不会替换当前应用。

* [应用使用情况报](teams-analytics-and-reports/app-usage-report.md) 表显示发布者提供的应用的原始名称。

* Microsoft Graph 权限许可对话框显示发布者提供应用的原始名称。 它可帮助你在向应用提供权限时准确识别应用。

可自定义字段的限制如下：

| 可自定义字段 | 考虑 |
|:---|:---|
| 任何 URL 字段 | 使用 `https`> 确保有效且安全的 URL。 |
| 简短说明 | 简短说明必须小于 80 个字符，并且不能重复完整说明中的内容。 |
| 图标 | 采用分辨率为 32x32 像素的 PNG 格式的透明轮廓图标。 |
| 颜色图标 | PNG 格式的全色图标，分辨率为 192x192 像素。 |
| 强调色 | 颜色必须与图标背景匹配。 |

## <a name="reset-app-details-to-default-values"></a>将应用详细信息重置为默认值

可以将应用详细信息重置为应用开发人员提供的原始值。 该选项仅适用于自定义的应用。

1. 在 Teams 管理中心，访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 若要打开应用详细信息页，请选择应用名称。

1. 在 **“操作”** 菜单中，选择 **“重置为默认** 值”。

   :::image type="content" source="media/reset-app-customization.png" alt-text="屏幕截图显示了自定义应用的“重置为默认”选项。":::

## <a name="related-articles"></a>相关文章

* [自定义组织的应用商店](customize-your-app-store.md)
* [重新命名应用](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
