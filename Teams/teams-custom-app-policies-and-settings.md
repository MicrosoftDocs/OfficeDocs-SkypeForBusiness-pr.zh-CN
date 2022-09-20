---
title: 管理自定义应用策略和设置
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
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
ms.openlocfilehash: d52fe50ba3fa02b3b39269fd06ce66ea0dfb5b32
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837162"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理自定义应用策略和设置

管理员可以使用自定义应用策略和设置来控制组织中哪些人可以将自定义应用上传到 Microsoft Teams。 管理员决定哪些用户可以上传自定义应用，管理员和团队所有者可以确定组织中的特定团队是否允许向其添加自定义应用。  编辑自定义应用策略后，更改可能需要几个小时才能生效。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

组织内的开发人员可以向 Teams 添加自定义应用程序，方法是将应用包（在 .zip 文件中）直接上传到团队或个人上下文中。 这与通过 Teams 应用商店添加应用程序的方式不同。 通过上传应用包添加自定义应用（也称为旁加载），可以让组织内的特定用户在应用准备广泛分发之前对其进行测试。

## <a name="custom-app-policy-and-settings"></a>自定义应用策略和设置

三个组件确定用户是否可以将自定义应用上传到团队，从而更细化地控制哪些人可以向团队添加自定义应用以及可以向哪些团队添加自定义应用：

- [用户自定义应用策略](#user-custom-app-policy)
- [团队自定义应用设置](#team-custom-app-setting)
- [组织范围内的自定义应用设置](#org-wide-custom-app-setting)

这些设置不会影响阻止第三方应用的能力。  

### <a name="user-custom-app-policy"></a>用户自定义应用策略

作为 [应用设置策略](teams-app-setup-policies.md)的一部分，管理员可以使用策略设置“**上传自定义应用**”来控制用户能否将自定义应用上传到 Teams。

如果此设置已禁用：

- 用户无法将自定义应用上传到组织或个人上下文中的任何团队。
- 用户可以与自定义应用交互，具体取决于组织范围内的自定义应用设置。

如果此设置已启用：

- 用户可以将自定义应用上传到允许该应用的团队以及用户是其所有者的团队，具体取决于组织范围内的自定义应用设置。
- 用户可以将自定义应用上传到个人上下文。
- 用户可以与自定义应用交互，具体取决于组织范围内的自定义应用设置。

可以编辑全局应用设置策略中的设置以包括所需的应用。 若要为组织中的不同用户组自定义 Teams，请创建并分配一个或多个自定义应用设置策略。

#### <a name="set-a-user-custom-app-policy"></a>设置用户自定义应用策略

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[设置策略](https://admin.teams.microsoft.com/policies/app-setup)**。
1. 选择“**添加**”。
1. 启用或禁用“**上传自定义应用**”。
1. 选择要用于策略的任何其他设置。
1. 选择“**保存**”。

### <a name="team-custom-app-setting"></a>团队自定义应用设置

管理员和团队所有者可以控制团队是否允许向该团队添加自定义应用。 此设置“**允许成员上传自定义应用**”以及用户的自定义应用策略决定哪些人可以向特定团队添加自定义应用。

如果此设置已禁用：

- 如果其自定义应用策略允许，团队所有者可以添加自定义应用。
- 非团队所有者的团队成员不能向团队添加自定义应用。

如果此设置已启用：

- 如果其自定义应用策略允许，团队所有者可以添加自定义应用。
- 如果自定义应用策略允许，非团队所有者的团队成员可以添加自定义应用。

#### <a name="configure-the-team-custom-app-setting"></a>配置团队自定义应用设置

1. 在 Teams 中，转到团队，然后选择 **“更多”选项...** > **管理团队**。
2. 选择 **“设置”** 并展开 **成员权限**。
3. 选中或清除“**允许成员上传自定义应用**”复选框。

    ![显示团队自定义应用设置的屏幕截图。](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>组织范围内的自定义应用设置

“[管理应用](manage-apps.md)”页面上的“**允许与自定义应用交互**”组织范围内的自定义应用设置适用于组织中的每个人，并控制他们是否可以上传自定义应用或与之交互。 此设置用作用户和团队自定义应用策略设置的主开/关开关。 它旨在作为安全事件期间的主开/关开关。 因此，即使启用了用户和团队自定义应用策略设置，除非启用了组织范围内的自定义应用设置，否则用户和团队的自定义应用策略设置将不会生效。

#### <a name="configure-the-org-wide-custom-app-setting"></a>配置组织范围内的自定义应用设置

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 选择 **组织范围的应用设置**。
1. 在“**自定义应用**”下，启用或禁用“**允许与自定义应用交互**”。

    ![显示组织范围内的自定义应用设置的屏幕截图。](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>自定义应用策略和设置如何协同工作

此表总结了自定义应用策略和设置、它们协同工作的方式，以及它们对控制组织中哪些人可以将自定义应用上传到 Teams 的联合效果。

例如，想要只允许团队所有者将自定义应用上传到特定团队。 将设置以下内容：

- 在 Microsoft Teams 管理中心启用“**允许与自定义应用交互**”。
- 对要限制访问的每个团队，禁用“**允许成员上传自定义应用**”。
- 在 Microsoft Teams 管理中心创建和分配自定义应用设置策略，启用“**上传自定义应用**”设置，并将其分配给团队所有者。

|组织范围内的自定义应用设置 |团队自定义应用设置 |用户自定义应用策略 |效果  |
|---------|---------|---------|---------|
| 关闭    | 关闭    | 关闭     |已为组织阻止与所有自定义应用的交互。 除 Teams 服务管理员或全局管理员外，任何人都无法上传自定义应用。可以使用 PowerShell 移除自定义应用。   |
| 关闭     | 关闭     | 开        |已为组织阻止与所有自定义应用的交互。 除 Teams 服务管理员或全局管理员外，任何人都无法上传自定义应用。可以使用 PowerShell 移除自定义应用。         |
| 关闭    | 开        | 关闭        |已为组织阻止与所有自定义应用的交互。 除 Teams 服务管理员或全局管理员外，任何人都无法上传自定义应用。可以使用 Windows PowerShell 删除自定义应用。         |
| 关闭    | 开      | 开       |已为组织阻止与所有自定义应用的交互。 除 Teams 服务管理员或全局管理员外，任何人都无法上传自定义应用。可以使用 PowerShell 移除自定义应用。         |
| 开    | 关闭       | 关闭         |  用户无法上传自定义应用。      |
| 开     | 关闭       | 开         | 如果用户是团队所有者，他们可以将自定义应用上传到团队。 如果用户不是团队所有者，则无法将自定义应用上传到团队。 用户可以将自定义应用上传到个人上下文中。     |
| 开     | 开     | 关闭         | 用户无法上传自定义应用。       |
| 开    | 开        | 开        | 用户可以将自定义应用上传到团队，无论用户是否是团队所有者。 用户可以将自定义应用上传到个人上下文中。       |

## <a name="related-articles"></a>相关文章

- [管理员 Teams 中应用的设置](admin-settings.md)。
- [在 Teams 中为用户分配策略](assign-policies-users-and-groups.md)。
