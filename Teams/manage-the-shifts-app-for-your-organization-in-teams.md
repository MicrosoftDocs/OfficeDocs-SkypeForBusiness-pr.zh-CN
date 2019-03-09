---
title: 在 Microsoft Teams 中为组织管理 Shifts 应用
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何设置和管理组织中的 firstline 工作者团队中的班次应用程序。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cae03a4388a1555d7a2cc608532fd84a7587678f
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494122"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理 Shifts 应用

> [!IMPORTANT]
> 有效 2019 年 10 月 1，，Microsoft StaffHub 将要停用。 我们正在构建 StaffHub 功能，包括时间表和任务管理功能，向 Microsoft 团队。 Firstline 工作人员的其他功能将推出向工作组随着时间的推移。 若要了解详细信息，请参阅[Microsoft StaffHub 要停用](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0)。  

## <a name="overview-of-shifts"></a>班次的概述
引进应用程序中的 Microsoft 团队保持 firstline 工作者连接和同步。它是移动首先生成 fast 和有效时间管理和团队的通信。 引进允许 firstline 工作者和经理使用其移动设备管理计划并保持联系。 

- 管理员创建、 更新和管理团队 shift 计划。 他们可以向一个人发送邮件 （"没有防泼上讲席"） 或整个团队 （"区域 GM 到达 20 分钟"）。 他们还可以发送策略文档、 新闻公告和视频。 
- 员工查看其即将开始的引进、 可以查看其他还有谁已安排在一天、 请求交换或提供 shift 键，并关闭请求的时间。 

务必要了解的引进当前不支持来宾用户。 这意味着来宾团队无法添加到或团队中开启来宾访问时，使用 shift 计划。 

## <a name="availability-of-shifts"></a>班次的可用性

引进可用于所有 Office 365 订阅包括团队，与几个例外。 例外情况是美国政府云社区 (GCC) 和团队免费。 Office 365 美国政府引进不可或团队忙产品。

进一步了解许可团队，包括 Office 365 订阅的列表，包括团队，请参阅[Office 365 许可团队](Office-365-licensing.md)。

## <a name="location-of-shifts-data"></a>引进数据的位置

北美、 西欧和亚太地区中的数据中心中的 Azure 中当前存储引进数据。 有关存储数据的详细信息，请参阅[其中是我的数据](http://o365datacentermap.azurewebsites.net/)？

## <a name="set-up-shifts"></a>设置引进

### <a name="enable-or-disable-shifts-in-your-organization"></a>启用或禁用组织中的变化

默认情况下，为您的组织中的所有工作组用户启用引进。 您可以关闭或打开 Microsoft 365 管理中心中的组织的应用程序。

1. 登录到 Microsoft 365 管理中心，使用您的 Office 365 管理员帐户。
2. 转到**设置** > **服务 & 加载项** > **Microsoft 团队**。 
3. **租户范围的设置**下选择**应用程序**，然后在**默认应用程序**，清除或选择**班次**复选框，以关闭或打开应用程序。 

    ![默认应用程序部分的屏幕截图](media/firstline-worker-enable-disable-shifts.png "Microsoft 365 管理中心内，显示的应用程序，包括引进应用程序列表中的默认应用程序部分的屏幕截图")

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>使用 pin 引进向工作组到 FirstLineWorker 应用程序安装程序策略

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

应用程序设置策略允许您自定义团队以突出显示您的组织中的用户的最重要的应用程序。 在策略中设置的应用程序固定到应用程序栏&mdash;团队桌面客户端的一侧和底部的团队移动客户端的栏&mdash;其中用户可以快速、 轻松地访问它们。 
 
团队包括您可以分配给 firstline 工作者您的组织中的内置 FirstLineWorker 应用程序设置策略。 默认情况下，该策略包括活动、 引进、 聊天和调用应用程序。 

若要查看 FirstLineWorker 策略中，Microsoft 团队管理中心的左侧窗格中，转到**团队应用程序** > **应用程序设置策略**。

![Microsoft 团队管理中心中的 FirstLineWorker 应用程序设置策略的屏幕截图](media/firstline-worker-app-setup-policy.png "Microsoft 团队管理中心中的 FirstLineWorker 应用程序设置策略的屏幕截图")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>将 FirstLineWorker 策略分配给各个用户

1. 在 Microsoft 团队管理中心的左侧导航窗格中，转到**用户**，，然后单击用户。
2. 旁边**分配策略**，选择**编辑**。
3. **团队应用程序设置策略**，下选择**FirstLineWorker**，，然后选择**保存**。

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a>将 FirstLineWorker 应用程序安装策略分配给组中的用户

通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块 Skype，可以向组中，如安全组的用户分配 FirstLineWorker 应用程序设置策略。 有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell Overview](teams-powershell-overview.md)。

本示例中，我们为 Contoso Firstline 工作组组中的所有用户分配 FirstLineWorker 应用程序设置策略。

> [!NOTE]
> 请确保您首次[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块的 Skype。

获取特定的组的 GroupObjectId。
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
获取指定组的成员。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
组中的所有用户都分配 FirstLineWorker 应用程序设置策略。
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
根据组中成员的数目，此命令可能需要几分钟才能执行。

## <a name="related-topics"></a>相关主题
- [切换为 firstline 工作人员和管理员的帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)