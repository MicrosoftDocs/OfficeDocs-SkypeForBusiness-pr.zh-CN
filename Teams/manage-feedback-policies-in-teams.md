---
title: 管理反馈策略Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: heprecel
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
description: 了解如何使用反馈策略来控制Teams用户是否可以向 Microsoft Teams反馈。
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656718"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>管理反馈策略Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

您的组织中的用户可以直接从桌面Teams Web 客户端内部向 Microsoft 发送有关Teams反馈，让我们了解我们的工作。 我们正在不断改进用户体验，Teams反馈来改进Teams体验。

> [!NOTE]
> 反馈策略在高级、GCC GCC DOD 部署中不可用。

**"提供反馈"功能**

用户可以通过访问"帮助"在 Teams 中提供反馈，向我们发送有关Teams和建议  >  。 通过"**提供反馈**"发送的数据Microsoft 365或Office 365协议下的"支持数据"，包括可能被视为"客户数据"或"个人数据"的信息。

!["提供反馈"选项的屏幕截图Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**调查**

用户还可以评价他们使用 Teams并向我们发送他们给出的分级的详细信息。 此弹出式调查会实时向用户显示Teams。 当用户在通知 **中选择"提供** 反馈"时，将显示调查供其完成。

![调查通知和表单Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>设置用户是否可以向 Microsoft Teams反馈

作为管理员，您可以控制您的组织中的用户是否可以通过"提供反馈"Teams Microsoft 发送有关用户反馈，以及他们是否收到调查。 默认情况下，将自动为组织中的所有用户分配全局 (组织范围的默认) 策略，并且"提供反馈"功能与调查在策略中启用。 教育Teams例外，其中功能为教师启用，学生禁用。

可以编辑全局策略，也可以创建和分配自定义策略。 编辑全局策略或分配自定义策略后，可能需要几个小时更改才能生效。

例如，您希望允许组织中的所有用户通过提供反馈发送反馈并接收调查，但培训中的新员工除外。 在此方案中，请创建自定义策略来关闭这两项功能，并将其分配给新员工。 组织中所有其他用户在启用功能后获取全局策略。  

使用 PowerShell 管理反馈策略。 使用 **New-CsTeamsFeedbackPolicy** cmdlet（可在此处找到）创建自定义策略。 *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* 使用 **Grant-CsTeamsFeedbackPolicy** cmdlet 将其分配给一个或多个用户或用户组，例如安全组或通讯组。 使用 **Set-CsTeamsFeedbackPolicy** 设置特定标志。

若要关闭并打开功能，请设置以下参数：

 - **提供反馈**：将 **userInitiatedMode** 参数设置为 **"启用** "，以允许分配有策略的用户提供反馈。 将 参数 **设置为 disabled** 会关闭该功能，并且分配有策略的用户没有提供反馈的选项。
 - **Surveys：** 将 **receiveSurveysMode** 参数设置为 **已启用** ，以允许分配了策略的用户接收调查。 若要让用户接收调查并允许他们选择退出，将 参数设置为 **enabledUserOverride**。 在Teams中，用户可以转到"设置  >  **隐私**"并选择是否要参与调查。 将 参数 **设置为 disabled** 会关闭该功能，分配有策略的用户不会收到调查。
 - **电子邮件**：使用 **AllowEmailCollection** 标志添加电子邮件字段。

## <a name="create-a-custom-feedback-policy"></a>创建自定义反馈策略

本示例创建一个称为"新员工反馈策略"的反馈策略，并关闭通过"提供反馈"和"调查" **提供** 反馈的能力。

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
- [向 Teams 中的用户分配策略](assign-policies.md)
