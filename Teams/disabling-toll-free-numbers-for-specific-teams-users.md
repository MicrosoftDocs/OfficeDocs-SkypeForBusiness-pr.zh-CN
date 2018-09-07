---
title: 禁用特定的团队用户的免费电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制如何组织者可以为他们的会议使用免费电话号码。
ms.openlocfilehash: 8fafe87823308035d2626d891ae12b72c2bcfeca
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23852154"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="70c1d-103">禁用特定的团队用户的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="70c1d-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="70c1d-104">如果您的组织具有其 Microsoft 音频会议网桥中免费电话号码，您可以允许或阻止特定的组织者的会议中其使用情况。</span><span class="sxs-lookup"><span data-stu-id="70c1d-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="70c1d-105">默认情况下，您的组织中的所有用户都启用使用免费电话号码，这意味着，这些号码，如果可用，可用于参与者加入他们的会议。</span><span class="sxs-lookup"><span data-stu-id="70c1d-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="70c1d-106">如果不为您的组织中的一些用户所需的行为，您可以限制特定用户在其通过免费电话号码启用控件的会议中使用这些号码。</span><span class="sxs-lookup"><span data-stu-id="70c1d-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="70c1d-107">当给定管理器禁用免费电话号码：</span><span class="sxs-lookup"><span data-stu-id="70c1d-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="70c1d-108">免费电话号码将不再包括在他或她的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="70c1d-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="70c1d-109">免费电话号码将不再列出其中引用的"查找本地号码"页上，或她的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="70c1d-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="70c1d-110">参与者将无法加入给定组织者的会议，如果拨组织的任何免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="70c1d-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="70c1d-111">将自动重新安排的组织者的所有会议，并将从其删除免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="70c1d-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="70c1d-112">这将向这些会议的所有参与者重新组织者的电子邮件邀请的所有发送。</span><span class="sxs-lookup"><span data-stu-id="70c1d-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="70c1d-113">参与者可以继续加入会议的组织者使用收费电话号码。</span><span class="sxs-lookup"><span data-stu-id="70c1d-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="70c1d-114">禁用特定用户的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="70c1d-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="70c1d-115">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="70c1d-115">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="70c1d-116">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="70c1d-116">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="70c1d-117">**音频会议**，旁边单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="70c1d-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="70c1d-118">关闭**包括来自此用户的会议请求中的免费电话号码**。</span><span class="sxs-lookup"><span data-stu-id="70c1d-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="70c1d-119">单击**保存。**</span><span class="sxs-lookup"><span data-stu-id="70c1d-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="70c1d-120">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="70c1d-120">**Using PowerShell**</span></span>  

<span data-ttu-id="70c1d-121">请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="70c1d-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
