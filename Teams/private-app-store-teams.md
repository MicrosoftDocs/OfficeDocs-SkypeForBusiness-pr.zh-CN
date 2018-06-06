---
title: 管理 Microsoft 团队专用应用程序商店
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: 用于管理中的 Microsoft 团队专用应用程序商店的应用程序的指南。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17a2a7e4be22878cf0625077b23fad388b38bc9e
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19576949"
---
<a name="manage-the-microsoft-teams-private-app-store"></a>管理 Microsoft 团队专用应用程序商店
============================================

> [!IMPORTANT]
> 此页介绍预发布功能，并包含在发布之前，可能下述更改的初步内容。 任何屏幕截图的占位符和外观可能不同于您所看到的内容。

您可以使用 Microsoft 团队专用应用程序商店以构建和分发到您的组织的业务线应用程序。 

Microsoft 团队专用应用程序商店允许您分发您生成专门针对您的组织的业务线应用程序和所依赖的完成向用户的关键业务功能。 
 
有两种方法来管理工作组专用应用程序存储区：
- 直接从团队客户端 
- 利用 Microsoft Graph Api （此方法尚不可用。） Cmdlet

## <a name="manage-the-teams-private-app-store-from-the-teams-client"></a>从工作组客户端管理团队专用应用程序商店

### <a name="get-a-teams-app-package"></a>获取团队应用程序包

使用[团队应用程序 Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio)创建团队应用程序包。 在应用程序包后，您可以将其添加到企业应用程序目录。 时为租户中的所有用户都可以都查看应用程序目录，只有管理员能够管理它。

### <a name="go-to-the-teams-private-app-store"></a>转到团队的专用应用程序商店

从 Microsoft 团队存储区中，选择用于组织特定 （在此示例中为 Contoso） 的名为新建部分。 您的组织中的用户可以在目录中查看应用程序，并安装到团队的成员。 

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-teams-private-app-store"></a>添加到团队的专用应用程序商店的应用程序

从存储区中，选择**上载自定义应用程序** > **上载 contoso**。

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image02.png)

（您还可以选择**上载我或我的团队**，该数据库称为 sideloading，使应用程序仅适用于您或您的所选团队。） 

导航到应用程序包并选择它。

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image03.png)

当您返回到您的应用程序目录时，就有新的企业应用程序。 请记住，只有您和您的组织的成员有权访问此应用程序目录。

### <a name="update-an-app-in-the-teams-private-app-store"></a>更新团队专用应用程序商店中的应用程序

1. 从您的应用程序目录中，选择"**...**" 在右上您要更新的应用程序。
2. 导航到更新的应用程序包并选择它。

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image04.png)

应用程序将为版本 2.0 进行了修订。 您还可以从该菜单整个公司的删除应用程序。

## <a name="manage-the-teams-private-app-store-by-using-cmdlets-and-microsoft-graph-apis"></a>使用 cmdlet 和 Microsoft Graph Api 管理团队专用应用程序商店

此方法尚不可用的预览。

## <a name="use-the-office-365-admin-portal-to-manage-private-apps"></a>使用 Office 365 管理门户管理专用应用程序

如果您有需要 bug 修补程序的应用程序，您可以临时禁用通过 Office 365 管理门户的应用程序。 除了前面的设置是，现在有部分专用于贵公司的应用程序。 您可以选择您想要启用或禁用的应用程序。

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image05.png)

这会阻止用户从与该应用程序，而不完全删除应用程序进行交互。 这些控件为管理员提供更大的灵活性和控制时您企业中的应用程序的管理。 


