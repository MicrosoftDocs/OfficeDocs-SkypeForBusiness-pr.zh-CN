---
title: 在 Skype for Business Server 2015 中查看会议策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要： 了解如何查看会议策略在 Skype 业务服务器 2015年。
ms.openlocfilehash: 4d91a04456f7c9d877e58caed1d576edc0f80b41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="view-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="6bcbe-103">在 Skype for Business Server 2015 中查看会议策略</span><span class="sxs-lookup"><span data-stu-id="6bcbe-103">View conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6bcbe-104">**摘要：**了解如何查看会议策略在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6bcbe-105">通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳，您可以查看会议策略。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6bcbe-106">通过 Skype 业务服务器控件面板查看会议策略</span><span class="sxs-lookup"><span data-stu-id="6bcbe-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6bcbe-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6bcbe-108">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6bcbe-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="6bcbe-110">在“**会议策略**”页面上，双击你要查看的会议策略。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="6bcbe-111">在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="6bcbe-112">**编辑会议策略-\<策略\>**将打开并显示所选策略的设置。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="6bcbe-113">有关配置设置的详细信息，请参阅[创建业务服务器 2015年的 Skype 会议策略](create-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server 2015](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6bcbe-114">通过 Skype 业务服务器管理外壳程序查看会议策略</span><span class="sxs-lookup"><span data-stu-id="6bcbe-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6bcbe-115">若要查看会议策略，请使用 **Get-CsConferencingPolicy** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6bcbe-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```
Get-CsConferencingPolicy
```

<span data-ttu-id="6bcbe-116">该 cmdlet 将返回类似如下的信息：</span><span class="sxs-lookup"><span data-stu-id="6bcbe-116">The cmdlet returns information such as the following:</span></span>
  
```
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

```

<span data-ttu-id="6bcbe-117">包括完整的语法描述和参数的列表的详细信息，请参阅[获取 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6bcbe-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

