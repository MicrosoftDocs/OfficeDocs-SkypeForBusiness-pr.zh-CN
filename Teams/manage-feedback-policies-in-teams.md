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
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="15963-103">管理 Microsoft 团队中的反馈策略</span><span class="sxs-lookup"><span data-stu-id="15963-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="15963-104">用户可通过转到\*\*\*\* > 团队客户端**提供反馈**, 向 Microsoft 发送有关团队的意见和建议。</span><span class="sxs-lookup"><span data-stu-id="15963-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="15963-105">我们正在不断改进团队体验, 我们将使用此反馈提高团队的能力。</span><span class="sxs-lookup"><span data-stu-id="15963-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![团队中的 "提供反馈" 选项的屏幕截图](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="15963-107">通过 "**提供反馈**" 发送的数据在您的 Office 365 协议下被视为 "支持数据", 包括其他人被视为 "客户数据" 或 "个人资料" 的信息。</span><span class="sxs-lookup"><span data-stu-id="15963-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="15963-108">设置用户是否可以向 Microsoft 发送有关团队的反馈</span><span class="sxs-lookup"><span data-stu-id="15963-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="15963-109">作为管理员, 你可以控制你的组织中的用户是否可以向 Microsoft 发送有关团队的反馈。</span><span class="sxs-lookup"><span data-stu-id="15963-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="15963-110">默认情况下, 组织中的所有用户都会自动分配全局 (组织范围的默认) 策略, 并且在策略中启用该功能。</span><span class="sxs-lookup"><span data-stu-id="15963-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="15963-111">例外情况是团队参与教育, 其中为教师启用了该功能, 并为学生禁用了该功能。</span><span class="sxs-lookup"><span data-stu-id="15963-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="15963-112">你可以编辑全局策略, 也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="15963-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="15963-113">如果向用户分配了自定义策略, 则该策略将应用于用户。</span><span class="sxs-lookup"><span data-stu-id="15963-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="15963-114">如果未向用户分配自定义策略, 则全局策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="15963-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="15963-115">编辑全局策略或分配策略后, 所做的更改可能需要长达24小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="15963-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="15963-116">例如, 你希望允许组织中的所有用户发送反馈中新员工以外的反馈。</span><span class="sxs-lookup"><span data-stu-id="15963-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="15963-117">在这种情况下, 你将创建一个自定义策略来关闭该功能, 并将其分配给新的员工。</span><span class="sxs-lookup"><span data-stu-id="15963-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="15963-118">组织中的所有其他用户将在启用该功能的情况中获得全局策略。</span><span class="sxs-lookup"><span data-stu-id="15963-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="15963-119">使用**CsTeamsFeedbackPolicy** cmdlet 创建自定义策略和**CsTeamsFeedbackPolicy** cmdlet 以将其分配给一个或多个用户或用户组, 如安全组或通讯组。</span><span class="sxs-lookup"><span data-stu-id="15963-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="15963-120">将**userInitiatedMode**参数设置为 "**已启用**", 以允许分配了该策略的用户提供反馈。</span><span class="sxs-lookup"><span data-stu-id="15963-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="15963-121">将参数设置为 "**已禁用**" 将关闭该功能, 并且分配了该策略的用户没有提供反馈的选项。</span><span class="sxs-lookup"><span data-stu-id="15963-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="15963-122">创建自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="15963-122">Create a custom feedback policy</span></span>

<span data-ttu-id="15963-123">在此示例中, 我们创建了一个名为 "新员工反馈" 策略的反馈策略, 并关闭了提供反馈的功能。</span><span class="sxs-lookup"><span data-stu-id="15963-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="15963-124">分配自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="15963-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="15963-125">向用户分配自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="15963-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="15963-126">在此示例中, 我们将名为 "新建员工反馈" 策略的自定义策略分配给名为 "user1" 的用户。</span><span class="sxs-lookup"><span data-stu-id="15963-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="15963-127">向组中的用户分配自定义反馈策略</span><span class="sxs-lookup"><span data-stu-id="15963-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="15963-128">你可能希望将自定义反馈策略分配给已标识的多个用户。</span><span class="sxs-lookup"><span data-stu-id="15963-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="15963-129">例如, 你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="15963-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="15963-130">在此示例中, 我们将名为 "新员工反馈" 策略的自定义反馈策略分配给 Contoso 新员工组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="15963-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="15963-131">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="15963-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="15963-132">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="15963-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="15963-133">将组中的所有用户分配给特定的反馈策略。</span><span class="sxs-lookup"><span data-stu-id="15963-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="15963-134">在此示例中, 它是新员工反馈策略。</span><span class="sxs-lookup"><span data-stu-id="15963-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="15963-135">此命令可能需要几分钟才能执行, 具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="15963-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="15963-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="15963-136">Related topics</span></span>

- [<span data-ttu-id="15963-137">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="15963-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)