---
title: Lync Server 2013：为您的会议、应用程序和中介服务器配置服务质量策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4711c618669a8fe47a877b4adeafe7759564855f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="ac703-102">在 Lync Server 2013 中为您的会议、应用程序和中介服务器配置服务质量策略</span><span class="sxs-lookup"><span data-stu-id="ac703-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac703-103">_**上次修改的主题：** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="ac703-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="ac703-p101">配置端口范围通过确保指定类型的所有流量（例如，所有音频流量）通过同一组端口进行传输来方便服务质量的使用。这使系统标识和标记给定数据包变得容易：如果端口 49152 是为音频通信保留的，则通过端口 49152 的所有数据包均可使用 DSCP 代码进行标记，以指示这是一个音频数据包。反过来，这使路由器能将此数据包标识为一个音频数据包，并为其提供比未标记数据包更高的优先级（如用于将文件从一台服务器复制到另一台服务器的数据包）。</span><span class="sxs-lookup"><span data-stu-id="ac703-p101">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="ac703-107">但是，简单地将一组端口限制为特定类型的流量不会产生通过那些使用适当的 DSCP 代码标记的端口的数据包。</span><span class="sxs-lookup"><span data-stu-id="ac703-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="ac703-108">除了定义端口范围之外，还必须创建用于指定与每个端口范围关联的 DSCP 代码的服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="ac703-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="ac703-109">对于 Microsoft Lync Server 2013，通常意味着创建两个策略：一个用于音频，一个用于视频。</span><span class="sxs-lookup"><span data-stu-id="ac703-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="ac703-110">使用组策略创建和管理服务质量策略是最轻松的。</span><span class="sxs-lookup"><span data-stu-id="ac703-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="ac703-111">（还可使用本地安全策略创建这些相同的策略。</span><span class="sxs-lookup"><span data-stu-id="ac703-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="ac703-112">但是，这需要在每台计算机上重复相同的过程。您的一组初始 QoS 策略（一个 for 音频，一个用于视频）应仅应用于运行会议服务器、应用程序服务器和/或中介服务器服务的 Lync Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="ac703-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="ac703-113">如果所有这些计算机都位于同一 Active Directory OU 中，则只需向该 OU 分配新的组策略对象 (GPO) 即可。</span><span class="sxs-lookup"><span data-stu-id="ac703-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="ac703-114">或者，您也可以执行其他步骤将新策略定向到指定计算机；例如，您可将相应计算机放在某个安全组中，然后使用组策略安全筛选将 GPO 应用于该安全组。</span><span class="sxs-lookup"><span data-stu-id="ac703-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="ac703-115">若要创建用于管理音频的服务质量策略，请登录到安装了组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="ac703-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="ac703-116">打开组策略管理（单击“开始”\*\*\*\*，指向“管理工具”\*\*\*\*，然后单击“组策略管理”\*\*\*\*），然后完成下列过程：</span><span class="sxs-lookup"><span data-stu-id="ac703-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="ac703-p105">在“组策略管理”中，查找应创建新策略的容器。例如，如果所有 Lync Server 计算机都位于一个名为 Lync Server 的 OU 中，则应在 Lync Server OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="ac703-p105">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="ac703-119">右键单击适当的容器，然后单击“在这个域中创建 GPO 并在此处链接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="ac703-120">在 "**新建 GPO** " 对话框中，在 "**名称**" 框中键入新组策略对象的名称（例如， **Lync Server QoS**），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="ac703-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="ac703-121">右键单击新创建的策略，然后单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="ac703-122">在组策略管理编辑器中，依次展开“计算机配置”\*\*\*\*、“策略”\*\*\*\* 和“Windows 设置”\*\*\*\*， 右键单击“基于策略的 QoS”\*\*\*\*，然后单击“创建新策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="ac703-123">在 "**基于策略的 QoS** " 对话框的 "开始" 页上，在 "**名称**" 框中键入新策略的名称（例如， **Lync Server QoS**）。</span><span class="sxs-lookup"><span data-stu-id="ac703-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="ac703-124">选择“指定 DSCP 值”\*\*\*\*，并将该值设置为“46”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="ac703-125">保留“指定出站调节率”\*\*\*\* 未选中，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="ac703-p107">在下一页上，确保选择“所有程序”\*\*\*\*，然后单击“下一步”\*\*\*\*。这将确保所有应用程序与指定端口范围内带有指定 DSCP 代码的数据包匹配。</span><span class="sxs-lookup"><span data-stu-id="ac703-p107">On the next page, make sure that **All applications** is selected and then click **Next**. This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="ac703-p108">在第 3 页上，确保选择“任何源 IP 地址和任何目标 IP 地址”\*\*\*\*，然后单击“下一步”\*\*\*\*。这两个设置将确保，无论发送和接收这些数据包的分别是哪台计算机（IP 地址），都会对数据包进行管理。</span><span class="sxs-lookup"><span data-stu-id="ac703-p108">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="ac703-130">在第四页上，从“选择此 QoS 策略所适用的协议”\*\*\*\* 下拉列表中选择“TCP 和 UDP”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="ac703-131">TCP （传输控制协议）和 UDP （用户数据报协议）是 Lync Server 及其客户端应用程序最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="ac703-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="ac703-p110">在标题“指定源端口号”\*\*\*\* 下，选择“来自此源端口或范围”\*\*\*\*。在附带的文本框中，键入为音频传输预留的端口范围。例如，如果为音频流量预留了 49152 至 57500 的端口，则使用以下格式输入端口范围：“49152:57500”\*\*\*\*。单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-p110">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ac703-p111">DSCP 值“46”有一定程度任意性：虽然 DSCP 46 通常用于标记音频数据包，但您不一定要使用 DSCP 46 进行音频通信。如果您已实现 QoS 并且对音频使用的是不同的 DSCP 代码（例如，DSCP 40），则应将服务质量策略配置为使用相同的代码（即，对音频使用 40）。如果正在实现服务质量，则建议对音频使用 DSCP 46，这只是因为此值常用于标记音频数据包。</span><span class="sxs-lookup"><span data-stu-id="ac703-p111">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications. If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio). If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="ac703-p112">为音频通信创建 QoS 策略之后，您应接着为视频通信创建第二个策略（而且还可以选择创建用于管理应用程序共享流量的第三个策略）。若要为视频创建策略，请同样执行创建音频策略时执行的基本过程，并进行以下替换：</span><span class="sxs-lookup"><span data-stu-id="ac703-p112">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic). To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="ac703-141">使用不同（并且唯一）的策略名称（例如，“Lync Server Video”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="ac703-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="ac703-p113">将 DSCP 值设置为“34”\*\*\*\* 而不是 46。（请注意，您不一定要使用 DSCP 值“34”。唯一要求是对视频和音频使用不同的 DSCP 值）。</span><span class="sxs-lookup"><span data-stu-id="ac703-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="ac703-p114">将之前配置的端口范围用于视频流量。例如，如果您已为视频预留了 57501 至 65535 的端口，则将端口范围设置为：“57501:65535”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="ac703-147">如果您决定创建用于管理应用程序共享流量的策略，则必须创建第三方策略，进行以下替换：</span><span class="sxs-lookup"><span data-stu-id="ac703-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="ac703-148">使用不同（并且唯一）的策略名称（例如，“Lync Server Application Sharing”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="ac703-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="ac703-p115">将 DSCP 值设置为“24”\*\*\*\* 而不是 46。（同样，不一定要使用 DSCP 值 24。唯一的要求是对应用程序共享使用与用于音频或视频的 DSCP 值不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="ac703-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="ac703-p116">将以前配置的端口范围用于视频通信。例如，如果已为应用程序共享保留端口 40803 至 49151，则可将端口范围设置为：“40803:49151”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="ac703-154">在 Lync Server 计算机上刷新组策略之前，您创建的新策略将不会生效。</span><span class="sxs-lookup"><span data-stu-id="ac703-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="ac703-155">尽管组策略会定期自行刷新，但是您可以通过在需要刷新的组策略所在的每台计算机上运行下列命令来强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="ac703-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="ac703-156">此命令可以从 Lync Server 命令行管理程序中运行，也可以通过管理员凭据下运行的任何命令窗口运行。</span><span class="sxs-lookup"><span data-stu-id="ac703-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="ac703-157">若要在管理员凭据下运行命令窗口，请单击“开始”\*\*\*\*，右键单击“命令提示符”\*\*\*\*，然后单击“以管理员身份运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="ac703-158">若要验证是否已应用新的 QoS 策略，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ac703-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="ac703-159">在 Lync Server 计算机上，单击“开始”\*\*\*\*，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="ac703-160">在“运行”\*\*\*\* 对话框中，键入“regedit”\*\*\*\*，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="ac703-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="ac703-161">在 "注册表编辑器" 中，依次展开 "**计算机**"、" **\_HKEY 本地\_计算机**"、"**软件**"、"**策略**"、" **Microsoft**" 和 " **Windows**"，然后单击 " **QoS**"。</span><span class="sxs-lookup"><span data-stu-id="ac703-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="ac703-162">在“QoS”\*\*\*\* 下，您应看到刚刚创建的每个 QoS 策略对应的注册表项。</span><span class="sxs-lookup"><span data-stu-id="ac703-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="ac703-163">例如，如果您创建了两个新策略（一个名为 Lync Server 音频 QoS 和另一个已命名的 Lync Server 视频 QoS），则应注册 Lync Server 音频 QoS 和 Lync Server 视频 qos 的条目。</span><span class="sxs-lookup"><span data-stu-id="ac703-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="ac703-164">要确保将网络数据包标记为相应的 DSCP 值，还应该通过完成以下过程在每台计算机上创建新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="ac703-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="ac703-165">单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="ac703-166">在“运行”\*\*\*\* 对话框中，键入“regedit”\*\*\*\*，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="ac703-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="ac703-167">在注册表编辑器中，展开 **"\_HKEY\_本地计算机**"，展开 "**系统**"，展开 " **CurrentControlSet**"，展开 "**服务**"，然后展开 " **Tcpip**"。</span><span class="sxs-lookup"><span data-stu-id="ac703-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="ac703-p120">右键单击“Tcpip”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“项”\*\*\*\*。创建新注册表项后，键入“QoS”\*\*\*\*，然后按 Enter 键以重命名该项。</span><span class="sxs-lookup"><span data-stu-id="ac703-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="ac703-p121">右键单击“QoS”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“字符串值”\*\*\*\*。在创建新的注册表值之后，键入“不使用 NLA”\*\*\*\*，然后按 Enter 键以重命名值。</span><span class="sxs-lookup"><span data-stu-id="ac703-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="ac703-p122">双击“不使用 NLA”\*\*\*\*。在“编辑字符串”\*\*\*\* 对话框的“数值数据”\*\*\*\* 框中，键入“1”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac703-p122">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="ac703-174">关闭注册表编辑器，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="ac703-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

