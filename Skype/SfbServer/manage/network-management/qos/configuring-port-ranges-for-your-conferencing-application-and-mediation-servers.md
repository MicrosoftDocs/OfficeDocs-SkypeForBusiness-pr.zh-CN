---
title: 配置端口范围和会议、 应用程序和中介服务器的服务质量策略
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文介绍如何配置端口范围和会议、 应用程序和中介服务器的服务质量策略。
ms.openlocfilehash: f1452c9166eb557d186b8569a37d5abb885d4354
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199557"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="aa3c1-103">配置端口范围和会议、 应用程序和中介服务器的服务质量策略</span><span class="sxs-lookup"><span data-stu-id="aa3c1-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="aa3c1-104">本文介绍如何配置端口范围和会议、 应用程序和中介服务器的服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="aa3c1-105">配置端口范围</span><span class="sxs-lookup"><span data-stu-id="aa3c1-105">Configure port ranges</span></span>

<span data-ttu-id="aa3c1-106">若要实现的服务质量，应配置音频、 视频和应用程序共享会议、 应用程序和中介服务器; 上的相同的端口范围此外，这些端口范围必须不以任何方式重叠。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="aa3c1-107">若要使用一个简单示例，假设您使用端口通过 10999 10000 视频会议服务器上。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="aa3c1-108">这意味着您必须在您的应用程序和中介服务器上中还预留端口通过 10999 10000 视频。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="aa3c1-109">如果您不 QoS 将未按预期。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="aa3c1-110">同样，假设您保留 10000 10999 对于视频，通过端口，但保留端口 10500 11999 通过音频。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="aa3c1-111">因为该端口范围重叠，这可以创建的服务质量，问题。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="aa3c1-112">使用 QoS，每种形式必须具有一组唯一的端口： 如果端口通过 10999 10000 用于视频，则您必须使用不同的范围 (例如，通过 11999，对于音频的 11000)。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="aa3c1-113">默认情况下，音频和视频的端口范围不重叠 Skype 中为 Business Server;但是，端口范围分配给应用程序共享音频和视频的端口范围重叠。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="aa3c1-114">（，反过来，表示无这些范围唯一。）您可以通过业务 Server 命令行管理程序运行以下三个命令中 Skype 验证会议、 应用程序和中介服务器的现有的端口范围：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="aa3c1-115">您可以在上述命令中看到的如 – 音频、 视频和应用程序共享 – 每个端口类型分配两个单独的属性值： 起始端口和端口计数。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="aa3c1-116">起始端口指示第一个端口用于该形式;例如，如果音频端口开始等于意味着 50000 用于音频流量的第一个端口是端口 50000。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="aa3c1-117">如果音频端口计数为 2 （其中不是有效的值，但此处用于举例说明），这意味着，只有两个端口被分配给音频。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="aa3c1-118">如果第一个端口是端口 50000 共有的两个端口，这意味着第二个端口必须端口 50001 （端口范围必须是连续的单元格）。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="aa3c1-119">因此，音频的端口范围将为通过 50001，非独占 50000 端口。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="aa3c1-120">请注意，应用程序服务器和中介服务器仅支持 QoS 音频;不需要更改视频或应用程序共享应用程序服务器或中介服务器中的端口。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="aa3c1-121">如果您运行前面三条命令，您将看到的默认端口值的 Skype 业务服务器配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa3c1-122">属性</span><span class="sxs-lookup"><span data-stu-id="aa3c1-122">Property</span></span></th>
<th><span data-ttu-id="aa3c1-123">会议服务器</span><span class="sxs-lookup"><span data-stu-id="aa3c1-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="aa3c1-124">应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="aa3c1-124">Application Server</span></span></th>
<th><span data-ttu-id="aa3c1-125">中介服务器</span><span class="sxs-lookup"><span data-stu-id="aa3c1-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa3c1-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="aa3c1-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-127">49152</span><span class="sxs-lookup"><span data-stu-id="aa3c1-127">49152</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-128">49152</span><span class="sxs-lookup"><span data-stu-id="aa3c1-128">49152</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-129">49152</span><span class="sxs-lookup"><span data-stu-id="aa3c1-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa3c1-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="aa3c1-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-131">8348</span><span class="sxs-lookup"><span data-stu-id="aa3c1-131">8348</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-132">8348</span><span class="sxs-lookup"><span data-stu-id="aa3c1-132">8348</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-133">8348</span><span class="sxs-lookup"><span data-stu-id="aa3c1-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa3c1-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="aa3c1-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-135">57501</span><span class="sxs-lookup"><span data-stu-id="aa3c1-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa3c1-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="aa3c1-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-137">8034</span><span class="sxs-lookup"><span data-stu-id="aa3c1-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa3c1-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="aa3c1-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-139">49152</span><span class="sxs-lookup"><span data-stu-id="aa3c1-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa3c1-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="aa3c1-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="aa3c1-141">16383</span><span class="sxs-lookup"><span data-stu-id="aa3c1-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="aa3c1-142">如前所述，进行 QoS 业务服务器端口配置 Skype 时，应确保： 1) 音频端口设置都是相同都会会议、 应用程序和中介服务器;以及 2） 不重叠端口范围。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="aa3c1-143">如果您在前面的表仔细查看，您将看到端口范围为跨三种服务器类型相同。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="aa3c1-144">例如，音频的起始端口设置为端口 49152 每种服务器类型，并且对于每台服务器中的音频预留的端口总数还是相同： 8348。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="aa3c1-145">但是，该端口范围重叠： 音频端口启动在端口 49152，但，以便执行端口留出应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="aa3c1-146">为了更好地利用的服务质量，应用程序共享应重新配置为使用唯一的端口范围。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="aa3c1-147">例如，您可以配置应用程序共享启动在端口 40803 和使用 8348 端口。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="aa3c1-148">(为什么 8348 端口？</span><span class="sxs-lookup"><span data-stu-id="aa3c1-148">(Why 8348 ports?</span></span> <span data-ttu-id="aa3c1-149">如果将这些值相加-40803 + 8348-的表示应用程序共享将使用端口 40803 通过端口 49150。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="aa3c1-150">音频端口不执行直到端口 49152 开始的因为您将不再有任何重叠端口范围。）</span><span class="sxs-lookup"><span data-stu-id="aa3c1-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="aa3c1-151">选择应用程序共享的新端口范围后，您可以使用集 CsConferencingServer cmdlet 进行更改。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="aa3c1-152">此更改不会不需要进行应用程序服务器上或中介服务器，因为这些服务器不处理应用程序共享流量。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="aa3c1-153">您只需更改这些服务器上的端口值，如果您决定将使用的音频流量的端口重新分配。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="aa3c1-154">若要修改单台会议服务器上共享的应用程序的端口值，业务 Server 命令行管理程序运行类似的命令从 Skype 中：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="aa3c1-155">如果您想要进行这些更改您的所有会议服务器上，您可以改为运行此命令：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="aa3c1-156">更改端口设置后, 应停止并重新启动受更改影响的每个服务。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="aa3c1-157">它不是强制会议服务器、 应用程序服务器和中介服务器共享完全相同的端口范围;仅 true 要求为您设置留出唯一的端口范围在所有服务器上。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-157">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="aa3c1-158">但是，管理通常会在所有服务器上使用一组相同的端口的情况下更轻松。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-158">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="aa3c1-159">会议、 应用程序和中介服务器，业务服务器配置服务质量策略 Skype</span><span class="sxs-lookup"><span data-stu-id="aa3c1-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="aa3c1-160">配置端口范围可以指定类型 （例如，所有音频流量） 的所有流量都随身通过一组相同的端口便于使用的服务质量。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-160">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="aa3c1-161">这便于系统以确定并将给定的数据包的标记： 如果端口 49152 以供音频流量，则可以使用指示这是音频数据包的 DSCP 代码标记通过端口 49152 旅行任何数据包。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-161">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="aa3c1-162">反过来，这样路由器识别为音频数据包，数据包，并为其提供优先级高于未标记数据包 （如数据包用于将文件复制到另一台服务器）。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-162">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="aa3c1-163">但是，只需出于特定类型的通信的端口的一组不会引起旅行通过这些端口正在使用的适当的 DSCP 代码标记的数据包。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="aa3c1-164">除了定义端口范围，您还必须创建指定的 DSCP 代码与每个端口范围相关联的服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="aa3c1-165">对于业务服务器 Skype，这通常意味着创建两个策略： 一个用于音频和视频之一。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="aa3c1-166">服务质量策略是最轻松创建、 和托管，通过使用组策略。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="aa3c1-167">（这些相同的策略可以还创建通过使用本地安全策略。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="aa3c1-168">但是的需要重复同一过程在每台计算机上的。）应只对业务服务器计算机运行会议服务器、 应用程序服务器和/或中介服务器服务的 Skype 应用 QoS 策略 （一个音频），一个用于视频您初始设置。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="aa3c1-169">如果上述所有计算机都位于同一 Active Directory OU 中，您可以只是分配给该 OU 的新组策略对象 (GPO)。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="aa3c1-170">或者，可以执行其他步骤来设定新策略，以指定的计算机。例如，可以在安全组中，将相应的计算机，然后使用组策略安全筛选来应用 GPO，只向该安全组。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="aa3c1-171">若要创建服务质量策略用于管理音频，登录到计算机上已安装组策略管理。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="aa3c1-172">打开组策略管理 （单击**开始**、**管理工具**，，然后单击**组策略管理**），然后完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="aa3c1-173">在组策略管理中，找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="aa3c1-174">例如，如果您的业务服务器计算机的所有 Skype 都位于业务服务器命名 Skype OU 中，然后新策略应创建在 Skype 对于业务服务器 OU。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="aa3c1-175">右键单击相应的容器，然后单击**创建在这个域 GPO 并在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="aa3c1-176">**新建 GPO**对话框中，在 (例如，**业务服务器 QoS 的 Skype**)，**名称**框中键入新的组策略对象的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="aa3c1-177">右键单击新创建的策略，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="aa3c1-178">在组策略管理编辑器中，展开**计算机配置**，展开**策略**、 **Windows 设置**、**基于策略的 QoS**，右键单击，然后单击**创建新策略**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="aa3c1-179">在**基于策略的 QoS**对话框中，在打开页上，键入**名称**框中的新策略 (例如，**业务服务器 QoS 的 Skype**) 的名称。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="aa3c1-180">选择**指定 DSCP 值**并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="aa3c1-181">保留未选择，**指定出站调节率**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="aa3c1-182">在下一页上，确保选中**所有应用程序**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="aa3c1-183">这只是确保所有应用程序将匹配具有指定 DSCP 代码指定的端口范围中的数据包。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="aa3c1-184">在第三页上，确保，这两个**任何源 IP 地址和任何目标 IP 地址**选择，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="aa3c1-185">这两个设置确保将管理数据包而不考虑哪台计算机 （IP 地址） 发送这些数据包和哪台计算机 （IP 地址） 将接收这些数据包。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="aa3c1-186">在第四页中，从**选择此 QoS 策略应用于的协议**下拉列表中选择**TCP 和 UDP** 。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="aa3c1-187">TCP （传输控制协议） 和 UDP （用户数据报协议） 是最常使用的业务服务器和其客户端应用程序的 Skype 的两个网络协议。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="aa3c1-188">在标题下**指定源端口号**，**从此源端口或范围**中进行选择。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="aa3c1-189">在相应的文本框中，键入供音频传输的端口范围。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="aa3c1-190">例如，如果预留端口 49152 到音频流量的端口 57500，输入使用以下格式的端口范围： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="aa3c1-191">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="aa3c1-192">46 的 DSCP 值是 ア ネ 较任意： 虽然 DSCP 46 通常用于标记的音频数据包，您不必 DSCP 46 用于音频通信。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="aa3c1-193">如果您已经实现了 QoS，并且您使用不同的 DSCP 代码进行音频 (例如，DSCP 40)，您应配置您的服务质量策略，以使用同一代码 (即，对于音频的 40)。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="aa3c1-194">如果您刚刚实现的服务质量，则建议使用 DSCP 46 对于音频，只需因为该值通常用于将音频数据包的标记。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="aa3c1-195">在创建音频流量的 QoS 策略后，您随后应创建视频流量 （和 （可选） 用于管理应用程序共享流量的第三个策略） 的第二个策略。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="aa3c1-196">若要创建视频的策略，请按照相同的基本过程您遵循创建音频策略时, 进行下列替换项操作：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="aa3c1-197">使用其他 （及唯一） 策略名称 (例如， **Skype 业务 Server 视频**)。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="aa3c1-198">设置为**34**而不是 46 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-198">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="aa3c1-199">（请注意，不需要使用 34 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-199">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="aa3c1-200">唯一的要求是不是用于音频，视频使用不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="aa3c1-200">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="aa3c1-201">使用视频流量的以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="aa3c1-202">例如，如果您保留了端口 57501 到 65535 视频，设置为此的端口范围： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="aa3c1-203">如果您决定创建用于管理应用程序共享流量的策略，则必须创建第三方策略，进行以下替代：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="aa3c1-204">使用其他 （及唯一） 策略名称 (例如，**业务服务器应用程序共享的 Skype**)。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="aa3c1-205">设置为**24**而不是 46 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-205">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="aa3c1-206">（同样，您不需要使用 DSCP 值，共 24 部分。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-206">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="aa3c1-207">唯一的要求。 您可用于不同的 DSCP 值应用程序共享比使用音频或视频）</span><span class="sxs-lookup"><span data-stu-id="aa3c1-207">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="aa3c1-208">使用视频流量的以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="aa3c1-209">例如，如果您保留了端口 40803 到 49151 应用程序共享，设置为此的端口范围： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="aa3c1-210">组策略已在您 Skype 的业务服务器计算机上刷新，已创建的新策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="aa3c1-211">尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="aa3c1-212">此命令可以从运行内 Skype 业务 Server 命令行管理程序或从管理员凭据运行任何命令窗口。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="aa3c1-213">若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="aa3c1-214">若要验证已应用新的 QoS 策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="aa3c1-215">在业务服务器计算机 Skype，单击**开始**，然后单击**运行**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="aa3c1-216">在**运行**对话框中，键入**regedit**，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="aa3c1-217">在注册表编辑器中，展开**计算机**，展开**HKEY\_本地\_计算机**、 展开**软件**，展开**策略**，展开**Microsoft**，展开**Windows**，，然后单击**QoS**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="aa3c1-218">**QoS**下应看到您刚创建的 QoS 策略的每个注册表项。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="aa3c1-219">例如，如果您创建两个新的策略 (一个命名 Skype 的业务 Server Audio QoS) 和其他命名 Skype 的业务 Server 视频 QoS，您应看到注册表项的 Skype 业务 Server Audio QoS 和 Skype 的业务 Server 视频 QoS。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="aa3c1-220">为了帮助确保使用适当的 DSCP 值标记网络数据包，，还应通过完成以下过程在每台计算机上创建新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="aa3c1-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="aa3c1-221">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="aa3c1-222">在**运行**对话框中，键入**regedit**，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="aa3c1-223">在注册表编辑器中，展开**HKEY\_本地\_计算机**，展开**系统**，展开**CurrentControlSet**，展开**服务**，然后展开**Tcpip**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="aa3c1-224">右键单击**Tcpip**，指向**新建**，，然后单击**项**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="aa3c1-225">创建新的注册表项后，键入**QoS**，，，然后按 ENTER 以重命名该项。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="aa3c1-226">右键单击**QoS**，指向**新建**，，然后单击**字符串值**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="aa3c1-227">创建新的注册表值后，键入**不使用 NLA**，，，然后按 ENTER 以重命名该值。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="aa3c1-228">双击**不使用 NLA**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="aa3c1-229">**编辑字符串**对话框中，在**值数据**框中，键入**1** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="aa3c1-230">关闭注册表编辑器，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="aa3c1-230">Close the Registry Editor and reboot your computer.</span></span>
