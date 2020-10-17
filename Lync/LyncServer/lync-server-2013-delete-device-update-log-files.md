---
title: Lync Server 2013：删除设备更新日志文件
description: Lync Server 2013：删除设备更新日志文件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe32b3147f28c7eab1b4864df44ae0967848426b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552498"
---
# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="f8da9-103">在 Lync Server 2013 中删除设备更新日志文件</span><span class="sxs-lookup"><span data-stu-id="f8da9-103">Delete Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8da9-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f8da9-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f8da9-105">设备更新 Web 服务可保留大量的日志文件集合。</span><span class="sxs-lookup"><span data-stu-id="f8da9-105">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="f8da9-106">此集合包括服务本身执行的审核日志和从客户端设备上传的日志文件。</span><span class="sxs-lookup"><span data-stu-id="f8da9-106">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="f8da9-107">若要防止服务器填满设备更新 Web 服务日志，您可能需要清除已在特定天数内的日志文件。</span><span class="sxs-lookup"><span data-stu-id="f8da9-107">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="f8da9-108">根据组织中的更新活动和客户端设备的数量以及使用 Lync Server 控制面板或 Lync Server 命令行管理程序，设置此天数。</span><span class="sxs-lookup"><span data-stu-id="f8da9-108">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="f8da9-109">使用 Lync Server 控制面板清除设备更新日志的具体方法</span><span class="sxs-lookup"><span data-stu-id="f8da9-109">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8da9-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f8da9-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8da9-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="f8da9-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f8da9-112">在左侧导航栏中，单击 **“客户端”**，然后单击 **“设备日志配置”**。</span><span class="sxs-lookup"><span data-stu-id="f8da9-112">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="f8da9-113">在 **“设备日志配置”** 页上，双击要更改的配置。</span><span class="sxs-lookup"><span data-stu-id="f8da9-113">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="f8da9-114">在 " **编辑日志设置** " 对话框中， \*\*将日志文件保留的天数 (1-365) \*\*，指定天数。</span><span class="sxs-lookup"><span data-stu-id="f8da9-114">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="f8da9-115">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f8da9-115">Click **Commit**.</span></span> <span data-ttu-id="f8da9-116">在服务器上已超过指定天数的所有文件都将被删除。</span><span class="sxs-lookup"><span data-stu-id="f8da9-116">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="f8da9-117">此设置将应用于此配置，直到您更改它。</span><span class="sxs-lookup"><span data-stu-id="f8da9-117">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="f8da9-118">使用 Windows PowerShell Cmdlet 清除设备更新日志</span><span class="sxs-lookup"><span data-stu-id="f8da9-118">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f8da9-119">您可以使用 Windows PowerShell 和 **CsDeviceUpdateLog** cmdlet 来清除设备更新日志。</span><span class="sxs-lookup"><span data-stu-id="f8da9-119">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="f8da9-120">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="f8da9-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8da9-121">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="f8da9-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="f8da9-122">清除一台服务器上的设备更新日志</span><span class="sxs-lookup"><span data-stu-id="f8da9-122">To clear device update logs on one server</span></span>

  - <span data-ttu-id="f8da9-123">以下命令清除 Web 服务器 atl-cs-001.litwareinc.com 上的设备更新日志。</span><span class="sxs-lookup"><span data-stu-id="f8da9-123">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f8da9-124">所有日志条目超过10天以前 (将从日志中删除 DaysBack 参数) 指定的值。</span><span class="sxs-lookup"><span data-stu-id="f8da9-124">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="f8da9-125">清除所有设备更新日志</span><span class="sxs-lookup"><span data-stu-id="f8da9-125">To clear all device update logs</span></span>

  - <span data-ttu-id="f8da9-126">此命令将删除已过期的条目 (在此示例中，条目的旧) 距组织中当前使用的所有设备更新日志的时间已超过10天。</span><span class="sxs-lookup"><span data-stu-id="f8da9-126">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="f8da9-127">有关详细信息，请参阅 [CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f8da9-127">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

