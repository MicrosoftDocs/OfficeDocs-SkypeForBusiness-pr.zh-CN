---
title: Lync Server 2013：启用呼叫详细信息录制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b033827600fc962ab5ea9df5c8848ed1533c75e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="512ee-102">在 Lync Server 2013 中启用呼叫详细记录</span><span class="sxs-lookup"><span data-stu-id="512ee-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="512ee-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="512ee-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="512ee-p101">呼叫详细记录 (CDR) 记录了有关对等活动（包括即时消息、IP 语音 (VoIP) 呼叫、应用程序共享、文件传输和会议）的使用和诊断信息。使用数据可以用于计算投资回报率 (ROI)，诊断数据可以用于解决对等活动和会议中遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="512ee-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="512ee-106">使用以下过程为整个组织或组织中的每个站点启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="512ee-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="512ee-107">为了启用 CDR，必须配置监控和监控数据库。</span><span class="sxs-lookup"><span data-stu-id="512ee-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="512ee-108">有关详细信息，请参阅<A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署监视</A>。</span><span class="sxs-lookup"><span data-stu-id="512ee-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="512ee-109">使用 Lync Server "控制面板" 启用 CDR</span><span class="sxs-lookup"><span data-stu-id="512ee-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="512ee-110">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="512ee-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="512ee-111">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="512ee-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="512ee-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="512ee-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="512ee-113">在左侧导航栏中，单击“**监控和存档**”，然后单击“**呼叫详细信息记录**”。</span><span class="sxs-lookup"><span data-stu-id="512ee-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="512ee-114">在“**呼叫详细信息记录**”页上，单击表中的相应站点，再单击“**操作**”，然后单击“**启用 CDR**”。</span><span class="sxs-lookup"><span data-stu-id="512ee-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="512ee-115">默认情况下，CDR 处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="512ee-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="512ee-116">使用 Windows PowerShell Cmdlet 启用 CDR</span><span class="sxs-lookup"><span data-stu-id="512ee-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="512ee-117">你可以使用 Windows PowerShell 和**CsCdrConfiguration** CMDLET 启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="512ee-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="512ee-118">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="512ee-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="512ee-119">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="512ee-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="512ee-120">在单个位置启用 CDR</span><span class="sxs-lookup"><span data-stu-id="512ee-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="512ee-121">若要启用 CDR，请将 EnableCDR 参数设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="512ee-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="512ee-122">在单个位置禁用 CDR</span><span class="sxs-lookup"><span data-stu-id="512ee-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="512ee-p105">若要禁用 CDR，请将 EnableCDR 参数设置为 False ($False)。禁用 CDR 不会卸载监控。而只会暂停 CDR 数据的收集和存储。</span><span class="sxs-lookup"><span data-stu-id="512ee-p105">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="512ee-126">使用单个命令在多个位置启用 CDR</span><span class="sxs-lookup"><span data-stu-id="512ee-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="512ee-127">此命令将为当前在组织中使用的所有 CDR 配置设置启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="512ee-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="512ee-128">有关详细信息，请参阅[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="512ee-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="512ee-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="512ee-129">See Also</span></span>


[<span data-ttu-id="512ee-130">在 Lync Server 2013 中规划监控</span><span class="sxs-lookup"><span data-stu-id="512ee-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="512ee-131">在 Lync Server 2013 中部署监视</span><span class="sxs-lookup"><span data-stu-id="512ee-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

