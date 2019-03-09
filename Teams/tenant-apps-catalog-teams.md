---
title: 将应用发布到 Microsoft Teams 租户应用目录
author: ChuckEdmonson
ms.author: lolaj
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: 面向 Microsoft 团队租户的应用程序目录中发布应用程序的指南。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 282e5bab91d08ee3374eddeaa0fe4628fb6b5ac0
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494258"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a>将应用发布到 Microsoft Teams 租户应用目录
=======================================================

您可以使用 Microsoft 团队租户的应用程序目录以测试和分发到您的组织的业务线应用程序。 

团队租户的应用程序目录允许您分发您生成专门针对您的组织的业务线应用程序和所依赖的完成向用户的关键业务功能。 
 
登录到您的团队客户端使用全局管理员凭据和发布您的组织的应用程序。 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a>从工作组客户端租户的应用程序目录发布应用程序

注意： 您需要登录到 Microsoft 团队客户端使用您的全局管理员凭据发布您的组织的应用程序。

### <a name="get-a-teams-app-package"></a>获取团队应用程序包

使用[团队应用程序 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建团队应用程序包。 在应用程序包后，您可以将其添加到企业应用程序目录。 时为租户中的所有用户视图应用程序目录，当前仅全局管理员可以发布和管理它的功能。 （最终，团队 admins 都将能够执行此操作以及。）

### <a name="go-to-the-tenant-apps-catalog"></a>转到租户的应用程序目录

启动 Microsoft 团队客户端并使用全局管理员凭据登录。 从 Microsoft 团队存储区中，选择用于组织特定 （在此示例中为 Contoso） 的名为新建部分。 您的组织中的用户可以在目录中查看应用程序，并安装到团队的成员。 

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>将应用程序添加到租户的应用程序目录

从存储区中，选择**上载自定义应用程序** > **上载 contoso**。

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image02.png)

（您还可以选择**上载我或我的团队**，该数据库称为 sideloading，使应用程序仅适用于您或您的所选团队。） 

导航到应用程序包并选择它。

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image03.png)

当您返回到您的租户的应用程序目录中时，就有新的企业应用程序。 请记住，只有您和您的组织的成员有权访问此应用程序目录。

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>更新应用程序中租户的应用程序目录

1. 从租户的应用程序目录，选择"**...**" 在右上您要更新的应用程序。
2. 导航到更新的应用程序包并选择它。

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image04.png)

应用程序将为版本 2.0 进行了修订。 您还可以从该菜单整个公司的删除应用程序。

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>使用 Office 365 管理门户管理租户的应用程序目录

如果您有需要 bug 修补程序的应用程序，您可以临时禁用通过 Office 365 管理门户的应用程序。 除了前面的设置是，现在有部分专用于贵公司的应用程序。 您可以选择您想要启用或禁用的应用程序。

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image05.png)

这会阻止用户从与该应用程序，而不完全删除应用程序进行交互。 这些控件为管理员提供更大的灵活性和控制时您企业中的应用程序的管理。 


