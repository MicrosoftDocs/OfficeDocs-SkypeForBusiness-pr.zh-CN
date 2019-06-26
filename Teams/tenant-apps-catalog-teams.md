---
title: 在 Microsoft 团队租户应用目录中发布应用
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: 有关在 Microsoft 团队租户应用目录中发布应用的指南。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d016fd1c341774115b9b68edafcc47a63e42b0d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221322"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>在 Microsoft 团队租户应用目录中发布应用
=======================================================

你可以使用 Microsoft 团队租户应用目录来测试和分配业务线应用程序到你的组织。

"团队租户应用" 目录使你可以分配专为你的组织构建的业务线应用程序, 以及你依赖于完成关键业务功能的业务线应用程序。

若要为你的组织发布应用, 请使用全局管理员凭据登录到团队客户端, 然后按照下面的说明进行操作。

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>从团队客户端发布租户应用目录中的应用

> [!NOTE]
> 你需要使用全局管理员凭据登录到 Microsoft 团队客户端, 以便为你的组织发布应用。

### <a name="get-a-teams-app-package"></a>获取团队应用包

团队应用包是使用[团队应用 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建的。 拥有应用程序包后, 即可将其添加到企业应用目录。 虽然租户中的所有用户都可以查看应用程序目录, 但目前只有全局管理员能够发布和管理它。 (最终, 团队管理员也将能够执行此操作。)

### <a name="go-to-the-tenant-apps-catalog"></a>转到租户应用目录

启动 Microsoft 团队客户端并使用全局管理员凭据登录。 从 "Microsoft 团队存储" 中, 选择为特定组织 (在本例中为 "Contoso") 指定的新分区。 您的组织中的用户可以查看目录中的应用, 并为他们所属的团队安装这些应用。

![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>将应用添加到租户应用目录

1. 在应用商店中, 选择 "上载**适用于 Contoso**的**自定义应用** > 上传"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image02.png)

    (您也可以选择 **"向我上载" 或 "我的团队**" (称为*旁加载*)。 旁加载使应用仅可供你的团队或你选择的团队使用。)

2. 导航到应用包并将其选中, 然后单击 "**打开**"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image03.png)

当你返回到租户应用目录时, 新的企业应用将位于此处。 请记住, 只有你和你的组织的成员才有权访问此应用程序目录。

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>更新租户应用目录中的应用

1. 从租户应用目录中, 选择 "**...**" 在要更新的应用的右上角。

2. 导航到已更新的应用包并将其选中, 然后单击 "**打开**"。

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image04.png)

该应用将被修改为版本2.0。 您也可以从此菜单中删除整个公司的应用。

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>使用 Office 365 管理门户管理租户应用目录

如果你有需要 bug 修复的应用, 你可以通过 Office 365 管理门户暂时禁用应用。 选择 "**设置** > **服务" & 加载项** > **Microsoft 团队**。 除了以前的设置, 现在还有一个专用于贵公司的应用的部分。 你可以选择要启用或禁用的应用。

![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image05.png)

禁用应用将阻止用户与应用交互, 而无需完全删除应用。 在企业中管理应用时, 这些控件可为你提供额外的灵活性和控制。
