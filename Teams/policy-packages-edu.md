---
title: 用于 EDU 管理员的 Microsoft Teams 政策包
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1.keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的策略程序包。
ms.openlocfilehash: 922481747e83b8885641185b8a7e4fa65bb2a1bd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708658"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a><span data-ttu-id="bb438-103">用于 EDU 管理员的 Microsoft Teams 政策包</span><span class="sxs-lookup"><span data-stu-id="bb438-103">Microsoft Teams policy packages for EDU admins</span></span>

<span data-ttu-id="bb438-104">Microsoft 团队中的策略程序包会收集预定义策略和策略设置，你可以分配给你的机构中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="bb438-104">A policy package in Microsoft Teams collects predefined policies and policy settings that you can assign to users with similar roles in your institution.</span></span> <span data-ttu-id="bb438-105">策略程序包简化、优化和帮助在管理策略时提供一致性。</span><span class="sxs-lookup"><span data-stu-id="bb438-105">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="bb438-106">在正常做法中，你将为每个用户分配一个策略程序包，并根据需要重新定义每个程序包中的策略以满足该用户组的需求。</span><span class="sxs-lookup"><span data-stu-id="bb438-106">In normal practice, you assign each of your users a policy package, and as necessary redefine the policies in each package to suit the needs of that user group.</span></span> <span data-ttu-id="bb438-107">更新程序包中的设置时，分配到该程序包的所有用户都将更改为批量更新。</span><span class="sxs-lookup"><span data-stu-id="bb438-107">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="bb438-108">通常，教育机构有许多具有独特需求的用户类型，具体取决于学生的年龄和成熟度。</span><span class="sxs-lookup"><span data-stu-id="bb438-108">Educational institutions in general have many user types with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="bb438-109">例如，你可能希望授予教师和教职员工对 Microsoft 团队的完全访问权限，但想要限制 Microsoft 团队功能，以便学生能够鼓励安全且专注于学习环境。</span><span class="sxs-lookup"><span data-stu-id="bb438-109">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="bb438-110">你可以使用策略程序包根据你的学校社区中不同 cohorts 的需求来调整设置。</span><span class="sxs-lookup"><span data-stu-id="bb438-110">You can use policy packages to tailor settings based on the needs of different cohorts in your school community.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="bb438-111">什么是策略包？</span><span class="sxs-lookup"><span data-stu-id="bb438-111">What is a policy package?</span></span>

<span data-ttu-id="bb438-112">策略程序包允许你控制 Microsoft 团队的功能，这些功能允许或限制 Microsoft 团队针对你的组织中的特定人员集使用。</span><span class="sxs-lookup"><span data-stu-id="bb438-112">Policy packages let you control Microsoft Teams features that allow or restrict Microsoft Teams use for  specific sets of people in your organization.</span></span> <span data-ttu-id="bb438-113">每个策略程序包均围绕用户角色进行设计，其中包含支持该角色的典型活动的预定义策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="bb438-113">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span>

<span data-ttu-id="bb438-114">策略程序包的预定义策略：</span><span class="sxs-lookup"><span data-stu-id="bb438-114">Policy packages predefine policies for:</span></span>
- <span data-ttu-id="bb438-115">消息传递</span><span class="sxs-lookup"><span data-stu-id="bb438-115">Messaging</span></span>
- <span data-ttu-id="bb438-116">会议</span><span class="sxs-lookup"><span data-stu-id="bb438-116">Meetings</span></span>
- <span data-ttu-id="bb438-117">应用设置</span><span class="sxs-lookup"><span data-stu-id="bb438-117">App Setup</span></span>
- <span data-ttu-id="bb438-118">通话</span><span class="sxs-lookup"><span data-stu-id="bb438-118">Calling</span></span>
- <span data-ttu-id="bb438-119">实时事件</span><span class="sxs-lookup"><span data-stu-id="bb438-119">Live events</span></span>

<span data-ttu-id="bb438-120">Microsoft 团队当前包含以下策略包：</span><span class="sxs-lookup"><span data-stu-id="bb438-120">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="bb438-121">Microsoft 团队管理中心中列出的程序包名称</span><span class="sxs-lookup"><span data-stu-id="bb438-121">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="bb438-122">最适合用于</span><span class="sxs-lookup"><span data-stu-id="bb438-122">Best used for</span></span>  |<span data-ttu-id="bb438-123">说明</span><span class="sxs-lookup"><span data-stu-id="bb438-123">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="bb438-124">Education_Teacher</span><span class="sxs-lookup"><span data-stu-id="bb438-124">Education_Teacher</span></span>| <span data-ttu-id="bb438-125">教育版和员工</span><span class="sxs-lookup"><span data-stu-id="bb438-125">Educators and staff</span></span>| <span data-ttu-id="bb438-126">使用此组策略和策略设置向组织内的教师和员工授予通过 Microsoft 团队的聊天、通话和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="bb438-126">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="bb438-127">Education_PrimaryStudent</span><span class="sxs-lookup"><span data-stu-id="bb438-127">Education_PrimaryStudent</span></span> | <span data-ttu-id="bb438-128">主要学校过时的学生</span><span class="sxs-lookup"><span data-stu-id="bb438-128">Primary school aged students</span></span>  | <span data-ttu-id="bb438-129">较旧的，您的机构内的主要学校过期学生可能需要 Microsoft 团队中的更多限制。</span><span class="sxs-lookup"><span data-stu-id="bb438-129">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="bb438-130">使用此组策略和策略设置来限制会议创建和管理、聊天管理和私人通话等功能。</span><span class="sxs-lookup"><span data-stu-id="bb438-130">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="bb438-131">Education_SecondaryStudent</span><span class="sxs-lookup"><span data-stu-id="bb438-131">Education_SecondaryStudent</span></span>| <span data-ttu-id="bb438-132">次要学校过期的学生</span><span class="sxs-lookup"><span data-stu-id="bb438-132">Secondary school aged students</span></span> | <span data-ttu-id="bb438-133">在你的机构内的次要学校过时学生可能需要 Microsoft 团队中的更多限制。</span><span class="sxs-lookup"><span data-stu-id="bb438-133">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="bb438-134">使用此组策略和策略设置来限制会议创建和管理、聊天管理和私人通话等功能。</span><span class="sxs-lookup"><span data-stu-id="bb438-134">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="bb438-135">Education_HigherEducationStudent</span><span class="sxs-lookup"><span data-stu-id="bb438-135">Education_HigherEducationStudent</span></span> | <span data-ttu-id="bb438-136">高等教育学生</span><span class="sxs-lookup"><span data-stu-id="bb438-136">Higher education students</span></span> | <span data-ttu-id="bb438-137">更高的教育 intuition 在您的内学生可能比较小的学生需要的限制更少，但建议您采取一些限制。</span><span class="sxs-lookup"><span data-stu-id="bb438-137">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="bb438-138">你可以使用这组策略和策略设置授予你的组织内的聊天、通话和会议的访问权限，但限制学生如何将 Microsoft 团队与外部参与者配合使用。</span><span class="sxs-lookup"><span data-stu-id="bb438-138">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|||

<span data-ttu-id="bb438-139">每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="bb438-139">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="bb438-140">例如，当你将 Education_Teacher 策略包分配给学校中的教师时，将为程序包中的每个策略创建一个名为 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="bb438-140">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 策略程序包的屏幕截图](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="bb438-142">如果你决定教师和管理支持人员需要不同的策略，则可以重新使用现有程序包的用途：标识你当前未使用的程序包，并将设置更改为适用于该组的设置。</span><span class="sxs-lookup"><span data-stu-id="bb438-142">If you decide that teachers and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="bb438-143">您可能需要向自己做笔记，其中有哪些组拥有哪个程序包，但这是唯一重新安排程序包的障碍。</span><span class="sxs-lookup"><span data-stu-id="bb438-143">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="why-use-policy-packages"></a><span data-ttu-id="bb438-144">为什么使用策略程序包</span><span class="sxs-lookup"><span data-stu-id="bb438-144">Why use policy packages</span></span>

<span data-ttu-id="bb438-145">如果您的机构拥有成百上千的用户，您可能会问自己： "为什么要花时间为所有用户分配一个程序包？"</span><span class="sxs-lookup"><span data-stu-id="bb438-145">If your institution has hundreds, or even thousands of users, you may be asking yourself: "Why take the time to assign one package or another to all those users?"</span></span>

<span data-ttu-id="bb438-146">将程序包分配给成百上千用户是管理时间方面的投资，无需任何疑问。</span><span class="sxs-lookup"><span data-stu-id="bb438-146">Assigning packages to hundreds of users is an investment in administrative time, without question.</span></span> <span data-ttu-id="bb438-147">投资的一个重要之处是，他们在一段时间内而不是立即支付。</span><span class="sxs-lookup"><span data-stu-id="bb438-147">An important thing about investments is that they pay off over time, rather than immediately.</span></span>

<span data-ttu-id="bb438-148">在教育环境中，有许多具有相同或类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="bb438-148">In an educational environment, there are many users with the same or similar roles.</span></span> <span data-ttu-id="bb438-149">当您以同样的方式管理用户体验时，您可以花费更少的时间进行工作。</span><span class="sxs-lookup"><span data-stu-id="bb438-149">You spend less effort over time when you manage their user experience the same way.</span></span> <span data-ttu-id="bb438-150">软件包组特定于机构中各种角色的一组策略。</span><span class="sxs-lookup"><span data-stu-id="bb438-150">Packages group a set of policies specific to the various roles in the institution.</span></span> <span data-ttu-id="bb438-151">具有相同许可证但角色不同的用户可以根据其角色分配相关策略，这比调整单个用户的策略更有效。</span><span class="sxs-lookup"><span data-stu-id="bb438-151">Users with the same license, but different roles, can have relevant policies assigned based on their role, which is more efficient than tweaking policies for individual users.</span></span>

<span data-ttu-id="bb438-152">一旦机构中的所有用户都已分类到组中，并且应用了程序包，从随后的用户管理程序包设置就是为分配到该程序包的所有用户更改程序包设置。</span><span class="sxs-lookup"><span data-stu-id="bb438-152">Once you have all users in the institution sorted into groups and have packages applied, managing them from then on is a matter of changing the package settings once for all users assigned to the package.</span></span> <span data-ttu-id="bb438-153">你可以选择在将用户分配给程序包之前或之后对包内的策略进行微调。</span><span class="sxs-lookup"><span data-stu-id="bb438-153">You can choose to fine-tune the policies within a package before or after assigning users to the package.</span></span>

<span data-ttu-id="bb438-154">请参阅在[Microsoft 团队中管理策略程序包](manage-policy-packages.md)，了解有关为单个用户分配程序包、向多达20个用户批量分配程序包以及管理和更新与每个程序包关联的策略的分步指导。</span><span class="sxs-lookup"><span data-stu-id="bb438-154">See [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 20 users, and managing and updating the policies linked to each package.</span></span>
