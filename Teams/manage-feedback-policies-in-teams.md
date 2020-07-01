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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用反馈策略控制组织中的团队用户是否可以向 Microsoft 提交有关团队的反馈。
ms.openlocfilehash: b489e574a1d1c2a2b1ac5faf69626e997dbbfaa9
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938481"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的反馈策略

[!INCLUDE [preview-feature](includes/preview-feature.md)]

你的组织中的用户可以向 Microsoft 发送有关团队的反馈，让我们可以直接从团队桌面和 web 客户端中了解如何操作。 我们正在不断改进团队体验，我们将使用此反馈提高团队的能力。

**"提供反馈" 功能**

用户可通过**转到**  >  团队**提供反馈**来向我们发送有关团队的评论和建议。 通过 "**提供反馈**" 发送的数据被视为 "支持数据" （您的 Microsoft 365 或 Office 365 协议），其中包括将以其他方式被视为 "客户数据" 或 "个人资料" 的信息。

![团队中的 "提供反馈" 选项的屏幕截图](media/manage-feedback-policies-in-teams-give-feedback.png)

**调查**

用户还可以对团队的体验进行评级，并向我们发送有关他们所提供的评级的详细信息。 此弹出调查将在团队中的时间内显示给用户。 当用户单击通知中的 "**提供反馈**" 时，将显示调查以完成。

![团队中的调查通知和表单的屏幕截图](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>设置用户是否可以向 Microsoft 发送有关团队的反馈

作为管理员，你可以控制你的组织中的用户是否可以通过**提供反馈**以及是否收到调查来向 Microsoft 发送有关团队的反馈。 默认情况下，组织中的所有用户都会自动分配全局（组织范围的默认）策略，并且在策略中启用 "**提供反馈**" 功能和 "调查"。 例外情况是团队教育版，其中为教师启用了功能并对学生禁用了这些功能。

你可以编辑全局策略，也可以创建并分配自定义策略。 编辑全局策略或分配自定义策略后，可能需要几个小时才能使更改生效。

例如，你希望允许组织中的所有用户通过**提供反馈**并接收除培训新员工之外的调查来发送反馈。 在此方案中，创建自定义策略以关闭这两个功能，并将其分配给新的员工。 组织中的所有其他用户均会在启用功能的情况中获得全局策略。  

使用 PowerShell 管理反馈策略。 使用**CsTeamsFeedbackPolicy** cmdlet （*可在[此处找到](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*）创建自定义策略和**授予 CsTeamsFeedbackPolicy** cmdlet 以将其分配给一个或多个用户或用户组，如安全组或通讯组。

要关闭并打开这些功能，请设置以下参数：

 - **提供反馈**：将**userInitiatedMode**参数设置为 "**已启用**"，以允许分配了该策略的用户提供反馈。 将参数设置为 "**已禁用**" 将关闭该功能，并且分配了该策略的用户没有提供反馈的选项。
 - **调查**：将**receiveSurveysMode**参数设置为 "**已启用**"，以允许分配了该策略的用户接收调查。 若要让用户收到调查并允许他们选择退出，请将参数设置为 " **enabledUserOverride**"。 在团队中，用户可以转到 "**设置**  >  **隐私**" 并选择他们是否希望参与调查。 将参数设置为 "**禁用**" 将关闭该功能，并且分配了该策略的用户将不会收到调查。

## <a name="create-a-custom-feedback-policy"></a>创建自定义反馈策略

在此示例中，我们创建了一个名为 "新员工反馈" 策略的反馈策略，并关闭了**提供反馈和调查**的功能。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>向用户分配自定义反馈策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

在此示例中，我们将名为 "新建员工反馈" 策略的自定义策略分配给名为 "user1" 的用户。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向团队中的用户分配策略](assign-policies.md)