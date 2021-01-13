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
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="835f1-103">在 Microsoft Teams 中管理反馈策略</span><span class="sxs-lookup"><span data-stu-id="835f1-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="835f1-104">您的组织中的用户可以直接从 Teams 桌面和 Web 客户端向 Microsoft 发送有关 Teams 的反馈，让我们了解我们的工作情况。</span><span class="sxs-lookup"><span data-stu-id="835f1-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="835f1-105">我们正在不断改进 Teams 体验，并使用此反馈来改进 Teams。</span><span class="sxs-lookup"><span data-stu-id="835f1-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="835f1-106">反馈策略在 GCC、GCC High 或 DOD 部署中不可用。</span><span class="sxs-lookup"><span data-stu-id="835f1-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="835f1-107">**"提供反馈"功能**</span><span class="sxs-lookup"><span data-stu-id="835f1-107">**The Give feedback feature**</span></span>

<span data-ttu-id="835f1-108">用户可以通过在 Teams 中访问"帮助提供反馈"来向我们发送有关  >  Teams 的评论和建议。</span><span class="sxs-lookup"><span data-stu-id="835f1-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="835f1-109">根据 Microsoft  365 或 Office 365 协议，通过"提供反馈"发送的数据被视为"支持数据"，包括否则被视为"客户数据"或"个人数据"的信息。</span><span class="sxs-lookup"><span data-stu-id="835f1-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Teams 中"提供反馈"选项的屏幕截图](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="835f1-111">**调查**</span><span class="sxs-lookup"><span data-stu-id="835f1-111">**Surveys**</span></span>

<span data-ttu-id="835f1-112">用户还可以评价他们使用 Teams 的体验，并向我们发送他们给出的分级的详细信息。</span><span class="sxs-lookup"><span data-stu-id="835f1-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="835f1-113">此弹出式调查在 Teams 中时时向用户显示。</span><span class="sxs-lookup"><span data-stu-id="835f1-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="835f1-114">当用户单击 **通知中的** "提供反馈"时，将显示调查，供其完成。</span><span class="sxs-lookup"><span data-stu-id="835f1-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Teams 中调查通知和表单的屏幕截图](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="835f1-116">设置用户是否可以向 Microsoft 发送有关 Teams 的反馈</span><span class="sxs-lookup"><span data-stu-id="835f1-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="835f1-117">作为管理员，你可以控制你组织中用户是否可以通过"提供反馈"向 Microsoft 发送有关Teams 的反馈，以及他们是否会收到调查。</span><span class="sxs-lookup"><span data-stu-id="835f1-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="835f1-118">默认情况下，将自动为组织中的所有用户分配全局 (组织范围的默认) 策略，并且策略中已启用"提供反馈"功能与调查。</span><span class="sxs-lookup"><span data-stu-id="835f1-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="835f1-119">Teams 教育例外，其中的功能为教师启用，学生禁用。</span><span class="sxs-lookup"><span data-stu-id="835f1-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="835f1-120">可以编辑全局策略，也可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="835f1-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="835f1-121">编辑全局策略或分配自定义策略后，可能需要几个小时更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="835f1-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="835f1-122">例如，您希望允许您的组织中的所有用户通过"提供反馈"发送反馈并接收调查，但培训中的新员工除外。</span><span class="sxs-lookup"><span data-stu-id="835f1-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="835f1-123">在此方案中，请创建自定义策略以关闭这两项功能，并将其分配给新员工。</span><span class="sxs-lookup"><span data-stu-id="835f1-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="835f1-124">组织中所有其他用户在启用功能后获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="835f1-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="835f1-125">使用 PowerShell 管理反馈策略。</span><span class="sxs-lookup"><span data-stu-id="835f1-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="835f1-126">使用可在此处找到的 **New-CsTeamsFeedbackPolicy** cmdlet 创建自定义策略，使用 **Grant-CsTeamsFeedbackPolicy** cmdlet 将其分配给一个或多个用户或用户组，例如安全组或通讯组。 *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*</span><span class="sxs-lookup"><span data-stu-id="835f1-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="835f1-127">若要关闭并打开功能，请设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="835f1-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="835f1-128">**提供反馈**：将 **userInitiatedMode** 参数设置为 **启用** ，以允许分配了策略的用户提供反馈。</span><span class="sxs-lookup"><span data-stu-id="835f1-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="835f1-129">将参数 **设置为禁用** 会关闭该功能，分配有策略的用户没有提供反馈的选项。</span><span class="sxs-lookup"><span data-stu-id="835f1-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="835f1-130">**Surveys：** 将 **receiveSurveysMode** 参数设置为 **启用** ，以允许分配了策略的用户接收调查。</span><span class="sxs-lookup"><span data-stu-id="835f1-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="835f1-131">若要让用户接收调查并允许他们选择退出，将参数设置为 **enabledUserOverride。**</span><span class="sxs-lookup"><span data-stu-id="835f1-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="835f1-132">在 Teams 中，用户可以转到"设置隐私"  >  并选择是否要参与调查。</span><span class="sxs-lookup"><span data-stu-id="835f1-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="835f1-133">将参数 **设置为禁用** 会关闭该功能，分配有策略的用户不会收到调查。</span><span class="sxs-lookup"><span data-stu-id="835f1-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="835f1-134">创建自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="835f1-134">Create a custom feedback policy</span></span>

<span data-ttu-id="835f1-135">本示例创建名为"新员工反馈策略"的反馈策略，并关闭通过"提供反馈"和调查 **提供** 反馈的能力。</span><span class="sxs-lookup"><span data-stu-id="835f1-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="835f1-136">向用户分配自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="835f1-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="835f1-137">本示例将名为"新员工反馈策略"的自定义策略分配给名为 user1 的用户。</span><span class="sxs-lookup"><span data-stu-id="835f1-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="835f1-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="835f1-138">Related topics</span></span>

- [<span data-ttu-id="835f1-139">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="835f1-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="835f1-140">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="835f1-140">Assign policies to your users in Teams</span></span>](assign-policies.md)