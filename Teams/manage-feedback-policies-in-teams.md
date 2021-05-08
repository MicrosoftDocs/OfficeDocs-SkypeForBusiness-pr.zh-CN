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
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="15b5e-103">管理反馈策略Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15b5e-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="15b5e-104">您的组织中的用户可以直接从桌面Teams Web 客户端内部向 Microsoft 发送有关Teams反馈，让我们了解我们的工作。</span><span class="sxs-lookup"><span data-stu-id="15b5e-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="15b5e-105">我们正在不断改进用户体验，Teams反馈来改进Teams体验。</span><span class="sxs-lookup"><span data-stu-id="15b5e-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="15b5e-106">反馈策略在高级、GCC GCC DOD 部署中不可用。</span><span class="sxs-lookup"><span data-stu-id="15b5e-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="15b5e-107">**"提供反馈"功能**</span><span class="sxs-lookup"><span data-stu-id="15b5e-107">**The Give feedback feature**</span></span>

<span data-ttu-id="15b5e-108">用户可以通过访问"帮助"在 Teams 中提供反馈，向我们发送有关Teams和建议  >  。</span><span class="sxs-lookup"><span data-stu-id="15b5e-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="15b5e-109">通过"**提供反馈**"发送的数据Microsoft 365或Office 365协议下的"支持数据"，包括可能被视为"客户数据"或"个人数据"的信息。</span><span class="sxs-lookup"><span data-stu-id="15b5e-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

!["提供反馈"选项的屏幕截图Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="15b5e-111">**调查**</span><span class="sxs-lookup"><span data-stu-id="15b5e-111">**Surveys**</span></span>

<span data-ttu-id="15b5e-112">用户还可以评价他们使用 Teams并向我们发送他们给出的分级的详细信息。</span><span class="sxs-lookup"><span data-stu-id="15b5e-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="15b5e-113">此弹出式调查会实时向用户显示Teams。</span><span class="sxs-lookup"><span data-stu-id="15b5e-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="15b5e-114">当用户在通知 **中选择"提供** 反馈"时，将显示调查供其完成。</span><span class="sxs-lookup"><span data-stu-id="15b5e-114">When a user selects **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![调查通知和表单Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="15b5e-116">设置用户是否可以向 Microsoft Teams反馈</span><span class="sxs-lookup"><span data-stu-id="15b5e-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="15b5e-117">作为管理员，您可以控制您的组织中的用户是否可以通过"提供反馈"Teams Microsoft 发送有关用户反馈，以及他们是否收到调查。</span><span class="sxs-lookup"><span data-stu-id="15b5e-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="15b5e-118">默认情况下，将自动为组织中的所有用户分配全局 (组织范围的默认) 策略，并且"提供反馈"功能与调查在策略中启用。</span><span class="sxs-lookup"><span data-stu-id="15b5e-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy, and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="15b5e-119">教育Teams例外，其中功能为教师启用，学生禁用。</span><span class="sxs-lookup"><span data-stu-id="15b5e-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="15b5e-120">可以编辑全局策略，也可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="15b5e-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="15b5e-121">编辑全局策略或分配自定义策略后，可能需要几个小时更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="15b5e-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="15b5e-122">例如，您希望允许组织中的所有用户通过提供反馈发送反馈并接收调查，但培训中的新员工除外。</span><span class="sxs-lookup"><span data-stu-id="15b5e-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="15b5e-123">在此方案中，请创建自定义策略来关闭这两项功能，并将其分配给新员工。</span><span class="sxs-lookup"><span data-stu-id="15b5e-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="15b5e-124">组织中所有其他用户在启用功能后获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="15b5e-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="15b5e-125">使用 PowerShell 管理反馈策略。</span><span class="sxs-lookup"><span data-stu-id="15b5e-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="15b5e-126">使用 **New-CsTeamsFeedbackPolicy** cmdlet（可在此处找到）创建自定义策略。 *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*</span><span class="sxs-lookup"><span data-stu-id="15b5e-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy.</span></span> <span data-ttu-id="15b5e-127">使用 **Grant-CsTeamsFeedbackPolicy** cmdlet 将其分配给一个或多个用户或用户组，例如安全组或通讯组。</span><span class="sxs-lookup"><span data-stu-id="15b5e-127">Use the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> <span data-ttu-id="15b5e-128">使用 **Set-CsTeamsFeedbackPolicy** 设置特定标志。</span><span class="sxs-lookup"><span data-stu-id="15b5e-128">Use **Set-CsTeamsFeedbackPolicy** to set specific flags.</span></span>

<span data-ttu-id="15b5e-129">若要关闭并打开功能，请设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="15b5e-129">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="15b5e-130">**提供反馈**：将 **userInitiatedMode** 参数设置为 **"启用** "，以允许分配有策略的用户提供反馈。</span><span class="sxs-lookup"><span data-stu-id="15b5e-130">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="15b5e-131">将 参数 **设置为 disabled** 会关闭该功能，并且分配有策略的用户没有提供反馈的选项。</span><span class="sxs-lookup"><span data-stu-id="15b5e-131">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="15b5e-132">**Surveys：** 将 **receiveSurveysMode** 参数设置为 **已启用** ，以允许分配了策略的用户接收调查。</span><span class="sxs-lookup"><span data-stu-id="15b5e-132">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="15b5e-133">若要让用户接收调查并允许他们选择退出，将 参数设置为 **enabledUserOverride**。</span><span class="sxs-lookup"><span data-stu-id="15b5e-133">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="15b5e-134">在Teams中，用户可以转到"设置  >  **隐私**"并选择是否要参与调查。</span><span class="sxs-lookup"><span data-stu-id="15b5e-134">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="15b5e-135">将 参数 **设置为 disabled** 会关闭该功能，分配有策略的用户不会收到调查。</span><span class="sxs-lookup"><span data-stu-id="15b5e-135">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>
 - <span data-ttu-id="15b5e-136">**电子邮件**：使用 **AllowEmailCollection** 标志添加电子邮件字段。</span><span class="sxs-lookup"><span data-stu-id="15b5e-136">**Email**: Use the **AllowEmailCollection** flag to add an email field.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="15b5e-137">创建自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="15b5e-137">Create a custom feedback policy</span></span>

<span data-ttu-id="15b5e-138">本示例创建一个称为"新员工反馈策略"的反馈策略，并关闭通过"提供反馈"和"调查" **提供** 反馈的能力。</span><span class="sxs-lookup"><span data-stu-id="15b5e-138">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="15b5e-139">向用户分配自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="15b5e-139">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="15b5e-140">本示例将名为"新员工反馈策略"的自定义策略分配给名为 user1 的用户。</span><span class="sxs-lookup"><span data-stu-id="15b5e-140">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="15b5e-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="15b5e-141">Related topics</span></span>

- [<span data-ttu-id="15b5e-142">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="15b5e-142">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="15b5e-143">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="15b5e-143">Assign policies to your users in Teams</span></span>](assign-policies.md)
