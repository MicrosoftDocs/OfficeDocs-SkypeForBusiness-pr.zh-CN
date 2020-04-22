---
title: 在 Microsoft Teams 中管理应用权限策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
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
description: 了解 Microsoft 团队中的应用权限策略以及如何使用它们控制你的组织中的用户可以使用哪些应用程序。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 3382eff6334c3879c1c30d503101446ceaae4df9
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749809"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理应用权限策略

作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。 你可以允许或阻止由 Microsoft、第三方和你的组织发布的所有应用或特定应用。 阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

你可以在 Microsoft 团队管理中心中管理应用权限策略。 可以使用全局（组织范围默认）策略，也可以创建自定义策略并将其分配给组中的单个用户或用户。  

![应用权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。 组织范围内的应用设置替代全局策略和你创建并分配给用户的任何自定义策略。

如果您的组织已在团队中，则在 Microsoft 365 管理中心的**租户范围设置**中配置的应用设置将反映在 "[管理应用](manage-apps.md)程序" 页面上的组织范围内应用设置中。 如果您不熟悉团队，并且只是开始使用，则默认情况下，所有应用都允许在全局策略中使用。 这包括由 Microsoft、第三方和你的组织发布的应用。

例如，你希望阻止所有第三方应用，并允许 Microsoft 针对你的组织中的人力资源团队应用特定应用。 首先，你将转到 "[管理应用](manage-apps.md)" 页面，并确保你希望为 HR 团队允许的应用在组织级别允许。 然后，创建名为 HR App 权限策略的自定义策略，将其设置为阻止并允许你所需的应用，并将其分配给 HR 团队上的用户。

> [!NOTE]
> 如果你在 Microsoft 365 政府-GCC 环境中部署团队，请参阅适用于 gcc 的[应用权限策略](#app-permission-policies-for-gcc)，了解有关特定于 GCC 的第三方应用设置的详细信息。

## <a name="create-a-custom-app-permission-policy"></a>创建自定义应用权限策略

如果你希望控制组织中不同组用户可用的应用，请创建并分配一个或多个自定义应用权限策略。 你可以基于 Microsoft、第三方或你的组织发布的应用创建和分配单独的自定义策略。 请务必注意，在创建自定义策略后，如果在组织范围的应用设置中禁用了第三方应用，则无法更改它。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。
2. 单击“添加”****。
    ![新应用权限策略的屏幕截图](media/app-permission-policies-new-policy.png)
3. 输入策略的名称和说明。
4. 在 " **Microsoft 应用**"、**第三方应用**和**租户应用**下，选择下列操作之一：

    - **允许所有应用**
    - **允许特定应用和阻止所有其他应用**
    - **阻止特定应用并允许所有其他应用**
    - **阻止所有应用**

5. 如果你选择 "**允许特定应用" 并阻止其他应用**，请添加你希望允许的应用：

    1. 选择 "**允许应用**"。
    1. 搜索要允许的应用，然后单击 "**添加**"。 搜索结果将筛选到应用发布者（**Microsoft 应用**、**第三方应用**或**租户应用**）。
    1. 选择应用列表后，单击 "**允许**"。

6. 同样，如果你选择 "**阻止特定应用" 并允许所有其他应用**，请搜索并添加要阻止的应用。
7. 单击“**保存**”。

## <a name="edit-an-app-permission-policy"></a>编辑应用权限策略

你可以使用 Microsoft 团队管理中心编辑策略，包括全局策略和你创建的自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 在此处进行所需的更改。 你可以基于应用发布者管理设置，并根据 "允许/阻止" 设置添加和删除应用。
4. 单击“**保存**”。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>向用户分配自定义应用权限策略

你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块，以便向用户组（如安全组或通讯组中的所有用户）分配自定义策略。

### <a name="assign-a-custom-app-permission-policy-to-a-user"></a>向用户分配自定义应用权限策略

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。****
3. 在 "**应用权限策略**" 下，选择要分配的应用权限策略，然后单击 "**应用**"。

若要将策略一次性分配给多个用户，请参阅[批量编辑 Teams 用户设置](edit-user-settings-in-bulk.md)。

或者，您也可以执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。
2. 单击策略名称的左侧以选择该策略。
3. 选择“管理用户”****。
4. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。******** 对想要添加的每一个用户重复此步骤。
5. 添加完用户后，单击 "**保存**"。

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>将自定义应用权限策略分配给组中的用户

你可能需要将自定义应用权限策略分配给已标识的多个用户。 例如，你可能想要向安全组中的所有用户分配策略。 你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。 有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

在此示例中，我们将名为 HR App 权限策略的自定义应用权限策略分配给 Contoso 制药人力资源项目组中的所有用户。  

> [!NOTE]
> 请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。

获取特定组的 GroupObjectId。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
获取指定组的成员。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
将组中的所有用户分配到特定应用权限策略。 在此示例中，它是 HR 应用权限策略。
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
此命令可能需要几分钟才能执行，具体取决于组中的成员数量。

## <a name="app-permission-policies-for-gcc"></a>适用于 GCC 的应用权限策略

在 Microsoft 365 政府版团队部署中，请务必了解以下有关适用于 GCC 的第三方应用设置的信息。

在 GCC 中，默认情况下将阻止所有第三方应用。 此外，在 Microsoft 团队管理中心的 "应用权限策略" 页面上，你将看到以下有关管理第三方应用的说明。

![GCC 中的应用权限策略的屏幕截图](media/app-permission-policies-gcc.png)

若要为你的组织中的一个用户或一组用户启用第三方应用，请执行下列操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **管理应用**"，然后在应用列表中，确认要为一组用户允许的第三方应用是否设置为 "在组织级别**阻止**"。

2. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"，然后编辑全局策略以阻止第三方应用。 要执行此操作：
    1. 在 "应用权限策略" 页面上，单击 "**全局（组织范围默认）**"，然后单击 "**编辑**"。
    2. 在 "**第三方应用**" 下，选择 "**阻止特定应用并允许所有其他**应用"，添加应用，然后单击 "**保存**"。

    > [!NOTE]
    > 请务必先执行此操作，然后再转到下一步，以便在组织级别允许应用。 这是因为如果在全局应用权限策略中未阻止第三方应用，则全局策略适用的所有用户都可以在组织级别允许访问第三方应用。

3. 允许在组织级别的第三方应用。 若要执行此操作，请在左侧导航中，转到 "**团队应用** > **管理应用**"。 在应用列表中，单击应用名称的左侧以选择应用，然后选择 "**允许**"。
4. [创建自定义应用权限策略](#create-a-custom-app-permission-policy)以允许应用，然后[将策略分配](#assign-a-custom-app-permission-policy-to-users)给所需的用户。

## <a name="faq"></a>常见问题

### <a name="working-with-app-permission-policies"></a>使用应用权限策略

#### <a name="what-app-interactions-do-permission-policies-affect"></a>权限策略影响的应用交互是什么？
权限策略通过控制最终用户的安装、发现和交互来控制应用的使用情况。 管理员仍然可以管理 Microsoft 团队管理中心中的应用，而不管分配给他们的权限策略如何。

#### <a name="can-i-control-line-of-business-lob-apps"></a>是否可以控制业务线（LOB）应用？
是的，你可以使用应用权限策略控制自定义（LOB）应用的推出和分发。 你可以创建自定义策略或编辑全局策略，以根据你的组织的需要允许或阻止自定义应用。

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>应用权限策略与已固定的应用和应用设置策略有何关系？

你可以将应用设置策略与应用权限策略结合使用。 已从用户的已启用应用集中选择预固定的应用。 此外，如果用户具有在应用设置策略中阻止应用的应用权限策略，则该应用不会显示在团队中。

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>是否可以使用应用权限策略来限制上载自定义应用程序？

你可以在 "**管理应用**" 页面上使用组织范围内的设置，或使用应用设置策略来限制为你的组织上载自定义应用。  

若要限制特定用户上载自定义应用程序，请使用自定义应用策略。 若要了解详细信息，请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>阻止应用是否会应用到团队移动客户端？

是的，当你阻止应用时，将阻止所有团队客户端上的应用。  

### <a name="user-experience"></a>用户体验

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>应用被阻止时的用户体验？

用户无法与已阻止的应用或其功能（如 bot、选项卡和消息传递扩展）交互。 在共享上下文（如团队或群组聊天）中，机器人仍可向该上下文的所有参与者发送消息。 团队在应用被阻止时向用户显示。

例如，当应用被阻止时，用户不能执行以下任一操作：

- 将应用程序个人或聊天添加到聊天或团队
- 将消息发送到应用的 bot
- 执行将信息发送回应用的按钮操作，例如可操作的消息  
- 查看应用的选项卡
- 设置连接器以接收通知
- 使用应用的消息扩展

旧版门户允许在组织级别控制应用，这意味着当应用被阻止时，组织中的所有用户都将阻止该应用。 在 "[管理应用程序](manage-apps.md)" 页面上阻止应用的工作方式完全相同。

对于分配给特定用户的应用权限策略，如果允许使用支持机器人或连接器功能的应用，并且该应用仅允许共享上下文中的某些用户，则不具有该应用权限的组聊天或频道的成员可以查看由 bot 或连接器发布的邮件历史记录和消息，但无法与之交互。

## <a name="related-topics"></a>相关主题

- [Teams 中适用于应用的管理设置](admin-settings.md)
