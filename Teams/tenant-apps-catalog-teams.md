---
title: 在 Microsoft 团队租户应用目录中发布应用
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: 有关在 Microsoft 团队租户应用目录中发布应用的指南。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 547461cee1b172fccf9fe021347cff36ba8a9d79
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708228"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>在 Microsoft 团队租户应用目录中发布应用
=======================================================

你可以使用 Microsoft 团队租户应用目录来测试和分配业务线应用程序到你的组织。

"团队租户应用" 目录使你可以分配专为你的组织构建的业务线应用程序，以及你依赖于完成关键业务功能的业务线应用程序。

若要为你的组织发布应用，请使用具有全局管理员或团队服务管理员角色的帐户登录团队客户端，然后按照下面的说明进行操作。

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>从团队客户端发布租户应用目录中的应用

> [!NOTE]
> 你需要使用已启用全局管理员或团队服务管理员角色的帐户登录到 Microsoft 团队客户端，以便为你的组织发布应用。 了解有关[使用管理员角色管理团队](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)的详细信息。

### <a name="get-a-teams-app-package"></a>获取团队应用包

团队应用包是使用[团队应用 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建的。 拥有应用程序包后，即可将其添加到企业应用目录。 虽然租户中的所有用户都可以查看应用程序目录，但只有全局管理员和团队服务管理员有权发布和管理它。

### <a name="go-to-the-tenant-apps-catalog"></a>转到租户应用目录

启动 Microsoft 团队客户端并使用全局或团队服务管理员凭据登录。 选择应用左侧的 "**应用**"，然后选择为特定组织指定的新分区（在本例中为 "Contoso"）。 您的组织中的用户可以查看目录中的应用，并为他们所属的团队安装这些应用。

![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>将应用添加到租户应用目录

1. 在 "**应用**" 页面上，选择 "上载**适用于 Contoso**的**自定义应用** > 上传"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image02.png)

    （您也可以选择 **"向我上载" 或 "我的团队**" （称为*旁加载*）。 旁加载使应用仅可供你的团队或你选择的团队使用。）

2. 导航到应用包并将其选中，然后单击 "**打开**"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image03.png)

当你返回到租户应用目录时，新的企业应用将位于此处。 请记住，只有你和你的组织的成员才有权访问此应用程序目录。

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>更新租户应用目录中的应用

1. 从租户应用目录中，选择 "**...**" 在要更新的应用的右上角。

2. 导航到已更新的应用包并将其选中，然后单击 "**打开**"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image04.png)

该应用将被修改为版本2.0。 您也可以从此菜单中删除整个公司的应用。

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>使用 Office 365 管理门户管理租户应用目录

如果你有需要 bug 修复的应用，你可以通过 Microsoft 365 管理中心临时禁用应用 >**团队管理中心** > **团队应用** > **权限策略** > <策略名称，例如 "全局（组织范围默认）" >**租户应用**> 阻止特定应用并允许所有其他应用，并将你的应用添加到列表。

![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image05.png)

禁用应用将阻止用户与应用交互，而无需完全删除应用。 在企业中管理应用时，这些控件可为你提供额外的灵活性和控制。
