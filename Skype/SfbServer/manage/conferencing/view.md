---
title: 在 Skype for Business Server 中查看会议策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要：了解如何在 Skype for Business Server 中查看会议策略。
ms.openlocfilehash: 39b37a1335f8b257f9dec1fff28bea90ac7a6db9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817502"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="8b1e3-103">在 Skype for Business Server 中查看会议策略</span><span class="sxs-lookup"><span data-stu-id="8b1e3-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="8b1e3-104">**摘要：** 了解如何在 Skype for Business Server 中查看会议策略。</span><span class="sxs-lookup"><span data-stu-id="8b1e3-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="8b1e3-105">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序查看会议策略。</span><span class="sxs-lookup"><span data-stu-id="8b1e3-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8b1e3-106">使用 Skype for Business Server 控制面板查看会议策略</span><span class="sxs-lookup"><span data-stu-id="8b1e3-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8b1e3-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8b1e3-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="8b1e3-108">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="8b1e3-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8b1e3-109">在左侧导航栏中，单击 **"会议"，** 然后单击 **"会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="8b1e3-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="8b1e3-110">在“会议策略”页面上，双击您要查看的会议策略。</span><span class="sxs-lookup"><span data-stu-id="8b1e3-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="8b1e3-111">在 **"编辑文件筛选器**"中，选中" **显示详细信息"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="8b1e3-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="8b1e3-112">**编辑会议策略 - \<policy\>** 打开，显示所选策略的设置。</span><span class="sxs-lookup"><span data-stu-id="8b1e3-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="8b1e3-113">有关配置设置的详细信息，请参阅在 Skype for Business Server 中创建 [会议策略](create-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1e3-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8b1e3-114">使用 Skype for Business Server 命令行管理程序查看会议策略</span><span class="sxs-lookup"><span data-stu-id="8b1e3-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8b1e3-115">若要查看会议策略，请使用 **Get-CsConferencingPolicy** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8b1e3-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="8b1e3-116">此 cmdlet 返回如下信息：</span><span class="sxs-lookup"><span data-stu-id="8b1e3-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="8b1e3-117">有关详细信息，包括完整的语法说明和参数列表，请参阅[Get-CsConferencingPolicy。](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8b1e3-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

