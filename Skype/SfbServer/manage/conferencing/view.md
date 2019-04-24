---
title: 查看会议策略中的业务服务器 Skype
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要： 了解如何为业务服务器在 Skype 中查看会议策略。
ms.openlocfilehash: 034de4e8d1a5d1a4a89589d3f6361d22e5a783be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197868"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="cc97d-103">查看会议策略中的业务服务器 Skype</span><span class="sxs-lookup"><span data-stu-id="cc97d-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="cc97d-104">**摘要：** 了解如何为业务服务器在 Skype 中查看会议策略。</span><span class="sxs-lookup"><span data-stu-id="cc97d-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="cc97d-105">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以查看会议策略。</span><span class="sxs-lookup"><span data-stu-id="cc97d-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cc97d-106">使用适用于业务 Server Control Panel Skype 查看会议策略</span><span class="sxs-lookup"><span data-stu-id="cc97d-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cc97d-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="cc97d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="cc97d-108">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="cc97d-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="cc97d-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="cc97d-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="cc97d-110">在“**会议策略**”页面上，双击你要查看的会议策略。</span><span class="sxs-lookup"><span data-stu-id="cc97d-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="cc97d-111">在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。</span><span class="sxs-lookup"><span data-stu-id="cc97d-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="cc97d-112">**编辑会议策略-\<策略\>** 打开显示所选策略的设置。</span><span class="sxs-lookup"><span data-stu-id="cc97d-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="cc97d-113">有关配置设置的详细信息，请参阅[Skype 业务服务器中的创建会议策略](create-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cc97d-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="cc97d-114">使用 Skype 业务 Server 命令行管理程序查看会议策略</span><span class="sxs-lookup"><span data-stu-id="cc97d-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="cc97d-115">若要查看会议策略，请使用 **Get-CsConferencingPolicy** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="cc97d-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```
Get-CsConferencingPolicy
```

<span data-ttu-id="cc97d-116">该 cmdlet 将返回类似如下的信息：</span><span class="sxs-lookup"><span data-stu-id="cc97d-116">The cmdlet returns information such as the following:</span></span>
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

<span data-ttu-id="cc97d-117">有关详细信息，包括完整语法说明和参数的列表，，请参阅[Get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="cc97d-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

