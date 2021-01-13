---
title: 在 Microsoft Teams 中管理应用权限策略
author: cichur
ms.author: v-cichur
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
description: 了解 Microsoft Teams 中的应用权限策略，以及如何使用它们来控制哪些应用可供组织用户使用。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802492"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理应用权限策略

作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。 你可以允许或阻止 Microsoft、第三方和组织发布的所有应用或特定应用。 阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

在 Microsoft Teams 管理中心中管理应用权限策略。 可以使用全局策略 (组织范围内的默认) 策略，也可以创建和分配自定义策略。 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。 编辑或分配策略后，可能需要几个小时更改才能生效。

![应用权限策略的屏幕截图](media/app-permission-policies.png)

> [!NOTE]
> 组织范围的应用设置会覆盖全局策略以及你创建并分配给用户的任何自定义策略。

如果你的组织已在 Teams 上，你在 Microsoft 365 管理中心的租户范围设置中配置的应用设置将反映在"管理应用"页面上的组织范围[应用设置](manage-apps.md)中。  如果你是 Teams 的新用户且刚刚入门，默认情况下，全局策略中允许所有应用。 这包括由 Microsoft、第三方和组织发布的应用。

例如，假设你想要阻止所有第三方应用，并允许 Microsoft 为贵组织的 HR 团队提供特定应用。 首先，转到"管理应用"[](manage-apps.md)页面，确保允许 HR 团队使用的应用在组织级别。 然后，创建名为 HR 应用权限策略的自定义策略，将其设置为阻止和允许所需的应用，并将其分配给 HR 团队中的用户。

> [!NOTE]
> 如果在 Microsoft 365 政府社区云 (GCC) 环境中部署了 Teams，请参阅"管理 [Microsoft 365](#manage-org-wide-app-settings-for-microsoft-365-government) 政府版组织范围内的应用设置"，详细了解 GCC 独有的第三方应用设置。

## <a name="create-a-custom-app-permission-policy"></a>创建自定义应用权限策略

如果要控制组织中不同用户组可用的应用，请创建并分配一个或多个自定义应用权限策略。 你可以根据应用是由 Microsoft、第三方还是你的组织发布的，创建和分配单独的自定义策略。 必须知道，创建自定义策略后，如果在组织范围内的应用设置中禁用了第三方应用，则不能更改该策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **权限策略"。**
2. 单击“添加”。 <br>
    ![新应用权限策略的屏幕截图](media/app-permission-policies-new-policy.png)
3. 输入策略的名称和说明。
4. 在 **"Microsoft 应用**、 **第三方** 应用"和" **自定义应用**"下，选择下列选项之一：

    - **允许所有应用**
    - **允许特定应用并阻止所有其他应用**
    - **阻止特定应用并允许其他所有应用**
    - **阻止所有应用**

5. 如果选择" **允许特定应用"并阻止其他** 应用，请添加要允许的应用：

    1. 选择 **"允许应用"。**
    1. 搜索要允许的应用，然后单击"添加 **"。** 搜索结果将筛选为应用发布者， (**Microsoft 应用**、第三方应用或自定义 **应用) 。**
    1. 选择应用列表后，单击"允许 **"。** 

6. 同样，如果选择了"阻止 **特定应用"并允许** 其他所有应用，请搜索并添加要阻止的应用，然后单击"阻止 **"。**
7. 单击“**保存**”。

## <a name="edit-an-app-permission-policy"></a>编辑应用权限策略

可以使用 Microsoft Teams 管理中心编辑策略，包括你创建的全局策略和自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **权限策略"。**
2. 单击策略名称左侧选择策略，然后单击"编辑 **"。**
3. 在此处，进行您需要的更改。 你可以根据应用发布者管理设置，并基于允许/阻止设置添加和删除应用。
4. 单击“**保存**”。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>向用户分配自定义应用权限策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>管理 Microsoft 365 政府版组织范围内的应用设置  

在 Teams 的 Microsoft 365 政府版 - GCC 部署中，必须了解以下内容，了解 GCC 独有的第三方应用设置。

在 GCC 中，默认情况下会阻止所有第三方应用。 此外，你将在 Microsoft Teams 管理中心的应用权限策略页面上看到有关管理第三方应用的以下说明。

![GCC 中应用权限策略的屏幕截图](media/app-permission-policies-gcc.png)

使用组织范围内的应用设置来控制用户是否可以安装第三方应用。 组织范围的应用设置控制所有用户的行为，并覆盖分配给用户的其他任何应用权限策略。 可以使用它们来控制恶意或有问题的应用。

1. 在"**权限策略"** 页上，选择 **"组织范围的应用设置"。** 然后，可以在面板中配置想要的设置。

    ![组织范围内应用设置的屏幕截图](media/app-permission-policies-gcc-org-wide.png)
    
2. 在第 **三方应用下**，关闭或打开这些设置以控制对第三方应用的访问：

    - **允许第三方应用**：控制用户是否可以使用第三方应用。 如果关闭此设置，用户将无法安装或使用任何第三方应用。 在 Teams 的 Microsoft 365 政府版 - GCC 部署中，此设置默认关闭。
    - **允许默认情况下发布到** 应用商店的任何新第三方应用：这控制发布到 Teams 应用商店的新第三方应用在 Teams 中是否自动可用。 只有在允许第三方应用时，才能设置此选项。

3. 在 **"阻止的应用**"下，添加要在整个组织中阻止的应用。 在 Teams 的 Microsoft 365 政府版 - GCC 部署中，所有第三方应用默认添加到此列表。 对于希望在你的组织中允许的任何第三方应用，请从此阻止的应用列表中删除该应用。 当你在组织范围内阻止应用时，你的所有用户都会自动阻止该应用，无论应用权限策略中是否允许该应用
4. 单击 **"** 保存"，使组织范围内的应用设置生效。

如前所述，若要允许第三方应用，可以编辑和使用全局 (组织范围内的默认) 策略，也可以创建和分配自定义策略。

## <a name="faq"></a>常见问题

### <a name="working-with-app-permission-policies"></a>使用应用权限策略

#### <a name="what-app-interactions-do-permission-policies-affect"></a>权限策略影响哪些应用交互？
权限策略通过控制最终用户的安装、发现和交互来控制应用使用情况。 无论分配了哪些权限策略，管理员仍可在 Microsoft Teams 管理中心管理应用。

#### <a name="can-i-control-line-of-business-lob-apps"></a>我能否控制 LOB () 业务线？
是的，可以使用应用权限策略来控制自定义 LOB 应用 () 分发。 可以创建自定义策略或编辑全局策略，以根据组织的需求允许或阻止自定义应用。

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>应用权限策略如何与固定的应用和应用设置策略相关？

可以将应用设置策略与应用权限策略一同使用。 预固定应用从用户启用的应用集进行选择。 此外，如果用户的应用权限策略阻止应用设置策略中的应用，则该应用不会显示在 Teams 中。

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>我可以使用应用权限策略来限制上传自定义应用吗？

可以在"管理应用"页面上使用组织范围的设置，或使用应用设置策略来限制为组织上传自定义应用。  

若要限制特定用户上传自定义应用，请使用自定义应用策略。 若要了解有关详细信息，请参阅["在 Teams 中管理自定义应用策略和设置"。](teams-custom-app-policies-and-settings.md)

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>阻止应用是否适用于 Teams 移动客户端？

是的，当你阻止应用时，该应用被阻止在所有 Teams 客户端上。  

### <a name="user-experience"></a>用户体验

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>当应用被阻止时，用户体验如何？

用户无法与阻止的应用或应用的功能（例如机器人、选项卡和消息传送扩展）交互。 在共享上下文（例如团队或群组聊天）中，机器人仍然可以向该上下文的所有参与者发送消息。 Teams 会向用户指示应用何时被阻止。

例如，当应用被阻止时，用户无法执行以下任一操作：

- 个人或聊天或团队添加应用
- 将消息发送到应用的机器人
- 执行将信息发送回应用的按钮操作，例如可操作消息  
- 查看应用的选项卡
- 设置连接器以接收通知
- 使用应用的消息传送扩展

旧门户允许在组织级别控制应用，这意味着当应用被阻止时，将阻止组织中所有用户使用该应用。 在"管理应用 ["页面上阻止](manage-apps.md) 应用的工作方式完全相同。

对于分配给特定用户的应用权限策略，如果允许然后阻止具有机器人或连接器功能的应用，并且如果应用仅允许共享上下文中的一些用户，则没有该应用权限的群组聊天或频道的成员可以看到机器人或连接器发布的消息历史记录和消息，但无法与其交互。

## <a name="related-topics"></a>相关主题

[Teams 中适用于应用的管理设置](admin-settings.md)

[在 Teams 中向用户分配策略](assign-policies.md)
