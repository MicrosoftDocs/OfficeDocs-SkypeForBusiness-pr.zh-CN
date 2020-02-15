---
title: Lync Server 2013：指定 CDR 数据的保留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4043c90cffc99b0c262e9091d3cb98d15ff89818
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a><span data-ttu-id="74949-102">在 Lync Server 2013 中指定 CDR 数据的保留</span><span class="sxs-lookup"><span data-stu-id="74949-102">Specifying retention of CDR data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74949-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="74949-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="74949-p101">默认情况下，呼叫详细信息记录 (CDR) 数据会在 60 天后清除。可以使用“呼叫详细信息记录”\*\*\*\* 页上的设置将该数据保留更长或更短的时间。如果禁用 CDR，则在启用 CDR 之前捕获的数据也将清除。</span><span class="sxs-lookup"><span data-stu-id="74949-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74949-p102">应该对 CDR 和用户体验质量 (QoE) 进行配置，使二者保留数据的天数相同。监控服务器报告网页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。</span><span class="sxs-lookup"><span data-stu-id="74949-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="74949-110">使用以下过程来配置 CDR 数据的清除设置。</span><span class="sxs-lookup"><span data-stu-id="74949-110">Use the following procedures to configure purge settings for CDR data.</span></span>

<div>

## <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="74949-111">指定 CDR 数据的保留</span><span class="sxs-lookup"><span data-stu-id="74949-111">To specify retention of CDR data</span></span>

1.  <span data-ttu-id="74949-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="74949-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="74949-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="74949-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74949-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="74949-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74949-115">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“呼叫详细信息记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74949-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="74949-116">在“呼叫详细信息记录”\*\*\*\* 页上，单击表中的相应站点，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74949-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="74949-117">要打开清除，请选择“启用 CDR 清除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74949-117">To turn on purging, select **Enable purging of CDRs**.</span></span>

6.  <span data-ttu-id="74949-118">在“CDR 最长保留期限(天):”\*\*\*\* 中选择呼叫详细信息记录的最长保留天数。</span><span class="sxs-lookup"><span data-stu-id="74949-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="74949-119">在“错误报告数据最长保留期限(天):”\*\*\*\* 中选择错误报告的最长保留天数。</span><span class="sxs-lookup"><span data-stu-id="74949-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="74949-120">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74949-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74949-121">使用 Windows PowerShell Cmdlet 指定 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="74949-121">Specifying CDR Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="74949-122">您可以使用 Windows PowerShell 和 Set-CsCdrConfiguration cmdlet 来创建 CDR 保留设置。</span><span class="sxs-lookup"><span data-stu-id="74949-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="74949-123">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="74949-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="74949-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="74949-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="74949-125">指定特定位置的 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="74949-125">To specify CDR retention for a specific location</span></span>

  - <span data-ttu-id="74949-126">此命令允许清除 Redmond 站点的 CDR 数据，并将该站点配置为将 CDR 数据和错误报告数据保留 20 天。</span><span class="sxs-lookup"><span data-stu-id="74949-126">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="74949-127">指定多个位置的 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="74949-127">To specify CDR retention for multiple locations</span></span>

  - <span data-ttu-id="74949-128">此命令会为组织中使用的所有 CDR 配置设置配置 CDR 保留。</span><span class="sxs-lookup"><span data-stu-id="74949-128">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<span data-ttu-id="74949-129">有关详细信息，请参阅[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="74949-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74949-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74949-130">See Also</span></span>


[<span data-ttu-id="74949-131">Lync Server 2013 中的呼叫详细信息记录（CDR）</span><span class="sxs-lookup"><span data-stu-id="74949-131">Call detail recording (CDR) in Lync Server 2013</span></span>](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

