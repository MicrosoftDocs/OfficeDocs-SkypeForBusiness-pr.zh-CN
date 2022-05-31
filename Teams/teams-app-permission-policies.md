---
title: 在 Microsoft Teams 中管理应用权限策略
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rarang
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
description: 了解Microsoft Teams中的应用权限策略，以及如何控制最终用户的应用可用性。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4872cb6222d8841bb2efe6be0e19fa17d3557e33
ms.sourcegitcommit: b8098d6ea36f10ee3a630a230ebd84bc2d96e37a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2022
ms.locfileid: "65780638"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理应用权限策略

作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。 你可以允许或阻止 Microsoft、第三方和你的组织发布的所有应用或特定应用。 阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

你可以在 Microsoft Teams 管理中心内管理应用权限策略。 可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。 编辑或分配策略后，更改可能需要几个小时才能生效。

![应用权限策略的屏幕截图。](media/app-permission-policies.png)

> [!NOTE]
> 组织范围的应用设置将覆盖全局策略以及你创建并分配给用户的任何自定义策略。

如果你的组织已在 Teams 上，则你在 Microsoft 365 管理中心“**租户范围内的设置**”中配置的应用设置将反映在“[管理应用](manage-apps.md)”页面上的组织范围的应用设置中。 如果你是 Teams 的新手并且刚入门，则默认情况下，将在全局策略中允许所有应用。 它包括 Microsoft、第三方软件提供商和组织发布的应用。

例如，假设你只想为组织中的 HR 团队允许一些特定的应用。 首先，在 [“管理应用](https://admin.teams.microsoft.com/policies/manage-apps) ”页上，确保允许 HR 团队使用的应用处于组织级别。 然后，创建自定义策略，将其设置为阻止和允许所需的应用，并将策略分配给 HR 团队中的用户。

> [!NOTE]
> 若要了解Microsoft 365 政府社区云高 (GCCH) 和国防部 (DoD) 环境特有的第三方应用设置，请参阅[Microsoft 365政府管理组织范围的应用设置](#manage-org-wide-app-settings-for-microsoft-365-government)。

## <a name="create-a-custom-app-permission-policy"></a>创建自定义应用权限策略

如果要控制适用于不同用户组的应用，请使用一个或多个自定义应用权限策略。 根据应用是由 Microsoft、第三方还是由你的组织发布，你可以创建并分配单独的自定义策略。 创建自定义策略后，如果在组织范围的应用设置中禁用了第三方应用，则无法对其进行更改。

1. 登录到[Teams管理中心](https://admin.teams.microsoft.com/dashboard)
1. 在左侧面板中，转到 **Teams应用** > **权限策略**。
1. 选择“**添加**”。

    ![新应用权限策略的屏幕截图。](media/app-permission-policies-new-policy.png)

1. 提供策略的名称和说明。
1. 在“**Microsoft 应用**”、“**第三方应用**”和“**自定义应用**”下，选择下列选项之一：

    * 允许所有应用
    * 允许特定的应用并阻止其他所有应用
    * 阻止特定的应用并允许其他所有应用
    * 阻止所有应用

1. 如果选择 **“允许特定应用”并阻止所有其他** 应用，请添加要允许的应用：

    1. 选择“**允许应用**”。
    1. 搜索要允许的应用，然后选择 **“添加**”。 搜索结果将筛选为应用发布者（**Microsoft 应用**、**第三方应用** 或 **自定义应用**）。
    1. 选择应用列表后，选择 **“允许**”。

1. 同样，如果选择了 **阻止特定应用并允许所有其他应用**，请搜索并添加要阻止的应用，然后选择 **“阻止**”。
1. 选择“**保存**”。

## <a name="edit-an-app-permission-policy"></a>编辑应用权限策略

可以使用Teams管理中心编辑策略，包括创建的全局策略和自定义策略。

1. 在Microsoft Teams管理中心的左窗格中，转到 **Teams应用** > **权限策略**。
1. 通过单击策略名称的左侧选择策略，然后选择 **“编辑”**。
1. 在此处根据需要进行更改。 你可以根据应用发布者来管理设置，也可以基于允许/阻止设置来添加和删除应用。
1. 选择“**保存**”。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>为用户分配自定义应用权限策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>管理 Microsoft 365 政府版的组织范围的应用设置  

在Microsoft 365政府 - GCC、GCCH 和 DoD 部署Teams中，默认情况下会阻止所有第三方应用。 在 GCCH 和 DOD 云中，第三方应用不可用。 此外，在GCC中，会在Microsoft Teams管理中心的应用权限策略页上看到有关管理第三方应用的以下说明。

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="GCCH 和 DoD 中应用权限策略的屏幕截图。":::

使用组织范围的应用设置来控制用户是否可以安装第三方应用。 组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。 你可以使用它们控制恶意应用或有问题的应用。

<!---
1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. --->

### <a name="for-gcc-clouds"></a>对于GCC云

1. 在“ **管理应用** ”页上，选择 **组织范围的应用设置**。 然后，你可以在面板中配置所需的设置。

  ![GCC中组织范围应用设置的屏幕截图。](media/app-permission-policies-gcc-org-wide.png)

1. 在“**第三方应用**”下，关闭或打开这些设置以控制对第三方应用的访问权限：

    * **允许第三方应用**：此选项控制用户是否可以使用第三方应用。 如果关闭此设置，则你的用户将不能安装或使用任何第三方应用。 在Microsoft 365政府 - GCCH 和 DoD 部署Teams中，此设置默认处于关闭状态。
    * **允许默认发布到应用商店的任何新的第三方应用**：此选项控制发布到Teams应用商店的新第三方应用是否在Teams中自动可用。 仅在允许第三方应用时才能设置此选项。

1. 在“**阻止的应用**”下，添加要在整个组织内阻止的应用。 在Microsoft 365政府 - GCCH 和 DoD 部署Teams中，默认情况下，所有第三方应用都会添加到此列表中。 对于想要在组织中允许的任何第三方应用，请从此阻止的应用列表中移除该应用。 当你阻止应用组织范围时，无论是否允许在任何应用权限策略中使用应用，应用都会自动阻止所有用户。

1. 选择 **“保存** ”以实现组织范围的应用设置。

若要允许第三方应用，请编辑和使用全局 (组织范围的默认) 策略，或者创建和分配自定义策略。

### <a name="for-gcch-and-dod-clouds"></a>对于 GCCH 和 DoD 云

1. 在“**权限策略**”页面上，选择“**组织范围的应用设置**”。 然后，你可以在面板中配置所需的设置。

  ![GCCH 和 DoD 中组织范围应用设置的屏幕截图。](media/app-permission-policies-gcch-dod-org-wide.png)

1. 在“**阻止的应用**”下，添加要在整个组织内阻止的应用。 在Microsoft 365政府 - GCCH 和 DoD 部署Teams中，默认情况下，所有第三方应用都会添加到此列表中。 当你阻止应用组织范围时，无论是否允许在任何应用权限策略中使用应用，应用都会自动阻止所有用户。
1. 选择 **“保存** ”以实现组织范围的应用设置。

## <a name="faq"></a>常见问题

### <a name="work-with-app-permission-policies"></a>使用应用权限策略

#### <a name="what-app-interactions-do-permission-policies-affect"></a>权限策略对哪些应用交互有影响？

通过控制最终用户的安装、发现和交互，权限策略可控制应用的使用。 无论向管理员分配的权限策略如何，管理员仍可以在 Microsoft Teams 管理中心内管理应用。

#### <a name="can-i-control-line-of-business-lob-apps"></a>我能否控制业务线 (LOB) 应用？

是的，你可以使用应用权限策略来控制自定义业务线 (LOB) 应用的推出和分发。 你可以创建自定义策略或编辑全局策略，以根据组织的需要允许或阻止自定义应用。

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>应用权限策略如何与已固定的应用和应用设置策略相关联？

你可以将应用设置策略与应用权限策略一起使用。 从为用户启用的应用集中选择预固定的应用。 此外，如果用户的应用权限策略阻止了应用设置策略中的应用，则该应用不会显示在 Teams 中。

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>我能否使用应用权限策略来限制上传自定义应用？

你可以使用“**管理应用**”页面上的组织范围设置或应用设置策略来限制上传组织的自定义应用。  

若要限制特定用户上传自定义应用，请使用自定义应用策略。 要了解详细信息，请参阅[在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>阻止应用是否适用于 Teams 移动客户端？

是的，如果阻止某个应用，则系统会在所有 Teams 客户端中阻止该应用。  

### <a name="user-experience"></a>用户体验

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>当应用被阻止时，用户会遇到什么情况？

用户无法与被阻止的应用或其功能（例如机器人、选项卡和消息传递扩展）进行交互。 在共享上下文（如团队或群组聊天）中，机器人仍可向该上下文的所有参与者发送消息。 当应用被阻止时，Teams 会向用户发出指示。

例如，当应用被阻止时，用户无法执行以下任何任务：

* 单独添加应用，或将其添加到聊天或团队
* 将消息发送到应用的机器人
* 执行将信息发送回应用的按钮操作，例如可操作邮件  
* 查看应用的选项卡
* 设置连接器以接收通知
* 使用应用的消息传递扩展

旧版门户允许在组织级别控制应用，这意味着当应用被阻止时，系统将为组织中的所有用户阻止该应用。 在“[管理应用](manage-apps.md)”页面上阻止应用的方式完全相同。

对于分配给特定用户的应用权限策略，如果允许然后阻止具有机器人或连接器功能的应用，并且仅允许共享上下文中的某些用户使用该应用，则群聊或频道中没有应用权限的成员可以查看机器人或连接器发布的消息历史记录和消息，但不能与其进行交互。

## <a name="see-also"></a>另请参阅

* [Teams 中应用的管理设置](admin-settings.md)
* [向 Teams 中的用户分配策略](policy-assignment-overview.md)
* [Teams功能可用性比较](/office365/servicedescriptions/teams-service-description#feature-availability)
