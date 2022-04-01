---
title: 管理对Teams应用的访问权限Microsoft 365
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 管理跨 Teams 应用的访问权限Microsoft 365。
ms.openlocfilehash: a9a0eb67323874e725510342e1e6810dcc5c0b0d
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592997"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>管理对Teams应用的访问权限Microsoft 365

应用开发人员可以增强其Microsoft Teams应用，以在 Outlook 和 Office.com 上工作，以及使用 Teams。 在增强后，最终用户可以在 Teams、Microsoft Outlook 和 Microsoft Office.com 上使用增强的应用。 目前，只有目标版本中的最终用户可以在 Teams、Outlook 和 Office.com 中查看和使用这些特定应用。 现有Teams管理体验适用于管理这些应用的访问权限。 消息中心提供有关此更改 [的通知](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)。 作为Teams管理员，您可以允许特定最终用户使用增强的应用，或者管理他们对 Teams、Outlook 和 Office.com 中增强应用的访问权限。 Teams管理员使用 Teams 管理中心管理应用访问权限。

为了在 Outlook 和 Office.com 中使用，增强的应用将继续使用在 Teams 中授予的现有Teams。 增强 [的应用的权限没有变化](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs)。

下面是增强的应用列表：

* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)

可以使用以下方法控制最终用户对 Teams 应用的访问权限。 如果你是应用管理员，Office全局管理员或Teams管理应用访问权限。

| 用于管理访问权限的选项 |门户|全局管理员|Teams管理员|
|--|---|---|--|
| 只有定向版本中的最终用户可以访问新应用。 将用户移动到标准版本。 请参阅 [设置标准或定向发布选项](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 管理中心 | 是 | 否 |
| 管理特定最终用户对新应用的访问权限。 请参阅[添加自定义权限策略](teams-app-permission-policies.md#create-a-custom-app-permission-policy)[并将自定义策略分配给用户](policy-assignment-overview.md)。 | Teams管理中心 | 是 | 是 |
| 管理组织中所有最终用户对新应用的访问权限。 请参阅 [允许或阻止应用](manage-apps.md#allow-and-block-apps)。 | Teams管理中心 | 是 | 是 |

> [!NOTE]
> 建议使用" [标准发布"选项](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 来管理最终用户访问权限。 其他选项将删除最终用户访问权限，他们将不再能够使用 Teams。

> [!NOTE]
> 在 Outlook 和 Office 中安装了同一应用的现有市场内加载项的用户将继续使用该应用。 加载项不可用于Teams，Teams管理员无法控制访问权限。

## <a name="see-also"></a>另请参阅

* [Microsoft Teams应用，Microsoft 365预览版Outlook Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [了解管理员角色Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [关于Outlook加载项](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [开发人员如何Teams应用以跨平台Microsoft 365](/microsoftteams/platform/m365-apps/overview)
