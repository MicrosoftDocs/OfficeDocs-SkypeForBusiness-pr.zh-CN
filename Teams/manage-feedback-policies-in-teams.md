---
title: 在 Microsoft Teams 中管理反馈策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用反馈策略来控制组织中 Teams 用户是否可以向 Microsoft 提交有关 Teams 的反馈。
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804692"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理反馈策略

[!INCLUDE [preview-feature](includes/preview-feature.md)]

您的组织中的用户可以直接从 Teams 桌面和 Web 客户端向 Microsoft 发送有关 Teams 的反馈，让我们了解我们的工作情况。 我们正在不断改进 Teams 体验，并使用此反馈来改进 Teams。

> [!NOTE]
> 反馈策略在 GCC、GCC High 或 DOD 部署中不可用。

**"提供反馈"功能**

用户可以通过在 Teams 中访问"帮助提供反馈"来向我们发送有关  >  Teams 的评论和建议。 根据 Microsoft  365 或 Office 365 协议，通过"提供反馈"发送的数据被视为"支持数据"，包括否则被视为"客户数据"或"个人数据"的信息。

![Teams 中"提供反馈"选项的屏幕截图](media/manage-feedback-policies-in-teams-give-feedback.png)

**调查**

用户还可以评价他们使用 Teams 的体验，并向我们发送他们给出的分级的详细信息。 此弹出式调查在 Teams 中时时向用户显示。 当用户单击 **通知中的** "提供反馈"时，将显示调查，供其完成。

![Teams 中调查通知和表单的屏幕截图](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>设置用户是否可以向 Microsoft 发送有关 Teams 的反馈

作为管理员，你可以控制你组织中用户是否可以通过"提供反馈"向 Microsoft 发送有关Teams 的反馈，以及他们是否会收到调查。 默认情况下，将自动为组织中的所有用户分配全局 (组织范围的默认) 策略，并且策略中已启用"提供反馈"功能与调查。 Teams 教育例外，其中的功能为教师启用，学生禁用。

可以编辑全局策略，也可以创建和分配自定义策略。 编辑全局策略或分配自定义策略后，可能需要几个小时更改才能生效。

例如，您希望允许您的组织中的所有用户通过"提供反馈"发送反馈并接收调查，但培训中的新员工除外。 在此方案中，请创建自定义策略以关闭这两项功能，并将其分配给新员工。 组织中所有其他用户在启用功能后获取全局策略。  

使用 PowerShell 管理反馈策略。 使用可在此处找到的 **New-CsTeamsFeedbackPolicy** cmdlet 创建自定义策略，使用 **Grant-CsTeamsFeedbackPolicy** cmdlet 将其分配给一个或多个用户或用户组，例如安全组或通讯组。 *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*

若要关闭并打开功能，请设置以下参数：

 - **提供反馈**：将 **userInitiatedMode** 参数设置为 **启用** ，以允许分配了策略的用户提供反馈。 将参数 **设置为禁用** 会关闭该功能，分配有策略的用户没有提供反馈的选项。
 - **Surveys：** 将 **receiveSurveysMode** 参数设置为 **启用** ，以允许分配了策略的用户接收调查。 若要让用户接收调查并允许他们选择退出，将参数设置为 **enabledUserOverride。** 在 Teams 中，用户可以转到"设置隐私"  >  并选择是否要参与调查。 将参数 **设置为禁用** 会关闭该功能，分配有策略的用户不会收到调查。

## <a name="create-a-custom-feedback-policy"></a>创建自定义反馈策略

本示例创建名为"新员工反馈策略"的反馈策略，并关闭通过"提供反馈"和调查 **提供** 反馈的能力。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>向用户分配自定义反馈策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

本示例将名为"新员工反馈策略"的自定义策略分配给名为 user1 的用户。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在 Teams 中向用户分配策略](assign-policies.md)