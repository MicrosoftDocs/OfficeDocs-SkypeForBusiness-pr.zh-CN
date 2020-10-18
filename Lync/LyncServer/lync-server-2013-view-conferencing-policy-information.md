---
title: Lync Server 2013：查看会议策略信息
description: Lync Server 2013：查看会议策略信息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e463c500e48f4032c8dab3a3787715f7265be9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579428"
---
# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="2b8a5-103">在 Lync Server 2013 中查看会议策略信息</span><span class="sxs-lookup"><span data-stu-id="2b8a5-103">View conferencing policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b8a5-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2b8a5-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2b8a5-105">在 Lync Server 2013 控制面板中，可以使用会议策略来控制如何在部署中实施会议。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-105">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="2b8a5-106">这包括下列会议策略：</span><span class="sxs-lookup"><span data-stu-id="2b8a5-106">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="2b8a5-107">部署 Lync Server 2013 时默认创建的全局策略。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-107">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="2b8a5-108">您可以创建并用来指定如何针对特定站点或用户实施会议的可选站点级别和用户级别策略。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-108">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="2b8a5-109">查看会议策略设置</span><span class="sxs-lookup"><span data-stu-id="2b8a5-109">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="2b8a5-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b8a5-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2b8a5-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2b8a5-113">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“会议策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-113">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="2b8a5-114">在“会议策略”\*\*\*\* 页面上，双击您要查看的会议策略。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-114">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="2b8a5-p103">在“编辑文件筛选器”\*\*\*\* 中，选中“显示详细信息…”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-p103">In **Edit File Filter**, select the **Show Details…** check box.</span></span>
    
    <span data-ttu-id="2b8a5-117">\*\*编辑会议策略- \<policy\> \*\*打开显示所选策略的设置。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-117">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="2b8a5-118">有关配置设置的详细信息，请参阅 [在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-118">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2b8a5-119">使用 Windows PowerShell Cmdlet 查看会议策略</span><span class="sxs-lookup"><span data-stu-id="2b8a5-119">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2b8a5-120">可以使用 Windows PowerShell 和 Get-CsConferencingPolicy cmdlet 查看会议策略。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-120">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="2b8a5-121">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2b8a5-122">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="2b8a5-123">查看会议策略</span><span class="sxs-lookup"><span data-stu-id="2b8a5-123">To view conferencing policies</span></span>

  - <span data-ttu-id="2b8a5-124">若要查看有关所有会议策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="2b8a5-124">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="2b8a5-125">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="2b8a5-125">That will return information similar to this:</span></span>
    
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

</div>

<span data-ttu-id="2b8a5-126">有关详细信息，请参阅 [set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="2b8a5-126">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

