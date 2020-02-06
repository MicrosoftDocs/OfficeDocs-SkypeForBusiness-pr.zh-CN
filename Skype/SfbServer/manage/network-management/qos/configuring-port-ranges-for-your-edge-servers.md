---
title: 为 Edge 服务器配置端口范围和服务质量
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文介绍如何配置边缘服务器的端口范围以及如何为你的 A/V 边缘服务器配置服务质量策略。
ms.openlocfilehash: 5762cb6861552696f160dfe69459c357f6b63452
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817431"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="fea3f-103">为 Skype for Business Server 中的 Edge 服务器配置端口范围和服务质量策略</span><span class="sxs-lookup"><span data-stu-id="fea3f-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="fea3f-104">本文介绍如何配置边缘服务器的端口范围以及如何为你的 A/V 边缘服务器配置服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="fea3f-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="fea3f-105">配置端口范围</span><span class="sxs-lookup"><span data-stu-id="fea3f-105">Configure port ranges</span></span>

<span data-ttu-id="fea3f-106">通过 Edge 服务器，你无需为音频、视频和应用程序共享配置单独的端口范围;同样，用于边缘服务器的端口范围不必与你的会议、应用程序和中介服务器使用的端口范围相匹配。</span><span class="sxs-lookup"><span data-stu-id="fea3f-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="fea3f-107">在继续本示例之前，很重要的一点是，虽然此选项存在，但我们建议您不要更改端口范围，因为如果移出50000端口范围，这可能会对某些方案产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="fea3f-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="fea3f-108">例如，假设您已将您的会议、应用程序和中介服务器配置为使用这些端口范围：</span><span class="sxs-lookup"><span data-stu-id="fea3f-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fea3f-109">数据包类型</span><span class="sxs-lookup"><span data-stu-id="fea3f-109">Packet Type</span></span></th>
<th><span data-ttu-id="fea3f-110">起始端口</span><span class="sxs-lookup"><span data-stu-id="fea3f-110">Starting Port</span></span></th>
<th><span data-ttu-id="fea3f-111">保留的端口数</span><span class="sxs-lookup"><span data-stu-id="fea3f-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fea3f-112">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="fea3f-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="fea3f-113">40803</span><span class="sxs-lookup"><span data-stu-id="fea3f-113">40803</span></span></p></td>
<td><p><span data-ttu-id="fea3f-114">8348</span><span class="sxs-lookup"><span data-stu-id="fea3f-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea3f-115">音频</span><span class="sxs-lookup"><span data-stu-id="fea3f-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="fea3f-116">49152</span><span class="sxs-lookup"><span data-stu-id="fea3f-116">49152</span></span></p></td>
<td><p><span data-ttu-id="fea3f-117">8348</span><span class="sxs-lookup"><span data-stu-id="fea3f-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fea3f-118">视频</span><span class="sxs-lookup"><span data-stu-id="fea3f-118">Video</span></span></p></td>
<td><p><span data-ttu-id="fea3f-119">57500</span><span class="sxs-lookup"><span data-stu-id="fea3f-119">57500</span></span></p></td>
<td><p><span data-ttu-id="fea3f-120">8034</span><span class="sxs-lookup"><span data-stu-id="fea3f-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fea3f-121"><strong>求和</strong></span><span class="sxs-lookup"><span data-stu-id="fea3f-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="fea3f-122">24730</span><span class="sxs-lookup"><span data-stu-id="fea3f-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fea3f-123">正如你所看到的，音频、视频和应用程序共享的端口范围从端口40803开始，总共包括24732个端口。</span><span class="sxs-lookup"><span data-stu-id="fea3f-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="fea3f-124">如果你愿意，可以将给定的边缘服务器配置为使用这些整体端口值，方法是从 Skype for Business 服务器管理外壳程序中运行类似于此的命令：</span><span class="sxs-lookup"><span data-stu-id="fea3f-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="fea3f-125">或者，使用以下命令同时配置组织中的所有边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="fea3f-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="fea3f-126">你可以使用此 Skype for Business Server Management Shell 命令验证你的 Edge 服务器的当前端口设置：</span><span class="sxs-lookup"><span data-stu-id="fea3f-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="fea3f-127">同样，虽然我们提供这些选项，但我们强烈建议你将其保留为用于端口配置的操作。</span><span class="sxs-lookup"><span data-stu-id="fea3f-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="fea3f-128">为您的 A/V 边缘服务器配置 QoS 策略</span><span class="sxs-lookup"><span data-stu-id="fea3f-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="fea3f-129">除了为你的会议、应用程序和中介服务器创建 QoS 策略之外，还必须为你的 A/V 边缘服务器的内部端创建音频和视频策略。</span><span class="sxs-lookup"><span data-stu-id="fea3f-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="fea3f-130">但是，你的 Edge 服务器上使用的策略与你的会议、应用程序和中介服务器上使用的策略不同。</span><span class="sxs-lookup"><span data-stu-id="fea3f-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="fea3f-131">对于会议、应用程序和中介服务器，你指定了源端口范围;在 "边缘服务器" 中，你需要指定目标端口范围。</span><span class="sxs-lookup"><span data-stu-id="fea3f-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="fea3f-132">因此，你不能直接将会议、应用程序和中介服务器 QoS 策略应用到你的边缘服务器：这些策略根本不起作用。</span><span class="sxs-lookup"><span data-stu-id="fea3f-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="fea3f-133">相反，你必须创建新策略并将这些策略应用到 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="fea3f-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="fea3f-134">以下过程介绍了创建可用于管理边缘服务器上的服务质量的 Active Directory 组策略对象的过程。</span><span class="sxs-lookup"><span data-stu-id="fea3f-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="fea3f-135">当然，您的边缘服务器可能是没有 Active Directory 帐户的独立服务器。</span><span class="sxs-lookup"><span data-stu-id="fea3f-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="fea3f-136">如果是这种情况，则可以使用本地组策略，而不是 Active Directory 组策略：唯一的区别在于必须使用本地组策略编辑器创建这些本地策略，并且必须在每个边缘服务器上分别创建相同的策略集。</span><span class="sxs-lookup"><span data-stu-id="fea3f-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="fea3f-137">若要启动边缘服务器上的本地组策略编辑器，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fea3f-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="fea3f-138">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="fea3f-139">在 "**运行**" 对话框中，键入 " **gpedit.msc**"，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="fea3f-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="fea3f-140">如果你要创建基于 Active Directory 的策略，则应登录到已安装组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="fea3f-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="fea3f-141">在这种情况下，请打开组策略管理（单击 "**开始**"，指向 "**管理工具**"，然后单击 "**组策略管理**"），然后完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fea3f-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="fea3f-142">在 "组策略管理" 中，找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="fea3f-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="fea3f-143">例如，如果所有 Skype for business 服务器计算机都位于名为 "Skype for business 服务器" 的 OU 中，则应在 Skype for business Server OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="fea3f-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="fea3f-144">右键单击相应的容器，然后单击 "**在此域中创建 GPO"，然后在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="fea3f-145">在 "**新建 GPO** " 对话框中，在 "**名称**" 框中键入新组策略对象的名称（例如， **Skype for business Server 音频**），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="fea3f-146">右键单击新创建的策略，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="fea3f-147">无论您是在创建 Active Directory 策略还是本地策略，该过程都是相同的：</span><span class="sxs-lookup"><span data-stu-id="fea3f-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="fea3f-148">在组策略管理编辑器或本地组策略编辑器中，展开 "**计算机配置**"，展开 "**策略**"，展开 " **Windows 设置**"，右键单击 "**基于策略的 QoS**"，然后单击 "**创建新策略**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="fea3f-149">在 "**基于策略的 QoS** " 对话框中的 "开始" 页面上，在 "**名称**" 框中键入新策略的名称（例如， **Skype for business Server 音频**）。</span><span class="sxs-lookup"><span data-stu-id="fea3f-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="fea3f-150">选择 "**指定 DSCP 值**" 并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="fea3f-151">"退出"**指定出站阻止率**未选中，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="fea3f-152">在下一页上，确保已选中 "**所有应用程序**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="fea3f-153">此设置指示网络查找 DSCP 标记为46的所有数据包，而不仅仅是由特定应用程序创建的数据包。</span><span class="sxs-lookup"><span data-stu-id="fea3f-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="fea3f-154">在第三页上，确保选中了 "**任何来源 ip 地址**" 和 "**任何目标 ip 地址**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="fea3f-155">这两个设置确保数据包将被管理，无论哪台计算机（IP 地址）发送这些数据包以及哪台计算机（IP 地址）将接收这些数据包。</span><span class="sxs-lookup"><span data-stu-id="fea3f-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="fea3f-156">在第4页上，从 "**选择协议此 QoS 策略应用**于" 下拉列表中选择 " **TCP 和 UDP** "。</span><span class="sxs-lookup"><span data-stu-id="fea3f-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="fea3f-157">TCP （传输控制协议）和 UDP （用户数据报协议）是 Skype for Business 服务器及其客户端应用程序最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="fea3f-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="fea3f-158">在 "标题" 下，**指定目标端口号**，选择 "**从此目标端口或范围**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="fea3f-159">在 "随附文本" 框中，键入为音频传输保留的端口范围。</span><span class="sxs-lookup"><span data-stu-id="fea3f-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="fea3f-160">例如，如果您通过端口57500为音频流量保留了端口49152，请使用以下格式输入端口范围： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="fea3f-161">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fea3f-161">Click **Finish**.</span></span>

<span data-ttu-id="fea3f-162">为音频流量创建 QoS 策略后，应为视频流量创建第二个策略。</span><span class="sxs-lookup"><span data-stu-id="fea3f-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="fea3f-163">若要创建视频的策略，请按照创建音频策略时所遵循的基本过程进行操作，进行以下替换：</span><span class="sxs-lookup"><span data-stu-id="fea3f-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="fea3f-164">使用不同（且唯一）的策略名称（例如， **Skype For Business 服务器视频**）。</span><span class="sxs-lookup"><span data-stu-id="fea3f-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="fea3f-165">将 DSCP 值设置为**34**而不是46。</span><span class="sxs-lookup"><span data-stu-id="fea3f-165">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="fea3f-166">（请注意，您不必使用34的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="fea3f-166">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="fea3f-167">唯一的要求是对视频使用的 DSCP 值与用于音频的值不同。）</span><span class="sxs-lookup"><span data-stu-id="fea3f-167">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="fea3f-168">对视频流量使用以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="fea3f-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="fea3f-169">例如，如果您已为视频保留端口57501到65535，请将端口范围设置为： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="fea3f-170">同样，应将此配置为目标端口范围。</span><span class="sxs-lookup"><span data-stu-id="fea3f-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="fea3f-171">如果你决定创建用于管理应用程序共享流量的策略，则必须创建第三个策略，从而进行以下替换：</span><span class="sxs-lookup"><span data-stu-id="fea3f-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="fea3f-172">使用不同（且唯一）的策略名称（例如， **Skype For Business 服务器应用程序共享**）。</span><span class="sxs-lookup"><span data-stu-id="fea3f-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="fea3f-173">将 DSCP 值设置为**24** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="fea3f-173">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="fea3f-174">（同样，您无需使用 DSCP 值24。</span><span class="sxs-lookup"><span data-stu-id="fea3f-174">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="fea3f-175">唯一的要求是对应用程序共享使用的 DSCP 值与音频或视频使用的 DSCP 值不同。）</span><span class="sxs-lookup"><span data-stu-id="fea3f-175">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="fea3f-176">对视频流量使用以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="fea3f-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="fea3f-177">例如，如果你已为应用程序共享保留了端口40803到49151，请将端口范围设置为： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="fea3f-178">在边缘服务器上刷新组策略之前，你创建的新策略将不会生效。</span><span class="sxs-lookup"><span data-stu-id="fea3f-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="fea3f-179">尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="fea3f-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="fea3f-180">此命令可以从 Skype for Business 服务器内运行，也可以从任何运行在 "管理员凭据" 下的命令窗口运行。</span><span class="sxs-lookup"><span data-stu-id="fea3f-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="fea3f-181">若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="fea3f-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="fea3f-182">请注意，即使在运行 Gpudate 后，你也可能需要重启 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="fea3f-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="fea3f-183">为了帮助确保网络数据包使用适当的 DSCP 值进行标记，还应通过完成以下过程在每台计算机上创建一个新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="fea3f-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="fea3f-184">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="fea3f-185">在 "**运行**" 对话框中，键入**regedit**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="fea3f-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="fea3f-186">在注册表编辑器中，展开 **"\_HKEY\_本地计算机**"，依次展开 "**系统**"、" **CurrentControlSet**"、"**服务**"，然后展开 " **Tcpip**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="fea3f-187">右键单击 " **Tcpip**"，指向 "**新建**"，然后单击 "**项**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="fea3f-188">创建新的注册表项后，键入**QoS**，然后按 enter 重命名该项。</span><span class="sxs-lookup"><span data-stu-id="fea3f-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="fea3f-189">右键单击 " **QoS**"，指向 "**新建**"，然后单击 "**字符串值**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="fea3f-190">创建新的注册表值后，键入 "不**使用 NLA**"，然后按 enter 重命名该值。</span><span class="sxs-lookup"><span data-stu-id="fea3f-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="fea3f-191">双击 "**不使用 NLA**"。</span><span class="sxs-lookup"><span data-stu-id="fea3f-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="fea3f-192">在 "**编辑字符串**" 对话框中，在 "**值数据**" 框中键入**1** ，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="fea3f-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="fea3f-193">关闭注册表编辑器，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="fea3f-193">Close the Registry Editor and reboot your computer.</span></span>
