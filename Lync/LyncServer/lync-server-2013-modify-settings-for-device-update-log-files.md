---
title: 'Lync Server 2013: 修改设备更新日志文件的设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37002e1043f990ae1e726301b9c720af35556201
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="11831-102">在 Lync Server 2013 中修改设备更新日志文件的设置</span><span class="sxs-lookup"><span data-stu-id="11831-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11831-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="11831-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="11831-104">你可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序更改设备更新信息在你的组织中的记录方式的设置。</span><span class="sxs-lookup"><span data-stu-id="11831-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="11831-105">下表显示了哪些设置是可修改的, 以及用于修改设置的工具。</span><span class="sxs-lookup"><span data-stu-id="11831-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="11831-106">可以在全局或每个网站上更改和应用日志设置。</span><span class="sxs-lookup"><span data-stu-id="11831-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11831-107">若要更改</span><span class="sxs-lookup"><span data-stu-id="11831-107">To change</span></span></th>
<th><span data-ttu-id="11831-108">使用</span><span class="sxs-lookup"><span data-stu-id="11831-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11831-109">日志文件的最大大小 (以字节为单位)</span><span class="sxs-lookup"><span data-stu-id="11831-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="11831-110">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="11831-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="11831-111">或</span><span class="sxs-lookup"><span data-stu-id="11831-111">-or-</span></span></p>
<p><span data-ttu-id="11831-112">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="11831-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11831-113">可以保留在缓存中的最大信息量 (以字节为单位)</span><span class="sxs-lookup"><span data-stu-id="11831-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="11831-114">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="11831-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="11831-115">或</span><span class="sxs-lookup"><span data-stu-id="11831-115">-or-</span></span></p>
<p><span data-ttu-id="11831-116">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="11831-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11831-117">将缓存的信息写入日志文件的频率 (以分钟为单位)</span><span class="sxs-lookup"><span data-stu-id="11831-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="11831-118">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="11831-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="11831-119">或</span><span class="sxs-lookup"><span data-stu-id="11831-119">-or-</span></span></p>
<p><span data-ttu-id="11831-120">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="11831-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11831-121">将日志文件保留多长时间 (天)</span><span class="sxs-lookup"><span data-stu-id="11831-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="11831-122">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="11831-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="11831-123">或</span><span class="sxs-lookup"><span data-stu-id="11831-123">-or-</span></span></p>
<p><span data-ttu-id="11831-124">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="11831-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11831-125">何时 (一天的时间) 检查应删除的过期文件</span><span class="sxs-lookup"><span data-stu-id="11831-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="11831-126">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="11831-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11831-127">允许的日志文件扩展名</span><span class="sxs-lookup"><span data-stu-id="11831-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="11831-128">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="11831-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11831-129">要保留的日志文件类型</span><span class="sxs-lookup"><span data-stu-id="11831-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="11831-130">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="11831-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="11831-131">使用 Lync Server "控制面板" 更改日志记录设置</span><span class="sxs-lookup"><span data-stu-id="11831-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="11831-132">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="11831-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11831-133">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="11831-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="11831-134">在左侧导航栏中, 单击 "**客户端**", 然后单击 "**设备日志配置**"。</span><span class="sxs-lookup"><span data-stu-id="11831-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="11831-135">在 "**设备日志配置**" 页面上, 双击要更改的配置。</span><span class="sxs-lookup"><span data-stu-id="11831-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="11831-136">在 "**编辑日志设置**" 对话框中, 更改以下任何设置:</span><span class="sxs-lookup"><span data-stu-id="11831-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="11831-137">**最大文件大小 (字节)**   指定日志文件在清除之前可以达到的最大大小。</span><span class="sxs-lookup"><span data-stu-id="11831-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="11831-138">默认值为1024000字节 (1 MB)。</span><span class="sxs-lookup"><span data-stu-id="11831-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="11831-139">**最大缓存大小 (字节)**   指定必须在日志文件缓存中保留的最大信息量 (以字节为单位), 然后才能在该缓存中清除, 并将数据写入日志文件。</span><span class="sxs-lookup"><span data-stu-id="11831-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="11831-140">默认值为512000字节 (0.5 MB)。</span><span class="sxs-lookup"><span data-stu-id="11831-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="11831-141">**刷新缓存的分钟数 (1-60)**   表示将日志文件缓存中存储的信息写入实际日志文件的频率。</span><span class="sxs-lookup"><span data-stu-id="11831-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="11831-142">记录数据后, 将清除缓存。</span><span class="sxs-lookup"><span data-stu-id="11831-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="11831-143">默认值为5分钟。</span><span class="sxs-lookup"><span data-stu-id="11831-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="11831-144">**保留日志文件的天数 (1-365)**   指定日志文件在清除之前保留的天数。</span><span class="sxs-lookup"><span data-stu-id="11831-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="11831-145">默认值为10天。</span><span class="sxs-lookup"><span data-stu-id="11831-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="11831-146">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="11831-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="11831-147">使用 Windows PowerShell Cmdlet 更改日志记录设置</span><span class="sxs-lookup"><span data-stu-id="11831-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="11831-148">可以使用 Windows PowerShell 和**CsDeviceUpdateConfiguration** cmdlet 修改设备更新日志文件设置。</span><span class="sxs-lookup"><span data-stu-id="11831-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="11831-149">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="11831-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11831-150">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="11831-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="11831-151">以下示例显示了可使用**CsDeviceUpdateConfiguration**修改设置的几种方式。</span><span class="sxs-lookup"><span data-stu-id="11831-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="11831-152">修改日志文件的最大大小和日志清除间隔</span><span class="sxs-lookup"><span data-stu-id="11831-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="11831-153">以下命令将修改应用于 Redmond 网站的设备更新日志设置。</span><span class="sxs-lookup"><span data-stu-id="11831-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="11831-154">在此示例中, 最大日志文件大小设置为204800字节, 日志清除间隔设置为14天。</span><span class="sxs-lookup"><span data-stu-id="11831-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="11831-155">修改日志清除的一天时间</span><span class="sxs-lookup"><span data-stu-id="11831-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="11831-156">此命令将雷德蒙站点的日志清除时间设置为 3:00 AM。</span><span class="sxs-lookup"><span data-stu-id="11831-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="11831-157">有关详细信息, 请参阅[CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="11831-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

