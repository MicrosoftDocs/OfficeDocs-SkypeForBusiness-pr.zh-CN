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
ms.openlocfilehash: 64be355da30feb3c629569f583897353c21cfa37
ms.sourcegitcommit: 481d18b76304adfa340b5f1b2f1b7965e9ff4993
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586615"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="4ecac-103">Teams 教育版中的分配</span><span class="sxs-lookup"><span data-stu-id="4ecac-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="4ecac-104">"用于教育的团队中的工作分配和成绩" 功能允许教师向学生分配任务、工作或测验。</span><span class="sxs-lookup"><span data-stu-id="4ecac-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="4ecac-105">教师可以管理工作分配日程表、说明、添加要提交的资源、量规的成绩等。</span><span class="sxs-lookup"><span data-stu-id="4ecac-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="4ecac-106">他们还可以在 "成绩" 选项卡中跟踪课堂和单个学生的进度。</span><span class="sxs-lookup"><span data-stu-id="4ecac-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="4ecac-107">[了解有关团队教育版中的作业和成绩的详细信息](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。</span><span class="sxs-lookup"><span data-stu-id="4ecac-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="4ecac-108">有关不同平台上的团队工作分配的详细信息，请参阅 [团队功能按平台](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="4ecac-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="4ecac-109">Microsoft 团队管理中心中的工作分配集成</span><span class="sxs-lookup"><span data-stu-id="4ecac-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="4ecac-110">使用 Microsoft 团队管理中心中的 "管理员" 设置，您可以打开或关闭您的组织及其学生的教育功能。</span><span class="sxs-lookup"><span data-stu-id="4ecac-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="4ecac-111">以下是与作业相关的设置：</span><span class="sxs-lookup"><span data-stu-id="4ecac-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="4ecac-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="4ecac-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="4ecac-113">每周监护人电子邮件摘要</span><span class="sxs-lookup"><span data-stu-id="4ecac-113">Weekly guardian email digest</span></span>


<span data-ttu-id="4ecac-114">监护人电子邮件将每个周末发送给家长或监护人。</span><span class="sxs-lookup"><span data-stu-id="4ecac-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="4ecac-115">该电子邮件包含有关上一周和即将到来的周的作业的信息。</span><span class="sxs-lookup"><span data-stu-id="4ecac-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="4ecac-116">可使用 [学校数据同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync)设置父和监护人同步。</span><span class="sxs-lookup"><span data-stu-id="4ecac-116">The Parent and Guardian Sync can be setup using [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="4ecac-117">通过 SDS 中的家长和监护人同步导入父联系人信息。</span><span class="sxs-lookup"><span data-stu-id="4ecac-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="4ecac-118">有关如何启用家长和监护人同步的说明，请参阅 [启用家长和监护人同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。</span><span class="sxs-lookup"><span data-stu-id="4ecac-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="4ecac-119">在 Microsoft 团队管理中心中启用监护人设置，因为默认情况下该设置处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="4ecac-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="4ecac-120">这将使教师能够发送每周摘要。</span><span class="sxs-lookup"><span data-stu-id="4ecac-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4ecac-121">教师可以通过在其自己的个人课堂团队 (**工作分配设置 > 父/监护人电子邮件**) 中取消摘要，从而选择退出摘要。</span><span class="sxs-lookup"><span data-stu-id="4ecac-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="4ecac-122">若要验证父母是否收到电子邮件，必须满足以下三项条件：</span><span class="sxs-lookup"><span data-stu-id="4ecac-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="4ecac-123">附加到 SDS 中的学生档案并标记为 _家长_ 或 _监护人_ 的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4ecac-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="4ecac-124">有关详细信息，请参阅 [父和监护人同步文件格式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)。</span><span class="sxs-lookup"><span data-stu-id="4ecac-124">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="4ecac-125">学生至少属于一个类，其中的电子邮件未由教师在 [作业设置](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中禁用。</span><span class="sxs-lookup"><span data-stu-id="4ecac-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="4ecac-126">该电子邮件将包含有关前一周或下一周的截止日期的作业的信息。</span><span class="sxs-lookup"><span data-stu-id="4ecac-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="4ecac-127">此功能的默认设置为 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="4ecac-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="4ecac-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="4ecac-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="4ecac-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="4ecac-129">MakeCode</span></span>
<span data-ttu-id="4ecac-130">Microsoft MakeCode 是一种基于块的编码平台，让所有学生都能使用电脑科学。</span><span class="sxs-lookup"><span data-stu-id="4ecac-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="4ecac-131">MakeCode 是一种受 Microsoft [使用条款](https://go.microsoft.com/fwlink/?LinkID=206977) 和 [隐私](https://go.microsoft.com/fwlink/?LinkId=521839) 政策制约的 microsoft 产品。</span><span class="sxs-lookup"><span data-stu-id="4ecac-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="4ecac-132">此功能的默认设置为 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="4ecac-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="4ecac-133">若要启用团队中的 MakeCode 作业，请转到 **团队管理中心**，导航到 " **作业** " 部分，然后将 MakeCode 切换选项转换为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="4ecac-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="4ecac-134">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4ecac-134">Click **Save**.</span></span> <span data-ttu-id="4ecac-135">等待几小时，这些设置生效。</span><span class="sxs-lookup"><span data-stu-id="4ecac-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="4ecac-136">有关此功能的工作原理的详细信息，请参阅此 [视频演示](https://makecode.com/blog/teams/teams-assignments)。</span><span class="sxs-lookup"><span data-stu-id="4ecac-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="4ecac-137">[了解有关 MakeCode 的详细信息](https://aka.ms/makecode)。</span><span class="sxs-lookup"><span data-stu-id="4ecac-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="4ecac-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="4ecac-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="4ecac-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="4ecac-139">Turnitin</span></span>

<span data-ttu-id="4ecac-140">[Turnitin](https://www.turnitin.com/) 是一种学术的完整性服务。</span><span class="sxs-lookup"><span data-stu-id="4ecac-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="4ecac-141">这是由其自身条款和隐私政策制约的第三方产品或服务。</span><span class="sxs-lookup"><span data-stu-id="4ecac-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="4ecac-142">您负责使用第三方产品和服务。</span><span class="sxs-lookup"><span data-stu-id="4ecac-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="4ecac-143">此功能的默认设置为- **关闭**。。</span><span class="sxs-lookup"><span data-stu-id="4ecac-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="4ecac-144">若要为你的组织启用 Turnitin，你将需要 Turnitin 订阅。</span><span class="sxs-lookup"><span data-stu-id="4ecac-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="4ecac-145">然后，你可以输入以下信息，这些信息可以在你的 Turnitin 管理控制台中找到：</span><span class="sxs-lookup"><span data-stu-id="4ecac-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="4ecac-146">**TurnitinApiKey**：这是在管理控制台中的集成下发现的32字符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4ecac-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="4ecac-147">**TurnitinApiUrl**：这是你的 Turnitin 管理员控制台的 HTTPS URL。</span><span class="sxs-lookup"><span data-stu-id="4ecac-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="4ecac-148">下面是帮助你获取此信息的一些说明。</span><span class="sxs-lookup"><span data-stu-id="4ecac-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="4ecac-149">**TurnitinApiUrl** 是您的管理员控制台的主机地址。</span><span class="sxs-lookup"><span data-stu-id="4ecac-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="4ecac-150">上例 `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="4ecac-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="4ecac-151">管理员控制台是你可以在其中创建集成和与集成相关联的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="4ecac-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="4ecac-152">从侧菜单中选择 " **集成** "，然后选择 " **添加集成** " 并为集成提供名称。</span><span class="sxs-lookup"><span data-stu-id="4ecac-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![显示添加新集成的屏幕截图](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="4ecac-154">按照提示操作后，将为您提供 **TurnitinApiKey** 。</span><span class="sxs-lookup"><span data-stu-id="4ecac-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="4ecac-155">复制 API 密钥并将其粘贴到 Microsoft 团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="4ecac-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="4ecac-156">这是唯一可以查看密钥的时候。</span><span class="sxs-lookup"><span data-stu-id="4ecac-156">This is the only time you can view the key.</span></span>

![显示复制 API 密钥的屏幕截图](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="4ecac-158">单击管理中心中的 " **保存** " 按钮以使用此设置时，请等待几个小时，这些设置才会生效。</span><span class="sxs-lookup"><span data-stu-id="4ecac-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

