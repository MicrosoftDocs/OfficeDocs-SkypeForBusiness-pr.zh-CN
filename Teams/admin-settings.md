---
title: Microsoft Teams 中适用于应用的管理设置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: 了解如何在 Microsoft Teams 中允许和启用应用，包括侧向加载外部应用。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: da73768f69159c32543d0843139facc2b9ef4f9a
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706352"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams 中适用于应用的管理设置
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

应用程序是选项卡、 连接器、 自动程序或这三种，提供通过团队 （第一方应用程序和也称为应用程序默认） 或第三方 （也称为外部应用程序） 的任意组合。 在 Microsoft 365 管理中心，您可以启用和禁用默认应用程序和配置设置来控制外部应用程序。 这些设置允许您指定的外部应用程序允许的和不允许，新的外部应用程序行为，以及是否允许端加载应用程序。

 若要管理团队中的应用程序的管理设置，请转到 Microsoft 365 管理中心，并选择**设置** > **服务 & 加载项** > **Microsoft 团队**。 如果你已使用 Office 365 管理员身份登录，单击此链接应该能访问相应位置：

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

要了解有关应用的管理员设置的详细信息，请观看以下视频： 
 
|  |  |
|---------|---------|
| 管理 Microsoft Teams 中的应用体验   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>在 Teams 中允许外部应用

默认情况下，启用“**在 Microsoft Teams 中允许外部应用**”，并选中所有应用。  如果要关闭此设置，则会禁用所有外部第三方应用程序。 

## <a name="enable-new-external-apps-by-default"></a>默认启用新的外部应用

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophy: 最佳实践：单独管理外部应用 
 
要开启一些应用（并关闭其他应用），请关闭“**允许侧向加载外部应用**”。 然后关闭你不希望用户使用的任何应用。 可选：关闭“**默认启用新的外部应用**”（如果你希望控制新应用）。 

> [!NOTE]
> 默认应用程序，如构建的 Microsoft，不受**启用默认情况下的新外部应用程序**的设置。 默认情况下，当 Microsoft 发布的启用了新的应用程序。

启用此设置后，用户可以激活新的应用程序，只要它们会添加到团队应用程序目录。 要打开 Teams 应用目录，单击 Teams 底部的“**应用商店**”，然后单击“**应用**”。 如果您希望控制哪些应用程序，请关闭此设置。 当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。 

侧向加载是你通过直接将 zip 文件上载到团队来向 Teams 添加应用的方式。 利用侧向加载可以在开发应用时对其进行测试。 利用它还可以构建仅限内部使用的应用并与你的团队共享该应用，而无需将其提交至 Office 应用商店中的 Teams 应用目录。 

仅团队所有者或获得权限的成员可以向 Teams 中侧向加载应用。  

![扩展外部应用程序部分的屏幕截图。](media/teams-tenant-wide-settings-external-apps.png "显示外部应用程序扩展外部应用程序部分的屏幕截图")

## <a name="creating-and-uploading-app-packages"></a>创建和上载应用包 

若要了解有关应用程序的详细信息，请参阅[适用于团队的开发应用程序](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)。 



