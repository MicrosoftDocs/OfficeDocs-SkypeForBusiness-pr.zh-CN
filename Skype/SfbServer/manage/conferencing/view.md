---
title: 在 Skype for Business 服务器中查看会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要：了解如何在 Skype for Business 服务器中查看会议策略。
ms.openlocfilehash: 2273e694ce2f34c8d395f87f207de85b409e18af
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818443"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="f6174-103">在 Skype for Business 服务器中查看会议策略</span><span class="sxs-lookup"><span data-stu-id="f6174-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="f6174-104">**摘要：** 了解如何在 Skype for Business 服务器中查看会议策略。</span><span class="sxs-lookup"><span data-stu-id="f6174-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="f6174-105">可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器查看会议策略。</span><span class="sxs-lookup"><span data-stu-id="f6174-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f6174-106">使用 Skype for Business 服务器控制面板查看会议策略</span><span class="sxs-lookup"><span data-stu-id="f6174-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f6174-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f6174-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f6174-108">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="f6174-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f6174-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="f6174-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="f6174-110">在“**会议策略**”页面上，双击你要查看的会议策略。</span><span class="sxs-lookup"><span data-stu-id="f6174-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="f6174-111">在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。</span><span class="sxs-lookup"><span data-stu-id="f6174-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="f6174-112">\*\*编辑会议策略- \<将\> \*\*打开显示所选策略的设置的策略。</span><span class="sxs-lookup"><span data-stu-id="f6174-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="f6174-113">有关配置设置的详细信息，请参阅[在 Skype For Business 服务器中创建会议策略](create-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f6174-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f6174-114">使用 Skype for Business Server Management Shell 查看会议策略</span><span class="sxs-lookup"><span data-stu-id="f6174-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f6174-115">若要查看会议策略，请使用 **Get-CsConferencingPolicy** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f6174-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="f6174-116">该 cmdlet 将返回类似如下的信息：</span><span class="sxs-lookup"><span data-stu-id="f6174-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="f6174-117">有关详细信息，包括完整语法说明和参数列表，请参阅[CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f6174-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

