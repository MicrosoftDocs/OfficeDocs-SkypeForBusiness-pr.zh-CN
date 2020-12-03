---
title: Teams 的分配
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 了解如何在 "团队教育版" 的 "Microsoft 团队管理中心" 中管理作业。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561048"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="18e11-103">Teams 教育版中的分配</span><span class="sxs-lookup"><span data-stu-id="18e11-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="18e11-104">作业是指分配给课程中的学生或团队成员的任务或工作单元，作为其研究的一部分。</span><span class="sxs-lookup"><span data-stu-id="18e11-104">Assignments are tasks or units of work assigned to a student or team member in a class as part of their study.</span></span> <span data-ttu-id="18e11-105">可以在团队类中创建作业。</span><span class="sxs-lookup"><span data-stu-id="18e11-105">You can create assignments within your Teams class.</span></span>

<span data-ttu-id="18e11-106">[了解有关作业的详细信息](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。</span><span class="sxs-lookup"><span data-stu-id="18e11-106">[Learn more about Assignments](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="18e11-107">有关不同平台上的团队工作分配的详细信息，请参阅 [团队功能按平台](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="18e11-107">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="18e11-108">Microsoft 团队管理中心中的作业</span><span class="sxs-lookup"><span data-stu-id="18e11-108">Assignments in the Microsoft Teams admin center</span></span>

<span data-ttu-id="18e11-109">使用 Microsoft 团队管理中心中的管理员设置，你可以打开或关闭以下功能，以便供你的组织内的学生和教师使用。</span><span class="sxs-lookup"><span data-stu-id="18e11-109">With the admin settings in Microsoft Teams admin center, you can turn the following features on or off to be available for students and teachers within your organization.</span></span> <span data-ttu-id="18e11-110">以下是与作业相关的设置：</span><span class="sxs-lookup"><span data-stu-id="18e11-110">The following are settings related to Assignments:</span></span>

<span data-ttu-id="18e11-111"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="18e11-111"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="18e11-112">每周监护人电子邮件摘要</span><span class="sxs-lookup"><span data-stu-id="18e11-112">Weekly guardian email digest</span></span>

<span data-ttu-id="18e11-113">该电子邮件将包含有关上一周和未来一周的作业的信息，并将通过周末发送。</span><span class="sxs-lookup"><span data-stu-id="18e11-113">The emails will contain information about assignments from the previous week and for the upcoming week, and will be sent over the weekend.</span></span> <span data-ttu-id="18e11-114">可在此处找到有关电子邮件内容的信息。</span><span class="sxs-lookup"><span data-stu-id="18e11-114">Information about the email content can be found here.</span></span> <span data-ttu-id="18e11-115">通过使用 [学校数据同步 (SDS) ](https://docs.microsoft.com/schooldatasync/)，管理员需要设置和更新电子邮件。</span><span class="sxs-lookup"><span data-stu-id="18e11-115">The emails need to be set up and updated by the admins by using [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span></span> <span data-ttu-id="18e11-116">此功能会自动从学校的学生信息系统 (SIS) 中为学生海报的团队填充课程。</span><span class="sxs-lookup"><span data-stu-id="18e11-116">This feature automatically populates classes for Teams with student rosters from the school's student information system (SIS).</span></span> <span data-ttu-id="18e11-117">启用此功能的步骤包括：</span><span class="sxs-lookup"><span data-stu-id="18e11-117">The steps to enable this feature are:</span></span>

1. <span data-ttu-id="18e11-118">通过 SDS 中的家长和监护人同步导入父联系人信息。</span><span class="sxs-lookup"><span data-stu-id="18e11-118">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="18e11-119">有关如何启用家长和监护人同步的说明，请参阅 [启用家长和监护人同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。</span><span class="sxs-lookup"><span data-stu-id="18e11-119">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="18e11-120">在 Microsoft 团队管理中心中启用监护人设置，因为默认情况下该设置处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="18e11-120">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="18e11-121">这将使教师能够发送每周摘要。</span><span class="sxs-lookup"><span data-stu-id="18e11-121">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="18e11-122">教师可以通过在其自己的个人课堂团队 (**工作分配设置 > 父/监护人电子邮件**) 中取消摘要，从而选择退出摘要。</span><span class="sxs-lookup"><span data-stu-id="18e11-122">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="18e11-123">若要验证父母是否收到电子邮件，必须满足以下三项条件：</span><span class="sxs-lookup"><span data-stu-id="18e11-123">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="18e11-124">附加到 SDS 中的学生档案并标记为 _家长_ 或 _监护人_ 的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="18e11-124">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="18e11-125">有关详细信息，请参阅 [父和监护人同步文件格式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)。</span><span class="sxs-lookup"><span data-stu-id="18e11-125">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="18e11-126">学生至少属于一个类，其中的电子邮件未由教师在 [作业设置](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中禁用。</span><span class="sxs-lookup"><span data-stu-id="18e11-126">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="18e11-127">该电子邮件将包含有关前一周或下一周的截止日期的作业的信息。</span><span class="sxs-lookup"><span data-stu-id="18e11-127">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="18e11-128">默认情况下，此设置处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="18e11-128">This setting is off by default.</span></span>


<span data-ttu-id="18e11-129"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="18e11-129"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="18e11-130">MakeCode</span><span class="sxs-lookup"><span data-stu-id="18e11-130">MakeCode</span></span>
<span data-ttu-id="18e11-131">Microsoft MakeCode 是一种基于块的编码平台，让所有学生都能使用电脑科学。</span><span class="sxs-lookup"><span data-stu-id="18e11-131">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="18e11-132">MakeCode 是一种受 Microsoft [使用条款](https://go.microsoft.com/fwlink/?LinkID=206977) 和 [隐私](https://go.microsoft.com/fwlink/?LinkId=521839) 政策制约的 microsoft 产品。</span><span class="sxs-lookup"><span data-stu-id="18e11-132">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="18e11-133">默认情况下，此设置处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="18e11-133">This setting is off by default.</span></span> <span data-ttu-id="18e11-134">若要启用团队中的 MakeCode 作业，请在 " **团队管理中心**" 中，导航到 " **作业** " 部分，然后将 MakeCode 切换选项转换为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="18e11-134">To enable MakeCode assignments in Teams, in the **Teams Admin Center**, navigate to the **Assignments** section and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="18e11-135">单击 " **保存** "，并允许几个小时才能使这些设置生效。</span><span class="sxs-lookup"><span data-stu-id="18e11-135">Click **Save** and allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="18e11-136">有关此功能的工作原理的详细信息，请参阅此 [视频演示](https://makecode.com/blog/teams/teams-assignments)。</span><span class="sxs-lookup"><span data-stu-id="18e11-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="18e11-137">[了解有关 MakeCode 的详细信息](https://aka.ms/makecode)。</span><span class="sxs-lookup"><span data-stu-id="18e11-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="18e11-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="18e11-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="18e11-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="18e11-139">Turnitin</span></span>

<span data-ttu-id="18e11-140">Turnitin 是一种 plagiarism 检测服务。</span><span class="sxs-lookup"><span data-stu-id="18e11-140">Turnitin is a plagiarism detection service.</span></span> <span data-ttu-id="18e11-141">这是由其自身条款和隐私政策制约的第三方产品或服务。</span><span class="sxs-lookup"><span data-stu-id="18e11-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="18e11-142">您负责使用第三方产品和服务。</span><span class="sxs-lookup"><span data-stu-id="18e11-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="18e11-143">默认情况下，此设置处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="18e11-143">This setting is off by default.</span></span>

<span data-ttu-id="18e11-144">为了成功为你的组织启用 Turnitin，你需要已拥有 Turnitin 订阅。</span><span class="sxs-lookup"><span data-stu-id="18e11-144">In order to successfully enable Turnitin for your organization, you will need to already have a Turnitin subscription.</span></span> <span data-ttu-id="18e11-145">你将需要输入以下附加信息，这些信息可在 Turnitin 管理控制台中找到：</span><span class="sxs-lookup"><span data-stu-id="18e11-145">You will need to enter the following additional information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="18e11-146">**TurnitinApiKey**：这是在管理控制台中的集成下发现的32字符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="18e11-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="18e11-147">**TurnitinApiUrl**：这是你的 Turnitin 管理员控制台的 HTTPS URL。</span><span class="sxs-lookup"><span data-stu-id="18e11-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="18e11-148">下面是帮助你获取此信息的一些说明。</span><span class="sxs-lookup"><span data-stu-id="18e11-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="18e11-149">**TurnitinApiUrl** 是您的管理员控制台的主机地址。</span><span class="sxs-lookup"><span data-stu-id="18e11-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="18e11-150">上例 `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="18e11-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="18e11-151">管理员控制台是你可以在其中创建集成和与集成相关联的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="18e11-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="18e11-152">从侧菜单中选择 " **集成** "，然后选择 " **添加集成** " 并为集成提供名称。</span><span class="sxs-lookup"><span data-stu-id="18e11-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![显示添加新集成的屏幕截图](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="18e11-154">按照提示操作后，将为您提供 **TurnitinApiKey** 。</span><span class="sxs-lookup"><span data-stu-id="18e11-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="18e11-155">复制 API 密钥并将其粘贴到 Microsoft 团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="18e11-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="18e11-156">这是唯一可以查看密钥的时候。</span><span class="sxs-lookup"><span data-stu-id="18e11-156">This is the only time you can view the key.</span></span>

![显示复制 API 密钥的屏幕截图](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="18e11-158">单击管理中心中的 " **保存** " 按钮后，此设置才会生效。</span><span class="sxs-lookup"><span data-stu-id="18e11-158">Upon clicking the **Save** button in the admin center for this setting, please allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="18e11-159">准备好开始使用团队中的 Turnitin 集成？</span><span class="sxs-lookup"><span data-stu-id="18e11-159">Ready to start using the Turnitin integration in Teams?</span></span> <span data-ttu-id="18e11-160">注册 [早期访问计划](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)。</span><span class="sxs-lookup"><span data-stu-id="18e11-160">Sign up for the [early access program](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span></span>
