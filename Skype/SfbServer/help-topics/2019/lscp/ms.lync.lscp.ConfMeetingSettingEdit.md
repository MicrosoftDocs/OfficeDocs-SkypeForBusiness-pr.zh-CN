---
title: 会议配置新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: 会议配置设置为用户计划的会议定义用户加入体验。 这些设置仅适用于计划的会议。 它们不适用于通过单击客户端中的 "立即开会" 选项创建的临时会议。
ms.openlocfilehash: 7c86415d08d2b48d542334ac74bc1316102e592d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796311"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="57665-105">会议配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="57665-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="57665-p102">会议配置设置可定义用户预定会议的用户加入体验。这些设置只适用于预定的会议，不适用于通过单击客户端中的“**现在开会**”选项创建的临时会议。</span><span class="sxs-lookup"><span data-stu-id="57665-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="57665-109">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="57665-109">UI Reference</span></span>

<span data-ttu-id="57665-110">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="57665-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="57665-111">**范围**标识要创建或修改的会议配置的范围：全局、网站或池。</span><span class="sxs-lookup"><span data-stu-id="57665-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="57665-112">**名称**会议配置默认命名，无法更改名称。</span><span class="sxs-lookup"><span data-stu-id="57665-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="57665-113">**PSTN 呼叫者绕过大厅**选中此复选框以自动允许通过公共交换电话网络（PSTN）电话线路拨入会议的用户。</span><span class="sxs-lookup"><span data-stu-id="57665-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="57665-114">清除此复选框可将 PSTN 呼叫者路由到会议厅，在会议演示者授予他们访问会议的权限之前，这些呼叫者将处于暂停状态。</span><span class="sxs-lookup"><span data-stu-id="57665-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="57665-115">**指定为演示者**选择在加入会议时自动指定为演示者的用户的类别（会议组织者除外）。</span><span class="sxs-lookup"><span data-stu-id="57665-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="57665-116">无论此设置如何，在安排会议时，演示者都可以显式指定为演示者，也可以在会议期间将其显式提升为演示者。</span><span class="sxs-lookup"><span data-stu-id="57665-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="57665-117">选项包括：</span><span class="sxs-lookup"><span data-stu-id="57665-117">The options are:</span></span>

  - <span data-ttu-id="57665-118">**无**如果不是组织者的任何人自动指定为演示者，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="57665-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="57665-119">**公司**选择此选项可自动将组织的成员指定为演示者。</span><span class="sxs-lookup"><span data-stu-id="57665-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="57665-120">**所有人**选择此选项可自动将任何人指定为演示者。</span><span class="sxs-lookup"><span data-stu-id="57665-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="57665-121">**默认为分配的会议类型**此设置控制 Outlook 会议加载项是否始终使用组织者分配的会议安排会议，这意味着计划的会议始终具有相同的联接 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="57665-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="57665-122">选中此复选框以让计划的会议始终使用相同的联接 URL。</span><span class="sxs-lookup"><span data-stu-id="57665-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="57665-123">清除此复选框可对每个会议使用不同的联接 URL。</span><span class="sxs-lookup"><span data-stu-id="57665-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="57665-124">**默认情况下，承认匿名用户**如果在默认情况下允许匿名用户（即未经身份验证的）用户出席会议，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="57665-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="57665-125">如果默认情况下不允许匿名用户出席会议，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="57665-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="57665-126">**徽标 URL**键入包含要用于自定义会议邀请的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="57665-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="57665-127">**帮助 URL**键入用户可在其中获取加入会议的帮助的网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="57665-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="57665-128">**合法文本 URL**键入包含该会议的法律信息和免责声明的网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="57665-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="57665-129">**自定义页脚文本**键入要在自定义会议邀请中使用的文本。</span><span class="sxs-lookup"><span data-stu-id="57665-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="57665-p107">有关使用会议配置的详细信息，请参阅操作文档中的[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)。有关设置大型会议的会议配置的详细信息，请参阅规划文档中的[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)。</span><span class="sxs-lookup"><span data-stu-id="57665-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


