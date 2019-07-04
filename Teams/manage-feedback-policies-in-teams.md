---
title: 管理 Microsoft 团队中的反馈策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用反馈策略控制组织中的团队用户是否可以向 Microsoft 提交有关团队的反馈。
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540950"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的反馈策略

[!INCLUDE [preview-feature](includes/preview-feature.md)]

用户可通过转到**** > 团队客户端**提供反馈**, 向 Microsoft 发送有关团队的意见和建议。 我们正在不断改进团队体验, 我们将使用此反馈提高团队的能力。

![团队中的 "提供反馈" 选项的屏幕截图](media/manage-feedback-policies-in-teams-give-feedback.png)

通过 "**提供反馈**" 发送的数据在您的 Office 365 协议下被视为 "支持数据", 包括其他人被视为 "客户数据" 或 "个人资料" 的信息。

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>设置用户是否可以向 Microsoft 发送有关团队的反馈

作为管理员, 你可以控制你的组织中的用户是否可以向 Microsoft 发送有关团队的反馈。 默认情况下, 组织中的所有用户都会自动分配全局 (组织范围的默认) 策略, 并且在策略中启用该功能。 例外情况是团队参与教育, 其中为教师启用了该功能, 并为学生禁用了该功能。

你可以编辑全局策略, 也可以创建并分配自定义策略。 如果向用户分配了自定义策略, 则该策略将应用于用户。 如果未向用户分配自定义策略, 则全局策略将应用于该用户。 编辑全局策略或分配策略后, 所做的更改可能需要长达24小时才能生效。

例如, 你希望允许组织中的所有用户发送反馈中新员工以外的反馈。 在这种情况下, 你将创建一个自定义策略来关闭该功能, 并将其分配给新的员工。 组织中的所有其他用户将在启用该功能的情况中获得全局策略。  

使用**CsTeamsFeedbackPolicy** cmdlet 创建自定义策略和**CsTeamsFeedbackPolicy** cmdlet 以将其分配给一个或多个用户或用户组, 如安全组或通讯组。 

将**userInitiatedMode**参数设置为 "**已启用**", 以允许分配了该策略的用户提供反馈。 将参数设置为 "**已禁用**" 将关闭该功能, 并且分配了该策略的用户没有提供反馈的选项。

## <a name="create-a-custom-feedback-policy"></a>创建自定义反馈策略

在此示例中, 我们创建了一个名为 "新员工反馈" 策略的反馈策略, 并关闭了提供反馈的功能。

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>分配自定义反馈策略

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>向用户分配自定义反馈策略

在此示例中, 我们将名为 "新建员工反馈" 策略的自定义策略分配给名为 "user1" 的用户。

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>向组中的用户分配自定义反馈策略

你可能希望将自定义反馈策略分配给已标识的多个用户。 例如, 你可能想要向安全组中的所有用户分配策略。

在此示例中, 我们将名为 "新员工反馈" 策略的自定义反馈策略分配给 Contoso 新员工组中的所有用户。  

获取特定组的 GroupObjectId。
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
获取指定组的成员。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
将组中的所有用户分配给特定的反馈策略。 在此示例中, 它是新员工反馈策略。
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
此命令可能需要几分钟才能执行, 具体取决于组中的成员数量。

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)