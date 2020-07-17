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
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="71bd1-103">管理 Microsoft 团队中的反馈策略</span><span class="sxs-lookup"><span data-stu-id="71bd1-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="71bd1-104">你的组织中的用户可以向 Microsoft 发送有关团队的反馈，让我们可以直接从团队桌面和 web 客户端中了解如何操作。</span><span class="sxs-lookup"><span data-stu-id="71bd1-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="71bd1-105">我们正在不断改进团队体验，我们将使用此反馈提高团队的能力。</span><span class="sxs-lookup"><span data-stu-id="71bd1-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="71bd1-106">**"提供反馈" 功能**</span><span class="sxs-lookup"><span data-stu-id="71bd1-106">**The Give feedback feature**</span></span>

<span data-ttu-id="71bd1-107">用户可通过**转到**  >  团队**提供反馈**来向我们发送有关团队的评论和建议。</span><span class="sxs-lookup"><span data-stu-id="71bd1-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="71bd1-108">通过 "**提供反馈**" 发送的数据被视为 "支持数据" （您的 Microsoft 365 或 Office 365 协议），其中包括将以其他方式被视为 "客户数据" 或 "个人资料" 的信息。</span><span class="sxs-lookup"><span data-stu-id="71bd1-108">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![团队中的 "提供反馈" 选项的屏幕截图](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="71bd1-110">**调查**</span><span class="sxs-lookup"><span data-stu-id="71bd1-110">**Surveys**</span></span>

<span data-ttu-id="71bd1-111">用户还可以对团队的体验进行评级，并向我们发送有关他们所提供的评级的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71bd1-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="71bd1-112">此弹出调查将在团队中的时间内显示给用户。</span><span class="sxs-lookup"><span data-stu-id="71bd1-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="71bd1-113">当用户单击通知中的 "**提供反馈**" 时，将显示调查以完成。</span><span class="sxs-lookup"><span data-stu-id="71bd1-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![团队中的调查通知和表单的屏幕截图](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="71bd1-115">设置用户是否可以向 Microsoft 发送有关团队的反馈</span><span class="sxs-lookup"><span data-stu-id="71bd1-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="71bd1-116">作为管理员，你可以控制你的组织中的用户是否可以通过**提供反馈**以及是否收到调查来向 Microsoft 发送有关团队的反馈。</span><span class="sxs-lookup"><span data-stu-id="71bd1-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="71bd1-117">默认情况下，组织中的所有用户都会自动分配全局（组织范围的默认）策略，并且在策略中启用 "**提供反馈**" 功能和 "调查"。</span><span class="sxs-lookup"><span data-stu-id="71bd1-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="71bd1-118">例外情况是团队教育版，其中为教师启用了功能并对学生禁用了这些功能。</span><span class="sxs-lookup"><span data-stu-id="71bd1-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="71bd1-119">你可以编辑全局策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="71bd1-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="71bd1-120">编辑全局策略或分配自定义策略后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="71bd1-120">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="71bd1-121">例如，你希望允许组织中的所有用户通过**提供反馈**并接收除培训新员工之外的调查来发送反馈。</span><span class="sxs-lookup"><span data-stu-id="71bd1-121">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="71bd1-122">在此方案中，创建自定义策略以关闭这两个功能，并将其分配给新的员工。</span><span class="sxs-lookup"><span data-stu-id="71bd1-122">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="71bd1-123">组织中的所有其他用户均会在启用功能的情况中获得全局策略。</span><span class="sxs-lookup"><span data-stu-id="71bd1-123">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="71bd1-124">使用 PowerShell 管理反馈策略。</span><span class="sxs-lookup"><span data-stu-id="71bd1-124">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="71bd1-125">使用**CsTeamsFeedbackPolicy** cmdlet （*可在[此处找到](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*）创建自定义策略和**授予 CsTeamsFeedbackPolicy** cmdlet 以将其分配给一个或多个用户或用户组，如安全组或通讯组。</span><span class="sxs-lookup"><span data-stu-id="71bd1-125">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="71bd1-126">要关闭并打开这些功能，请设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="71bd1-126">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="71bd1-127">**提供反馈**：将**userInitiatedMode**参数设置为 "**已启用**"，以允许分配了该策略的用户提供反馈。</span><span class="sxs-lookup"><span data-stu-id="71bd1-127">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="71bd1-128">将参数设置为 "**已禁用**" 将关闭该功能，并且分配了该策略的用户没有提供反馈的选项。</span><span class="sxs-lookup"><span data-stu-id="71bd1-128">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="71bd1-129">**调查**：将**receiveSurveysMode**参数设置为 "**已启用**"，以允许分配了该策略的用户接收调查。</span><span class="sxs-lookup"><span data-stu-id="71bd1-129">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="71bd1-130">若要让用户收到调查并允许他们选择退出，请将参数设置为 " **enabledUserOverride**"。</span><span class="sxs-lookup"><span data-stu-id="71bd1-130">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="71bd1-131">在团队中，用户可以转到 "**设置**  >  **隐私**" 并选择他们是否希望参与调查。</span><span class="sxs-lookup"><span data-stu-id="71bd1-131">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="71bd1-132">将参数设置为 "**禁用**" 将关闭该功能，并且分配了该策略的用户将不会收到调查。</span><span class="sxs-lookup"><span data-stu-id="71bd1-132">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="71bd1-133">创建自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="71bd1-133">Create a custom feedback policy</span></span>

<span data-ttu-id="71bd1-134">在此示例中，我们创建了一个名为 "新员工反馈" 策略的反馈策略，并关闭了**提供反馈和调查**的功能。</span><span class="sxs-lookup"><span data-stu-id="71bd1-134">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="71bd1-135">向用户分配自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="71bd1-135">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="71bd1-136">在此示例中，我们将名为 "新建员工反馈" 策略的自定义策略分配给名为 "user1" 的用户。</span><span class="sxs-lookup"><span data-stu-id="71bd1-136">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="71bd1-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="71bd1-137">Related topics</span></span>

- [<span data-ttu-id="71bd1-138">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="71bd1-138">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="71bd1-139">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="71bd1-139">Assign policies to your users in Teams</span></span>](assign-policies.md)