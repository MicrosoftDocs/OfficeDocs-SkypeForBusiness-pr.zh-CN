---
title: Lync Server 2013：修改设备更新日志文件的设置
description: Lync Server 2013：修改设备更新日志文件的设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c2086e11a67207a00ca99773cc818106b16d05c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566968"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="fde45-103">在 Lync Server 2013 中修改设备更新日志文件的设置</span><span class="sxs-lookup"><span data-stu-id="fde45-103">Modify settings for Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fde45-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fde45-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fde45-105">您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序更改设备更新信息在组织中的记录方式的设置。</span><span class="sxs-lookup"><span data-stu-id="fde45-105">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="fde45-106">下表显示了哪些设置是可修改的，以及用来修改设置) 哪个工具 (s。</span><span class="sxs-lookup"><span data-stu-id="fde45-106">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="fde45-107">可以在全局或每个站点上更改和应用日志设置。</span><span class="sxs-lookup"><span data-stu-id="fde45-107">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fde45-108">若要更改</span><span class="sxs-lookup"><span data-stu-id="fde45-108">To change</span></span></th>
<th><span data-ttu-id="fde45-109">用途</span><span class="sxs-lookup"><span data-stu-id="fde45-109">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fde45-110">日志文件的最大大小 () （以字节为单位）</span><span class="sxs-lookup"><span data-stu-id="fde45-110">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="fde45-111">Lync 服务器控制面板</span><span class="sxs-lookup"><span data-stu-id="fde45-111">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="fde45-112">-或者-</span><span class="sxs-lookup"><span data-stu-id="fde45-112">-or-</span></span></p>
<p><span data-ttu-id="fde45-113">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="fde45-113">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fde45-114">可在缓存中保留的最大信息量 (（以字节为单位）) </span><span class="sxs-lookup"><span data-stu-id="fde45-114">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="fde45-115">Lync 服务器控制面板</span><span class="sxs-lookup"><span data-stu-id="fde45-115">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="fde45-116">-或者-</span><span class="sxs-lookup"><span data-stu-id="fde45-116">-or-</span></span></p>
<p><span data-ttu-id="fde45-117">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="fde45-117">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fde45-118">将缓存信息写入日志文件的时间（分钟） (的频率) </span><span class="sxs-lookup"><span data-stu-id="fde45-118">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="fde45-119">Lync 服务器控制面板</span><span class="sxs-lookup"><span data-stu-id="fde45-119">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="fde45-120">-或者-</span><span class="sxs-lookup"><span data-stu-id="fde45-120">-or-</span></span></p>
<p><span data-ttu-id="fde45-121">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="fde45-121">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fde45-122">) 保留日志文件的时间 (（天）</span><span class="sxs-lookup"><span data-stu-id="fde45-122">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="fde45-123">Lync 服务器控制面板</span><span class="sxs-lookup"><span data-stu-id="fde45-123">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="fde45-124">-或者-</span><span class="sxs-lookup"><span data-stu-id="fde45-124">-or-</span></span></p>
<p><span data-ttu-id="fde45-125">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="fde45-125">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fde45-126">当一天中的 (时间) 检查应删除的已过期文件</span><span class="sxs-lookup"><span data-stu-id="fde45-126">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="fde45-127">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="fde45-127">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fde45-128">允许的日志文件扩展名</span><span class="sxs-lookup"><span data-stu-id="fde45-128">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="fde45-129">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="fde45-129">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fde45-130">要保留的日志文件类型</span><span class="sxs-lookup"><span data-stu-id="fde45-130">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="fde45-131">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="fde45-131">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="fde45-132">使用 Lync Server 控制面板更改日志记录设置的具体方法</span><span class="sxs-lookup"><span data-stu-id="fde45-132">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fde45-133">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="fde45-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fde45-134">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="fde45-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="fde45-135">在左侧导航栏中，单击 **“客户端”**，然后单击 **“设备日志配置”**。</span><span class="sxs-lookup"><span data-stu-id="fde45-135">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="fde45-136">在 **“设备日志配置”** 页上，双击要更改的配置。</span><span class="sxs-lookup"><span data-stu-id="fde45-136">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="fde45-137">在 " **编辑日志设置** " 对话框中，更改以下任何设置：</span><span class="sxs-lookup"><span data-stu-id="fde45-137">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="fde45-138">\*\* (字节的最大文件大小) \*\*    指定日志文件在清除之前可以达到的最大大小。</span><span class="sxs-lookup"><span data-stu-id="fde45-138">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="fde45-139">默认值为1024000个字节 (1 MB) 。</span><span class="sxs-lookup"><span data-stu-id="fde45-139">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="fde45-140">\*\* (字节的最大缓存大小) \*\*    指定必须在日志文件缓存中保留的最大信息量（以字节为单位），在该缓存必须被清除，并将数据写入日志文件时，才能在日志文件缓存中保留 () 。</span><span class="sxs-lookup"><span data-stu-id="fde45-140">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="fde45-141">默认值为512000个字节 (0.5 MB) 。</span><span class="sxs-lookup"><span data-stu-id="fde45-141">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="fde45-142">\*\*刷新缓存 (1-60 的分钟数) \*\*    指示日志文件缓存中存储的信息写入实际日志文件的频率。</span><span class="sxs-lookup"><span data-stu-id="fde45-142">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="fde45-143">记录数据后，将清除缓存。</span><span class="sxs-lookup"><span data-stu-id="fde45-143">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="fde45-144">默认值为5分钟。</span><span class="sxs-lookup"><span data-stu-id="fde45-144">The default is five minutes.</span></span>
    
      - <span data-ttu-id="fde45-145">\*\*日志文件 (1-365) \*\*     的保留天数指定日志文件在清除之前保留的天数。</span><span class="sxs-lookup"><span data-stu-id="fde45-145">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="fde45-146">默认值为10天。</span><span class="sxs-lookup"><span data-stu-id="fde45-146">The default is 10 days.</span></span>

5.  <span data-ttu-id="fde45-147">单击 **“提交”**。</span><span class="sxs-lookup"><span data-stu-id="fde45-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fde45-148">使用 Windows PowerShell Cmdlet 更改日志记录设置</span><span class="sxs-lookup"><span data-stu-id="fde45-148">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fde45-149">可以使用 Windows PowerShell 和 **CsDeviceUpdateConfiguration** cmdlet 修改设备更新日志文件设置。</span><span class="sxs-lookup"><span data-stu-id="fde45-149">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="fde45-150">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="fde45-150">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fde45-151">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="fde45-151">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="fde45-152">以下示例显示了使用 **CsDeviceUpdateConfiguration** 修改设置的几种方法。</span><span class="sxs-lookup"><span data-stu-id="fde45-152">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="fde45-153">修改日志文件的最大大小和日志清除间隔</span><span class="sxs-lookup"><span data-stu-id="fde45-153">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="fde45-154">以下命令将修改应用于 Redmond 站点的设备更新日志设置。</span><span class="sxs-lookup"><span data-stu-id="fde45-154">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="fde45-155">在此示例中，日志文件的最大大小设置为204800个字节，日志清理间隔设置为14天。</span><span class="sxs-lookup"><span data-stu-id="fde45-155">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="fde45-156">修改日志清除的一天的时间</span><span class="sxs-lookup"><span data-stu-id="fde45-156">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="fde45-157">此命令将 Redmond 网站的日志清除时间设置为 3:00 AM。</span><span class="sxs-lookup"><span data-stu-id="fde45-157">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="fde45-158">有关详细信息，请参阅 [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fde45-158">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

