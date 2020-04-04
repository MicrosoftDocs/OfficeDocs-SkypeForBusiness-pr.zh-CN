---
title: 管理你的组织的倒班应用
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在组织中的一线工作人员的团队中设置和管理倒班应用。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9298ed02c6b8559bdaf1e59c74a149a9d5164124
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141185"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理 Shifts 应用

> [!IMPORTANT]
> 2019年12月31日生效，Microsoft StaffHub 将停用。 我们正在将 StaffHub 功能构建到 Microsoft 团队中。 今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。 StaffHub 将停止为2019年12月31日的所有用户工作。 任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。 若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview-of-shifts"></a>倒班概述

Microsoft 团队中的 "移动" 应用让一线工作人员保持连接和同步。它首先构建了移动，为团队提供快速、有效的时间管理和沟通。 倒班让一线工作者和他们的经理使用自己的移动设备管理计划和保持联系。 

- 经理负责创建、更新和管理团队的倒班计划。 他们可以向一个人发送消息（"在地面上有溢出"）或整个团队（"区域 GM 在20分钟内送达"）。 他们还可以发送策略文档、新闻公告和视频。 
- 员工查看他们的即将到来的班次，可查看当天安排的其他人、请求交换或提供班次，以及请求下班时间。 

请务必知道当前班次不支持来宾用户。 这意味着在团队中启用来宾访问时，无法将团队中的来宾添加到或使用倒班计划。 

## <a name="availability-of-shifts"></a>倒班的可用性

倒班在所有企业版 Sku 可用，其中有团队可用。

## <a name="location-of-shifts-data"></a>倒班数据的位置

倒班数据当前存储在北美、西欧和亚太地区数据中心的 Azure 中。 有关存储数据的位置的详细信息，请参阅[我的数据在哪里](http://o365datacentermap.azurewebsites.net/)？

## <a name="set-up-shifts"></a>设置倒班

### <a name="enable-or-disable-shifts-in-your-organization"></a>启用或禁用组织中的班次

默认情况下，将为组织中的所有团队用户启用倒班。 你可以在 Microsoft 团队管理中心的 "[管理应用](../../manage-apps.md)" 页面上，关闭或打开组织级别的应用。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **管理应用**"。
2. 在应用列表中，执行下列操作之一：

    - 若要为你的组织关闭班次，请搜索 "倒班" 应用，选择它，然后单击 "**阻止**"。
    - 若要为你的组织启用倒班，请搜索 "倒班" 应用，选择它，然后单击 "**允许**"。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>启用或禁用组织中特定用户的班次

若要允许或阻止组织中的特定用户使用倒班，请确保在 "[管理应用](../../manage-apps.md)" 页面上为你的组织启用了班次，然后创建自定义应用权限策略并将其分配给这些用户。 若要了解详细信息，请参阅[管理团队中的应用权限策略](../../teams-app-permission-policies.md)。

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>使用 FirstlineWorker 应用设置策略固定对团队的倒班

应用设置策略允许你自定义团队，以突出显示你的组织中的用户最重要的应用。 策略中设置的应用将固定到应用程序栏，&mdash;应用栏位于团队桌面客户端和团队移动客户&mdash;端的底部，用户可在其中快速轻松地访问它们。 
 
团队包括一个内置的 FirstlineWorker 应用设置策略，可分配给你的组织中的一线工作人员。 默认情况下，该策略包括活动、班次、聊天和呼叫应用。 

若要查看 FirstlineWorker 策略，请在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **应用" 设置策略**。

![FirstlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft 团队管理中心中的 FirstlineWorker 应用设置策略的屏幕截图")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>将 FirstlineWorker 策略分配给单个用户

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。****
2. 在 "**分配的策略**" 旁边，选择 "**编辑**"。
3. 在 "**团队应用设置策略**" 下，选择 " **FirstlineWorker**"，然后选择 "**保存**"。

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a>将 FirstlineWorker 应用设置策略分配给组的用户成员

你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块，将 FirstlineWorker 应用设置策略分配给组的用户成员（如安全组）。 有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](../../teams-powershell-overview.md)。

在此示例中，我们将 FirstlineWorker 应用设置策略分配给 Contoso 一线团队组的所有用户成员。

> [!NOTE]
> 请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。

获取特定组的 GroupObjectId。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
获取指定组的成员。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
将 FirstlineWorker 应用设置策略分配给该组的所有用户成员。
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
此命令可能需要几分钟才能执行，具体取决于组中的成员数量。

## <a name="related-topics"></a>相关主题
- [倒班一线工作者的帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
