---
title: Lync Server 2013：为您的会议、应用程序和中介服务器配置端口范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd505990b9a060c3b669700ea9192dc1ad6b84c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="59eea-102">在 Lync Server 2013 中为您的会议、应用程序和中介服务器配置端口范围</span><span class="sxs-lookup"><span data-stu-id="59eea-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59eea-103">_**上次修改的主题：** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="59eea-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="59eea-p101">为了实现服务质量，您应在会议、应用程序和中介服务器上为音频、视频和应用程序共享配置相同的端口范围；此外，这些端口范围在任何情况下不得重叠。为了使用简单示例，假定您在会议服务器上将端口 10000 至 10999 用于视频。这意味着，您还必须在应用程序和中介服务器上为视频保留 10000 至 10999 这些端口。如果不这样做，QoS 将不会按预期工作。</span><span class="sxs-lookup"><span data-stu-id="59eea-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="59eea-p102">同样，假定您为视频保留了端口 10000 至 10999，但之后为音频保留了端口 10500 至 11999。这会产生服务质量问题，因为端口范围重叠。对于 QoS，每种形式必须具有一组唯一的端口：如果您将端口 10000 至 10999 用于视频，则必须使用不同的范围（例如，对音频使用 11000 至 11999）。</span><span class="sxs-lookup"><span data-stu-id="59eea-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="59eea-111">默认情况下，Microsoft Lync Server 2013 中的音频和视频端口范围不重叠;但是，分配给应用程序共享的端口范围与音频和视频端口范围重叠。</span><span class="sxs-lookup"><span data-stu-id="59eea-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="59eea-112">（反过来，这意味着这些范围都不是唯一的。）您可以通过在 Lync Server 2013 命令行管理程序中运行以下三个命令来验证您的会议、应用程序和中介服务器的现有端口范围：</span><span class="sxs-lookup"><span data-stu-id="59eea-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="59eea-p104">正如您在上面的命令中看到的，每种端口类型（音频、视频和应用程序共享）将分配有两个不同的属性值：起始端口和端口计数。起始端口指示用于相应形式的第一个端口；例如，如果音频起始端口等于 50000，则意味着用于音频通信的第一个端口为端口 50000。如果音频端口计数为 2（这不是一个有效值，但在此处作说明之用），则意味着仅为音频分配了 2 个端口。如果第一个端口为端口 50000 并且总共有两个端口，则意味着第二个端口必须为端口 50001（端口范围必须是连续的）。因此，音频的端口范围将为 50000 到 50001（包括 50000 和 50001）。</span><span class="sxs-lookup"><span data-stu-id="59eea-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="59eea-118">注意，应用程序服务器和中介服务器仅支持音频的服务质量；您无需更改应用程序服务器或中介服务器中的视频或应用程序共享端口。</span><span class="sxs-lookup"><span data-stu-id="59eea-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="59eea-119">如果您运行上述三个命令，则会看到 Lync Server 2013 的默认端口值配置如下：</span><span class="sxs-lookup"><span data-stu-id="59eea-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59eea-120">属性</span><span class="sxs-lookup"><span data-stu-id="59eea-120">Property</span></span></th>
<th><span data-ttu-id="59eea-121">会议服务器</span><span class="sxs-lookup"><span data-stu-id="59eea-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="59eea-122">应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="59eea-122">Application Server</span></span></th>
<th><span data-ttu-id="59eea-123">中介服务器</span><span class="sxs-lookup"><span data-stu-id="59eea-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59eea-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="59eea-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="59eea-125">49152</span><span class="sxs-lookup"><span data-stu-id="59eea-125">49152</span></span></p></td>
<td><p><span data-ttu-id="59eea-126">49152</span><span class="sxs-lookup"><span data-stu-id="59eea-126">49152</span></span></p></td>
<td><p><span data-ttu-id="59eea-127">49152</span><span class="sxs-lookup"><span data-stu-id="59eea-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59eea-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="59eea-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="59eea-129">8348</span><span class="sxs-lookup"><span data-stu-id="59eea-129">8348</span></span></p></td>
<td><p><span data-ttu-id="59eea-130">8348</span><span class="sxs-lookup"><span data-stu-id="59eea-130">8348</span></span></p></td>
<td><p><span data-ttu-id="59eea-131">8348</span><span class="sxs-lookup"><span data-stu-id="59eea-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59eea-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="59eea-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="59eea-133">57501</span><span class="sxs-lookup"><span data-stu-id="59eea-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59eea-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="59eea-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="59eea-135">8034</span><span class="sxs-lookup"><span data-stu-id="59eea-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59eea-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="59eea-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="59eea-137">49152</span><span class="sxs-lookup"><span data-stu-id="59eea-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59eea-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="59eea-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="59eea-139">16383</span><span class="sxs-lookup"><span data-stu-id="59eea-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59eea-140">如前所述，在为 QoS 配置 Lync Server 端口时，应确保：1）音频端口设置在您的所有会议、应用程序和中介服务器上都相同;和2）端口范围不重叠。</span><span class="sxs-lookup"><span data-stu-id="59eea-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="59eea-141">如果仔细查看前面的表，您将看到端口范围在三种服务器类型中相同。</span><span class="sxs-lookup"><span data-stu-id="59eea-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="59eea-142">例如，在每个服务器类型上，启动音频端口设置为端口49152，在每个服务器上为音频保留的端口总数也相同：8348。</span><span class="sxs-lookup"><span data-stu-id="59eea-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="59eea-143">但是，端口范围重叠：音频端口从端口49152开始，但这些端口设置为应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="59eea-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="59eea-144">为了获得最佳使用服务质量，应将应用程序共享重新配置为使用唯一的端口范围。</span><span class="sxs-lookup"><span data-stu-id="59eea-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="59eea-145">例如，可以将应用程序共享配置为在端口40803处启动，并使用8348端口。</span><span class="sxs-lookup"><span data-stu-id="59eea-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="59eea-146">（为什么要8348端口？</span><span class="sxs-lookup"><span data-stu-id="59eea-146">(Why 8348 ports?</span></span> <span data-ttu-id="59eea-147">如果将这些值一起添加--40803 + 8348--这意味着应用程序共享将使用端口40803通过端口49150。</span><span class="sxs-lookup"><span data-stu-id="59eea-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="59eea-148">由于音频端口不会开始到端口49152，因此您将不再具有任何重叠的端口范围。</span><span class="sxs-lookup"><span data-stu-id="59eea-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="59eea-p106">为应用程序共享选择新的端口范围之后，您可使用 Set-CsConferencingServer cmdlet 进行更改。此更改无需在应用程序服务器或中介服务器上进行，因为这些服务器不会处理应用程序共享流量。如果您决定重新分配用于音频通信的端口，则只需更改这些服务器上的端口值。</span><span class="sxs-lookup"><span data-stu-id="59eea-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="59eea-152">若要修改单个会议服务器上的应用程序共享的端口值，请在 Lync Server 命令行管理程序中运行与此类似的命令：</span><span class="sxs-lookup"><span data-stu-id="59eea-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="59eea-153">如果要在所有会议服务器上进行这些更改，则可改为运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="59eea-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="59eea-154">更改端口设置之后，您应停止，然后重新启动受更改影响的每个服务。</span><span class="sxs-lookup"><span data-stu-id="59eea-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="59eea-p107">会议服务器、应用程序服务器和中介服务器不必共享完全相同的端口范围；您唯一必须做的是在所有服务器上留出唯一的端口范围。但是，如果您在所有服务器上使用相同的端口集，则管理一般会更加轻松。</span><span class="sxs-lookup"><span data-stu-id="59eea-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

