---
title: 为会议、应用程序和中介服务器配置端口范围和服务质量策略
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文介绍如何为会议、应用程序和中介服务器配置端口范围和服务质量策略。
ms.openlocfilehash: 8c65e36528615aca181b6aac17aab844c1a4d206
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800122"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="719b5-103">为会议、应用程序和中介服务器配置端口范围和服务质量策略</span><span class="sxs-lookup"><span data-stu-id="719b5-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="719b5-104">本文介绍如何为会议、应用程序和中介服务器配置端口范围和服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="719b5-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="719b5-105">配置端口范围</span><span class="sxs-lookup"><span data-stu-id="719b5-105">Configure port ranges</span></span>

<span data-ttu-id="719b5-106">若要实现服务质量，应为会议、应用程序和中介服务器上的音频、视频和应用程序共享配置相同的端口范围;此外，这些端口范围不得以任何方式重叠。</span><span class="sxs-lookup"><span data-stu-id="719b5-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="719b5-107">为了使用简单示例，假定您在会议服务器上将端口 10000 至 10999 用于视频。</span><span class="sxs-lookup"><span data-stu-id="719b5-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="719b5-108">这意味着，您还必须在应用程序和中介服务器上为视频保留 10000 至 10999 这些端口。</span><span class="sxs-lookup"><span data-stu-id="719b5-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="719b5-109">如果不这样做，QoS 将不会按预期工作。</span><span class="sxs-lookup"><span data-stu-id="719b5-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="719b5-110">同样，假定您为视频保留了端口 10000 至 10999，但之后为音频保留了端口 10500 至 11999。</span><span class="sxs-lookup"><span data-stu-id="719b5-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="719b5-111">这会产生服务质量问题，因为端口范围重叠。</span><span class="sxs-lookup"><span data-stu-id="719b5-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="719b5-112">对于 QoS，每种形式都必须有一组唯一的端口：如果将端口 10000 到 10999 用于视频，则必须对音频 (使用不同的范围 (例如，11000 到 1199) 9。</span><span class="sxs-lookup"><span data-stu-id="719b5-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="719b5-113">默认情况下，音频和视频端口范围不会在 Skype for Business Server 中重叠;但是，分配给应用程序共享的端口范围与音频和视频端口范围重叠。</span><span class="sxs-lookup"><span data-stu-id="719b5-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="719b5-114"> (这意味着这些范围都不是唯一的。) 可以通过在 Skype for Business Server 命令行管理程序 中运行以下三个命令来验证会议、应用程序和中介服务器的现有端口范围：</span><span class="sxs-lookup"><span data-stu-id="719b5-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="719b5-115">正如您在上面的命令中看到的，每种端口类型（音频、视频和应用程序共享）将分配有两个不同的属性值：起始端口和端口计数。</span><span class="sxs-lookup"><span data-stu-id="719b5-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="719b5-116">起始端口指示用于相应形式的第一个端口；例如，如果音频起始端口等于 50000，则意味着用于音频通信的第一个端口为端口 50000。</span><span class="sxs-lookup"><span data-stu-id="719b5-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="719b5-117">如果音频端口计数为 2 (，则此值不是有效值，但在此处用于说明) ，这意味着只为音频分配了两个端口。</span><span class="sxs-lookup"><span data-stu-id="719b5-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="719b5-118">如果第一个端口为端口 50000 并且总共有两个端口，则意味着第二个端口必须为端口 50001（端口范围必须是连续的）。</span><span class="sxs-lookup"><span data-stu-id="719b5-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="719b5-119">因此，音频的端口范围将为 50000 到 50001（包括 50000 和 50001）。</span><span class="sxs-lookup"><span data-stu-id="719b5-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="719b5-120">注意，应用程序服务器和中介服务器仅支持音频的服务质量；您无需更改应用程序服务器或中介服务器中的视频或应用程序共享端口。</span><span class="sxs-lookup"><span data-stu-id="719b5-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="719b5-121">如果运行上述三个命令，你将看到 Skype for Business Server 的默认端口值配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="719b5-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="719b5-122">属性</span><span class="sxs-lookup"><span data-stu-id="719b5-122">Property</span></span></th>
<th><span data-ttu-id="719b5-123">会议服务器</span><span class="sxs-lookup"><span data-stu-id="719b5-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="719b5-124">应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="719b5-124">Application Server</span></span></th>
<th><span data-ttu-id="719b5-125">中介服务器</span><span class="sxs-lookup"><span data-stu-id="719b5-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="719b5-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="719b5-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="719b5-127">49152</span><span class="sxs-lookup"><span data-stu-id="719b5-127">49152</span></span></p></td>
<td><p><span data-ttu-id="719b5-128">49152</span><span class="sxs-lookup"><span data-stu-id="719b5-128">49152</span></span></p></td>
<td><p><span data-ttu-id="719b5-129">49152</span><span class="sxs-lookup"><span data-stu-id="719b5-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719b5-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="719b5-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="719b5-131">8348</span><span class="sxs-lookup"><span data-stu-id="719b5-131">8348</span></span></p></td>
<td><p><span data-ttu-id="719b5-132">8348</span><span class="sxs-lookup"><span data-stu-id="719b5-132">8348</span></span></p></td>
<td><p><span data-ttu-id="719b5-133">8348</span><span class="sxs-lookup"><span data-stu-id="719b5-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719b5-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="719b5-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="719b5-135">57501</span><span class="sxs-lookup"><span data-stu-id="719b5-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719b5-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="719b5-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="719b5-137">8034</span><span class="sxs-lookup"><span data-stu-id="719b5-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719b5-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="719b5-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="719b5-139">49152</span><span class="sxs-lookup"><span data-stu-id="719b5-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719b5-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="719b5-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="719b5-141">16383</span><span class="sxs-lookup"><span data-stu-id="719b5-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="719b5-142">如前所述，为 QoS 配置 Skype for Business Server 端口时，应确保：1) 音频端口设置在会议、应用程序和中介服务器中相同;和 2) 端口范围不重叠。</span><span class="sxs-lookup"><span data-stu-id="719b5-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="719b5-143">如果您仔细查看上表，您将发现这三种服务器类型中的端口范围相同。</span><span class="sxs-lookup"><span data-stu-id="719b5-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="719b5-144">例如，起始音频端口在每个服务器类型上设置为端口 49152，并且每个服务器中为音频保留的端口总数也相同：8348。</span><span class="sxs-lookup"><span data-stu-id="719b5-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="719b5-145">但是，端口范围重叠：音频端口从端口 49152 开始，但留出用于应用程序共享的端口也重叠。</span><span class="sxs-lookup"><span data-stu-id="719b5-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="719b5-146">为了充分利用服务质量，应重新配置应用程序共享以使用唯一的端口范围。</span><span class="sxs-lookup"><span data-stu-id="719b5-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="719b5-147">例如，可以将应用程序共享配置为从端口 40803 开始并使用 8348 端口。</span><span class="sxs-lookup"><span data-stu-id="719b5-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="719b5-148"> (为什么使用 8348 端口？</span><span class="sxs-lookup"><span data-stu-id="719b5-148">(Why 8348 ports?</span></span> <span data-ttu-id="719b5-149">如果将这些值相加 （ 40803 + 8348）意味着应用程序共享将使用端口 40803 到端口 49150。</span><span class="sxs-lookup"><span data-stu-id="719b5-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="719b5-150">由于音频端口在端口 49152 之前不会开始，因此您将不再具有任何重叠的端口范围。) </span><span class="sxs-lookup"><span data-stu-id="719b5-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="719b5-151">选择应用程序共享的新端口范围后，可以使用 Set-CsConferencingServer cmdlet 进行更改。</span><span class="sxs-lookup"><span data-stu-id="719b5-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="719b5-152">此更改无需在应用程序服务器或中介服务器上进行，因为这些服务器不会处理应用程序共享流量。</span><span class="sxs-lookup"><span data-stu-id="719b5-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="719b5-153">如果您决定重新分配用于音频通信的端口，则只需更改这些服务器上的端口值。</span><span class="sxs-lookup"><span data-stu-id="719b5-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="719b5-154">若要修改单个会议服务器上应用程序共享的端口值，请从 Skype for Business Server 命令行管理程序 中运行类似以下命令：</span><span class="sxs-lookup"><span data-stu-id="719b5-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="719b5-155">如果要在所有会议服务器上进行这些更改，可以改为运行此命令：</span><span class="sxs-lookup"><span data-stu-id="719b5-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="719b5-156">更改端口设置后，应停止并重新启动受更改影响的每项服务。</span><span class="sxs-lookup"><span data-stu-id="719b5-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="719b5-p107">会议服务器、应用程序服务器和中介服务器不必共享完全相同的端口范围；您唯一必须做的是在所有服务器上留出唯一的端口范围。但是，如果您在所有服务器上使用相同的端口集，则管理一般会更加轻松。</span><span class="sxs-lookup"><span data-stu-id="719b5-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="719b5-159">在 Skype for Business Server 中为会议、应用程序和中介服务器配置服务质量策略</span><span class="sxs-lookup"><span data-stu-id="719b5-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="719b5-p108">配置端口范围通过确保指定类型的所有流量（例如，所有音频流量）通过同一组端口进行传输来方便服务质量的使用。这使系统标识和标记给定数据包变得容易：如果端口 49152 是为音频通信保留的，则通过端口 49152 的所有数据包均可使用 DSCP 代码进行标记，以指示这是一个音频数据包。反过来，这使路由器能将此数据包标识为一个音频数据包，并为其提供比未标记数据包更高的优先级（如用于将文件从一台服务器复制到另一台服务器的数据包）。</span><span class="sxs-lookup"><span data-stu-id="719b5-p108">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="719b5-163">但是，简单地将一组端口限制为特定类型的流量不会产生通过那些使用适当的 DSCP 代码标记的端口的数据包。</span><span class="sxs-lookup"><span data-stu-id="719b5-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="719b5-164">除了定义端口范围之外，还必须创建指定要与每个端口范围关联的 DSCP 代码的服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="719b5-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="719b5-165">对于 Skype for Business Server，这通常意味着创建两个策略：一个策略用于音频，另一个策略用于视频。</span><span class="sxs-lookup"><span data-stu-id="719b5-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="719b5-166">通过使用组策略，可以轻松创建和管理服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="719b5-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="719b5-167">（还可使用本地安全策略创建这些相同的策略。</span><span class="sxs-lookup"><span data-stu-id="719b5-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="719b5-168">但是，这要求您在每台计算机上重复相同的过程。) 初始 QoS 策略集 (一组用于音频，另一组用于视频) 应仅应用于运行会议服务器、应用程序服务器和/或中介服务器服务的 Skype for Business Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="719b5-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="719b5-169">如果所有这些计算机都位于同一个 Active Directory OU 中，则只需将新的组策略对象 (GPO) 分配给该 OU。</span><span class="sxs-lookup"><span data-stu-id="719b5-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="719b5-170">或者，您也可以执行其他步骤将新策略定向到指定计算机；例如，您可将相应计算机放在某个安全组中，然后使用组策略安全筛选将 GPO 应用于该安全组。</span><span class="sxs-lookup"><span data-stu-id="719b5-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="719b5-171">若要创建用于管理音频的服务质量策略，请登录到安装了组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="719b5-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="719b5-172">打开组策略管理（单击“开始”，指向“管理工具”，然后单击“组策略管理”），然后完成下列过程：</span><span class="sxs-lookup"><span data-stu-id="719b5-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="719b5-173">在组策略管理中，找到其中应创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="719b5-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="719b5-174">例如，如果所有 Skype for Business Server 计算机都位于名为 Skype for Business Server 的 OU 中，则应该在 Skype for Business Server OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="719b5-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="719b5-175">右键单击相应的容器，然后单击"在此域中创建 **GPO"，并在此处链接它**。</span><span class="sxs-lookup"><span data-stu-id="719b5-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="719b5-176">在"新建 **GPO"** 对话框中，在"名称"框中键入新组策略对象的名称 (例如 **Skype for Business Server QoS**) ，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="719b5-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="719b5-177">右键单击新建的策略，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="719b5-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="719b5-178">在组策略管理编辑器中，依次展开“计算机配置”、“策略”和“Windows 设置”， 右键单击“基于策略的 QoS”，然后单击“创建新策略”。</span><span class="sxs-lookup"><span data-stu-id="719b5-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="719b5-179">在基于策略的 **QoS** 对话框中的打开页上，在"名称"框中键入新策略的名称 (例如 Skype for Business **Server QoS**) **名称** 。</span><span class="sxs-lookup"><span data-stu-id="719b5-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="719b5-180">选择“指定 DSCP 值”，并将该值设置为“46”。</span><span class="sxs-lookup"><span data-stu-id="719b5-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="719b5-181">将“指定出站调节率”保留为未选中状态，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="719b5-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="719b5-182">下一页上，确保选择了 **所有** 应用程序，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="719b5-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="719b5-183">这将确保所有应用程序与指定端口范围内带有指定 DSCP 代码的数据包匹配。</span><span class="sxs-lookup"><span data-stu-id="719b5-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="719b5-184">第三页上，确保同时选择"任何 **源 IP** 地址"和"任何目标 IP 地址"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="719b5-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="719b5-185">这两个设置确保将管理这些数据包，与哪台计算机（IP 地址）发送这些数据包及哪台计算机（IP 地址）将接收这些数据包无关。</span><span class="sxs-lookup"><span data-stu-id="719b5-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="719b5-186">在第四页上，从“选择此 QoS 策略所适用的协议”下拉列表中选择“TCP 和 UDP”。</span><span class="sxs-lookup"><span data-stu-id="719b5-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="719b5-187">TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Skype for Business Server 及其客户端应用程序最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="719b5-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="719b5-188">在标题“指定源端口号”下，选择“从此源端口或范围”。</span><span class="sxs-lookup"><span data-stu-id="719b5-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="719b5-189">在附带的文本框中，键入为音频传输保留的端口范围。</span><span class="sxs-lookup"><span data-stu-id="719b5-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="719b5-190">例如，如果为音频流量保留端口 49152 到端口 57500，则使用此格式输入端口范围 **：49152：57500。**</span><span class="sxs-lookup"><span data-stu-id="719b5-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="719b5-191">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="719b5-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="719b5-192">DSCP 值“46”有一定程度任意性：虽然 DSCP 46 通常用于标记音频数据包，但您不一定要使用 DSCP 46 进行音频通信。</span><span class="sxs-lookup"><span data-stu-id="719b5-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="719b5-193">如果已实施 QoS，并且对音频 (（例如 DSCP 40) ）使用不同的 DSCP 代码，则应该将服务质量策略配置为使用相同的代码 (即 40 用于音频) 。</span><span class="sxs-lookup"><span data-stu-id="719b5-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="719b5-194">如果正在实现服务质量，则建议对音频使用 DSCP 46，这只是因为此值常用于标记音频数据包。</span><span class="sxs-lookup"><span data-stu-id="719b5-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="719b5-195">为音频流量创建 QoS 策略后，应为视频流量创建第二个策略 (（可选）第三个策略来管理应用程序共享流量) 。</span><span class="sxs-lookup"><span data-stu-id="719b5-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="719b5-196">要为视频创建策略，请按照您创建音频策略时遵循的相同基本过程，进行下列替换项：</span><span class="sxs-lookup"><span data-stu-id="719b5-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="719b5-197">使用不同的 (和) 策略名称 (例如 **，Skype for Business Server Video) 。**</span><span class="sxs-lookup"><span data-stu-id="719b5-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="719b5-p120">将 DSCP 值设置为“34”而不是 46。（注意，不一定要使用 DSCP 值 34。唯一的要求是对视频使用与用于音频的 DSCP 值不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="719b5-p120">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="719b5-201">将以前配置的端口范围用于视频流量。</span><span class="sxs-lookup"><span data-stu-id="719b5-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="719b5-202">例如，如果为视频保留端口 57501 到 65535，请设置端口范围 **：57501：65535。**</span><span class="sxs-lookup"><span data-stu-id="719b5-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="719b5-203">如果您决定创建用于管理应用程序共享通信的策略，则必须创建第三个策略，进行以下替换：</span><span class="sxs-lookup"><span data-stu-id="719b5-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="719b5-204">使用不同的 (和) 策略名称 (例如 **，Skype for Business Server 应用程序共享**) 。</span><span class="sxs-lookup"><span data-stu-id="719b5-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="719b5-p122">将 DSCP 值设置为“24”而不是 46。（同样，不一定要使用 DSCP 值 24。唯一的要求是对应用程序共享使用与用于音频或视频的 DSCP 值不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="719b5-p122">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="719b5-208">将以前配置的端口范围用于视频流量。</span><span class="sxs-lookup"><span data-stu-id="719b5-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="719b5-209">例如，如果为应用程序共享保留端口 40803 到 49151，则端口范围设置为 **：40803：49151。**</span><span class="sxs-lookup"><span data-stu-id="719b5-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="719b5-210">在 Skype for Business Server 计算机上刷新组策略之前，已创建的新策略不会生效。</span><span class="sxs-lookup"><span data-stu-id="719b5-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="719b5-211">尽管组策略会定期自行刷新，但是您可以通过在需要刷新的组策略所在的每台计算机上运行下列命令来强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="719b5-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="719b5-212">此命令可以从 Skype for Business Server 命令行管理程序 中运行，也可以从在管理员凭据下运行的任何命令窗口运行。</span><span class="sxs-lookup"><span data-stu-id="719b5-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="719b5-213">若要在管理员凭据下运行命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。</span><span class="sxs-lookup"><span data-stu-id="719b5-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="719b5-214">若要验证是否已应用新的 QoS 策略，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="719b5-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="719b5-215">在 Skype for Business Server 计算机上 **，单击"** 开始"，然后单击"**运行"。**</span><span class="sxs-lookup"><span data-stu-id="719b5-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="719b5-216">在 **"运行** "对话框中，键入 **regedit，** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="719b5-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="719b5-217">在注册表编辑器中，展开 **计算机**，展开 **HKEY \_ LOCAL \_ MACHINE，** 展开 **SOFTWARE，** 展开 **策略**，**展开 Microsoft，** 展开 **Windows，** 然后单击 **QoS。**</span><span class="sxs-lookup"><span data-stu-id="719b5-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="719b5-218">在“QoS”下，您应看到刚刚创建的每个 QoS 策略对应的注册表项。</span><span class="sxs-lookup"><span data-stu-id="719b5-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="719b5-219">例如，如果创建了两个新策略 (一个名为 Skype for Business Server 音频 QoS，另一个名为 Skype for Business Server Video QoS) ，则应该会看到 Skype for Business Server 音频 QoS 和 Skype for Business Server Video QoS 的注册表条目。</span><span class="sxs-lookup"><span data-stu-id="719b5-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="719b5-220">要确保将网络数据包标记为相应的 DSCP 值，还应该通过完成以下过程在每台计算机上创建新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="719b5-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="719b5-221">单击“开始”，然后单击“运行”。</span><span class="sxs-lookup"><span data-stu-id="719b5-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="719b5-222">在 **"运行** "对话框中，键入 **regedit，** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="719b5-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="719b5-223">在注册表编辑器中，展开 **HKEY \_ LOCAL \_ MACHINE，** 展开 **系统**，展开 **CurrentControlSet，** 展开 **服务**，然后展开 **Tcpip。**</span><span class="sxs-lookup"><span data-stu-id="719b5-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="719b5-224">右键单击“Tcpip”，指向“新建”，然后单击“项”。</span><span class="sxs-lookup"><span data-stu-id="719b5-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="719b5-225">新建注册表项后，键入 **QoS，** 然后按 Enter 重命名该注册表项。</span><span class="sxs-lookup"><span data-stu-id="719b5-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="719b5-226">右键单击“QoS”，指向“新建”，然后单击“字符串值”。</span><span class="sxs-lookup"><span data-stu-id="719b5-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="719b5-227">创建新注册表值后，键入 **"不使用 NLA"，** 然后按 Enter 重命名该值。</span><span class="sxs-lookup"><span data-stu-id="719b5-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="719b5-228">双击“不使用 NLA”。</span><span class="sxs-lookup"><span data-stu-id="719b5-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="719b5-229">在 **"编辑字符串**"对话框中，在"值"数据框中键入 **1，** 然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="719b5-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="719b5-230">关闭注册表编辑器并重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="719b5-230">Close the Registry Editor and reboot your computer.</span></span>
