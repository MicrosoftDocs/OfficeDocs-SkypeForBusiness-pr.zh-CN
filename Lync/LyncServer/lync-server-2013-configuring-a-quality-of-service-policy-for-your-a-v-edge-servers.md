---
title: 为您的 A/V 边缘服务器配置服务质量策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f5bfabfe794ed274d28074aaf162bc715a6ed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="71bc5-102">在 Lync Server 2013 中为您的 A/V 边缘服务器配置服务质量策略</span><span class="sxs-lookup"><span data-stu-id="71bc5-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71bc5-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="71bc5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="71bc5-104">除了为你的会议、应用程序和中介服务器创建 QoS 策略之外, 还必须为你的 A/V 边缘服务器的内部端创建音频和视频策略。</span><span class="sxs-lookup"><span data-stu-id="71bc5-104">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="71bc5-105">但是, 你的 Edge 服务器上使用的策略与你的会议、应用程序和中介服务器上使用的策略不同。</span><span class="sxs-lookup"><span data-stu-id="71bc5-105">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="71bc5-106">对于会议、应用程序和中介服务器, 你指定了源端口范围;在 "边缘服务器" 中, 你需要指定目标端口范围。</span><span class="sxs-lookup"><span data-stu-id="71bc5-106">For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="71bc5-107">因此, 你不能直接将会议、应用程序和中介服务器 QoS 策略应用到 Edge 服务器: 这些策略根本不起作用。</span><span class="sxs-lookup"><span data-stu-id="71bc5-107">Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="71bc5-108">相反, 你必须创建新策略并将这些策略应用到 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="71bc5-108">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="71bc5-109">以下过程介绍了创建可用于管理边缘服务器上的服务质量的 Active Directory 组策略对象的过程。</span><span class="sxs-lookup"><span data-stu-id="71bc5-109">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="71bc5-110">当然, 您的边缘服务器可能是没有 Active Directory 帐户的独立服务器。</span><span class="sxs-lookup"><span data-stu-id="71bc5-110">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="71bc5-111">如果是这种情况, 则可以使用本地组策略, 而不是 Active Directory 组策略: 唯一的区别在于必须使用本地组策略编辑器创建这些本地策略, 并且必须在每个边缘服务器上分别创建相同的策略集。</span><span class="sxs-lookup"><span data-stu-id="71bc5-111">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="71bc5-112">若要在边缘服务器上启动本地组策略编辑器, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="71bc5-112">To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="71bc5-113">单击 "**开始**", 然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="71bc5-114">在 "**运行**" 对话框中, 键入 " **gpedit.msc** ", 然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="71bc5-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="71bc5-115">如果你要创建基于 Active Directory 的策略, 则应登录到已安装组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="71bc5-115">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="71bc5-116">在这种情况下, 请打开组策略管理 (单击 "**开始**", 指向 "**管理工具**", 然后单击 "**组策略管理**"), 然后完成以下步骤:</span><span class="sxs-lookup"><span data-stu-id="71bc5-116">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="71bc5-117">在 "组策略管理" 中, 找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="71bc5-117">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="71bc5-118">例如, 如果所有 Lync Server 计算机都位于名为 Lync Server 的 OU 中, 则应在 Lync Server OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="71bc5-118">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="71bc5-119">右键单击相应的容器, 然后单击 "**在此域中创建 GPO", 然后在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="71bc5-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="71bc5-120">在 "**新建 GPO** " 对话框中, 在 "**名称**" 框中键入新组策略对象的名称 (例如, **Lync Server 音频**), 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="71bc5-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="71bc5-121">右键单击新创建的策略, 然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="71bc5-122">无论您是在创建 Active Directory 策略还是本地策略, 该过程都是相同的:</span><span class="sxs-lookup"><span data-stu-id="71bc5-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="71bc5-123">在组策略管理编辑器或本地组策略编辑器中, 展开 "**计算机配置**", 展开 "**策略**", 展开 " **Windows 设置**", 右键单击 "**基于策略的 QoS**", 然后单击 "**创建新策略**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="71bc5-124">在 "**基于策略的 QoS** " 对话框中的 "开始" 页面上, 在 "**名称**" 框中键入新策略的名称 (例如**Lync Server 音频**)。</span><span class="sxs-lookup"><span data-stu-id="71bc5-124">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="71bc5-125">选择 "**指定 DSCP 值**" 并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="71bc5-125">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="71bc5-126">"退出"**指定出站阻止率**未选中, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-126">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="71bc5-127">在下一页上, 确保已选中 "**所有应用程序**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-127">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="71bc5-128">此设置指示网络查找 DSCP 标记为46的所有数据包, 而不仅仅是由特定应用程序创建的数据包。</span><span class="sxs-lookup"><span data-stu-id="71bc5-128">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="71bc5-129">在第三页上, 确保选中了 "**任何来源 ip 地址**" 和 "**任何目标 ip 地址**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-129">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="71bc5-130">这两个设置确保数据包将被管理, 无论哪台计算机 (IP 地址) 发送这些数据包以及哪台计算机 (IP 地址) 将接收这些数据包。</span><span class="sxs-lookup"><span data-stu-id="71bc5-130">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="71bc5-131">在第4页上, 从 "**选择协议此 QoS 策略应用**于" 下拉列表中选择 " **TCP 和 UDP** "。</span><span class="sxs-lookup"><span data-stu-id="71bc5-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="71bc5-132">TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Lync Server 及其客户端应用程序最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="71bc5-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="71bc5-133">在 "标题" 下,**指定目标端口号**, 选择 "**从此目标端口或范围**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-133">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="71bc5-134">在 "随附文本" 框中, 键入为音频传输保留的端口范围。</span><span class="sxs-lookup"><span data-stu-id="71bc5-134">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="71bc5-135">例如, 如果通过端口57500为音频流量保留了端口 49152, 请使用以下格式输入端口范围: **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="71bc5-135">For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="71bc5-136">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="71bc5-136">Click **Finish**.</span></span>

<span data-ttu-id="71bc5-137">为音频流量创建 QoS 策略后, 应为视频流量创建第二个策略。</span><span class="sxs-lookup"><span data-stu-id="71bc5-137">After you have created the QoS policy for audio traffic you should create a second policy for video traffic.</span></span> <span data-ttu-id="71bc5-138">若要创建视频的策略, 请按照创建音频策略时所遵循的基本过程进行操作, 进行以下替换:</span><span class="sxs-lookup"><span data-stu-id="71bc5-138">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="71bc5-139">使用不同 (且唯一) 的策略名称 (如**Lync Server 视频**)。</span><span class="sxs-lookup"><span data-stu-id="71bc5-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="71bc5-140">将 DSCP 值设置为**34**而不是46。</span><span class="sxs-lookup"><span data-stu-id="71bc5-140">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="71bc5-141">(请注意, 您不必使用34的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="71bc5-141">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="71bc5-142">唯一的要求是对视频使用的 DSCP 值与用于音频的值不同。)</span><span class="sxs-lookup"><span data-stu-id="71bc5-142">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="71bc5-143">对视频流量使用以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="71bc5-143">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="71bc5-144">例如, 如果您已为视频保留了57501到65535的备用端口, 则将端口范围设置为: **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="71bc5-144">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="71bc5-145">同样, 应将此配置为目标端口范围。</span><span class="sxs-lookup"><span data-stu-id="71bc5-145">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="71bc5-146">如果你决定创建用于管理应用程序共享流量的策略, 则必须创建第三个策略, 从而进行以下替换:</span><span class="sxs-lookup"><span data-stu-id="71bc5-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="71bc5-147">使用不同 (且唯一) 的策略名称 (如**Lync Server 应用程序共享**)。</span><span class="sxs-lookup"><span data-stu-id="71bc5-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="71bc5-148">将 DSCP 值设置为**24** , 而不是46。</span><span class="sxs-lookup"><span data-stu-id="71bc5-148">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="71bc5-149">(同样, 您无需使用 DSCP 值24。</span><span class="sxs-lookup"><span data-stu-id="71bc5-149">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="71bc5-150">唯一的要求是对应用程序共享使用的 DSCP 值与音频或视频使用的 DSCP 值不同。)</span><span class="sxs-lookup"><span data-stu-id="71bc5-150">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="71bc5-151">对视频流量使用以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="71bc5-151">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="71bc5-152">例如, 如果你已为应用程序共享保留端口40803到 49151, 请将端口范围设置为: **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="71bc5-152">For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="71bc5-153">在边缘服务器上刷新组策略之前, 你创建的新策略将不会生效。</span><span class="sxs-lookup"><span data-stu-id="71bc5-153">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="71bc5-154">尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="71bc5-154">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="71bc5-155">此命令可以从 Lync 服务器内运行, 也可以从运行于 "管理员凭据" 下的任何命令窗口运行。</span><span class="sxs-lookup"><span data-stu-id="71bc5-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="71bc5-156">若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="71bc5-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="71bc5-157">请注意, 即使在运行 Gpudate 后, 你也可能需要重启 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="71bc5-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="71bc5-158">为了帮助确保网络数据包使用适当的 DSCP 值进行标记, 还应通过完成以下过程在每台计算机上创建一个新的注册表项:</span><span class="sxs-lookup"><span data-stu-id="71bc5-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="71bc5-159">单击 "**开始**", 然后单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="71bc5-160">在 "**运行**" 对话框中, 键入**regedit** , 然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="71bc5-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="71bc5-161">在注册表编辑器中, 展开 **"\_HKEY\_本地计算机**", 依次展开 "**系统**"、" **CurrentControlSet**"、"**服务**", 然后展开 " **Tcpip**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="71bc5-162">右键单击 " **Tcpip**", 指向 "**新建**", 然后单击 "**项**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-162">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="71bc5-163">创建新的注册表项后, 键入**QoS** , 然后按 enter 重命名该项。</span><span class="sxs-lookup"><span data-stu-id="71bc5-163">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="71bc5-164">右键单击 " **QoS**", 指向 "**新建**", 然后单击 "**字符串值**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-164">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="71bc5-165">创建新的注册表值后, 键入 "不**使用 NLA** ", 然后按 enter 重命名该值。</span><span class="sxs-lookup"><span data-stu-id="71bc5-165">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="71bc5-166">双击 "**不使用 NLA**"。</span><span class="sxs-lookup"><span data-stu-id="71bc5-166">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="71bc5-167">在 "**编辑字符串**" 对话框中, 在 "**值数据**" 框中键入**1** , 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="71bc5-167">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="71bc5-168">关闭注册表编辑器, 然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="71bc5-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

