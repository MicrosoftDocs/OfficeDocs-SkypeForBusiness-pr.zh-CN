---
title: Lync Server 2013：查看 CDR 配置信息
description: Lync Server 2013：查看 CDR 配置信息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 687ee05701c022e1d7ecfe2cd8be5190949c51d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551308"
---
# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="67f2f-103">在 Lync Server 2013 中查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="67f2f-103">View CDR configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67f2f-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="67f2f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="67f2f-p101">利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="67f2f-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="67f2f-107">安装 Microsoft Lync Server 2013 时，将为你创建一个 CDR 配置设置的单一全局集合。</span><span class="sxs-lookup"><span data-stu-id="67f2f-107">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="67f2f-108">管理员还可以选择创建可应用于各个站点的自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="67f2f-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="67f2f-109">您可以使用 Lync Server 控制面板或 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet 查看在您的组织中使用的 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="67f2f-109">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="67f2f-110">使用 Lync Server 控制面板查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="67f2f-110">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="67f2f-111">在 Lync Server 控制面板中，单击 " **监控和存档**"。</span><span class="sxs-lookup"><span data-stu-id="67f2f-111">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="67f2f-p103">所有 CDR 配置设置的列表将显示在“呼叫详细信息记录”\*\*\*\* 选项卡中；对于每个设置集合，您将看到集合“名称”\*\*\*\*；是否已启用 CDR（“CDR”\*\*\*\* 属性）；是否已启用清除（“CDR 清除”\*\*\*\* 属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。</span><span class="sxs-lookup"><span data-stu-id="67f2f-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="67f2f-115">使用 Windows PowerShell Cmdlet 查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="67f2f-115">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="67f2f-116">您可以使用 Windows PowerShell 和 Get-CsCdrConfiguration cmdlet 查看 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="67f2f-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="67f2f-117">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="67f2f-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="67f2f-118">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="67f2f-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="67f2f-119">查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="67f2f-119">To view CDR configuration information</span></span>

  - <span data-ttu-id="67f2f-120">若要查看有关所有 CDR 配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="67f2f-120">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="67f2f-121">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="67f2f-121">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="67f2f-122">有关详细信息，请参阅 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="67f2f-122">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

