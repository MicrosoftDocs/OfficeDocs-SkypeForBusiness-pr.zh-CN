---
title: 跨 Microsoft 365 管理对 Teams 应用的访问
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
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何跨Microsoft 365管理对 Teams 应用的访问。
ms.openlocfilehash: 4c6f12d6895bd9c11d240f460285d2aa8cf27cb4
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175866"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>跨 Microsoft 365 管理对 Teams 应用的访问

除了在 Teams 中工作的应用外，应用开发人员还可以增强其 Microsoft Teams 应用以在 Outlook 和 Office.com 上工作。 在增强后，最终用户可以在 Teams、Microsoft Outlook 和 Microsoft Office.com 上使用增强的应用。 目前，只有定向版本中的最终用户才能在 Teams、Outlook 和 Office.com 中查看和使用这些特定应用。 现有的 Teams 管理员体验适用于管理对这些应用的访问。 [消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)中提供了有关此更改的通知。 作为 Teams 管理员，你可以允许特定的最终用户使用增强的应用，或管理他们在 Teams、Outlook 和 Office.com 上对增强应用的访问权限。 Teams 管理员使用 Teams 管理中心来管理应用访问权限。

为了在 Outlook 和 Office.com 中使用，增强型应用将继续使用 Teams 中授予的现有权限。 增强型 [应用的权限没有变化](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs)。

下面是增强的应用列表：

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

可以使用以下方法控制最终用户对 Teams 应用的访问。 如果你是 Office 应用管理员，请联系全局管理员或 Teams 管理员来管理应用访问权限。

| 用于管理访问权限的选项 |门户|全局管理员|Teams 管理员|
|--|---|---|--|
| 只有目标版本中的最终用户才能访问新应用。 将用户移动到标准版本。 请参阅 [设置标准或定向发布选项](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Microsoft 365 管理中心 | 是 | 否 |
| 管理特定最终用户对新应用的访问权限。 请参阅 [“添加自定义权限策略](teams-app-permission-policies.md#create-a-custom-app-permission-policy) ”并将 [自定义策略分配给用户](policy-assignment-overview.md)。 | Teams 管理中心 | 是 | 是 |
| 管理组织中所有最终用户对新应用的访问权限。 请参阅 [“允许”或“阻止应用](manage-apps.md#allow-and-block-apps)”。 | Teams 管理中心 | 是 | 是 |

> [!NOTE]
> 建议使用 [“标准发布”选项](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 来管理最终用户访问权限。 其他选项会删除最终用户的访问权限，他们将无法再在 Teams 中使用现有应用。

> [!NOTE]
> 在 Outlook 和 Office 中安装了同一应用的现有市场内加载项的用户将继续使用该应用。 加载项不是 Teams 应用，Teams 管理员无法控制访问权限。

## <a name="see-also"></a>另请参阅

* [专为 Outlook 和 Office.com 推出预览版Microsoft 365而设计的 Microsoft Teams 应用](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [了解Microsoft 365中的管理员角色](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [关于 Outlook 加载项](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [开发人员如何扩展 Teams 应用以跨Microsoft 365工作](/microsoftteams/platform/m365-apps/overview)
