---
title: 'Lync Server 2013: 设备报表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e172837622c4ad40a29cca74dcaf42497c4b2bd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="beaef-102">Lync Server 2013 中的设备报表</span><span class="sxs-lookup"><span data-stu-id="beaef-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beaef-103">_**主题上次修改时间:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="beaef-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="beaef-104">设备报告可能更好地为麦克风和扬声器报告加了标题；这是因为，该设备报告检索按呼叫中使用的麦克风和扬声器分组的呼叫相关的指标（例如，质量欠佳的呼叫百分比、回声和语音切换时间）。</span><span class="sxs-lookup"><span data-stu-id="beaef-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="beaef-105">如果你对 IP 电话感兴趣 (通常也称为 "设备"), 请改用[Lync Server 2013 中的 Ip 手机库存报告](lync-server-2013-ip-phone-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="beaef-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="beaef-p102">该设备报告在管理员确定特定类型的设备遇到的质量欠佳的呼叫量是否高于其他呼叫时极其有用。转而，这会对即将购买新设备或替换现有设备时所做的任何决策产生影响。</span><span class="sxs-lookup"><span data-stu-id="beaef-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="beaef-p103">默认情况下，设备报告中显示的信息也基于该呼叫中使用的麦克风（捕获设备）和扬声器/耳麦（呈现设备）。例如，假定您有多个使用下列捕获设备和下列呈现设备的用户：</span><span class="sxs-lookup"><span data-stu-id="beaef-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="beaef-111">捕获设备 - 麦克风（SoundMAX 集成的数字 HD 音频）</span><span class="sxs-lookup"><span data-stu-id="beaef-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="beaef-112">呈现设备 - 头戴式耳机 (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="beaef-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="beaef-113">如果这些用户进行了总共 254 次呼叫，则您将在此报告中看到此类似条目：</span><span class="sxs-lookup"><span data-stu-id="beaef-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beaef-114">捕获设备</span><span class="sxs-lookup"><span data-stu-id="beaef-114">Capture device</span></span></th>
<th><span data-ttu-id="beaef-115">呈现设备</span><span class="sxs-lookup"><span data-stu-id="beaef-115">Render device</span></span></th>
<th><span data-ttu-id="beaef-116">呼叫量</span><span class="sxs-lookup"><span data-stu-id="beaef-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beaef-117">麦克风（SoundMAX 集成数字 HD 音频）</span><span class="sxs-lookup"><span data-stu-id="beaef-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="beaef-118">头戴式耳机 (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="beaef-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="beaef-119">254</span><span class="sxs-lookup"><span data-stu-id="beaef-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="beaef-p104">现在，假定您有一些使用相同捕获设备但不同的呈现设备的用户。在这种情况下，您在报告中将有第二行的条目，一行用于捕获设备和呈现设备的唯一组合：</span><span class="sxs-lookup"><span data-stu-id="beaef-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beaef-122">捕获设备</span><span class="sxs-lookup"><span data-stu-id="beaef-122">Capture device</span></span></th>
<th><span data-ttu-id="beaef-123">呈现设备</span><span class="sxs-lookup"><span data-stu-id="beaef-123">Render device</span></span></th>
<th><span data-ttu-id="beaef-124">呼叫量</span><span class="sxs-lookup"><span data-stu-id="beaef-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beaef-125">麦克风（SoundMAX 集成数字 HD 音频）</span><span class="sxs-lookup"><span data-stu-id="beaef-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="beaef-126">头戴式耳机 (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="beaef-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="beaef-127">254</span><span class="sxs-lookup"><span data-stu-id="beaef-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-128">麦克风（SoundMAX 集成数字 HD 音频）</span><span class="sxs-lookup"><span data-stu-id="beaef-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="beaef-129">扬声器（SoundMAX 集成数字 HD 音频）</span><span class="sxs-lookup"><span data-stu-id="beaef-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="beaef-130">319</span><span class="sxs-lookup"><span data-stu-id="beaef-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="beaef-p105">如果您更想看到给定设备（例如，对于 SoundMAX 捕获设备，与使用的呈现设备无关）的合并总数，从设备类型下拉列表（捕获设备或呈现设备）选择相应的选项。如果在此示例中选择捕获设备，将会为您提供类似以下输出：</span><span class="sxs-lookup"><span data-stu-id="beaef-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beaef-133">捕获设备</span><span class="sxs-lookup"><span data-stu-id="beaef-133">Capture device</span></span></th>
<th><span data-ttu-id="beaef-134">呼叫量</span><span class="sxs-lookup"><span data-stu-id="beaef-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beaef-135">麦克风（SoundMAX 集成数字 HD 音频）</span><span class="sxs-lookup"><span data-stu-id="beaef-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="beaef-136">573</span><span class="sxs-lookup"><span data-stu-id="beaef-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="beaef-137">访问设备报告</span><span class="sxs-lookup"><span data-stu-id="beaef-137">Accessing the Device Report</span></span>

<span data-ttu-id="beaef-138">通常可从监控报告主页访问该设备报告。</span><span class="sxs-lookup"><span data-stu-id="beaef-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="beaef-139">但是, 如果你在[Lync Server 2013 中查看 "呼叫详细信息" 报告](lync-server-2013-call-detail-report.md), 你可以通过单击以下任一指标向下钻取到特定设备的设备报告:</span><span class="sxs-lookup"><span data-stu-id="beaef-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="beaef-140">捕获设备</span><span class="sxs-lookup"><span data-stu-id="beaef-140">Capture Device</span></span>

  - <span data-ttu-id="beaef-141">呈现设备</span><span class="sxs-lookup"><span data-stu-id="beaef-141">Render Device</span></span>

<span data-ttu-id="beaef-142">在 "设备" 报表中, 通过单击以下任一指标, 可以向下钻取到[Lync Server 2013 中的 "通话清单" 报告](lync-server-2013-call-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="beaef-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="beaef-143">呼叫量</span><span class="sxs-lookup"><span data-stu-id="beaef-143">Call volume</span></span>

  - <span data-ttu-id="beaef-144">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="beaef-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="beaef-145">充分利用设备报告</span><span class="sxs-lookup"><span data-stu-id="beaef-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="beaef-146">当涉及到设备名称时，设备报告会进行极其详细的描述；例如，假定您有下列捕获设备：</span><span class="sxs-lookup"><span data-stu-id="beaef-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="beaef-147">Aastra 3002 麦克风 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="beaef-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="beaef-148">Aastra 3002 麦克风 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="beaef-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="beaef-149">Aastra 3002 麦克风 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="beaef-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="beaef-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="beaef-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="beaef-151">Aastra 6725ip 麦克风 (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-152">Aastra 6725ip 麦克风 (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="beaef-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="beaef-153">Aastra 6725ip 麦克风 (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-154">Aastra 6725ip 麦克风 (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-155">Aastra 6725ip 麦克风 (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-156">Aastra 6725ip 麦克风 (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-157">Aastra 6725ip 麦克风 (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-158">Aastra 6725ip 麦克风 (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-159">Aastra 6725ip 麦克风 (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-160">Aastra 6725ip 麦克风 (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="beaef-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="beaef-161">Aastra 6725ip 麦克风 (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="beaef-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="beaef-162">Aastra 6725ip 麦克风 (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="beaef-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="beaef-163">Aastra 6725ip 麦克风（USB 音频设备）</span><span class="sxs-lookup"><span data-stu-id="beaef-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="beaef-164">Aastra 6725ip 麦克风（USB 音频设备）-V0</span><span class="sxs-lookup"><span data-stu-id="beaef-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beaef-165">请记住, 如果你运行的是 Lync Server 2013 的本地化版本, 则捕获设备名称可能不同。</span><span class="sxs-lookup"><span data-stu-id="beaef-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="beaef-166">美国英语中名为 Aastra 6725ip 麦克风 (Aastra 6725ip)-V0 的设备在法语和西班牙语中可能会有不同的名称。</span><span class="sxs-lookup"><span data-stu-id="beaef-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="beaef-167">很多时候，您想拥有该级别的详细信息；但在其他时候，您可能仅对多少呼叫在使用普通的 Aastra 麦克风感兴趣，而与型号无关。</span><span class="sxs-lookup"><span data-stu-id="beaef-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="beaef-168">获取信息的一种方法是将设备报表数据导出到 Microsoft Excel, 然后将该数据保存到逗号分隔值文件 (例如 C:\\数据\\设备\_Report .csv)。</span><span class="sxs-lookup"><span data-stu-id="beaef-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="beaef-169">然后使用一组类似这些的命令，将 .CSV 文件导入到 Windows PowerShell 中，并报告回使用 Aastra 捕获设备所做的呼叫总数：</span><span class="sxs-lookup"><span data-stu-id="beaef-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="beaef-p109">这将返回使代表用 Aastra 捕获设备执行的呼叫总数的单个值。例如：</span><span class="sxs-lookup"><span data-stu-id="beaef-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="beaef-172">筛选器</span><span class="sxs-lookup"><span data-stu-id="beaef-172">Filters</span></span>

<span data-ttu-id="beaef-p110">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，通过设备报告，您可以对诸如呼叫类型（即，该呼叫是否为客户端呼叫）的内容、电话会议或公用电话交换网 (PSTN) 呼叫进行筛选。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对设备进行分组。</span><span class="sxs-lookup"><span data-stu-id="beaef-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="beaef-177">下表列出了可用于设备报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="beaef-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="beaef-178">设备报告筛选器</span><span class="sxs-lookup"><span data-stu-id="beaef-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beaef-179">名称</span><span class="sxs-lookup"><span data-stu-id="beaef-179">Name</span></span></th>
<th><span data-ttu-id="beaef-180">描述</span><span class="sxs-lookup"><span data-stu-id="beaef-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beaef-181"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p111">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="beaef-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="beaef-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="beaef-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="beaef-p112">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="beaef-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="beaef-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="beaef-187">7/7/2012</span></span></p>
<p><span data-ttu-id="beaef-188">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="beaef-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="beaef-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="beaef-189">7/3/2012</span></span></p>
<p><span data-ttu-id="beaef-190">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="beaef-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-191"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p113">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="beaef-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="beaef-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="beaef-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="beaef-p114">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="beaef-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="beaef-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="beaef-197">7/7/2012</span></span></p>
<p><span data-ttu-id="beaef-198">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="beaef-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="beaef-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="beaef-199">7/3/2012</span></span></p>
<p><span data-ttu-id="beaef-200">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="beaef-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-201"><strong>语音切换原因</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p115">呼叫必须切换为半双工模式才能防止回声的原因。在半双工模式中，通信一次只能在一个方向进行，与用户在使用对讲机进行通信时的轮流方式相似。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="beaef-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-205">[所有]</span><span class="sxs-lookup"><span data-stu-id="beaef-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-206">无</span><span class="sxs-lookup"><span data-stu-id="beaef-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-207">错误的时间戳</span><span class="sxs-lookup"><span data-stu-id="beaef-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-208">回声</span><span class="sxs-lookup"><span data-stu-id="beaef-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-209">DNLP（动态非线性处理器）</span><span class="sxs-lookup"><span data-stu-id="beaef-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-210">复杂度低</span><span class="sxs-lookup"><span data-stu-id="beaef-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-211">设备状态差</span><span class="sxs-lookup"><span data-stu-id="beaef-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-212">AEC 后的回声（回声抑制）</span><span class="sxs-lookup"><span data-stu-id="beaef-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-213"><strong>回声原因</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p116">在呼叫中检测到超出接受水平的回声的原因。（在长途通讯中，回声是声音的反射，与朝井底大喊时出现的现象一样。）选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="beaef-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-216">[所有]</span><span class="sxs-lookup"><span data-stu-id="beaef-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-217">无</span><span class="sxs-lookup"><span data-stu-id="beaef-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-218">错误的时间戳</span><span class="sxs-lookup"><span data-stu-id="beaef-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-219">AEC 后的回声（回声抑制）</span><span class="sxs-lookup"><span data-stu-id="beaef-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-220">ANLP（自适应非线性处理器）</span><span class="sxs-lookup"><span data-stu-id="beaef-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-221">DNLP（动态非线性处理器）</span><span class="sxs-lookup"><span data-stu-id="beaef-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-222">麦克风剪辑</span><span class="sxs-lookup"><span data-stu-id="beaef-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-223"><strong>呼叫类型</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p117">指示发起的呼叫类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="beaef-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-226">[所有]</span><span class="sxs-lookup"><span data-stu-id="beaef-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-227">客户端呼叫</span><span class="sxs-lookup"><span data-stu-id="beaef-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-228">PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="beaef-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-229">电话会议</span><span class="sxs-lookup"><span data-stu-id="beaef-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-230"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p118">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="beaef-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-233">[所有]</span><span class="sxs-lookup"><span data-stu-id="beaef-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-234">内部</span><span class="sxs-lookup"><span data-stu-id="beaef-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-235">外部</span><span class="sxs-lookup"><span data-stu-id="beaef-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-236"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p119">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="beaef-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-239">[所有]</span><span class="sxs-lookup"><span data-stu-id="beaef-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-240">有线</span><span class="sxs-lookup"><span data-stu-id="beaef-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-241">无线</span><span class="sxs-lookup"><span data-stu-id="beaef-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p120">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="beaef-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-245">[所有]</span><span class="sxs-lookup"><span data-stu-id="beaef-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-246">VPN</span><span class="sxs-lookup"><span data-stu-id="beaef-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-247">非 VPN</span><span class="sxs-lookup"><span data-stu-id="beaef-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-248"><strong>设备类型</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p121">指示设备的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="beaef-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-251">捕获设备</span><span class="sxs-lookup"><span data-stu-id="beaef-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-252">呈现设备</span><span class="sxs-lookup"><span data-stu-id="beaef-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="beaef-253">捕获/呈现设备</span><span class="sxs-lookup"><span data-stu-id="beaef-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-254"><strong>设备名称</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-p122">捕获或呈现设备的名称。您可以输入完整设备名称，也可以输入设备名称的任何部分。例如，若要查找设备麦克风 (Microsoft LifeCam VX-1000.)，可输入完整设备名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="beaef-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="beaef-258">麦克风 (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="beaef-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="beaef-p123">或者，可只输入该名称的一部分。例如：</span><span class="sxs-lookup"><span data-stu-id="beaef-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="beaef-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="beaef-261">LifeCam</span></span></p>
<p><span data-ttu-id="beaef-262">请注意, 上述筛选器返回任何在其名称中&quot;任何&quot;位置包含字符串 LifeCam 的设备。</span><span class="sxs-lookup"><span data-stu-id="beaef-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="beaef-263">指标</span><span class="sxs-lookup"><span data-stu-id="beaef-263">Metrics</span></span>

<span data-ttu-id="beaef-264">下表列出了设备报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="beaef-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="beaef-265">设备报告度量</span><span class="sxs-lookup"><span data-stu-id="beaef-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beaef-266">名称</span><span class="sxs-lookup"><span data-stu-id="beaef-266">Name</span></span></th>
<th><span data-ttu-id="beaef-267">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="beaef-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="beaef-268">描述</span><span class="sxs-lookup"><span data-stu-id="beaef-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beaef-269"><strong>捕获设备</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-270">是</span><span class="sxs-lookup"><span data-stu-id="beaef-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-271">用于传输音频的设备（例如麦克风或网络摄像机）。</span><span class="sxs-lookup"><span data-stu-id="beaef-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-272"><strong>呈现设备</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-273">是</span><span class="sxs-lookup"><span data-stu-id="beaef-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-274">用于接收音频的设备（例如耳机或扬声器）。</span><span class="sxs-lookup"><span data-stu-id="beaef-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-275"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-276">是</span><span class="sxs-lookup"><span data-stu-id="beaef-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-277">发起的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="beaef-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-278"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-279">是</span><span class="sxs-lookup"><span data-stu-id="beaef-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-280">分类为&quot;差的通话百分比。&quot;较差的通话是指至少一个已测量指标超过允许值的电话 (例如, 经历过多抖动的呼叫)。</span><span class="sxs-lookup"><span data-stu-id="beaef-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-281"><strong>唯一用户数</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-282">是</span><span class="sxs-lookup"><span data-stu-id="beaef-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-p124">使用过该设备的唯一用户。如果某用户使用该设备 13 次，他（她）也被计为一个唯一用户，与使用该设备一次的用户相同。</span><span class="sxs-lookup"><span data-stu-id="beaef-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-285"><strong>语音切换时间比率</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-286">是</span><span class="sxs-lookup"><span data-stu-id="beaef-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-p125">必须在半双工模式中执行的用于防止回声的呼叫百分比。在半双工模式中，通信一次只能在一个方向进行，与用户在使用对讲机进行通信时的轮流方式相似。</span><span class="sxs-lookup"><span data-stu-id="beaef-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-289"><strong>麦克风无法正常工作的比率</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-290">是</span><span class="sxs-lookup"><span data-stu-id="beaef-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-p126">捕获设备未在可接受水平运行的呼叫的百分比。这些值高表示呼叫的质量问题主要是由于捕获设备未按预期正常运行造成的。</span><span class="sxs-lookup"><span data-stu-id="beaef-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-293"><strong>扬声器无法正常工作的比率</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-294">是</span><span class="sxs-lookup"><span data-stu-id="beaef-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-p127">呈现设备未在可接受水平运行的呼叫的百分比。这些值高表示呼叫的质量问题主要是由于呈现设备未按预期正常运行造成的。</span><span class="sxs-lookup"><span data-stu-id="beaef-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-297"><strong>具有语音切换的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-298">是</span><span class="sxs-lookup"><span data-stu-id="beaef-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-p128">必须在半双工模式中拨打的总呼叫数的百分比。在半双工模式中，通信一次只能在一个方向进行，与用户在使用对讲机进行通信时的轮流方式相似。</span><span class="sxs-lookup"><span data-stu-id="beaef-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-301"><strong>麦克风回声百分比</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-302">是</span><span class="sxs-lookup"><span data-stu-id="beaef-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-p129">在麦克风捕获流量中检测回声时的时间百分比。通常，对于耳机或话筒，值较低，而对于扬声器电话或独立扬声器，值较高。对于支持板载声学回声消除的设备，高值表示回声泄漏。对于其他设备，不应使用此指标评估设备质量。</span><span class="sxs-lookup"><span data-stu-id="beaef-p129">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaef-307"><strong>回声发送百分比</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-308">是</span><span class="sxs-lookup"><span data-stu-id="beaef-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-309">传输到其他用户的回声的百分比。</span><span class="sxs-lookup"><span data-stu-id="beaef-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaef-310"><strong>具有回声的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="beaef-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="beaef-311">是</span><span class="sxs-lookup"><span data-stu-id="beaef-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="beaef-312">回声超出可接受水平的总呼叫数的百分比。</span><span class="sxs-lookup"><span data-stu-id="beaef-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

