---
title: 管理自定义应用策略和设置
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何管理自定义应用策略和设置，以控制组织中哪些人可以在 Microsoft Teams 中上传自定义应用。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: e89a7aa3a2d016551695406551068cd07a2042e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119211"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理自定义应用策略和设置

> [!NOTE]
> 若要使用 App Studio，请参阅通过 [C#/.NET](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) 和 App Studio 开始使用 Microsoft Teams 平台。最后一步尚未运行，因此需要下载 zip，并使用旧方式在将应用包上传到 [Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload)中安装它。

作为管理员，可以使用自定义应用策略和设置来控制组织中哪些人可以将自定义应用上传到 Microsoft Teams。 管理员决定哪些用户可以上传自定义应用，管理员和团队所有者可以确定您的组织中的特定团队是否允许向这些用户添加自定义应用。  编辑自定义应用策略后，可能需要几个小时更改才能生效。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

## <a name="overview-of-custom-apps"></a>自定义应用概述

用户可以将应用包上传到 Teams， (.zip 文件) 直接上传到团队或个人上下文中。 这不同于通过 Teams 应用商店添加应用的方式。 通过上传应用包（也称为旁加载）来添加自定义应用，允许你在应用准备好广泛分发之前，在开发应用时测试该应用。 它还允许你生成一个仅供内部使用的应用，并与你的团队共享它，而无需将该应用提交到 Teams 应用商店中的 Teams 应用目录。

![显示应用商店中"上传自定义应用"选项的屏幕截图](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>自定义应用策略和设置

三个组件确定用户是否可以将自定义应用上传到团队，从而让你精细控制谁可以将自定义应用添加到团队，以及可以将自定义应用添加到哪些团队：

- [用户自定义应用策略](#user-custom-app-policy)
- [团队自定义应用设置](#team-custom-app-setting)
- [组织范围的自定义应用设置](#org-wide-custom-app-setting)

这些设置不会影响阻止第三方应用的能力。  

### <a name="user-custom-app-policy"></a>用户自定义应用策略

作为应用 [设置策略的](teams-app-setup-policies.md)一部分，管理员可以使用策略设置 **"** 上传自定义应用"来控制用户是否可以将自定义应用上传到 Teams。
 
如果此设置已关闭：

- 用户无法将自定义应用上传到组织或个人上下文中的任何团队。
- 用户可以与自定义应用交互，具体取决于组织范围的自定义应用设置。

如果此设置已打开：

- 用户可以将自定义应用上传到允许它的团队以及他们作为所有者的团队，具体取决于组织范围的自定义应用设置。
- 用户可以将自定义应用上传到个人上下文。 
- 用户可以与自定义应用交互，具体取决于组织范围的自定义应用设置。

可以在全局应用设置策略中编辑设置，以包含你需要的应用。 如果要为组织中不同用户组自定义 Teams，请创建并分配一个或多个自定义应用设置策略。

#### <a name="set-a-user-custom-app-policy"></a>设置用户自定义应用策略

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **设置策略"。**
2. 单击“**添加**”。
3. 打开或关闭"上传 **自定义应用"。**
4. 选择要用于策略的其他任何设置。
5. 单击“**保存**”。

### <a name="team-custom-app-setting"></a>团队自定义应用设置

管理员和团队所有者可以控制团队是否允许向团队添加自定义应用。 此设置" **允许成员上传自定义应用**"以及用户的自定义应用策略确定谁可以将自定义应用添加到特定团队。
 
如果此设置已关闭：

- 团队所有者可以添加自定义应用（如果其自定义应用策略允许）。
- 不是团队所有者的团队成员不能向团队添加自定义应用。

如果此设置已打开：

- 团队所有者可以添加自定义应用（如果其自定义应用策略允许）。
- 不是团队所有者的团队成员可以添加自定义应用（如果其自定义应用策略允许）。

#### <a name="configure-the-team-custom-app-setting"></a>配置团队自定义应用设置

1. 在 Teams 中，转到团队，单击"更多 **选项" 10"**  >  **管理团队"。**
2. 单击 **"设置**"，然后展开 **"成员权限"。**
3. 选中或清除" **允许成员上传自定义应用** "复选框。

    ![显示团队自定义应用设置的屏幕截图](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>组织范围的自定义应用设置

"**管理应用**"页上的"允许与自定义应用与组织范围的 [](manage-apps.md)自定义应用交互"设置适用于组织中的每个人，并控制他们是否可以上传自定义应用或与自定义应用交互。 此设置充当用户和团队自定义应用策略设置的主开/关开关。 它旨在充当安全事件期间的主开/关开关。 因此，用户和团队自定义应用策略设置不会生效，除非启用了组织范围的自定义应用设置，即使启用了用户和团队自定义应用策略设置。

#### <a name="configure-the-org-wide-custom-app-setting"></a>配置组织范围的自定义应用设置

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 单击 **"组织范围的应用设置"。**
3. 在 **"自定义应用**"下，打开或关闭 **"允许与自定义应用交互"。**

    ![显示组织范围的自定义应用设置的屏幕截图](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>自定义应用策略和设置如何协同工作

下表汇总了自定义应用策略和设置、它们如何协同工作，以及它们对控制组织中哪些人可以将自定义应用上传到 Teams 的组合效果。

例如，您希望只允许团队所有者将自定义应用上传到特定团队。 可以设置以下项：
- 在 Microsoft Teams **管理中心中** 打开"允许与自定义应用交互"设置。
- 关闭" **允许成员为要限制** 访问的每个团队上传自定义应用"。
- 在启用"上传自定义应用"设置后，在 Microsoft Teams管理中心创建并分配自定义应用设置策略，并将其分配给团队所有者。

|组织范围的自定义应用设置 |团队自定义应用设置 |用户自定义应用策略 |效果  |
|---------|---------|---------|---------|
| 关    | 关    | 关     |将阻止与组织的所有自定义应用交互。 除 Teams 服务管理员或全局管理员外，任何人都无法上传自定义应用。可以使用 PowerShell 删除自定义应用。   |
| 关     | 关     | 开        |将阻止与组织的所有自定义应用交互。 除 Teams 服务管理员或全局管理员外，任何人都无法上传自定义应用。可以使用 PowerShell 删除自定义应用。         |
| 关    | 开        | 关        |将阻止与组织的所有自定义应用交互。 除 Teams 服务管理员或全局管理员外，任何人都无法上传自定义应用。可以使用 Windows PowerShell删除自定义应用。         |
| 关    | 开      | 开       |将阻止与组织的所有自定义应用交互。 除 Teams 服务管理员或全局管理员外，任何人都无法上传自定义应用。可以使用 PowerShell 删除自定义应用。         |
| 开    | 关       | 关         |  用户无法上传自定义应用。      |
| 开     | 关       | 开         | 如果用户是团队所有者，他们可以将自定义应用上传到团队。 如果用户不是团队所有者，他们无法将自定义应用上传到团队。 用户可以在个人上下文中上传自定义应用。     |
| 开     | 开     | 关         | 用户无法上传自定义应用。       |
| 开    | 开        | 开        | 用户可以将自定义应用上传到团队，无论该用户是否是团队所有者。 用户可以在个人上下文中上传自定义应用。       |

## <a name="related-topics"></a>相关主题
 
[Teams 中应用的管理设置](admin-settings.md)

[向 Teams 中的用户分配策略](assign-policies.md)