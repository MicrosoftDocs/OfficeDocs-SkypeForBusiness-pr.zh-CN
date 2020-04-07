---
title: 在 Microsoft 团队管理中心中管理你的应用
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 了解如何在 Microsoft 团队管理中心的 "管理应用" 页面上管理团队应用
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 5e261dfd6f23ec298e354a7732a9a1afa9d6b22e
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170550"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中管理你的应用
======================================================

作为管理员，Microsoft 团队管理中心中的 "**管理应用**" 页面是你在组织的应用程序目录中查看和管理所有团队应用的位置。 在此处，你可以查看应用的组织级别状态和属性，将新的自定义应用上载到租户应用目录、阻止或允许组织级别的应用，以及管理组织范围内的应用设置。

"**管理应用**" 页面为你提供租户目录中所有可用应用的视图，为你提供了确定要在组织中允许或阻止哪些应用的信息。 然后，你可以使用[应用权限策略](teams-app-permission-policies.md)、[应用设置策略](teams-app-setup-policies.md)和[自定义应用策略和设置](teams-custom-app-policies-and-settings.md)来为你的组织中的特定用户配置应用体验。

在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **管理应用**"。 您必须是全局管理员或团队服务管理员才能访问该页面。

## <a name="view-apps-in-your-tenant-app-catalog"></a>查看租户应用程序目录中的应用

你可以查看租户应用目录中的每个应用，包括有关每个应用的以下信息。

!["托管应用" 页面的屏幕截图](media/manage-apps.png)

- **名称**：应用名称。 单击应用名称以查看有关应用的详细信息。 其中包括应用的说明，无论它是允许还是阻止、应用于应用的版本、认证状态、支持的功能和应用 ID。 下面是一个示例：<br> 
![应用的 "应用详细信息" 页面的屏幕截图](media/manage-apps-app-details.png)
- **认证**：如果应用已通过认证，你将看到**Microsoft 365 认证**或**发布商证明**。 单击链接以查看应用的认证详细信息。 如果你看到 "**--**"，则表示没有适用于该应用的认证信息。 若要了解有关团队中已认证应用的详细信息，请参阅[Microsoft 365 应用认证计划](https://docs.microsoft.com/teams-app-certification/all-apps)。  
- **类别**：应用于应用的类别。
- **应用状态**： "组织" 级别的应用状态，可为下列之一：
    - **允许**：应用可用于你的组织中的所有用户。
    - 已**阻止**：应用被阻止，不能用于你的组织中的任何用户。<br>
请务必了解，此列表示以前位于**组织范围设置**窗格中的应用的 "允许" 和 "已阻止" 状态。 现在，你可以在 "**管理应用**" 页面上的组织范围内查看、阻止和允许应用。 
- **版本**：应用版本。

若要查看表中所需的信息，请单击右上角的 "**编辑列**" 以在表中添加或删除列。

## <a name="upload-a-new-app"></a>上载新应用程序

你可以使用应用目录来测试和分发专为你的组织构建的业务线应用程序。 团队应用包是使用[团队应用 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建的。 当你有应用包时，你可以将其添加到你的应用程序目录。 虽然组织中的所有用户都可以查看应用程序目录，但只有全局管理员和团队服务管理员可以发布和管理它。

若要将新的自定义应用上载到租户应用目录，请单击 "**上传新应用**" 以将你的应用包上载为 .zip 格式。 应用在上载后不会突出显示，因此你需要搜索你的应用目录才能找到它。

若要在上载应用后更新该应用，请在 "**管理应用**" 页面上的应用列表中单击应用名称，然后单击 "**更新**"。 执行此操作将替换你的应用目录中的现有应用，并且所有应用权限策略和应用设置策略都将对已更新的应用保持强制。

若要了解详细信息，请参阅[管理团队中的业务线应用](manage-your-lob-apps.md)。

## <a name="allow-and-block-apps"></a>允许和阻止应用

"**管理应用**" 页面是允许或阻止组织级别的单个应用的位置。 它显示了每个可用的应用及其当前的组织级应用状态。 （阻止和允许组织级别的应用已从**组织范围内的应用设置**窗格移动到此处。）

若要允许或阻止某个应用，请将其选中，然后单击 "**允许**" 或 "**阻止**"。 阻止应用时，将禁用与该应用的所有交互，并且该应用不会在团队中针对你的组织中的任何用户显示。

当你在 "**管理应用**" 页面上阻止或允许应用时，将阻止或允许组织中的所有用户使用该应用。  在团队应用权限策略中阻止或允许某个应用时，系统会阻止或允许分配该策略的用户。 若要使用户能够安装任何应用并与之交互，你必须在 "管理应用" 页面上的 "**管理应用**" 页面上和分配给用户的应用权限策略中允许该应用。

 > [!NOTE]
 > 若要卸载应用，请右键单击该应用，然后单击 "**卸载**" 或使用左侧面上的 "**更多应用**" 菜单。 

## <a name="manage-org-wide-app-settings"></a>管理组织范围内的应用设置

使用组织范围内的应用设置控制用户是否可以安装第三方应用以及用户是否可以上载或与你的组织中的自定义应用交互。 组织范围内的应用设置控制所有用户的行为，并替代分配给用户的任何其他应用权限策略。 你可以使用它们控制恶意或有问题的应用。

1. 在 "**管理应用程序**" 页面上，选择 "**组织范围内的应用设置**"。 然后，你可以在面板中配置所需的设置。

    ![组织范围内的应用设置的屏幕截图](media/manage-apps-org-wide-app-settings.png)
    
2. 在 "**第三方应用**" 下，关闭或打开这些设置以控制对第三方应用的访问：

    - **允许团队中的第三方应用**：这将控制用户是否可以使用第三方应用。 如果关闭此设置，你的用户将无法安装或使用任何第三方应用。 对于你允许的应用，状态显示为 "**允许"，但已禁用 "组织范围**"。              

        > [!NOTE]
        > 在 Microsoft 365 政府版团队部署中，默认情况下 "**允许团队中的第三方应用**" 设置处于关闭状态。

        当**允许团队中的第三方应用**处于关闭状态时，将禁用[传出 webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，这意味着用户无法创建它们。 当此设置处于打开状态时，将为所有用户启用传出 webhooks，无论用户是否在用户的应用权限策略中打开或关闭该设置。
    - **默认情况下允许发布到应用商店的任何新第三方应用**：这将控制发布到团队应用商店的新的第三方应用是否会自动在团队中可用。 仅当你允许第三方应用时，你才能设置此选项。

3. 在 "**自定义应用**" 下，关闭或打开 "**允许与自定义应用交互**"。 此设置控制用户是否可以与自定义应用交互。 若要了解详细信息，请参阅[管理团队中的自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。
4. 单击 "**保存**" 以使组织范围内的应用设置生效。

## <a name="related-topics"></a>相关主题

- [Teams 中适用于应用的管理设置](admin-settings.md)
