---
title: Lync Server 2013：查看会议配置设置
description: Lync Server 2013：查看会议配置设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190b9d331a8cd0a08e17c482dbc3b0bc27590003
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576398"
---
# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="dffcc-103">在 Lync Server 2013 中查看会议配置设置</span><span class="sxs-lookup"><span data-stu-id="dffcc-103">View meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dffcc-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dffcc-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dffcc-105">在 Lync Server 2013 控制面板中，使用 "会议配置" 设置来控制如何在部署中实施会议。</span><span class="sxs-lookup"><span data-stu-id="dffcc-105">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="dffcc-106">这包括以下会议配置：</span><span class="sxs-lookup"><span data-stu-id="dffcc-106">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="dffcc-107">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="dffcc-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="dffcc-108">可选的网站级别和用户级别的配置，您可以创建和使用这些配置来指定如何为特定网站或用户实施会议。</span><span class="sxs-lookup"><span data-stu-id="dffcc-108">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="dffcc-109">查看会议配置设置</span><span class="sxs-lookup"><span data-stu-id="dffcc-109">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="dffcc-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="dffcc-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dffcc-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="dffcc-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dffcc-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="dffcc-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dffcc-113">在左侧导航栏中，单击 **“会议”**，然后单击 **“会议配置”**。</span><span class="sxs-lookup"><span data-stu-id="dffcc-113">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="dffcc-114">在 " **会议配置** " 页上，单击要查看的会议配置。</span><span class="sxs-lookup"><span data-stu-id="dffcc-114">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="dffcc-115">在 "**编辑文件筛选器**" 中，选择 "**显示详细信息 ...** "</span><span class="sxs-lookup"><span data-stu-id="dffcc-115">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="dffcc-116">复选框来关闭域筛选。</span><span class="sxs-lookup"><span data-stu-id="dffcc-116">check box.</span></span>
    
    <span data-ttu-id="dffcc-117">\*\*编辑会议配置- \<policy\> \*\*打开显示所选策略的设置。</span><span class="sxs-lookup"><span data-stu-id="dffcc-117">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="dffcc-118">有关配置设置的详细信息，请参阅 [在 Lync Server 2013 中创建或修改会议配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="dffcc-118">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dffcc-119">使用 Windows PowerShell Cmdlet 查看会议配置信息</span><span class="sxs-lookup"><span data-stu-id="dffcc-119">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dffcc-120">可以使用 Windows PowerShell 和 Get-CsMeetingConfiguration cmdlet 查看会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="dffcc-120">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="dffcc-121">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="dffcc-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dffcc-122">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="dffcc-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="dffcc-123">查看会议配置信息</span><span class="sxs-lookup"><span data-stu-id="dffcc-123">To view meeting configuration information</span></span>

  - <span data-ttu-id="dffcc-124">若要查看有关所有会议配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="dffcc-124">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="dffcc-125">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="dffcc-125">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="dffcc-126">有关详细信息，请参阅 [get-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="dffcc-126">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

