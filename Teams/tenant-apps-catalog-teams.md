---
title: 在 Microsoft 团队租户应用目录中发布应用
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: 有关在 Microsoft 团队租户应用程序目录中发布应用的指南。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161611"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>在 Microsoft 团队租户应用目录中发布应用
=======================================================

你可以使用 Microsoft 团队租户应用目录来测试和分配业务线应用程序到你的组织。

团队租户应用程序目录允许你分配专为你的组织构建的业务线应用程序，并且你依赖于完成关键的业务功能。

若要为你的组织发布应用，请使用具有全局管理员或团队服务管理员角色的帐户登录团队客户端，然后按照下面的步骤操作。

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>从团队客户端发布租户应用目录中的应用

> [!NOTE]
> 这些步骤介绍了如何使用团队客户端发布应用。 你还可以在 Microsoft 团队管理中心的 "**管理应用**" 页面上发布应用。 若要了解详细信息，请参阅[管理团队中的应用](manage-apps.md)。

### <a name="get-a-teams-app-package"></a>获取团队应用包

团队应用包是使用[团队应用 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建的。 拥有应用包后，即可将其添加到租户应用目录。 虽然您的组织中的所有用户都可以查看应用程序目录，但只有全局管理员和团队服务管理员能够发布和管理它。

### <a name="go-to-the-tenant-app-catalog"></a>转到租户应用目录

启动团队并使用全局或团队服务管理员凭据登录。 选择应用左侧的 "**应用**"，然后选择为特定组织指定的新分区（在本例中为 "Contoso"）。 您的组织中的用户可以查看目录中的应用，并为他们所属的团队安装这些应用。

![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>将应用添加到租户应用目录

1. 在 "**应用**" 页面上，选择 "上载**适用于 Contoso**的**自定义应用** > 上传"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image02.png)

    （您也可以选择 **"向我上载" 或 "我的团队**" （称为*旁加载*）。 旁加载使应用仅可供你的团队或你选择的团队使用。）

2. 导航到应用包并将其选中，然后单击 "**打开**"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image03.png)

当你返回到租户应用目录时，新的企业应用将位于此处。 请记住，只有你和你的组织的成员才有权访问此应用程序目录。

### <a name="update-an-app-in-the-tenant-app-catalog"></a>更新租户应用目录中的应用

1. 从租户应用程序目录中，选择 "**...**" 在要更新的应用的右上角。

2. 导航到已更新的应用包并将其选中，然后单击 "**打开**"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image04.png)

该应用将被修改为版本2.0。 您也可以从此菜单中删除整个公司的应用。

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>使用 Microsoft 团队管理中心管理租户应用目录

如果你有需要 bug 修复的应用，你可以暂时为应用权限策略中的用户禁用应用。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。
2. 选择要编辑的应用权限策略，然后单击 "**编辑**"。
3. 在 "**租户应用**" 下，选择 "**阻止特定应用并允许所有其他应用**"，然后添加要阻止的应用。

禁用应用会阻止用户与应用交互，而无需完全删除应用。 在组织中管理应用时，这些控件可为你提供额外的灵活性和控制。

若要了解详细信息，请参阅[管理团队中的应用权限策略](teams-app-permission-policies.md)。