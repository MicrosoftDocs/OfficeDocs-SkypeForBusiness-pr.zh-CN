---
title: 会议配置新建或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 会议配置设置定义了用户的连接体验由用户计划的会议。 这些设置仅应用于已安排的会议。 它们不适用于通过单击客户端中的立即开会选项创建的特别会议。
ms.openlocfilehash: af9a1cca6a34320a7e2bd2ba53b08040351f784e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="d157d-105">会议配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="d157d-105">Meeting Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="d157d-p102">会议配置设置可定义用户预定会议的用户加入体验。这些设置只适用于预定的会议，不适用于通过单击客户端中的“**现在开会**”选项创建的临时会议。</span><span class="sxs-lookup"><span data-stu-id="d157d-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="d157d-109">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="d157d-109">UI Reference</span></span>

<span data-ttu-id="d157d-110">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="d157d-110">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="d157d-111">**作用域**标识要创建或修改的会议配置作用域： 全局站点或池。</span><span class="sxs-lookup"><span data-stu-id="d157d-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>
    
- <span data-ttu-id="d157d-112">**名称**会议配置默认情况下，命名和名称不能更改。</span><span class="sxs-lookup"><span data-stu-id="d157d-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>
    
- <span data-ttu-id="d157d-113">**PSTN 呼叫者绕过大厅**选中此复选框可自动为会议公用交换的电话网络 (PSTN) 电话线上承认正在拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="d157d-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="d157d-114">清除此复选框可以路由 PSTN 呼叫到会议大厅，它们位于保留直到会议演示者授予他们对会议的访问。</span><span class="sxs-lookup"><span data-stu-id="d157d-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>
    
- <span data-ttu-id="d157d-115">**指定作为演示者**选择的类别 （除了会议组织者） 的用户被自动指定为演示者加入会议。</span><span class="sxs-lookup"><span data-stu-id="d157d-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="d157d-116">无论设置此演示者可以将显式指定为演示者时安排的会议，或它们可以明确提升为演示者在会议过程。</span><span class="sxs-lookup"><span data-stu-id="d157d-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="d157d-117">包含以下选项：</span><span class="sxs-lookup"><span data-stu-id="d157d-117">The options are:</span></span>
    
  - <span data-ttu-id="d157d-118">**无**如果没有其他组织者人被自动指定为演示者，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="d157d-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>
    
  - <span data-ttu-id="d157d-119">**公司**选择此选项可自动将只有您的组织的成员指定为演示者。</span><span class="sxs-lookup"><span data-stu-id="d157d-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>
    
  - <span data-ttu-id="d157d-120">**每个人都**选择此选项可自动指定任何人成为演示者。</span><span class="sxs-lookup"><span data-stu-id="d157d-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>
    
- <span data-ttu-id="d157d-121">**默认情况下分配会议类型**此设置用于控制是否 Outlook 会议外接程序总是安排会议通过组织者的分配会议，这意味着总是安排会议具有相同连接 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="d157d-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="d157d-122">选中此复选框可以始终使用同一个连接 URL 的计划的会议。</span><span class="sxs-lookup"><span data-stu-id="d157d-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="d157d-123">清除此复选框可以为每个会议使用不同连接 URL。</span><span class="sxs-lookup"><span data-stu-id="d157d-123">Clear this check box to use a different join URL for each conference.</span></span>
    
- <span data-ttu-id="d157d-124">**Admit 默认的匿名用户**选中此复选框如果匿名 （即未经身份验证的） 都允许用户，默认情况下能够参加会议。</span><span class="sxs-lookup"><span data-stu-id="d157d-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="d157d-125">如果允许匿名用户将不能够参加会议，默认情况下，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="d157d-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>
    
- <span data-ttu-id="d157d-126">**徽标的 URL**键入具有要用于自定义会议邀请的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="d157d-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>
    
- <span data-ttu-id="d157d-127">**帮助的 URL**键入用户可用于获取有关加入会议帮助网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="d157d-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>
    
- <span data-ttu-id="d157d-128">**法律文本的 URL**键入具有法律信息的网站的 URL 和会议的免责声明。</span><span class="sxs-lookup"><span data-stu-id="d157d-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>
    
- <span data-ttu-id="d157d-129">**自定义页脚文本**键入的文本用于自定义会议邀请。</span><span class="sxs-lookup"><span data-stu-id="d157d-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>
    
<span data-ttu-id="d157d-130">有关使用会议配置的详细信息，请参阅[创建或修改会议配置设置集合](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)操作文档中。</span><span class="sxs-lookup"><span data-stu-id="d157d-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="d157d-131">大型的会议设置会议配置有关的详细信息，请参见[设置了支持大型会议](http://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)的规划文档中。</span><span class="sxs-lookup"><span data-stu-id="d157d-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](http://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>
  

