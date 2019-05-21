---
title: 对特定 Teams 用户禁用免费电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制组织者在其会议中使用免费电话号码的情况。
ms.openlocfilehash: 423aab1c942850c94385f4df15a07d3218dbe2da
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290330"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="1fb6b-103">对特定 Teams 用户禁用免费电话号码</span><span class="sxs-lookup"><span data-stu-id="1fb6b-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="1fb6b-104">如果组织在其 Microsoft 音频会议网桥中拥有免费电话号码，可以在特定的组织者的会议中允许或阻止其使用免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="1fb6b-105">默认方式，组织中的所有用户均启用免费电话号码，这意味着，这些号码，如果可用，参会者可使用它们参加会议。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="1fb6b-106">如果不希望组织中的某些用户可以这样参会，可以通过免费电话号码启用控件限制特定用户在其会议中使用这些号码。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="1fb6b-107">当针对某设定组织者禁用免费电话号码时：</span><span class="sxs-lookup"><span data-stu-id="1fb6b-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="1fb6b-108">免费电话号码将不再包含在他或她的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="1fb6b-109">免费电话号码将不再在"查找本地号码"页上列出，该页面在他或她的会议邀请中被引用。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="1fb6b-110">参会者如果拨组织的任何免费电话号码，都将无法参加该设定组织者的会议。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="1fb6b-111">将自动重新安排该组织者的所有会议，并将从其删除免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="1fb6b-112">因此将向这些会议的所有参与者重新发送该组织者的所有电子邮件邀请。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="1fb6b-113">参会者可以继续使用收费电话号码参加该组织者的会议。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="1fb6b-114">对特定用户禁用免费电话号码</span><span class="sxs-lookup"><span data-stu-id="1fb6b-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="1fb6b-115">从**Microsoft 团队管理中心**:</span><span class="sxs-lookup"><span data-stu-id="1fb6b-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="1fb6b-116">在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="1fb6b-117">在“**音频会议**”旁边，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="1fb6b-118">设置**包括来自此用户的会议请求中**的免费电话号码\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="1fb6b-119">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="1fb6b-120">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1fb6b-120">**Using PowerShell**</span></span>  

<span data-ttu-id="1fb6b-121">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="1fb6b-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
