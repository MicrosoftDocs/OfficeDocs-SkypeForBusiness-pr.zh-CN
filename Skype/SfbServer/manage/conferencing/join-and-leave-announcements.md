---
title: 在 Skype for Business Server 中管理会议加入和离开通知
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 摘要：了解如何在 Skype for Business Server 中管理会议加入和离开通知。
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828102"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="bed8e-103">在 Skype for Business Server 中管理会议加入和离开通知</span><span class="sxs-lookup"><span data-stu-id="bed8e-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="bed8e-104">**摘要：** 了解如何在 Skype for Business Server 中管理会议加入和离开通知。</span><span class="sxs-lookup"><span data-stu-id="bed8e-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="bed8e-105">当电话拨入用户加入或离开会议时，会议通知应用程序可以通过播放提示音或说其姓名来宣布其进入或退出。</span><span class="sxs-lookup"><span data-stu-id="bed8e-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="bed8e-106">可以使用具有以下参数的 Skype for Business Server 命令行管理程序和 **Set-CsDialinConferencing** cmdlet 更改通知的运行方式：</span><span class="sxs-lookup"><span data-stu-id="bed8e-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="bed8e-107">EnableNameRecording - 确定是否要求匿名参与者在进入会议之前记录其姓名。</span><span class="sxs-lookup"><span data-stu-id="bed8e-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="bed8e-108">（经过身份验证的参与者不会记录他们的姓名，因为将使用他们的显示名称。</span><span class="sxs-lookup"><span data-stu-id="bed8e-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="bed8e-109">）</span><span class="sxs-lookup"><span data-stu-id="bed8e-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="bed8e-110">EntryExitAnnouncementsEnabledByDefault - 指示默认情况下是打开还是关闭通知。</span><span class="sxs-lookup"><span data-stu-id="bed8e-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="bed8e-111">默认值为"$false"，这意味着默认情况下，参与者加入或离开会议时没有通知。</span><span class="sxs-lookup"><span data-stu-id="bed8e-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="bed8e-112">在安排会议时，会议组织者可以覆盖此设置。</span><span class="sxs-lookup"><span data-stu-id="bed8e-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="bed8e-113">EntryExitAnnouncementsType - 指示参与者加入或离开启用了通知的会议时采取的操作。</span><span class="sxs-lookup"><span data-stu-id="bed8e-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="bed8e-114">默认值为"UseNames"，这意味着在打开通知时有类似如下通知："Ken Myer 已加入会议"。</span><span class="sxs-lookup"><span data-stu-id="bed8e-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="bed8e-p105">可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。</span><span class="sxs-lookup"><span data-stu-id="bed8e-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="bed8e-117">修改会议加入和离开通知行为</span><span class="sxs-lookup"><span data-stu-id="bed8e-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="bed8e-118">以 RTCUniversalServerAdmins 组成员或者 Cs-ServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="bed8e-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="bed8e-119">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="bed8e-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bed8e-120">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="bed8e-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="bed8e-121">此 cmdlet 检索有关在加入会议时是否要求参与者记录其姓名的信息，以及参与者加入或离开电话拨入式会议时 Skype for Business Server 如何响应的信息。</span><span class="sxs-lookup"><span data-stu-id="bed8e-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="bed8e-122">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="bed8e-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="bed8e-123">在下面的示例中，在站点范围为 Redmond 配置设置。</span><span class="sxs-lookup"><span data-stu-id="bed8e-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="bed8e-124">通知已打开，但在参与者加入会议时系统未提示他们说出姓名。</span><span class="sxs-lookup"><span data-stu-id="bed8e-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="bed8e-125">参与者进入或离开会议时播放提示音：</span><span class="sxs-lookup"><span data-stu-id="bed8e-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="bed8e-126">有关详细信息，包括语法和参数的完整列表，请参阅[Set-CsDialInConferencingConfiguration。](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bed8e-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

