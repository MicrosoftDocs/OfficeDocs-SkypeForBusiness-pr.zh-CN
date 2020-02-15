---
title: Optional启用和禁用会议加入和离开通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b18dadbb4b7dc5a35f8688c46f2836b46cb55a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="ba12a-102">Optional在 Lync Server 2013 中启用和禁用会议加入和离开通知</span><span class="sxs-lookup"><span data-stu-id="ba12a-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba12a-103">_**上次修改的主题：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="ba12a-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="ba12a-104">当电话拨入用户加入会议或离开会议时，会议通知应用程序可以通过播放声音或说出其名称来宣布进入或退出。</span><span class="sxs-lookup"><span data-stu-id="ba12a-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="ba12a-105">您可以通过运行 cmdlet 来更改通知方式。</span><span class="sxs-lookup"><span data-stu-id="ba12a-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="ba12a-106">此步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="ba12a-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="ba12a-107">修改会议加入和离开通知行为</span><span class="sxs-lookup"><span data-stu-id="ba12a-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="ba12a-108">以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="ba12a-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="ba12a-109">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba12a-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ba12a-110">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="ba12a-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="ba12a-111">此 cmdlet 检索有关参与者在加入会议时是否需要记录其名称的信息，以及当参与者加入或离开电话拨入式会议时，Lync Server 如何响应。</span><span class="sxs-lookup"><span data-stu-id="ba12a-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="ba12a-112">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="ba12a-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="ba12a-113">**EnableNameRecording**   确定在进入会议之前是否要求匿名参与者录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="ba12a-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="ba12a-114">（经过身份验证的参与者不会记录他们的姓名，因为将使用他们的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ba12a-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="ba12a-115">）</span><span class="sxs-lookup"><span data-stu-id="ba12a-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="ba12a-116">**EntryExitAnnouncementsEnabledByDefault**   指示默认情况下是打开还是关闭通知。</span><span class="sxs-lookup"><span data-stu-id="ba12a-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="ba12a-117">默认值为 "$false"，这意味着当参与者加入或离开会议时，默认情况下没有通知。</span><span class="sxs-lookup"><span data-stu-id="ba12a-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="ba12a-118">会议组织者在安排会议时可以覆盖此设置。</span><span class="sxs-lookup"><span data-stu-id="ba12a-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="ba12a-119">**EntryExitAnnouncementsType**   指示每当参与者加入或离开启用了通知的会议时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ba12a-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="ba12a-120">默认值为 "UseNames"，这意味着与以下内容类似的通知： "Ken Myer 已加入会议"。当通知打开时。</span><span class="sxs-lookup"><span data-stu-id="ba12a-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="ba12a-p105">可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。</span><span class="sxs-lookup"><span data-stu-id="ba12a-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="ba12a-123">例如：</span><span class="sxs-lookup"><span data-stu-id="ba12a-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="ba12a-p106">在此示例中，在 site 作用域为 Redmond 配置设置。通知已打开，但在参与者加入会议时系统未提示他们说出姓名。参与者进入或离开会议时将播放提示音。</span><span class="sxs-lookup"><span data-stu-id="ba12a-p106">In this example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

