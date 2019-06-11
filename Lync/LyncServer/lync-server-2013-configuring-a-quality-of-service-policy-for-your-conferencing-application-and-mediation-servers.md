---
title: Lync Server 2013：为您的会议、应用程序和中介服务器配置服务质量策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a79835fb19f5a30a11eac4859f133aeec5c8cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="a16d8-102">在 Lync Server 2013 中为您的会议、应用程序和中介服务器配置服务质量策略</span><span class="sxs-lookup"><span data-stu-id="a16d8-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a16d8-103">_**主题上次修改时间:** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="a16d8-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="a16d8-104">通过配置端口范围, 可确保指定类型的所有流量 (例如, 所有音频流量) 通过同一组端口传播, 从而促进服务质量的使用。</span><span class="sxs-lookup"><span data-stu-id="a16d8-104">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="a16d8-105">这使系统可以轻松识别和标记给定数据包: 如果端口49152是为音频流量保留的, 则通过端口49152传送的任何数据包都可以使用 DSCP 代码进行标记, 以指示这是音频数据包。</span><span class="sxs-lookup"><span data-stu-id="a16d8-105">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="a16d8-106">这使路由器能够将数据包识别为音频数据包, 并为其提供比未标记数据包更高的优先级 (如用于将文件从一台服务器复制到另一台服务器的数据包)。</span><span class="sxs-lookup"><span data-stu-id="a16d8-106">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="a16d8-107">但是, 仅将一组端口限制为特定类型的流量不会导致数据包传播到使用相应 DSCP 代码标记的这些端口。</span><span class="sxs-lookup"><span data-stu-id="a16d8-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="a16d8-108">除了定义端口范围之外, 还必须创建服务策略的质量策略, 以指定与每个端口范围关联的 DSCP 代码。</span><span class="sxs-lookup"><span data-stu-id="a16d8-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="a16d8-109">对于 Microsoft Lync Server 2013, 通常意味着创建两个策略: 一个用于音频, 另一个用于视频。</span><span class="sxs-lookup"><span data-stu-id="a16d8-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="a16d8-110">服务质量策略最轻松地通过使用组策略来创建和管理。</span><span class="sxs-lookup"><span data-stu-id="a16d8-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="a16d8-111">(也可以使用本地安全策略创建这些相同的策略。</span><span class="sxs-lookup"><span data-stu-id="a16d8-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="a16d8-112">但是, 这要求你在每台计算机上重复相同的过程。)QoS 策略的初始集 (一个用于音频, 另一个用于视频) 应仅应用于运行会议服务器、应用服务器和/或中介服务器服务的 Lync Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="a16d8-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="a16d8-113">如果所有这些计算机都位于同一个 Active Directory OU 中, 则只需将新的组策略对象 (GPO) 分配给该 OU 即可。</span><span class="sxs-lookup"><span data-stu-id="a16d8-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="a16d8-114">或者, 你可以执行其他步骤将新策略定向到指定的计算机;例如, 你可以将相应的计算机放置在安全组中, 然后使用组策略安全筛选功能将 GPO 仅应用于该安全组。</span><span class="sxs-lookup"><span data-stu-id="a16d8-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="a16d8-115">为了创建用于管理音频的服务质量策略, 请登录到已安装组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="a16d8-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="a16d8-116">打开组策略管理 (单击 "**开始**", 指向 "**管理工具**", 然后单击 "**组策略管理**"), 然后完成以下过程:</span><span class="sxs-lookup"><span data-stu-id="a16d8-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="a16d8-117">在 "组策略管理" 中, 找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="a16d8-117">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="a16d8-118">例如, 如果所有 Lync Server 计算机都位于名为 Lync Server 的 OU 中, 则应在 Lync Server OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="a16d8-118">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="a16d8-119">右键单击相应的容器, 然后单击 "**在此域中创建 GPO", 然后在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="a16d8-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="a16d8-120">在 "**新建 GPO** " 对话框中, 在 "**名称**" 框中键入新组策略对象的名称 (例如, **Lync Server QoS**), 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a16d8-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="a16d8-121">右键单击新创建的策略, 然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="a16d8-122">在组策略管理编辑器中, 展开 "**计算机配置**", 展开 "**策略**", 展开 " **Windows 设置**", 右键单击 "**基于策略的 QoS**", 然后单击 "**创建新策略**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="a16d8-123">在 "**基于策略的 QoS** " 对话框中的 "开始" 页面上, 在 "**名称**" 框中键入新策略的名称 (例如**Lync Server QoS**)。</span><span class="sxs-lookup"><span data-stu-id="a16d8-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="a16d8-124">选择 "**指定 DSCP 值**" 并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="a16d8-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="a16d8-125">"退出"**指定出站阻止率**未选中, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="a16d8-126">在下一页上, 确保已选中 "**所有应用程序**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-126">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="a16d8-127">这只是确保所有应用程序都将指定端口范围中的数据包与指定的 DSCP 代码相匹配。</span><span class="sxs-lookup"><span data-stu-id="a16d8-127">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="a16d8-128">在第三页上, 确保选中了 "**任何来源 ip 地址" 和 "任何目标 ip 地址**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-128">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="a16d8-129">这两个设置确保数据包将被管理, 无论哪台计算机 (IP 地址) 发送这些数据包以及哪台计算机 (IP 地址) 将接收这些数据包。</span><span class="sxs-lookup"><span data-stu-id="a16d8-129">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="a16d8-130">在第4页上, 从 "**选择协议此 QoS 策略应用**于" 下拉列表中选择 " **TCP 和 UDP** "。</span><span class="sxs-lookup"><span data-stu-id="a16d8-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="a16d8-131">TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Lync Server 及其客户端应用程序最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="a16d8-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="a16d8-132">在 "标题" 下,**指定源端口号**, 选择 "**从此源端口或范围**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-132">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="a16d8-133">在 "随附文本" 框中, 键入为音频传输保留的端口范围。</span><span class="sxs-lookup"><span data-stu-id="a16d8-133">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="a16d8-134">例如, 如果您通过端口57500为音频流量保留了端口 49152, 请输入使用以下格式的端口范围: **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="a16d8-134">For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="a16d8-135">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a16d8-135">Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a16d8-136">46的 DSCP 值有一定的作用: 尽管 DSCP 46 通常用于标记音频数据包, 但您不必使用 DSCP 46 进行音频通信。</span><span class="sxs-lookup"><span data-stu-id="a16d8-136">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="a16d8-137">如果你已实现 QoS, 并且使用的是不同的音频 DSCP 代码 (例如, DSCP 40), 则应将你的服务质量策略配置为使用相同的代码 (例如, 40 表示音频)。</span><span class="sxs-lookup"><span data-stu-id="a16d8-137">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="a16d8-138">如果您刚刚实现服务质量, 建议您对音频使用 DSCP 46, 只是因为该值通常用于标记音频数据包。</span><span class="sxs-lookup"><span data-stu-id="a16d8-138">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="a16d8-139">为音频流量创建 QoS 策略之后, 您应该为视频通信创建第二个策略 (也可以选择第三个用于管理应用程序共享流量的策略)。</span><span class="sxs-lookup"><span data-stu-id="a16d8-139">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="a16d8-140">若要创建视频的策略, 请按照创建音频策略时所遵循的基本过程进行操作, 进行以下替换:</span><span class="sxs-lookup"><span data-stu-id="a16d8-140">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="a16d8-141">使用不同 (且唯一) 的策略名称 (如**Lync Server 视频**)。</span><span class="sxs-lookup"><span data-stu-id="a16d8-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="a16d8-142">将 DSCP 值设置为**34**而不是46。</span><span class="sxs-lookup"><span data-stu-id="a16d8-142">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="a16d8-143">(请注意, 您不必使用34的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="a16d8-143">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="a16d8-144">唯一的要求是对视频使用的 DSCP 值与用于音频的值不同。)</span><span class="sxs-lookup"><span data-stu-id="a16d8-144">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="a16d8-145">对视频流量使用以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="a16d8-145">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="a16d8-146">例如, 如果您已为视频保留了57501到65535的备用端口, 则将端口范围设置为: **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="a16d8-146">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="a16d8-147">如果你决定创建用于管理应用程序共享流量的策略, 则必须创建第三个策略, 从而进行以下替换:</span><span class="sxs-lookup"><span data-stu-id="a16d8-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="a16d8-148">使用不同 (且唯一) 的策略名称 (如**Lync Server 应用程序共享**)。</span><span class="sxs-lookup"><span data-stu-id="a16d8-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="a16d8-149">将 DSCP 值设置为**24** , 而不是46。</span><span class="sxs-lookup"><span data-stu-id="a16d8-149">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="a16d8-150">(同样, 您无需使用 DSCP 值24。</span><span class="sxs-lookup"><span data-stu-id="a16d8-150">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="a16d8-151">唯一的要求是对应用程序共享使用的 DSCP 值与音频或视频使用的 DSCP 值不同。)</span><span class="sxs-lookup"><span data-stu-id="a16d8-151">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="a16d8-152">对视频流量使用以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="a16d8-152">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="a16d8-153">例如, 如果你已为应用程序共享保留端口40803到 49151, 请将端口范围设置为: **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="a16d8-153">For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="a16d8-154">在 Lync 服务器计算机上刷新组策略之前, 你创建的新策略将不会生效。</span><span class="sxs-lookup"><span data-stu-id="a16d8-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="a16d8-155">尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="a16d8-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="a16d8-156">此命令可以从 Lync Server Management Shell 或在 "管理员凭据" 下运行的任何命令窗口中运行。</span><span class="sxs-lookup"><span data-stu-id="a16d8-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="a16d8-157">若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="a16d8-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="a16d8-158">若要验证是否已应用新的 QoS 策略, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="a16d8-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="a16d8-159">在 Lync 服务器计算机上, 单击 "**开始**", 然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="a16d8-160">在 "**运行**" 对话框中, 键入**regedit** , 然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="a16d8-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="a16d8-161">在注册表编辑器中, 展开 "**计算机**", 依次展开 " **\_HKEY 本地\_计算机**"、"**软件**"、"**策略**"、" **Microsoft**"、" **Windows**", 然后单击 " **QoS**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="a16d8-162">在 " **QoS** " 下, 你应该看到刚才创建的每个 QoS 策略的注册表项。</span><span class="sxs-lookup"><span data-stu-id="a16d8-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="a16d8-163">例如, 如果您创建了两个新策略 (一个名为 Lync Server 音频 QoS 和其他已命名的 Lync 服务器视频 QoS), 则应输入 Lync Server 音频 QoS 和 Lync Server 视频 QoS 的注册表项。</span><span class="sxs-lookup"><span data-stu-id="a16d8-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="a16d8-164">为了帮助确保网络数据包使用适当的 DSCP 值进行标记, 还应通过完成以下过程在每台计算机上创建一个新的注册表项:</span><span class="sxs-lookup"><span data-stu-id="a16d8-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="a16d8-165">单击 "**开始**", 然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="a16d8-166">在 "**运行**" 对话框中, 键入**regedit** , 然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="a16d8-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="a16d8-167">在注册表编辑器中, 展开 **"\_HKEY\_本地计算机**", 依次展开 "**系统**"、" **CurrentControlSet**"、"**服务**", 然后展开 " **Tcpip**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="a16d8-168">右键单击 " **Tcpip**", 指向 "**新建**", 然后单击 "**项**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-168">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="a16d8-169">创建新的注册表项后, 键入**QoS** , 然后按 enter 重命名该项。</span><span class="sxs-lookup"><span data-stu-id="a16d8-169">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="a16d8-170">右键单击 " **QoS**", 指向 "**新建**", 然后单击 "**字符串值**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-170">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="a16d8-171">创建新的注册表值后, 键入 "不**使用 NLA** ", 然后按 enter 重命名该值。</span><span class="sxs-lookup"><span data-stu-id="a16d8-171">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="a16d8-172">双击 "不**使用 NLA**"。</span><span class="sxs-lookup"><span data-stu-id="a16d8-172">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="a16d8-173">在 "**编辑字符串**" 对话框中, 在 "**值数据**" 框中键入**1** , 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a16d8-173">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="a16d8-174">关闭注册表编辑器, 然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="a16d8-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

