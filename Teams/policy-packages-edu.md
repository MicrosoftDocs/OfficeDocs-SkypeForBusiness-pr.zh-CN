---
title: 面向 EDU 管理员的 Microsoft Teams 策略和策略包
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Priority
search.appverid: MET150
description: 了解教育或 EDU 设置中的策略，以及如何在 Microsoft Teams 中使用和管理策略包。
ms.openlocfilehash: 8e024003957a295d56e26a46f473d543f2cb0ded
ms.sourcegitcommit: 02dd624d39a14f48b9d2463881605d2f051722e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2020
ms.locfileid: "44874420"
---
# <a name="teams-policies-and-policy-packages-for-education"></a><span data-ttu-id="c14ac-103">面向教育的 Teams 策略和策略包</span><span class="sxs-lookup"><span data-stu-id="c14ac-103">Teams Policies and Policy Packages for Education</span></span>

> [!NOTE]
> <span data-ttu-id="c14ac-104">有关 Microsoft Teams 中策略的更多信息，请查看[向 Microsoft Teams 中的用户分配策略](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c14ac-104">For the larger story on policies in Microsoft Teams, please review [Assign policies to your users in Microsoft Teams](assign-policies.md).</span></span>

<span data-ttu-id="c14ac-105">请务必注意，本文将介绍多种向 Teams 中的用户分配策略的方法。</span><span class="sxs-lookup"><span data-stu-id="c14ac-105">It's important to note this article will cover multiple ways to assign policies to users in Teams.</span></span>

- <span data-ttu-id="c14ac-106">手动分配给单个用户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-106">Manual assign to individual users.</span></span>
- <span data-ttu-id="c14ac-107">通过 PowerShell 批量分配给多个用户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-107">Bulk assigning via PowerShell to multiple users.</span></span>
- <span data-ttu-id="c14ac-108">将策略包分配给单个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-108">Assigning policy packages to individual or multiple users.</span></span>

<span data-ttu-id="c14ac-109">这些方法的优缺点取决于机构的个人需求。</span><span class="sxs-lookup"><span data-stu-id="c14ac-109">The advantages and disadvantages of these approaches come down to the institution's individual needs.</span></span>

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a><span data-ttu-id="c14ac-110">管理员：Microsoft Teams 策略管理入门</span><span class="sxs-lookup"><span data-stu-id="c14ac-110">Admins: Getting started with Microsoft Teams policy management</span></span>

<span data-ttu-id="c14ac-111">Microsoft Teams 的核心是使用户能够执行诸如参加会议或实时事件、聊天、拨打电话和使用应用之类的事情。</span><span class="sxs-lookup"><span data-stu-id="c14ac-111">Microsoft Teams, at its core, is about users being able to do things like go to meetings or live events, chat, make calls, and use apps.</span></span> <span data-ttu-id="c14ac-112">设置恰当的 Microsoft Teams 管理员策略是为 Teams 中的学生营造安全的学习环境的关键一步。</span><span class="sxs-lookup"><span data-stu-id="c14ac-112">And setting the right Microsoft Teams admin policies is a critical step in creating a safe learning environment for students within Teams.</span></span> <span data-ttu-id="c14ac-113">作为管理员，你可以使用策略来控制你的教育机构中的用户可以使用的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="c14ac-113">As an admin, you can use policies to control the Teams features that are available to users in your educational institute.</span></span>

<span data-ttu-id="c14ac-114">下面是你将在 Microsoft Teams 中找到的策略区域列表：</span><span class="sxs-lookup"><span data-stu-id="c14ac-114">Here's a list of the policy areas you will find in Microsoft Teams:</span></span>

- <span data-ttu-id="c14ac-115">会议</span><span class="sxs-lookup"><span data-stu-id="c14ac-115">Meetings</span></span>
- <span data-ttu-id="c14ac-116">实时事件</span><span class="sxs-lookup"><span data-stu-id="c14ac-116">Live events</span></span>
- <span data-ttu-id="c14ac-117">通话</span><span class="sxs-lookup"><span data-stu-id="c14ac-117">Calling</span></span>
- <span data-ttu-id="c14ac-118">消息传递</span><span class="sxs-lookup"><span data-stu-id="c14ac-118">Messaging</span></span>
- <span data-ttu-id="c14ac-119">Teams</span><span class="sxs-lookup"><span data-stu-id="c14ac-119">Teams</span></span>
- <span data-ttu-id="c14ac-120">应用权限</span><span class="sxs-lookup"><span data-stu-id="c14ac-120">App permissions</span></span>

:::image type="content" source="media/edu-admin-center-users.png" alt-text="应用了策略的用户的屏幕截图。":::

<span data-ttu-id="c14ac-122">使用管理员凭据登录后，可轻松地在 [ Microsoft Teams 管理中心](https://admin.teams.microsoft.com)中管理所有 Teams 策略。</span><span class="sxs-lookup"><span data-stu-id="c14ac-122">You can easily manage all Teams policies in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) by signing in with your admin credentials.</span></span>

### <a name="where-to-find-microsoft-teams-policies"></a><span data-ttu-id="c14ac-123">在哪里可以找到 Microsoft Teams 策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-123">Where to find Microsoft Teams policies</span></span>

<span data-ttu-id="c14ac-124">登录 Teams 管理中心后，可单击 Teams 管理中心左侧导航中的策略选项，转到需要管理的任何 Teams 区域的策略设置。</span><span class="sxs-lookup"><span data-stu-id="c14ac-124">Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage, by clicking on the policy option in the left hand navigation of the Teams admin center.</span></span> <span data-ttu-id="c14ac-125">我们提供了消息传递策略位置的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="c14ac-125">We've included a screenshot of the location of the messaging policies.</span></span>

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 管理中心中的消息策略位置。":::

### <a name="how-to-create-and-update-a-policy-definition"></a><span data-ttu-id="c14ac-127">如何创建和更新策略定义</span><span class="sxs-lookup"><span data-stu-id="c14ac-127">How to create and update a policy definition</span></span>

<span data-ttu-id="c14ac-128">在向用户分配策略之前，你需要首先通过 Teams 为每个功能区域添加和创建策略定义。</span><span class="sxs-lookup"><span data-stu-id="c14ac-128">Before you assign policies to your users, you need to first add and create your policy definitions for each capability area with Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c14ac-129">建议为学生和教师设置不同的策略定义。</span><span class="sxs-lookup"><span data-stu-id="c14ac-129">We recommend that you set different policy definitions for your students and educators.</span></span>

<span data-ttu-id="c14ac-130">默认情况下，将为每个新用户（学生或教师）分配每个功能区域的全局（组织范围默认）策略定义。</span><span class="sxs-lookup"><span data-stu-id="c14ac-130">By default, every new user (student or educator) will be assigned the Global (Org-wide default) policy definition for each capability area.</span></span> <span data-ttu-id="c14ac-131">建议按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c14ac-131">We recommend you follow these steps:</span></span>

1. <span data-ttu-id="c14ac-132">为每个 Teams 功能区域创建一个自定义策略定义，然后可以将其分配给教师（如果不这样做，则你对全局策略所做的任何更改都会限制教师，直到他们拥有自己的策略为止）。</span><span class="sxs-lookup"><span data-stu-id="c14ac-132">Create a custom policy definition for each Teams capability area that can then be assigned to your educators (without this, any changes you make to the Global policy will restrict educators until they have their own policy).</span></span>
1. <span data-ttu-id="c14ac-133">将教师分配给新的策略定义。</span><span class="sxs-lookup"><span data-stu-id="c14ac-133">Assign your educators to this new policy definition.</span></span>
1. <span data-ttu-id="c14ac-134">更新全局（组织范围默认）策略定义，然后将其分配给学生。</span><span class="sxs-lookup"><span data-stu-id="c14ac-134">Update the Global (Org-wide default) policy definition, then assign it to your students.</span></span>

<span data-ttu-id="c14ac-135">若要创建或编辑策略定义，请转到要使用的策略功能区域（例如，消息传递策略）。</span><span class="sxs-lookup"><span data-stu-id="c14ac-135">To create or edit policy definitions, go to the policy capability area you want to work in (for example, Messaging policies).</span></span> <span data-ttu-id="c14ac-136">如果想要创建新的自定义策略定义（将为针对教师创建的自定义策略定义执行此操作），请选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-136">Select **Add** if you want to create a new custom policy definition (which you'll do for the custom policy definition you create for educators).</span></span> <span data-ttu-id="c14ac-137">或者，若要更改现有策略定义，请选择“**编辑**”（如果选择为学生更新全局策略，则会执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="c14ac-137">Otherwise, to change an existing policy definition, then select **Edit** (which will be what you do if you choose to update the Global policy for students).</span></span>

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="消息传递策略部分的特写，可看到“添加”按钮。":::

<span data-ttu-id="c14ac-139">无论选择添加还是编辑策略定义，你都将进入一个视图，其中列出了与此策略区域相关的所有策略选项。</span><span class="sxs-lookup"><span data-stu-id="c14ac-139">Whether you choose to add or edit a policy definition, you're brought to a view that lists all the policy options related to this policy area.</span></span> <span data-ttu-id="c14ac-140">使用此列表可选择要在策略定义中设置的值。</span><span class="sxs-lookup"><span data-stu-id="c14ac-140">Use this list to select what values you want set in your policy definition.</span></span>

![包含与所选策略区域相关的策略选项的页面。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> <span data-ttu-id="c14ac-142">离开页面前，请不要忘记选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-142">Don’t forget to select **Save** before you leave the page.</span></span>

### <a name="how-to-assign-a-policy-definition-to-a-user"></a><span data-ttu-id="c14ac-143">如何向用户分配策略定义</span><span class="sxs-lookup"><span data-stu-id="c14ac-143">How to assign a policy definition to a user</span></span>

> [!NOTE]
> <span data-ttu-id="c14ac-144">分配策略定义时，可能需要一段时间才能传播给所有用户和客户端。</span><span class="sxs-lookup"><span data-stu-id="c14ac-144">Assigning a policy definition may take a while to propagate out to all the users and clients.</span></span> <span data-ttu-id="c14ac-145">首次在 Azure/M365 中创建用户帐户时，以及每当有新学生加入教育机构时，你都可能需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c14ac-145">You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.</span></span>

<span data-ttu-id="c14ac-146">创建或更新策略定义后，可通过在策略页面中选择“**管理用户**”，搜索所需的用户，然后应用策略，将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-146">Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** in policy page, searching for the desired user then applying the policy.</span></span>

![消息传递策略页面顶部右侧的“管理用户”面板。](media/edu-manage-users-pane.png)

<span data-ttu-id="c14ac-148">你还可以通过导航到“用户”，选择要为其更新策略的用户，选择“策略”，然后选择“编辑”，将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-148">You can also assign a policy to a user by navigating to Users, selecting the user you wish to update policies for, selecting Policies, then Edit.</span></span> <span data-ttu-id="c14ac-149">在此处，可以选择对于每个功能区域要分配给用户的策略定义。</span><span class="sxs-lookup"><span data-stu-id="c14ac-149">From there, you can select the policy definition you’d like to use assign to the user for each capability area.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c14ac-150">如果你是大型教育机构的一员，则可能很难利用 Microsoft Teams 管理门户体验为每个用户设置策略。</span><span class="sxs-lookup"><span data-stu-id="c14ac-150">If you're part of a large educational institute, using the Microsoft Teams admin portal experience to set policies for each user may be difficult.</span></span> <span data-ttu-id="c14ac-151">最好通过 PowerShell 批量分配策略。</span><span class="sxs-lookup"><span data-stu-id="c14ac-151">It'll be better for you to assign policies in batches via PowerShell.</span></span> <span data-ttu-id="c14ac-152">我们提供了一些特定于 EDU 的信息，说明如何[将策略分配给教育机构中的大量用户](batch-policy-assignment-edu.md)（如果需要），你还可以查看下面有关策略包的部分，这是另一种管理大量用户的策略和设置的好方法。</span><span class="sxs-lookup"><span data-stu-id="c14ac-152">We have some EDU-specific information on how to [Assign policies to large sets of users in your educational institute](batch-policy-assignment-edu.md) if you need it, and you can also check out the section below on policy packages, which are another great way to manage policies and settings for large groups of users.</span></span>

![“编辑用户策略”窗格，位于“已分配的策略”页面右上方。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a><span data-ttu-id="c14ac-154">Microsoft Teams 中的策略包</span><span class="sxs-lookup"><span data-stu-id="c14ac-154">Policy packages in Microsoft Teams</span></span>

<span data-ttu-id="c14ac-155">Teams 中的策略包将收集预定义策略和上述策略设置，并将其分配给机构中具有相似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-155">A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution.</span></span> <span data-ttu-id="c14ac-156">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="c14ac-156">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="c14ac-157">通常，为每个用户分配一个策略包，然后根据需要重新定义每个包中的策略，以满足该用户组的需要。</span><span class="sxs-lookup"><span data-stu-id="c14ac-157">In normal practice, you assign each of your users a policy package, and  redefine the policies in each package as needed to suit the needs of that user group.</span></span> <span data-ttu-id="c14ac-158">更新包中的设置时，分配给该包的所有用户都将作为批量更新进行更改。</span><span class="sxs-lookup"><span data-stu-id="c14ac-158">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="c14ac-159">一般情况下，教育机构的许多用户有其独特的需求，部分取决于学生的年龄和成熟度。</span><span class="sxs-lookup"><span data-stu-id="c14ac-159">Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="c14ac-160">例如，你可能想要授予教师和教职员工对 Microsoft Teams 的完全访问权限，但想要对学生限制 Microsoft Teams 功能，以便鼓励营造安全且专注的学习环境。</span><span class="sxs-lookup"><span data-stu-id="c14ac-160">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="c14ac-161">可使用策略包根据教育机构社区中不同群体的需求来定制设置。</span><span class="sxs-lookup"><span data-stu-id="c14ac-161">You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.</span></span>

> [!NOTE]
> <span data-ttu-id="c14ac-162">有关详细信息，可查看[管理 Microsoft Teams 中的策略包](manage-policy-packages.md)，了解有关向单个用户分配包、向多达 5000 个用户批量分配包以及管理和更新链接到每个包的策略的分步指导。</span><span class="sxs-lookup"><span data-stu-id="c14ac-162">For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.</span></span>

<span data-ttu-id="c14ac-163">就像本文前面的策略列表一样，策略包预定义以下各项的策略：</span><span class="sxs-lookup"><span data-stu-id="c14ac-163">Just like the policy list earlier in this article, policy packages predefine policies for:</span></span>

- <span data-ttu-id="c14ac-164">会议</span><span class="sxs-lookup"><span data-stu-id="c14ac-164">Meetings</span></span>
- <span data-ttu-id="c14ac-165">实时事件</span><span class="sxs-lookup"><span data-stu-id="c14ac-165">Live events</span></span>
- <span data-ttu-id="c14ac-166">通话</span><span class="sxs-lookup"><span data-stu-id="c14ac-166">Calling</span></span>
- <span data-ttu-id="c14ac-167">消息传递</span><span class="sxs-lookup"><span data-stu-id="c14ac-167">Messaging</span></span>
- <span data-ttu-id="c14ac-168">Teams</span><span class="sxs-lookup"><span data-stu-id="c14ac-168">Teams</span></span>
- <span data-ttu-id="c14ac-169">应用权限</span><span class="sxs-lookup"><span data-stu-id="c14ac-169">App permissions</span></span>

<span data-ttu-id="c14ac-170">Microsoft Teams 当前包含以下策略包：</span><span class="sxs-lookup"><span data-stu-id="c14ac-170">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="c14ac-171">Microsoft Teams 管理中心中列出的包名称</span><span class="sxs-lookup"><span data-stu-id="c14ac-171">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="c14ac-172">最适合用于</span><span class="sxs-lookup"><span data-stu-id="c14ac-172">Best used for</span></span>  |<span data-ttu-id="c14ac-173">说明</span><span class="sxs-lookup"><span data-stu-id="c14ac-173">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="c14ac-174">**Education_Teacher**</span><span class="sxs-lookup"><span data-stu-id="c14ac-174">**Education_Teacher**</span></span>| <span data-ttu-id="c14ac-175">教师和教职员工</span><span class="sxs-lookup"><span data-stu-id="c14ac-175">Educators and staff</span></span>| <span data-ttu-id="c14ac-176">使用这组策略和策略设置可以为组织中的教师和教职员工授予通过 Microsoft Teams 进行聊天、通话和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="c14ac-176">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="c14ac-177">**Education_PrimaryStudent**</span><span class="sxs-lookup"><span data-stu-id="c14ac-177">**Education_PrimaryStudent**</span></span>| <span data-ttu-id="c14ac-178">小学适龄学生</span><span class="sxs-lookup"><span data-stu-id="c14ac-178">Primary school aged students</span></span>  | <span data-ttu-id="c14ac-179">你所在机构内年幼的小学适龄学生可能需要 Microsoft Teams 中的更多限制。</span><span class="sxs-lookup"><span data-stu-id="c14ac-179">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="c14ac-180">使用这组策略和策略设置可限制会议创建和管理、聊天管理和私人通话等功能。</span><span class="sxs-lookup"><span data-stu-id="c14ac-180">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="c14ac-181">**Education_SecondaryStudent**</span><span class="sxs-lookup"><span data-stu-id="c14ac-181">**Education_SecondaryStudent**</span></span>| <span data-ttu-id="c14ac-182">中学学龄学生</span><span class="sxs-lookup"><span data-stu-id="c14ac-182">Secondary school aged students</span></span> | <span data-ttu-id="c14ac-183">你所在机构内的中学适龄学生可能需要 Microsoft Teams 中的更多限制。</span><span class="sxs-lookup"><span data-stu-id="c14ac-183">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="c14ac-184">使用这组策略和策略设置可限制会议创建和管理、聊天管理和私人通话等功能。</span><span class="sxs-lookup"><span data-stu-id="c14ac-184">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="c14ac-185">**Education_HigherEducationStudent**</span><span class="sxs-lookup"><span data-stu-id="c14ac-185">**Education_HigherEducationStudent**</span></span>| <span data-ttu-id="c14ac-186">高等教育学生</span><span class="sxs-lookup"><span data-stu-id="c14ac-186">Higher education students</span></span> | <span data-ttu-id="c14ac-187">你所在机构内的高等教育学生所需的限制可能比年幼学生要少，但是可能建议采用某些限制。</span><span class="sxs-lookup"><span data-stu-id="c14ac-187">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="c14ac-188">可以使用这组策略和策略设置来授予对组织内的聊天、通话和会议的访问权限，但限制学生与外部参与者一起使用 Microsoft Teams 的方式。</span><span class="sxs-lookup"><span data-stu-id="c14ac-188">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|<span data-ttu-id="c14ac-189">**Education_PrimaryTeacher_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="c14ac-189">**Education_PrimaryTeacher_RemoteLearning**</span></span>| <span data-ttu-id="c14ac-190">教师和教职员工</span><span class="sxs-lookup"><span data-stu-id="c14ac-190">Educators and staff</span></span> | <span data-ttu-id="c14ac-191">创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="c14ac-191">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span> |
|<span data-ttu-id="c14ac-192">**Education_PrimaryStudent_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="c14ac-192">**Education_PrimaryStudent_RemoteLearning**</span></span>| <span data-ttu-id="c14ac-193">小学适龄学生</span><span class="sxs-lookup"><span data-stu-id="c14ac-193">Primary school aged students</span></span>| <span data-ttu-id="c14ac-194">创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="c14ac-194">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="策略包页面，其中包含可供选择的策略包列表。":::

<span data-ttu-id="c14ac-196">将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="c14ac-196">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="c14ac-197">例如，当你将 Education_Teacher 策略包分配给教育机构中的教师时，将为包中的每个策略创建一个名为 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="c14ac-197">For example, when you assign the Education_Teacher policy package to educators in your educational institution, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 策略包的屏幕截图](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="c14ac-199">如果确定教师和管理支持人员需要不同的策略，则可以重新调整现有包：识别当前不使用的包，并更改设置以适合该组。</span><span class="sxs-lookup"><span data-stu-id="c14ac-199">If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="c14ac-200">你可能需要自己记录哪个小组拥有哪个包，但这是重新调整包的唯一障碍。</span><span class="sxs-lookup"><span data-stu-id="c14ac-200">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="policies-that-should-be-assigned-for-student-safety"></a><span data-ttu-id="c14ac-201">应为学生安全分配的策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-201">Policies that should be assigned for student safety</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="c14ac-202">会议策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-202">Meeting policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-meetings"></a><span data-ttu-id="c14ac-203">关闭创建和启动会议的功能</span><span class="sxs-lookup"><span data-stu-id="c14ac-203">Turn off the ability to create and start meetings</span></span>

<span data-ttu-id="c14ac-204">若要确保学生无法安排会议来进行无人参与的通信，可通过以下常规设置将会议策略设置为**关闭**会议创建功能：</span><span class="sxs-lookup"><span data-stu-id="c14ac-204">To ensure that students can’t schedule a meeting to communicate unattended, in meeting policies set to **Off** meeting creation capabilities through these General settings:</span></span>

- <span data-ttu-id="c14ac-205">**允许在频道中立即开会**：关闭</span><span class="sxs-lookup"><span data-stu-id="c14ac-205">**Allow Meet now in channels**: Off</span></span>
- <span data-ttu-id="c14ac-206">**允许 Outlook 加载项**：关闭</span><span class="sxs-lookup"><span data-stu-id="c14ac-206">**Allow the Outlook add-in**: Off</span></span>
- <span data-ttu-id="c14ac-207">**允许安排频道会议**：关闭</span><span class="sxs-lookup"><span data-stu-id="c14ac-207">**Allow channel meeting scheduling**: Off</span></span>
- <span data-ttu-id="c14ac-208">**允许安排私人会议**：关闭</span><span class="sxs-lookup"><span data-stu-id="c14ac-208">**Allow scheduling private meetings**: Off</span></span>

![远程学习页面上的教育学生，显示“常规”部分，此处的所有选项均已关闭。](media/edu-policy-list-a.png)

- <span data-ttu-id="c14ac-210">在同一页面上，在会议部分中的“参与者和来宾”中：</span><span class="sxs-lookup"><span data-stu-id="c14ac-210">And on the same page, in the Participants and Guests in meeting section:</span></span>
  - <span data-ttu-id="c14ac-211">**允许在私人会议中立即开会**：关闭</span><span class="sxs-lookup"><span data-stu-id="c14ac-211">**Allow Meet now in private meetings**: Off</span></span>
  - <span data-ttu-id="c14ac-212">**允许在会议中聊天**：已禁用</span><span class="sxs-lookup"><span data-stu-id="c14ac-212">**Allow chat in meetings**: Disabled</span></span>

![“参与者和来宾”部分，“允许在私人会议中立即开会”设置为“关闭”。](media/edu-participants-and-guests.png)

<span data-ttu-id="c14ac-214">为学生关闭“**允许在频道中立即开会**”、“**允许安排频道会议**”、“**允许安排私人会议**”和“**在私人会议中立即开会**”，不仅可阻止学生以组织者身份安排会议，还可为教育客户提供以下安全措施：</span><span class="sxs-lookup"><span data-stu-id="c14ac-214">Turning off **Allow Meet now in channels**, **Allow channel meeting scheduling**, **Allow scheduling private meetings**, and **Meet now in private meetings** for students not only blocks students from scheduling a meeting as the organizer, they also provide the following safety measures for education:</span></span>

- <span data-ttu-id="c14ac-215">如果学生尝试在教师之前加入会议，则他们将无法在最新版本的 Teams 应用中加入会议。</span><span class="sxs-lookup"><span data-stu-id="c14ac-215">If students attempt to join the meeting before the educator, they won't be able to join the meeting in the latest version of the Teams app.</span></span>
- <span data-ttu-id="c14ac-216">尽管会议创建适用于任何用户和任何许可证，但是上述有关会议加入阻止的安全措施仅基于用户的许可证类型应用于 Teams 中的教育客户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-216">Although meeting creation applies to any users and any licenses, the safety measures on meeting join block described above apply only to education customers in Teams based on the users’ license type.</span></span>

<span data-ttu-id="c14ac-217">如果你将“**允许在会议中聊天**”策略更改为禁用，并阻止学生从上方安排会议，但是继续对教育工作者启用此策略时（对于不是从某个频道或频道中的“立即开会”安排的会议），则学生将无法在教师加入会议之前进行聊天，也不能在会议结束后进行聊天。</span><span class="sxs-lookup"><span data-stu-id="c14ac-217">When you change the **Allow chat in meetings** policy to disabled and block students from scheduling meetings from above while and keep this policy on for educators (for the meetings that are not scheduled from a channel or meet now in a channel), students won't be able to chat before the educator joins the meeting, nor after the meeting.</span></span> <span data-ttu-id="c14ac-218">他们仍然可以在会议之前、期间和之后查看历史聊天记录。</span><span class="sxs-lookup"><span data-stu-id="c14ac-218">They will still be able to see the chat history before, during, and after the meeting.</span></span> <span data-ttu-id="c14ac-219">例如，他们将能够查看来自老师的消息或会议录制链接（如果录制了会议）。</span><span class="sxs-lookup"><span data-stu-id="c14ac-219">As an example, they'll be able to see messages from the teacher, or the meeting recording link, if the meeting was recorded.</span></span>

<span data-ttu-id="c14ac-220">如果学生和教师都禁用了“**允许在会议中聊天**”策略，则任何人都无法在会议聊天窗口中聊天。</span><span class="sxs-lookup"><span data-stu-id="c14ac-220">If both students and educators have the **Allow chat in meetings** policy turned off, no one will be able to chat in the meeting chat window.</span></span> <span data-ttu-id="c14ac-221">上述关于会议聊天限制的安全措施仅基于用户的许可类型应用于 Teams 中的教育客户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-221">The safety measure on meeting chat restriction described above only applies to education customers in Teams based on users’ license type.</span></span>

#### <a name="control-whether-or-not-students-can-share-their-videos-during-calls-and-meetings"></a><span data-ttu-id="c14ac-222">控制学生是否可以在通话和会议期间分享他们的视频</span><span class="sxs-lookup"><span data-stu-id="c14ac-222">Control whether or not students can share their videos during calls and meetings</span></span>

<span data-ttu-id="c14ac-223">在会议策略部分，确保为学生设置的音频和视频值与教育机构的指导原则以及学生、教师、家长和监护人的期望相符（“**允许云录制**”除外，建议将其设置为“**关闭**”）。</span><span class="sxs-lookup"><span data-stu-id="c14ac-223">In the meeting policies section, ensure that the Audio and visual values you set for your students aligns to your educational institution’s guidelines, as well as the desires of students, educators, and parents and guardians (With the exception of **Allow cloud recording**, which we recommend be set to **Off**).</span></span>

<span data-ttu-id="c14ac-224">选项如下：</span><span class="sxs-lookup"><span data-stu-id="c14ac-224">The options here:</span></span>

- <span data-ttu-id="c14ac-225">**允许听录**：关闭/打开</span><span class="sxs-lookup"><span data-stu-id="c14ac-225">**Allow transcription**: Off/On</span></span>
- <span data-ttu-id="c14ac-226">**允许云录制**：**关闭**</span><span class="sxs-lookup"><span data-stu-id="c14ac-226">**Allow cloud recording**: **Off**</span></span>
- <span data-ttu-id="c14ac-227">**允许 IP 视频**：关闭/打开</span><span class="sxs-lookup"><span data-stu-id="c14ac-227">**Allow IP Video**: Off/On</span></span>

:::image type="content" source="media/edu-policy-list-b.png" alt-text="远程学习页面中的教育学生，其中显示视频选项。":::

### <a name="live-events-policies"></a><span data-ttu-id="c14ac-229">实时事件策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-229">Live events policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-live-events"></a><span data-ttu-id="c14ac-230">关闭创建和启动实时事件的功能</span><span class="sxs-lookup"><span data-stu-id="c14ac-230">Turn off the ability to create and start live events</span></span>

<span data-ttu-id="c14ac-231">若要确保学生无法计划实时事件来进行无人参与的通信，请为学生禁用“**允许安排**”策略，方法是将其设置为“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-231">To ensure that students can’t schedule a live events to communicate unattended, disable the **Allow scheduling** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-allow-scheduling-off.png" alt-text="远程学习页面中的教育学生，其中“允许安排”选项已关闭。":::

### <a name="calling-policies"></a><span data-ttu-id="c14ac-233">通话策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-233">Calling policies</span></span>

#### <a name="turn-off-the-ability-to-make-private-calls"></a><span data-ttu-id="c14ac-234">关闭进行私人通话的功能</span><span class="sxs-lookup"><span data-stu-id="c14ac-234">Turn off the ability to make private calls</span></span>

<span data-ttu-id="c14ac-235">若要确保学生无法与其他学生或教师进行私人通话，可为学生禁用“**拨打私人电话**”策略，方法是将其设置为“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-235">To ensure that students can’t make private calls with other students or educators, disable the **Make private calls** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-private-calls-off.png" alt-text="远程学习页面中的教育学生，其中“拨打私人电话”设置为“关闭”。":::

### <a name="messaging-policies"></a><span data-ttu-id="c14ac-237">消息传递策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-237">Messaging policies</span></span>

#### <a name="turn-off-the-ability-to-delete-or-edit-sent-messages"></a><span data-ttu-id="c14ac-238">关闭删除或编辑已发送消息的功能</span><span class="sxs-lookup"><span data-stu-id="c14ac-238">Turn off the ability to delete or edit sent messages</span></span>

- <span data-ttu-id="c14ac-239">对于学生：若要确保学生发送的消息未被删除或更改，学生应将以下设置设为“**关闭**”：</span><span class="sxs-lookup"><span data-stu-id="c14ac-239">For students: To make sure the messages that students send aren’t deleted or altered, students should have these settings turned **Off**:</span></span>
  - <span data-ttu-id="c14ac-240">**删除已发送的消息**</span><span class="sxs-lookup"><span data-stu-id="c14ac-240">**Delete sent messages**</span></span>
  - <span data-ttu-id="c14ac-241">**编辑已发送的消息**</span><span class="sxs-lookup"><span data-stu-id="c14ac-241">**Edit sent messages**</span></span>
- <span data-ttu-id="c14ac-242">对于教师：若要确保教师能够审查或删除学生发送的不适当消息，教师应将以下设置设为“**打开**”：</span><span class="sxs-lookup"><span data-stu-id="c14ac-242">For educators: To make sure that educators can moderate or delete inappropriate messages students sent, educators should have these settings turned **On**:</span></span>
  - <span data-ttu-id="c14ac-243">**所有者可以删除已发送的消息**（此设置允许教师删除不适当的学生消息）</span><span class="sxs-lookup"><span data-stu-id="c14ac-243">**Owners can delete sent messages** (This setting allows educators to delete inappropriate student messages)</span></span>
  - <span data-ttu-id="c14ac-244">**删除已发送的消息**</span><span class="sxs-lookup"><span data-stu-id="c14ac-244">**Delete sent messages**</span></span>
  - <span data-ttu-id="c14ac-245">**编辑已发送的消息**</span><span class="sxs-lookup"><span data-stu-id="c14ac-245">**Edit sent messages**</span></span>

![远程学习页面中的教育学生，学生和教师的已发送消息设置。](media/edu-delete-edit-sent.png)

> [!NOTE]
> <span data-ttu-id="c14ac-247">有关此主题的详细信息，请查看[将课堂团队中的学生设为静音](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17)。</span><span class="sxs-lookup"><span data-stu-id="c14ac-247">For more information on this topic, check out [Mute student comments in a class team.](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17).</span></span>

#### <a name="control-whether-students-can-chat-privately"></a><span data-ttu-id="c14ac-248">控制学生是否可以私下聊天</span><span class="sxs-lookup"><span data-stu-id="c14ac-248">Control whether students can chat privately</span></span>

<span data-ttu-id="c14ac-249">确保为学生设置的“**聊天打开/关闭**”值与教育机构的指导原则以及学生和教师的期望相符。</span><span class="sxs-lookup"><span data-stu-id="c14ac-249">Ensure that the **Chat On/Off** value you set for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span> <span data-ttu-id="c14ac-250">此控件可打开或关闭用户在 Teams 中一对一私聊或群聊的功能。</span><span class="sxs-lookup"><span data-stu-id="c14ac-250">This control turns on or off the ability for a user to communicate privately in 1:1 chat or group chat in Teams.</span></span>

![远程学习页面中的教育学生，其中聊天选项已关闭。](media/edu-chat-private.png)

#### <a name="control-whether-students-can-personalize-their-messages"></a><span data-ttu-id="c14ac-252">控制学生是否可以对其消息进行个性化设置</span><span class="sxs-lookup"><span data-stu-id="c14ac-252">Control whether students can personalize their messages</span></span>

<span data-ttu-id="c14ac-253">确保为学生设置的值与教育机构的指导原则以及学生、教师、家长和监护人的期望相符。</span><span class="sxs-lookup"><span data-stu-id="c14ac-253">Ensure that the value you set for students aligns to your educational institution’s guidelines as well as the desires of students, educators, parents, and guardians.</span></span> <span data-ttu-id="c14ac-254">建议将“**适用于学生的 Giphy**”设置为“**关闭**”，并**打开**“**Meme 和贴纸**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-254">Our recommendation is to set **Giphy for students** to **Off**, and keep **Memes and Stickers** turned **On**.</span></span>

![远程学习页面上的教育学生，包含 Giphy 选项以及 Meme 和贴纸选项。](media/edu-personalize-messages.png)

#### <a name="control-whether-students-can-send-voice-messages"></a><span data-ttu-id="c14ac-256">控制学生是否可以发送语音消息</span><span class="sxs-lookup"><span data-stu-id="c14ac-256">Control whether students can send voice messages</span></span>

<span data-ttu-id="c14ac-257">确保为学生设置的“**创建语音消息**”值与教育机构的指导原则以及学生和教师的期望相符。</span><span class="sxs-lookup"><span data-stu-id="c14ac-257">Ensure that the value you set for **Create voice messages** for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span>

![远程学习页面中的教育学生，包含“创建语音消息”选项。](media/edu-create-send-voice-mess.png)

#### <a name="turn-off-the-ability-to-remove-users-from-chat-for-students"></a><span data-ttu-id="c14ac-259">关闭从聊天中删除用户的功能</span><span class="sxs-lookup"><span data-stu-id="c14ac-259">Turn off the ability to remove users from chat for students</span></span>

<span data-ttu-id="c14ac-260">学生不应能够从其参与的任何聊天中删除其他用户。</span><span class="sxs-lookup"><span data-stu-id="c14ac-260">Students should not have the ability to remove other users from any chats they're included in.</span></span> <span data-ttu-id="c14ac-261">“**从组聊天中删除用户**”的设置应设为“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-261">The setting for **Remove users from group chats** should be set to **Off**.</span></span>

![远程学习页面中的教育学生，其中“从组聊天中删除用户”设置为“关闭”。](media/edu-remove-users-from-chat-for-students.png)

### <a name="teams-policies"></a><span data-ttu-id="c14ac-263">Teams 策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-263">Teams policies</span></span>

#### <a name="turn-off-the-ability-to-discover-and-create-private-channels"></a><span data-ttu-id="c14ac-264">关闭发现和创建专用频道的功能</span><span class="sxs-lookup"><span data-stu-id="c14ac-264">Turn off the ability to discover and create private channels</span></span>

<span data-ttu-id="c14ac-265">若要确保学生无法创建专用频道作为个人空间来在没有监督的情况下进行交流，请为学生将“**创建专用频道**”策略设置为“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-265">To ensure that students can’t create a private channel as personal space to communicate without supervision, set the **Create private channels** policy for students to **Off**.</span></span>

![Teams 策略页面，“新建团队策略”面板重叠在页面右侧，该面板上的“创建专用频道”设置为“关闭”。](media/edu-private-channels.png)

> [!IMPORTANT]
> <span data-ttu-id="c14ac-267">你可能还希望确保学生无法在 Microsoft Teams 中创建新团队。</span><span class="sxs-lookup"><span data-stu-id="c14ac-267">Likely you will also want to ensure students don't have the ability to create new teams in Microsoft Teams.</span></span> <span data-ttu-id="c14ac-268">这实际上是一个 M365 组设置，可在[此处](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="c14ac-268">This is actually an M365 groups setting, and you can read more about it [here](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="c14ac-269">应用权限策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-269">App permission policies</span></span>

#### <a name="control-whether-students-can-add-apps-within-teams"></a><span data-ttu-id="c14ac-270">控制学生是否可以在 Teams 中添加应用</span><span class="sxs-lookup"><span data-stu-id="c14ac-270">Control whether students can add apps within Teams</span></span>

<span data-ttu-id="c14ac-271">确保为学生设置的值与教育机构的指导原则相符。</span><span class="sxs-lookup"><span data-stu-id="c14ac-271">Ensure the values you set for students align to your educational institution’s guidelines.</span></span> <span data-ttu-id="c14ac-272">例如，如果希望让学生使用你批准的应用程序，则可以选择：</span><span class="sxs-lookup"><span data-stu-id="c14ac-272">For example, if you’d like the students to be exposed to the apps you approve, you can select:</span></span>

- <span data-ttu-id="c14ac-273">**Microsoft 应用**：**允许所有应用**</span><span class="sxs-lookup"><span data-stu-id="c14ac-273">**Microsoft apps**: **Allow all apps**</span></span>
- <span data-ttu-id="c14ac-274">**对于第三方应用**：**允许特定的应用并阻止其他所有应用**</span><span class="sxs-lookup"><span data-stu-id="c14ac-274">**For Third-party apps**: **Allow specific apps and block all others**</span></span>
- <span data-ttu-id="c14ac-275">**对于租户应用**：**允许特定的应用并阻止其他所有应用**</span><span class="sxs-lookup"><span data-stu-id="c14ac-275">**For Tenant apps**: **Allow specific apps and block all others**</span></span>

:::image type="content" source="media/edu-policies-apps.png" alt-text="远程学习页面中的教育学生以及设置的应用策略选项。":::

> [!NOTE]
> <span data-ttu-id="c14ac-277">这是一个示例，如上所述，应按照教育机构的指导原则设置这些策略。</span><span class="sxs-lookup"><span data-stu-id="c14ac-277">This is an example, and as stated above, you should set these policies in accordance to your educational institution's guidelines.</span></span>

## <a name="policies-that-should-be-assigned-for-educators"></a><span data-ttu-id="c14ac-278">应为教师分配的策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-278">Policies that should be assigned for educators</span></span>

<span data-ttu-id="c14ac-279">这些是建议管理员应用于教师的策略设置，以便他们可以为其学生提供安全的课堂体验。</span><span class="sxs-lookup"><span data-stu-id="c14ac-279">These are recommended policy settings for admins to apply for educators, so they can have a safe class experience for their students.</span></span>

> [!NOTE]
> <span data-ttu-id="c14ac-280">与将在下面看到的教师部分相比，针对学生的策略建议包含更多信息。</span><span class="sxs-lookup"><span data-stu-id="c14ac-280">The policy recommendations for students contains more information than the educators' sections you'll see below.</span></span> <span data-ttu-id="c14ac-281">尽管你可以根据自己的教育机构的政策和程序来设置策略设置，但此处提供的建议与学生的安全密切相关。</span><span class="sxs-lookup"><span data-stu-id="c14ac-281">While you may set policy settings in-line with your educational institute's own policies and procedures, the recommendations provided here are strictly relevant when it comes to the safety and security of students.</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="c14ac-282">会议策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-282">Meeting policies</span></span>

<span data-ttu-id="c14ac-283">这些设置将允许教师控制对其会议的访问。</span><span class="sxs-lookup"><span data-stu-id="c14ac-283">These settings will allow educators to control access to their meetings.</span></span>

- <span data-ttu-id="c14ac-284">**允许匿名人员发起会议**：**关闭**</span><span class="sxs-lookup"><span data-stu-id="c14ac-284">**Let anonymous people start a meeting**: **Off**</span></span>
- <span data-ttu-id="c14ac-285">**自动允许人员**：**你所在组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="c14ac-285">**Automatically admit people**: **Everyone in your organization**</span></span>
- <span data-ttu-id="c14ac-286">**允许拨号加入的用户绕过大厅**：**关闭**</span><span class="sxs-lookup"><span data-stu-id="c14ac-286">**Allow dial-in users to bypass the lobby**: **Off**</span></span>
- <span data-ttu-id="c14ac-287"><sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**</span><span class="sxs-lookup"><span data-stu-id="c14ac-287"><sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**</span></span>

<span data-ttu-id="c14ac-288"><sup>1</sup> 该设置不在 Microsoft Teams 管理中心中，因此你将需要使用 PowerShell 通过 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 或 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 设置 **DesignatedPresenterRoleMode** 参数。</span><span class="sxs-lookup"><span data-stu-id="c14ac-288"><sup>1</sup> This setting isn't in the Microsoft Teams admin center, so you'll need to use PowerShell to set the **DesignatedPresenterRoleMode** parameter using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) or [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="c14ac-289">这将把 Teams“**会议选项**”中的“**谁可以参加?** 设置的默认值设置为“**只有我**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-289">This sets the default value of the **Who can present?** setting in **Meeting options** in Teams to **Only me**.</span></span> <span data-ttu-id="c14ac-290">通过此设置，只有会议组织者可以成为演示者，所有其他会议参与者都将被指定为与会者。</span><span class="sxs-lookup"><span data-stu-id="c14ac-290">With this setting, only the meeting organizer can be a presenter and all other meeting participants are designated as attendees.</span></span> <span data-ttu-id="c14ac-291">若要了解详细信息，请参阅“[会议策略设置 - 指定的演示者角色模式](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode)”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-291">To learn more, see [Meeting policy settings - Designated presenter role mode](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode).</span></span>

> [!NOTE]
> <span data-ttu-id="c14ac-292">对于不是教师的教职员工，你可能希望将参数设置为 **EveryoneUserOverride**（对应于 Teams 中的“**每个人**”设置）或 **EveryoneInCompanyUserOverride**（对应于 Teams 中的“**我的组织中的人员**”设置。）</span><span class="sxs-lookup"><span data-stu-id="c14ac-292">For staff who aren't educators, you may want to set the parameter to **EveryoneUserOverride** (which corresponds to the **Everyone** setting in Teams) or **EveryoneInCompanyUserOverride** (which corresponds to the **People in my organization** setting in Teams.)</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="c14ac-293">消息传递策略</span><span class="sxs-lookup"><span data-stu-id="c14ac-293">Messaging policies</span></span>

<span data-ttu-id="c14ac-294">将“**所有者可以删除已发送的消息**”设置为“**打开**”时，教师能够监视聊天会话并删除频道会议中不适当的消息。</span><span class="sxs-lookup"><span data-stu-id="c14ac-294">Setting **Owners can delete sent messages** to **On** will allow educators to monitor chat sessions and remove inappropriate messages in channel meetings.</span></span>

> [!NOTE]
> <span data-ttu-id="c14ac-295">这样，当在频道内创建会议时，教师可以删除班级聊天中不适当的消息，或者删除频道本身内的消息。</span><span class="sxs-lookup"><span data-stu-id="c14ac-295">This allows educators to remove inappropriate messages in class chats when the meeting is created within the channel, or to remove messages within the channel itself.</span></span>

## <a name="what-educators-can-do-to-protect-students"></a><span data-ttu-id="c14ac-296">教师可执行哪些操作来保护学生</span><span class="sxs-lookup"><span data-stu-id="c14ac-296">What educators can do to protect students</span></span>

<span data-ttu-id="c14ac-297">当然，虽然设置策略是管理员在 Teams 设置中主动保护学生的一种好方法，但教师是定期与学生互动的人，他们在确保学生安全方面也起着至关重要的作用。</span><span class="sxs-lookup"><span data-stu-id="c14ac-297">Of course, while setting policies is a great way for Admins to proactively protect students in a Teams setting, educators are the people who are interacting with the students on a regular basis, and they also have a vital role to play to keep students safe.</span></span> <span data-ttu-id="c14ac-298">管理员可能需要与同自己协作的讲师讨论以下信息。</span><span class="sxs-lookup"><span data-stu-id="c14ac-298">Admins may want to discuss the following information with the educators they work with.</span></span>

### <a name="set-meeting-roles-through-your-meeting-options"></a><span data-ttu-id="c14ac-299">通过会议选项设置会议角色</span><span class="sxs-lookup"><span data-stu-id="c14ac-299">Set meeting roles through your Meeting options</span></span>

<span data-ttu-id="c14ac-300">通过会议选项，你可以控制会议参与者以与会者还是演示者身份加入你的会议。</span><span class="sxs-lookup"><span data-stu-id="c14ac-300">Meeting options allow you to control if meeting participants join your meetings as attendees or presenters.</span></span> <span data-ttu-id="c14ac-301">选项如下：</span><span class="sxs-lookup"><span data-stu-id="c14ac-301">Your options are:</span></span>

- <span data-ttu-id="c14ac-302">转到“**日历**”并导航到要更新的会议。</span><span class="sxs-lookup"><span data-stu-id="c14ac-302">Go to your **Calendar**  and navigate to the meeting you'd like to update.</span></span> <span data-ttu-id="c14ac-303">单击或点击会议加入链接附近的“**会议选项**”以打开“**会议选项**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-303">Click or tap **Meeting options** near the meeting join link to open your **Meeting options**.</span></span>

![加入 Microsoft Teams 会议邀请，“会议选项”位于邀请链接下方的最右边。](media/edu-join-meeting-options.png)

- <span data-ttu-id="c14ac-305">通过“**谁可以绕过大厅**”部分来控制谁可以直接进入会议。</span><span class="sxs-lookup"><span data-stu-id="c14ac-305">Control who can enter the meeting directly with the **Who can bypass the lobby** selection.</span></span> <span data-ttu-id="c14ac-306">将其设置为“**我组织中的人员**”以防止外部用户有选项进入，然后将“**始终允许呼叫者绕过大厅**”设置为“**关闭**”，以使参与者等待准许加入会议，而不是立即加入会议。</span><span class="sxs-lookup"><span data-stu-id="c14ac-306">Set it to **People in my organization** to keep external users from having the option to enter, and turn **Always let callers bypass the lobby** to **Off** to have participants wait to be admitted to the meeting instead of joining immediately.</span></span> <span data-ttu-id="c14ac-307">你还可以选择“**在呼叫方加入或退出会议时通知**”，并且应将其设置为“**打开**”，以便你始终了解哪些人出席会议。</span><span class="sxs-lookup"><span data-stu-id="c14ac-307">You also have the option to **Announce when callers join or leave**, and this should be set to **On** so you're always aware of who's in the meeting.</span></span>
- <span data-ttu-id="c14ac-308">控制作为演示者或与会者加入会议的人员。</span><span class="sxs-lookup"><span data-stu-id="c14ac-308">Control who joins the meeting as a presenter or attendee.</span></span> <span data-ttu-id="c14ac-309">可以选择“**仅我**”来指定所有其他参与者为与会者。</span><span class="sxs-lookup"><span data-stu-id="c14ac-309">You can select **Only Me** to designate all other participants as attendees.</span></span> <span data-ttu-id="c14ac-310">对于在课堂环境中举行的会议，这是最安全的设置。</span><span class="sxs-lookup"><span data-stu-id="c14ac-310">This is the safest set-up for meetings held in a classroom setting.</span></span>
  - <span data-ttu-id="c14ac-311">如果希望会议中有多个演示者，请选择“**特定用户**”，然后选择应作为演示者加入的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="c14ac-311">If you expect to have more than one presenter in your meeting, select **Specific people** and pick the other participants who should join as presenters.</span></span> <span data-ttu-id="c14ac-312">如果希望所有参与者都作为演示者加入会议，请选择“**所有人**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-312">Select **Everyone** if you want all participants to join the meeting as a presenter.</span></span>

:::image type="content" source="media/edu-meeting-options.png" alt-text="“谁可以绕过大厅”下拉列表并选中“我组织中的人员”，“谁可进行演示”下拉列表并选中“仅我”。":::

### <a name="roles-in-an-online-meeting"></a><span data-ttu-id="c14ac-314">联机会议中的角色</span><span class="sxs-lookup"><span data-stu-id="c14ac-314">Roles in an online meeting</span></span>

<span data-ttu-id="c14ac-315">会议的每位参与者都会被分配演示者或与会者角色。</span><span class="sxs-lookup"><span data-stu-id="c14ac-315">Every participant in a meeting is assigned a role as a presenter or attendee.</span></span> <span data-ttu-id="c14ac-316">参与者的角色控制他们在会议中可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c14ac-316">A participant's role controls what they can do in a meeting.</span></span> <span data-ttu-id="c14ac-317">请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c14ac-317">Please see the table below.</span></span>

|<span data-ttu-id="c14ac-318">功能</span><span class="sxs-lookup"><span data-stu-id="c14ac-318">Capabilities</span></span>  |<span data-ttu-id="c14ac-319">组织者/演示者</span><span class="sxs-lookup"><span data-stu-id="c14ac-319">Organizer/Presenter</span></span>  |<span data-ttu-id="c14ac-320">与会者</span><span class="sxs-lookup"><span data-stu-id="c14ac-320">Attendee</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c14ac-321">说话和共享视频</span><span class="sxs-lookup"><span data-stu-id="c14ac-321">Speak and share video</span></span>     |     <span data-ttu-id="c14ac-322">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-322">Y</span></span>     |     <span data-ttu-id="c14ac-323">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-323">Y</span></span>     |
|<span data-ttu-id="c14ac-324">参加会议聊天</span><span class="sxs-lookup"><span data-stu-id="c14ac-324">Participate in meeting chat</span></span>     |     <span data-ttu-id="c14ac-325">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-325">Y</span></span>     |     <span data-ttu-id="c14ac-326">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-326">Y</span></span>     |
|<span data-ttu-id="c14ac-327">私下查看其他人共享的 PowerPoint 文件</span><span class="sxs-lookup"><span data-stu-id="c14ac-327">Privately view a PowerPoint file shared by someone else</span></span>     |     <span data-ttu-id="c14ac-328">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-328">Y</span></span>     |     <span data-ttu-id="c14ac-329">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-329">Y</span></span>     |
|<span data-ttu-id="c14ac-330">共享内容</span><span class="sxs-lookup"><span data-stu-id="c14ac-330">Share content</span></span>     |     <span data-ttu-id="c14ac-331">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-331">Y</span></span>     |     <span data-ttu-id="c14ac-332">N</span><span class="sxs-lookup"><span data-stu-id="c14ac-332">N</span></span>     |
|<span data-ttu-id="c14ac-333">使其他参与者静音</span><span class="sxs-lookup"><span data-stu-id="c14ac-333">Mute other participants</span></span>|     <span data-ttu-id="c14ac-334">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-334">Y</span></span>     |     <span data-ttu-id="c14ac-335">N</span><span class="sxs-lookup"><span data-stu-id="c14ac-335">N</span></span>     |
|<span data-ttu-id="c14ac-336">删除参与者</span><span class="sxs-lookup"><span data-stu-id="c14ac-336">Remove participants</span></span>      |     <span data-ttu-id="c14ac-337">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-337">Y</span></span>     |     <span data-ttu-id="c14ac-338">N</span><span class="sxs-lookup"><span data-stu-id="c14ac-338">N</span></span>     |
|<span data-ttu-id="c14ac-339">允许大厅中的参与者进入</span><span class="sxs-lookup"><span data-stu-id="c14ac-339">Admit participants from the lobby</span></span>|     <span data-ttu-id="c14ac-340">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-340">Y</span></span>     |     <span data-ttu-id="c14ac-341">N</span><span class="sxs-lookup"><span data-stu-id="c14ac-341">N</span></span>     |
|<span data-ttu-id="c14ac-342">更改其他参与者的角色</span><span class="sxs-lookup"><span data-stu-id="c14ac-342">Change the roles of other participants</span></span>     |     <span data-ttu-id="c14ac-343">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-343">Y</span></span>     |     <span data-ttu-id="c14ac-344">N</span><span class="sxs-lookup"><span data-stu-id="c14ac-344">N</span></span>     |
|<span data-ttu-id="c14ac-345">开始或停止录制</span><span class="sxs-lookup"><span data-stu-id="c14ac-345">Start or stop recording</span></span>     |     <span data-ttu-id="c14ac-346">Y</span><span class="sxs-lookup"><span data-stu-id="c14ac-346">Y</span></span>     |     <span data-ttu-id="c14ac-347">N</span><span class="sxs-lookup"><span data-stu-id="c14ac-347">N</span></span>     |

### <a name="change-roles-during-a-meeting"></a><span data-ttu-id="c14ac-348">在会议期间更改角色</span><span class="sxs-lookup"><span data-stu-id="c14ac-348">Change roles during a meeting</span></span>

<span data-ttu-id="c14ac-349">会议的每位参与者都会被分配演示者或与会者角色。</span><span class="sxs-lookup"><span data-stu-id="c14ac-349">Every participant in a meeting is assigned a role as presenter or attendee.</span></span> <span data-ttu-id="c14ac-350">参与者的角色控制他们在会议中可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c14ac-350">A participant's role controls what they can do while in a meeting.</span></span>

- <span data-ttu-id="c14ac-351">要更改参与者的角色，请在通话控件中单击或点击“**显示参与者**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-351">To change a participant's role, click or tap to **Show participants** in your call controls.</span></span> <span data-ttu-id="c14ac-352">右键单击需要更改其角色的参与者，然后选择“**设为与会者**”或“**设为演示者**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-352">Right-click on the participant whose role needs to be changed, and then select **Make an attendee** or **Make a presenter**.</span></span>

![“人脉”栏，显示一个菜单选项，“设为与会者”是菜单上的第四个选项。](media/edu-make-attendee-menu.png)

- <span data-ttu-id="c14ac-354">要快速访问你的会议选项并更改当前参与者和将来加入会议的任何人的会议角色设置，请在通话控件中单击或点击“**更多操作**”，然后单击“**显示会议详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-354">To quickly access your Meeting options and change the meeting role settings for both current participants and anyone joining your meeting in the future, click or tap **More actions** in your call controls, and then **Show meeting details**.</span></span> <span data-ttu-id="c14ac-355">可在会议的加入链接附近找到指向“**会议选项**”的链接。</span><span class="sxs-lookup"><span data-stu-id="c14ac-355">You can find the link to your **Meeting options** near the join link for the meeting.</span></span>

:::image type="content" source="media/edu-meeting-details.png" alt-text="会议窗口，右侧为会议详细信息窗格。":::

### <a name="mute-student-comments"></a><span data-ttu-id="c14ac-357">将学生评论静音</span><span class="sxs-lookup"><span data-stu-id="c14ac-357">Mute student comments</span></span>

<span data-ttu-id="c14ac-358">会议结束后，如果安排了频道会议，则可以阻止学生进一步发表评论。</span><span class="sxs-lookup"><span data-stu-id="c14ac-358">After the meeting, you can block students from commenting further if you scheduled a channel meeting.</span></span>

#### <a name="for-a-specific-meeting"></a><span data-ttu-id="c14ac-359">对于特定会议</span><span class="sxs-lookup"><span data-stu-id="c14ac-359">For a specific meeting</span></span>

<span data-ttu-id="c14ac-360">当你在频道中安排会议时，会议本身是一个频道帖子，并且会议聊天是帖子的副本。</span><span class="sxs-lookup"><span data-stu-id="c14ac-360">When you schedule a meeting in a channel, the meeting itself is a channel post, and the meeting chats are replicas of the post.</span></span> <span data-ttu-id="c14ac-361">作为团队所有者，你可对该帖子单击或点击“**更多操作**”，然后单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-361">As the team owner, you can click or tap **More actions** for that post, click **Edit**.</span></span>

:::image type="content" source="media/edu-meeting-edit.png" alt-text="在频道帖子上选择更多选项，可看到“编辑”菜单选项显示为弹出菜单上的第二个选项。":::

<span data-ttu-id="c14ac-363">编辑窗格上有一个下拉选项，可将该选项设置为“**你和审查方可以回复**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-363">On the edit pane, you have a dropdown option, where you can set that option to be **You and moderators can reply**.</span></span>

![在“编辑”菜单上，显示“每个人都可以回复”选项以及“你和审查方可以回复”选项旁边的复选标记。](media/edu-you-and-mods-reply.png)

### <a name="for-all-meetings-and-posts-of-a-team"></a><span data-ttu-id="c14ac-365">对于团队的所有会议和发布</span><span class="sxs-lookup"><span data-stu-id="c14ac-365">For all meetings and posts of a team</span></span>

<span data-ttu-id="c14ac-366">你可以控制学生何时可以在课堂团队和会议聊天中发布和回复。</span><span class="sxs-lookup"><span data-stu-id="c14ac-366">You can control when students can post and reply in the class team and meeting chats.</span></span> <span data-ttu-id="c14ac-367">单击或点击团队的“**更多操作**”，单击“**管理团队**”，转到“**成员**”，然后选择要静音的个人或“**将所有学生设为静音**”。</span><span class="sxs-lookup"><span data-stu-id="c14ac-367">Click or tap **More actions** of the team, click **Manage Team**, go to **Members**, and either select individuals to mute or **Mute all students**.</span></span>

![与会者会议列表，列表顶部显示了将单个学生设为静音或将所有学生设为静音的选项。](media/edu-student-mute.png)

## <a name="further-reading"></a><span data-ttu-id="c14ac-369">延伸阅读</span><span class="sxs-lookup"><span data-stu-id="c14ac-369">Further reading</span></span>

<span data-ttu-id="c14ac-370">请查看[使用 Teams 会议进行远程学习时保证学生安全](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)，了解有关保护学生的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c14ac-370">Please review the [Keeping students safe while using meetings in Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8) for more information on protecting students.</span></span>
