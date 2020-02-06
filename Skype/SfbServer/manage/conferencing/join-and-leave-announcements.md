---
title: 在 Skype for Business 服务器中管理会议加入和退出通知
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 摘要：了解如何在 Skype for Business 服务器中管理会议加入和退出通知。
ms.openlocfilehash: 5f975637ca1d85e11c6889a07ff90055ef79ffc5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818543"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="73b47-103">在 Skype for Business 服务器中管理会议加入和退出通知</span><span class="sxs-lookup"><span data-stu-id="73b47-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="73b47-104">**摘要：** 了解如何在 Skype for Business 服务器中管理会议加入和退出通知。</span><span class="sxs-lookup"><span data-stu-id="73b47-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="73b47-105">当拨入用户加入或离开会议时，会议公告应用程序可以通过播放音频或说出其名称来宣布其进入或退出。</span><span class="sxs-lookup"><span data-stu-id="73b47-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="73b47-106">你可以通过使用 Skype for Business Server Management Shell 和**CsDialinConferencing** cmdlet 以及以下参数来更改通知的工作方式：</span><span class="sxs-lookup"><span data-stu-id="73b47-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="73b47-p102">EnableNameRecording - 确定在匿名参与者进入会议之前是否要求参与者记录其姓名。默认值为“$true”，即系统会提示匿名参与者在加入会议时说出其姓名。（经过身份验证的参与者不会记录他们的姓名，因为将使用他们的显示名称。）</span><span class="sxs-lookup"><span data-stu-id="73b47-p102">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference. The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference. (Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="73b47-p103">EntryExitAnnouncementsEnabledByDefault - 指示默认打开还是关闭通知。默认值为“$false”，即默认情况下，在参与者加入或离开会议时没有通知。会议组织者在安排会议时可以覆盖此设置。</span><span class="sxs-lookup"><span data-stu-id="73b47-p103">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default. The default value is "$false," which means that by default there are no announcements when participants join or leave a conference. The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="73b47-p104">EntryExitAnnouncementsType - 指示参与者加入或离开启用了通知的会议时将执行的操作。默认值为“UseNames”，即有通知，类似于：“Ken Myer 已加入会议”（如果已打开通知）。</span><span class="sxs-lookup"><span data-stu-id="73b47-p104">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled. The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="73b47-p105">可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。</span><span class="sxs-lookup"><span data-stu-id="73b47-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="73b47-117">修改会议加入和离开通知行为</span><span class="sxs-lookup"><span data-stu-id="73b47-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="73b47-118">以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="73b47-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="73b47-119">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73b47-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73b47-120">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="73b47-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="73b47-121">此 cmdlet 检索有关参与者在加入会议时是否需要参与者记录其名称的信息，以及 Skype for business 服务器在参与者加入或离开电话拨入式会议时如何响应。</span><span class="sxs-lookup"><span data-stu-id="73b47-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="73b47-122">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="73b47-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="73b47-p106">在以下示例中，在 site 作用域为 Redmond 配置设置。通知已打开，但在参与者加入会议时系统未提示他们说出姓名。参与者进入或离开会议时将播放提示音：</span><span class="sxs-lookup"><span data-stu-id="73b47-p106">In the following example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="73b47-126">有关详细信息，包括语法和参数的完整列表，请参阅[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="73b47-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

