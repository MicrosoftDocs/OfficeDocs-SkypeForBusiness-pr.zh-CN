---
title: 'Lync Server 2013: 查看会议配置设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3107045d62b244c7ee89dbb47228bc5dd72583
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="99893-102">在 Lync Server 2013 中查看会议配置设置</span><span class="sxs-lookup"><span data-stu-id="99893-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99893-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="99893-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="99893-104">在 Lync Server 2013 控制面板中, 使用 "会议配置" 设置来控制在部署中实现会议的方式。</span><span class="sxs-lookup"><span data-stu-id="99893-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="99893-105">这包括以下会议配置:</span><span class="sxs-lookup"><span data-stu-id="99893-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="99893-106">部署 Lync Server 2013 时默认创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="99893-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="99893-107">可创建和使用的可选网站级和用户级配置, 用于指定如何为特定网站或用户实现会议。</span><span class="sxs-lookup"><span data-stu-id="99893-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="99893-108">查看会议配置设置</span><span class="sxs-lookup"><span data-stu-id="99893-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="99893-109">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="99893-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99893-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="99893-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99893-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="99893-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99893-112">在左侧导航栏中, 单击 "**会议**", 然后单击 "**会议配置**"。</span><span class="sxs-lookup"><span data-stu-id="99893-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="99893-113">在“**会议配置**”页上，单击要查看的会议配置。</span><span class="sxs-lookup"><span data-stu-id="99893-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="99893-114">在 "**编辑文件筛选器**" 中, 选择 "**显示详细信息 ...** "</span><span class="sxs-lookup"><span data-stu-id="99893-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="99893-115">复选框。</span><span class="sxs-lookup"><span data-stu-id="99893-115">check box.</span></span>
    
    <span data-ttu-id="99893-116">\*\*编辑会议配置- \<策略\> \*\*将打开, 显示所选策略的设置。</span><span class="sxs-lookup"><span data-stu-id="99893-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="99893-117">有关配置设置的详细信息, 请参阅[在 Lync Server 2013 中创建或修改会议配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="99893-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="99893-118">使用 Windows PowerShell Cmdlet 查看会议配置信息</span><span class="sxs-lookup"><span data-stu-id="99893-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="99893-119">可使用 Windows PowerShell 和 CsMeetingConfiguration cmdlet 查看会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="99893-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="99893-120">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="99893-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="99893-121">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="99893-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="99893-122">查看会议配置信息</span><span class="sxs-lookup"><span data-stu-id="99893-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="99893-123">若要查看有关所有会议配置设置的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="99893-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="99893-124">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="99893-124">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="99893-125">有关详细信息, 请参阅[CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="99893-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

