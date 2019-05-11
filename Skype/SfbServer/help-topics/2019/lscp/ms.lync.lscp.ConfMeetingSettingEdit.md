---
title: 会议配置创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: 会议配置设置中定义的用户安排的会议的用户加入体验。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的立即开会选项创建的临时会议。
ms.openlocfilehash: 05613fb9c8df89bb9c7efc5fe7bfced78ca12574
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891584"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="2fc3f-105">会议配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="2fc3f-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="2fc3f-p102">会议配置设置可定义用户预定会议的用户加入体验。这些设置只适用于预定的会议，不适用于通过单击客户端中的“**现在开会**”选项创建的临时会议。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2fc3f-109">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="2fc3f-109">UI Reference</span></span>

<span data-ttu-id="2fc3f-110">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2fc3f-111">**范围**标识您正在创建或修改的会议配置的范围： 全局、 站点或池。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="2fc3f-112">**名称**会议配置已命名默认情况下，且不能更改名称。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="2fc3f-113">**PSTN 呼叫者绕过大厅**选中此复选框，以自动向会议通过公用电话交换网 (pstn) 电话线路允许拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="2fc3f-114">清除，直到会议演示者授予其加入会议的访问权限，它们位于保留路由 PSTN 呼叫者到会议会议厅，此复选框。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="2fc3f-115">**指定为演示者**选择当用户加入会议时自动指定为演示者 （除了会议组织者） 用户的类别。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="2fc3f-116">此设置，无论演示者可以将明确指定为演示者，计划会议或他们可以显式提升为演示者在会议过程时。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="2fc3f-117">选项如下：</span><span class="sxs-lookup"><span data-stu-id="2fc3f-117">The options are:</span></span>

  - <span data-ttu-id="2fc3f-118">**无**如果组织者以外任何人自动指定为演示者，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="2fc3f-119">**公司**选择此选项可自动将只有您的组织的成员指定为演示者。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="2fc3f-120">**所有人**选择此选项可自动指定任何人成为演示者。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="2fc3f-121">**默认情况下已分配会议类型**是否 Outlook 会议外接程序始终安排会议使用组织者的分配会议此设置控制，这意味着始终安排会议具有相同的联接 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="2fc3f-122">选中此复选框具有始终使用相同的 URL 加入安排的会议。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="2fc3f-123">清除此复选框，每个会议都使用不同的联接 URL。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="2fc3f-124">**默认情况下 Admit 匿名用户**选中此复选框如果匿名 （即，未经身份验证） 允许用户默认情况下参加会议。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="2fc3f-125">如果匿名用户不允许参加会议默认情况下，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="2fc3f-126">**徽标 URL**键入要用于自定义会议邀请的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="2fc3f-127">**帮助 URL**键入用户可从中获得加入会议的网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="2fc3f-128">**法律文本 URL**键入的法律信息的网站的 URL 和会议免责声明。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="2fc3f-129">**自定义页脚文本**键入要在自定义会议邀请中使用的文本。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="2fc3f-p107">有关使用会议配置的详细信息，请参阅操作文档中的[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)。有关设置大型会议的会议配置的详细信息，请参阅规划文档中的[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2fc3f-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


