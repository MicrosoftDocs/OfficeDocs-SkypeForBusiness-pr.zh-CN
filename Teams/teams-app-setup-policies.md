---
title: 在 Microsoft Teams 中管理应用设置策略
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
description: 了解如何在 Microsoft 团队中为你的组织中的用户使用和管理应用设置策略。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 9ddbcd1a5110cff52ce518cf052279204fc8e2c9
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938211"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理应用设置策略

> [!NOTE]
> 如果启用了组织范围的应用设置，**允许与自定义应用交互**，则你可能看不到 Microsoft 团队管理中心中的应用安装策略。 它目前正在推出，即将在您的组织中提供。

作为管理员，你可以使用应用设置策略执行以下操作：

- 自定义 Teams 以突出显示对用户最为重要的应用。 你可以选择要固定的应用，并设置它们的显示顺序。 通过固定应用，可展示组织中的用户所需的应用，包括由第三方或组织中的开发人员构建的应用。
- 控制用户是否可以将应用固定到 Teams。
- 代表用户安装应用 **（在预览中）**。 在用户启动团队时，选择默认为用户安装的应用。 请记住，如果分配给应用的[应用权限策略](teams-app-permission-policies.md)允许，用户仍然可以自行安装应用。

将应用程序固定到应用栏。 这是 Teams 桌面客户端的侧边栏和 Teams 移动客户端（iOS 和 Android）的底边栏。

|团队桌面客户端  |团队移动客户端 |
|---------|---------|
|![显示团队桌面客户端的屏幕截图](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![显示团队移动客户端的屏幕截图](media/app-setup-policies-mobile-app-bar.png)      |

若要查看其预安装应用，请在应用栏中单击 " **..."** 团队桌面和 web 客户端中的更多应用，并在移动客户端中向上轻扫。

在 Microsoft 团队管理中心中管理应用设置策略。 你可以使用全局（组织范围默认）策略或创建并分配自定义策略。  除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

你可以编辑全局策略中的设置以包括所需的应用。 如果要为组织中的不同组用户自定义团队，请创建并分配一个或多个自定义策略。

![显示应用设置策略页面的屏幕截图](media/app-setup-policies.png)

> [!NOTE]
> 如果你有团队教育版，请务必了解，默认情况下，作业应用固定在全局策略中，即使当前，你也看不到全局策略中列出了该应用。 它将是团队客户端上的固定应用列表中的第四个应用。

## <a name="create-a-custom-app-setup-policy"></a>创建自定义应用设置策略

你可以使用 Microsoft 团队管理中心创建自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"。
2. 单击“添加”****。
    ![显示 "添加应用设置策略" 页面的屏幕截图](media/app-setup-policies-add.png)
3. 输入策略的名称和说明。
4. 打开或关闭 "**上载自定义应用程序**"，具体取决于是否希望允许用户将自定义应用程序上载到团队。 如果 "[组织范围内的应用设置](manage-apps.md#manage-org-wide-app-settings)" 中的 "**允许第三方应用**" 处于关闭状态，则不能更改此设置。
5. 打开或关闭 "**允许用户固定**"，具体取决于是否希望让用户通过将应用固定到应用栏来对其应用栏进行个性化设置。
6. 若要为用户安装应用 **（在预览中）**，请执行下列操作：

    1. 在 "**已安装的应用**" 下，单击 "**添加应用**"。
    2. 在 "**添加已安装的应用**" 窗格中，搜索你希望在用户启动团队时为用户自动安装的应用。 你还可以按应用权限策略筛选应用。 选择应用列表后，单击 "**添加**"。

        ![显示 "添加已安装的应用" 窗格的屏幕截图](media/app-setup-policies-add-installed-apps.png)

7. 若要固定应用，请执行下列操作：

    1. 在 "**固定应用**" 下，单击 "**添加应用程序**"。
    2. 在 "**添加固定的应用**" 窗格中，搜索要添加的应用，然后单击 "**添加**"。 你还可以按应用权限策略筛选应用。 选择要固定的应用列表后，单击 "**添加**"。

         ![显示 "添加固定应用" 窗格的屏幕截图](media/app-setup-policies-add-apps.png)

    3. 按希望在团队中显示的顺序排列应用，然后单击 "**保存**"。

        ![显示 "固定的应用" 部分的屏幕截图](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>编辑应用设置策略

你可以使用 Microsoft 团队管理中心编辑策略，包括全局（组织范围默认）策略和你创建的自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 在此处进行所需的更改。
4. 单击“**保存**”。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>向用户分配自定义应用设置策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>常见问题

### <a name="working-with-app-setup-policies"></a>使用应用设置策略

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft 团队管理中心中包括哪些内置应用设置策略？

- **全局（组织范围默认值）**：此默认策略适用于你组织中的所有用户，除非你分配其他策略。 编辑全局策略以固定对你的用户最重要的应用。
- **FirstLineWorker**：此政策适用于一线工作者。 你可以将其分配给你的组织中的一线工作人员。 请务必知道，例如你创建的自定义策略，你必须将策略分配给用户才能使设置处于活动状态。 有关详细信息，请转到本文的 "向[用户分配自定义应用设置策略](#assign-a-custom-app-setup-policy-to-users)" 部分。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>为什么我无法在 "添加固定的应用" 窗格中找到应用？

并非所有应用都可以通过应用设置策略固定到团队。 某些应用可能不支持此功能。 若要查找可固定的应用，请在 "**添加固定的应用**" 窗格中搜索该应用。 具有个人作用域（静态选项卡）和机器人的选项卡可以固定到团队桌面客户端，并且这些应用在 "**添加固定应用**" 窗格中可用。

请记住，"团队" 应用商店将列出所有团队应用，而 "**添加固定的应用**" 窗格仅包括可通过策略固定到团队的应用。 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是教育版管理员的团队。我需要了解有关团队教育版中的应用设置策略的哪些信息？

"呼叫" 应用在教育版团队中不可用。 创建新的自定义应用设置策略时，将在应用列表中显示调用应用。 但是，应用不会固定到团队客户端和团队，教育用户将看不到团队中的 "调用" 应用。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>可以向策略添加多少个固定的应用？

必须将两个应用中的至少一个应用固定到团队移动客户端（iOS 和 Android）。 如果策略的应用少于两个，则移动客户端不会反映策略设置，而是将继续使用现有配置。

对于可添加到策略的固定应用的数量没有限制。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>策略更改需要多长时间才能生效？

编辑或分配策略后，可能需要几个小时才能使更改生效。

### <a name="user-experience"></a>用户体验

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>用户如何能够查看团队中的所有固定应用？

若要查看为用户固定的所有应用，用户可能需要执行以下操作，具体取决于已安装应用的数量以及其团队客户端窗口的大小。

|团队桌面客户端 |团队移动客户端 |
|---------|---------|
|在团队侧面的应用栏中，单击 **.。。更多应用**。| 在团队底部附近的应用栏中，向上轻扫。|
|![显示团队桌面客户端中的更多应用的屏幕截图](media/app-setup-policies-desktop-more-apps.png)<br>   |![在团队移动客户端中显示更多应用的屏幕截图](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>我需要了解有关团队移动体验的哪些信息？

团队移动客户端（iOS 和 Android）目前不支持带有静态选项卡的个人应用。 根据策略中设置的应用，固定到团队桌面客户端的应用可能不会显示在团队移动客户端中。 在移动客户端上，个人机器人仍将显示在聊天中。

通过团队移动客户端，用户将看到核心团队应用（如活动、聊天和团队），并且你可以固定 Microsoft 的一些第三方应用，例如倒班。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>用户是否可以更改通过策略固定的应用顺序？

如果启用了 "**允许用户固定**" 选项，用户可以更改团队桌面和移动客户端上的固定应用的顺序。 用户无法更改团队 web 客户端上的固定应用的顺序。

#### <a name="does-user-pinning-take-precedence"></a>用户固定是否优先？

如果分配给用户的应用设置策略被更改为阻止用户应用固定，团队会删除固定到应用栏的任何应用。 如果随后将策略更改为允许用户应用固定，则用户必须重新固定其以前固定的应用。

### <a name="custom-teams-apps"></a>自定义团队应用

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>我的组织构建了一个自定义团队应用，并已将其发布到 AppSource 或租户应用目录，但当应用固定到团队中的应用栏时，应用图标不会按预期显示。 如何解决此问题？

在提交应用之前，请确保遵循徽标指南。 若要了解详细信息，请参阅[卖方仪表板提交清单](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。 

## <a name="related-topics"></a>相关主题

[Teams 中适用于应用的管理设置](admin-settings.md)

[向团队中的用户分配策略](assign-policies.md)
