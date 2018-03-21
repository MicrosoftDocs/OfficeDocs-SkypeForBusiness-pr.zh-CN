---
title: "移动到 Microsoft 的用户的音频会议提供商"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Change your Skype for Business users from third-party audio conferencing providers (ACP) to a Microsoft dial-in conferencing provider. '
ms.openlocfilehash: 8df53a27f3dc0934411284c373206fc4b6dcf41a
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="0bc33-103">移动到 Microsoft 的用户的音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="0bc33-103">Moving a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="0bc33-104">要为业务和 Microsoft 小组使用 Skype 与 Office 365 音频会议，用户需要有分配给他们和他们的音频会议提供商**音频会议**许可证您自己组织中必须设置给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0bc33-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an **Audio Conferencing** license assigned to them and their audio conferencing provider must be set to Microsoft.</span></span> <span data-ttu-id="0bc33-105">查看[试用或购买 Office 365 中的音频会议](try-or-purchase-audio-conferencing-in-office-365.md)若要获得许可和多少它的成本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0bc33-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="0bc33-106">若要向微软移动用户的音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="0bc33-106">To move a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="0bc33-107">如果**音频会议**许可分配给不具备音频会议提供商的用户，用户的提供商将被自动设置为 Microsoft，您不必执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="0bc33-107">If an **Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to Microsoft and you don't have to do anything else.</span></span> <span data-ttu-id="0bc33-108">如果该用户已经具有音频会议提供商，必须将它们分配**音频会议**许可证后到 Microsoft 更改用户的提供商。</span><span class="sxs-lookup"><span data-stu-id="0bc33-108">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an **Audio Conferencing** license.</span></span>
  
<span data-ttu-id="0bc33-109">将 Microsoft 设置为具有**音频会议**许可的用户音频会议提供商分配，但正在使用另一个音频会议提供商，请执行此操作：</span><span class="sxs-lookup"><span data-stu-id="0bc33-109">To set Microsoft as the audio conferencing provider for a user that has an **Audio Conferencing** license assigned but is using another audio conferencing provider, do this:</span></span>
  
1. <span data-ttu-id="0bc33-110">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0bc33-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0bc33-111">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="0bc33-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0bc33-112">在**Skype 的业务管理中心**，转到**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="0bc33-112">In the **Skype for Business admin center**, go to **Audio conferencing**.</span></span>
    
4. <span data-ttu-id="0bc33-113">如果您看到一个横幅通知您存在具有**音频会议**的用户许可证分配但没有 Microsoft 设置为其音频会议提供商，但单击**以将其移动，请单击此处**。</span><span class="sxs-lookup"><span data-stu-id="0bc33-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="0bc33-114">如果您看不到标语，在**业务管理中心的 Skype**单击**用户**，然后选择**用户可以转移到会议音频**筛选器。</span><span class="sxs-lookup"><span data-stu-id="0bc33-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
5. <span data-ttu-id="0bc33-115">选择您想要移动的用户，然后在操作窗格中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="0bc33-115">Select the users you want to move, and then in the Action pane, click **Edit**.</span></span>
    
6. <span data-ttu-id="0bc33-116">在**提供程序名称**列表中选择**Microsoft** 。</span><span class="sxs-lookup"><span data-stu-id="0bc33-116">Select **Microsoft** in the **Provider name** list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0bc33-117">当更改为 Microsoft 用户的音频会议提供商时，会更改用户的音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="0bc33-117">When the audio conferencing provider of a user is changed to Microsoft, the audio conferencing information of the user will change.</span></span> <span data-ttu-id="0bc33-118">如果您需要保留此信息，请在更改任何用户的提供商之前某个位置记录。</span><span class="sxs-lookup"><span data-stu-id="0bc33-118">If you need to keep this information, please record it somewhere before changing the provider of any of the users.</span></span> 
  
7. <span data-ttu-id="0bc33-119">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="0bc33-119">Click **Save**.</span></span>
    
## <a name="what-else-should-i-know"></a><span data-ttu-id="0bc33-120">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="0bc33-120">What else should I know?</span></span>

- <span data-ttu-id="0bc33-121">如果选择用户列表中，您可以查看用户的默认音频会议信息，但您将无法查看音频会议针。</span><span class="sxs-lookup"><span data-stu-id="0bc33-121">If you select the user in the list, you can view the default audio conferencing information of the user but you won't be able to see the audio conferencing PIN.</span></span> <span data-ttu-id="0bc33-122">通过单击**重置**，可以重置用户的 PIN 音频会议。</span><span class="sxs-lookup"><span data-stu-id="0bc33-122">You can reset the audio conferencing PIN of a user by clicking **Reset**.</span></span>
    
- <span data-ttu-id="0bc33-123">如果您想要更改的用户的音频会议设置，您可以从列表中选择用户然后单击**编辑**并在**属性**页上进行更改。</span><span class="sxs-lookup"><span data-stu-id="0bc33-123">If you want to change audio conferencing settings for a user, you can select the user from the list and then click **Edit** and make your changes on the **Properties** page.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="0bc33-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="0bc33-124">Related topics</span></span>

[<span data-ttu-id="0bc33-125">设置音频会议 for Skype Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="0bc33-125">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

