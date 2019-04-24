---
title: 配置边缘服务器的端口范围和服务质量
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文介绍如何配置边缘服务器的端口范围以及如何配置服务质量策略 a / V 边缘服务器。
ms.openlocfilehash: 11fdb542c6256c21e169480194bc5154bf1c1428
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214931"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="c9628-103">配置端口范围和 Skype 业务服务器在边缘服务器的服务质量策略</span><span class="sxs-lookup"><span data-stu-id="c9628-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="c9628-104">本文介绍如何配置边缘服务器的端口范围以及如何配置服务质量策略 a / V 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="c9628-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="c9628-105">配置端口范围</span><span class="sxs-lookup"><span data-stu-id="c9628-105">Configure port ranges</span></span>

<span data-ttu-id="c9628-106">与边缘服务器，您不必配置单独的端口范围的音频、 视频和应用程序共享;同样，用于边缘服务器的端口范围没有匹配用于您的会议、 应用程序和中介服务器的端口范围。</span><span class="sxs-lookup"><span data-stu-id="c9628-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="c9628-107">我们继续进行我们的示例之前，请务必压力时存在此选项，建议您更改端口范围，如这可能会影响某些情况下，如果移动超出 50000 端口范围。</span><span class="sxs-lookup"><span data-stu-id="c9628-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="c9628-108">例如，假设您已配置的会议、 应用程序和中介服务器要使用这些端口范围：</span><span class="sxs-lookup"><span data-stu-id="c9628-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9628-109">数据包类型</span><span class="sxs-lookup"><span data-stu-id="c9628-109">Packet Type</span></span></th>
<th><span data-ttu-id="c9628-110">起始端口</span><span class="sxs-lookup"><span data-stu-id="c9628-110">Starting Port</span></span></th>
<th><span data-ttu-id="c9628-111">预留的端口数</span><span class="sxs-lookup"><span data-stu-id="c9628-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9628-112">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="c9628-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c9628-113">40803</span><span class="sxs-lookup"><span data-stu-id="c9628-113">40803</span></span></p></td>
<td><p><span data-ttu-id="c9628-114">8348</span><span class="sxs-lookup"><span data-stu-id="c9628-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9628-115">音频</span><span class="sxs-lookup"><span data-stu-id="c9628-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="c9628-116">49152</span><span class="sxs-lookup"><span data-stu-id="c9628-116">49152</span></span></p></td>
<td><p><span data-ttu-id="c9628-117">8348</span><span class="sxs-lookup"><span data-stu-id="c9628-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9628-118">视频</span><span class="sxs-lookup"><span data-stu-id="c9628-118">Video</span></span></p></td>
<td><p><span data-ttu-id="c9628-119">57500</span><span class="sxs-lookup"><span data-stu-id="c9628-119">57500</span></span></p></td>
<td><p><span data-ttu-id="c9628-120">8034</span><span class="sxs-lookup"><span data-stu-id="c9628-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9628-121"><strong>汇总</strong></span><span class="sxs-lookup"><span data-stu-id="c9628-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="c9628-122">24730</span><span class="sxs-lookup"><span data-stu-id="c9628-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9628-123">您可以看到，您的端口范围的音频、 视频和应用程序共享端口 40803 处开始，并包含总共 24732 端口。</span><span class="sxs-lookup"><span data-stu-id="c9628-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="c9628-124">如果您愿意，您可以配置给定的边缘服务器，使用这些总体来运行 Business Server 命令行管理程序命令与此类似从中 Skype 端口值：</span><span class="sxs-lookup"><span data-stu-id="c9628-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="c9628-125">或者，使用以下命令同时配置您的组织中的所有边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="c9628-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="c9628-126">您可以使用此 Skype 业务 Server 命令行管理程序命令验证边缘服务器的当前端口设置：</span><span class="sxs-lookup"><span data-stu-id="c9628-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="c9628-127">同样，虽然我们执行提供这些选项，我们强烈建议您保持不变的端口配置操作。</span><span class="sxs-lookup"><span data-stu-id="c9628-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="c9628-128">QoS 策略配置 a / V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="c9628-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="c9628-129">除了创建 QoS 策略会议、 应用程序和中介服务器，还必须创建音频和视频策略的内部端 A / V 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="c9628-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="c9628-130">但是，边缘服务器上使用的策略与具有不同会议、 应用程序和中介服务器上使用的策略。</span><span class="sxs-lookup"><span data-stu-id="c9628-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="c9628-131">会议、 应用程序和中介服务器，您指定的源端口范围;与边缘服务器，您需要指定的目标端口范围。</span><span class="sxs-lookup"><span data-stu-id="c9628-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="c9628-132">因此，不能只需将会议、 应用程序和中介服务器 QoS 策略应用到边缘服务器： 这些策略只需将不起作用。</span><span class="sxs-lookup"><span data-stu-id="c9628-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="c9628-133">相反，您必须创建新策略，并将这些策略应用于边缘服务器仅。</span><span class="sxs-lookup"><span data-stu-id="c9628-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="c9628-134">以下过程介绍创建用于管理边缘服务器上的服务质量的 Active Directory 组策略对象的过程。</span><span class="sxs-lookup"><span data-stu-id="c9628-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="c9628-135">当然，则可能边缘服务器是独立服务器不具有 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="c9628-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="c9628-136">如果是这样，您可以使用本地组策略，而不是 Active Directory 组策略： 唯一的区别是，您必须创建使用本地组策略编辑器中，这些本地策略，并分别必须在每台边缘服务器上创建一组相同的策略。</span><span class="sxs-lookup"><span data-stu-id="c9628-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="c9628-137">要开始在边缘服务器上的本地组策略编辑器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c9628-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="c9628-138">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="c9628-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="c9628-139">在**运行**对话框中，键入**gpedit.msc**，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c9628-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="c9628-140">如果您正在创建基于 Active Directory 的策略，然后您应登录到计算机上已安装组策略管理。</span><span class="sxs-lookup"><span data-stu-id="c9628-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="c9628-141">在这种情况下，打开组策略管理 （单击**开始**、**管理工具**，，然后单击**组策略管理**），然后完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c9628-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="c9628-142">在组策略管理中，找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="c9628-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="c9628-143">例如，如果您的业务服务器计算机的所有 Skype 都位于业务服务器命名 Skype OU 中，新策略应创建在 Skype 对于业务服务器 OU。</span><span class="sxs-lookup"><span data-stu-id="c9628-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="c9628-144">右键单击相应的容器，然后单击**创建在这个域 GPO 并在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="c9628-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="c9628-145">**新建 GPO**对话框中，在 (例如，**对于业务服务器音频的 Skype**)，**名称**框中键入新的组策略对象的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c9628-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="c9628-146">右键单击新创建的策略，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c9628-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="c9628-147">从此处的过程是相同无论您创建的 Active Directory 策略还是本地策略：</span><span class="sxs-lookup"><span data-stu-id="c9628-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="c9628-148">在组策略管理编辑器或本地组策略编辑器中，表中，展开**计算机配置**、 展开**策略**、 **Windows 设置**数据，右键单击**基于策略的 QoS**，，然后单击**创建新策略**。</span><span class="sxs-lookup"><span data-stu-id="c9628-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="c9628-149">在**基于策略的 QoS**对话框中，在打开页上，键入**名称**框中的新策略 (例如，**对于业务服务器音频的 Skype**) 的名称。</span><span class="sxs-lookup"><span data-stu-id="c9628-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="c9628-150">选择**指定 DSCP 值**并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="c9628-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="c9628-151">保留未选择，**指定出站调节率**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c9628-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="c9628-152">在下一页上，确保选中**所有应用程序**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c9628-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="c9628-153">此设置指示网络以查找所有包的特定应用程序创建的 46，而不仅仅是数据包的 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="c9628-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="c9628-154">在第三页上，确保同时**任何源 IP 地址**和**任何目标 IP 地址**选中，则，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c9628-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="c9628-155">这两个设置确保将管理数据包而不考虑哪台计算机 （IP 地址） 发送这些数据包和哪台计算机 （IP 地址） 将接收这些数据包。</span><span class="sxs-lookup"><span data-stu-id="c9628-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="c9628-156">在第四页中，从**选择此 QoS 策略应用于的协议**下拉列表中选择**TCP 和 UDP** 。</span><span class="sxs-lookup"><span data-stu-id="c9628-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="c9628-157">TCP （传输控制协议） 和 UDP （用户数据报协议） 是最常使用的业务服务器和其客户端应用程序的 Skype 的两个网络协议。</span><span class="sxs-lookup"><span data-stu-id="c9628-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="c9628-158">在标题下**指定目标端口号**，**从此目标端口或范围**中进行选择。</span><span class="sxs-lookup"><span data-stu-id="c9628-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="c9628-159">在相应的文本框中，键入供音频传输的端口范围。</span><span class="sxs-lookup"><span data-stu-id="c9628-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="c9628-160">例如，如果预留端口 49152 到音频流量的端口 57500，输入使用以下格式的端口范围： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="c9628-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="c9628-161">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="c9628-161">Click **Finish**.</span></span>

<span data-ttu-id="c9628-162">在创建音频流量的 QoS 策略后，您应创建视频流量的第二个策略。</span><span class="sxs-lookup"><span data-stu-id="c9628-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="c9628-163">若要创建视频的策略，请按照相同的基本过程您遵循创建音频策略时, 进行下列替换项操作：</span><span class="sxs-lookup"><span data-stu-id="c9628-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="c9628-164">使用其他 （及唯一） 策略名称 (例如， **Skype 业务 Server 视频**)。</span><span class="sxs-lookup"><span data-stu-id="c9628-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="c9628-165">设置为**34**而不是 46 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="c9628-165">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="c9628-166">（请注意，不需要使用 34 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="c9628-166">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="c9628-167">唯一的要求是不是用于音频，视频使用不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="c9628-167">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="c9628-168">使用视频流量的以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="c9628-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="c9628-169">例如，如果您保留了端口 57501 到 65535 视频，设置为此的端口范围： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="c9628-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="c9628-170">同样，这应配置为目标端口范围。</span><span class="sxs-lookup"><span data-stu-id="c9628-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="c9628-171">如果您决定创建用于管理应用程序共享流量的策略，则必须创建第三方策略，进行以下替代：</span><span class="sxs-lookup"><span data-stu-id="c9628-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="c9628-172">使用其他 （及唯一） 策略名称 (例如，**业务服务器应用程序共享的 Skype**)。</span><span class="sxs-lookup"><span data-stu-id="c9628-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="c9628-173">设置为**24**而不是 46 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="c9628-173">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="c9628-174">（同样，您不需要使用 DSCP 值，共 24 部分。</span><span class="sxs-lookup"><span data-stu-id="c9628-174">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="c9628-175">唯一的要求。 您可用于不同的 DSCP 值应用程序共享比使用音频或视频）</span><span class="sxs-lookup"><span data-stu-id="c9628-175">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="c9628-176">使用视频流量的以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="c9628-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="c9628-177">例如，如果您保留了端口 40803 到 49151 应用程序共享，设置为此的端口范围： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="c9628-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="c9628-178">组策略已在边缘服务器上刷新，已创建的新策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="c9628-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="c9628-179">尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="c9628-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="c9628-180">此命令可以从运行内 Skype 业务服务器或从管理员凭据运行任何命令窗口。</span><span class="sxs-lookup"><span data-stu-id="c9628-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="c9628-181">若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="c9628-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="c9628-182">请注意，您可能需要在运行 Gpudate.exe 后重新启动边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="c9628-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="c9628-183">为了帮助确保使用适当的 DSCP 值标记网络数据包，，还应通过完成以下过程在每台计算机上创建新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="c9628-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="c9628-184">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="c9628-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="c9628-185">在**运行**对话框中，键入**regedit**，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c9628-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="c9628-186">在注册表编辑器中，展开**HKEY\_本地\_计算机**，展开**系统**，展开**CurrentControlSet**，展开**服务**，然后展开**Tcpip**。</span><span class="sxs-lookup"><span data-stu-id="c9628-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="c9628-187">右键单击**Tcpip**，指向**新建**，，然后单击**项**。</span><span class="sxs-lookup"><span data-stu-id="c9628-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="c9628-188">创建新的注册表项后，键入**QoS**，，，然后按 ENTER 以重命名该项。</span><span class="sxs-lookup"><span data-stu-id="c9628-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="c9628-189">右键单击**QoS**，指向**新建**，，然后单击**字符串值**。</span><span class="sxs-lookup"><span data-stu-id="c9628-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="c9628-190">创建新的注册表值后，键入**不使用 NLA**，，，然后按 ENTER 以重命名该值。</span><span class="sxs-lookup"><span data-stu-id="c9628-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="c9628-191">双击**请勿使用 NLA**。</span><span class="sxs-lookup"><span data-stu-id="c9628-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="c9628-192">**编辑字符串**对话框中，在**值数据**框中，键入**1** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c9628-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="c9628-193">关闭注册表编辑器，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="c9628-193">Close the Registry Editor and reboot your computer.</span></span>
