---
title: 为 A/V 边缘服务器配置服务质量策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b75e6094fd7d84e086e31bbc4535faf0df84155
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="0eff8-102">为 Lync Server 2013 中的 A/V 边缘服务器配置服务质量策略</span><span class="sxs-lookup"><span data-stu-id="0eff8-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eff8-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0eff8-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0eff8-p101">除了为会议、应用程序和中介服务器创建 QoS 策略外，还必须为 A/V 边缘服务器的内部端创建音频和视频策略。但是，边缘服务器中使用的策略与会议、应用程序和中介服务器中使用的策略不同。对于会议、应用程序和中介服务器，您要为其指定源端口范围；对于边缘服务器，您需要指定目标端口范围。因此，不能简单地将会议、应用程序和中介服务器的 QoS 策略应用于边缘服务器：这些策略将不起作用。您必须创建新策略并将这些策略仅应用于边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p101">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers. However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers. For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range. Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work. Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="0eff8-p102">以下过程介绍创建可用于在边缘服务器上管理服务质量的 Active Directory 组策略对象的过程。当然，您的边缘服务器可能是没有 Active Directory 帐户的独立服务器。如果是这样，可以使用本地组策略，而不使用 Active Directory 组策略：唯一的差别是必须使用本地组策略编辑器创建这些本地策略，并且必须在每台边缘服务器上分别创建同一组策略。若要在边缘服务器上启动本地组策略编辑器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0eff8-p102">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers. Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts. If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server. To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="0eff8-113">单击“开始”\*\*\*\*，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="0eff8-114">在“运行”\*\*\*\* 对话框中键入“gpedit.msc”\*\*\*\*，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="0eff8-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="0eff8-p103">如果要创建基于 Active Directory 的策略，应登录已安装“组策略管理”的计算机。在此情况下，打开“组策略管理”（单击“开始”\*\*\*\*，指向“管理工具”\*\*\*\*，然后单击“组策略管理”\*\*\*\*），然后完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0eff8-p103">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed. In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="0eff8-p104">在“组策略管理”中，查找应创建新策略的容器。例如，如果所有 Lync Server 计算机都位于一个名为 Lync Server 的 OU 中，则应在 Lync Server OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p104">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="0eff8-119">右键单击适当的容器，然后单击“在这个域中创建 GPO 并在此处链接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="0eff8-120">在“新建 GPO”\*\*\*\* 对话框的“名称”\*\*\*\* 框中键入新的组策略对象的名称（例如，“Lync Server Audio”\*\*\*\*），然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="0eff8-121">右键单击新创建的策略，然后单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="0eff8-122">无论您要创建 Active Directory 策略还是本地策略，此处的过程都相同：</span><span class="sxs-lookup"><span data-stu-id="0eff8-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="0eff8-123">在组策略管理编辑器或本地组策略编辑器中，依次展开“计算机配置”\*\*\*\*、“策略”\*\*\*\* 和“Windows 设置”\*\*\*\*，右键单击“基于策略的 QoS”\*\*\*\*，然后单击“新建策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="0eff8-p105">在“基于策略的 QoS”\*\*\*\* 对话框中的打开页上，在“名称”\*\*\*\* 框中键入新策略的名称（例如，“Lync Server Audio”\*\*\*\*）。选择“指定 DSCP 值”\*\*\*\* 并将该值设置为“46”\*\*\*\*。将“指定出站调节率”\*\*\*\* 保留未选中状态，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="0eff8-p106">在下一页中，确保已选中“全部应用程序”\*\*\*\*，然后单击“下一步”\*\*\*\*。此设置指示网络查找 DSCP 标记为 46 的所有数据包，而不只是特定应用程序创建的数据包。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="0eff8-p107">在第三页上，确保选中“任意源 IP 地址”\*\*\*\* 和“任意目标 IP 地址”\*\*\*\*，然后单击“下一步”\*\*\*\*。这两个设置确保将管理这些数据包，与哪台计算机（IP 地址）发送这些数据包及哪台计算机（IP 地址）将接收这些数据包无关。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="0eff8-131">在第四页上，从“选择此 QoS 策略所适用的协议”\*\*\*\* 下拉列表中选择“TCP 和 UDP”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="0eff8-132">TCP （传输控制协议）和 UDP （用户数据报协议）是 Lync Server 及其客户端应用程序最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="0eff8-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="0eff8-p109">在标题“指定目标端口号”\*\*\*\* 下，选择“从此目标端口或范围”\*\*\*\*。在对应的文本框中，键入为音频传输保留的端口范围。例如，如果为音频通信保留了端口 49152 至端口 57500，则使用以下格式输入此端口范围：“49152:57500”\*\*\*\*。单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p109">Under the heading **Specify the destination port number**, select **From this destination port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<span data-ttu-id="0eff8-p110">在为音频通信创建 QoS 策略后，应为视频通信创建第二个策略。若要创建用于视频的策略，请执行与创建音频策略时相同的基本过程，但进行以下替代：</span><span class="sxs-lookup"><span data-stu-id="0eff8-p110">After you have created the QoS policy for audio traffic you should create a second policy for video traffic. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="0eff8-139">使用不同（并且唯一）的策略名称（例如，“Lync Server Video”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="0eff8-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="0eff8-p111">将 DSCP 值设置为“34”\*\*\*\* 而不是 46。（注意，不一定要使用 DSCP 值 34。唯一的要求是对视频使用与用于音频的 DSCP 值不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="0eff8-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="0eff8-p112">将以前配置的端口范围用于视频通信。例如，如果已为视频保留端口 57501 至 65535，则可将端口范围设置为：“57501:65535”\*\*\*\*。同样，应将其配置为目标端口范围。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p112">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**. Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="0eff8-146">如果您决定创建用于管理应用程序共享通信的策略，则必须创建第三个策略，但进行以下替代：</span><span class="sxs-lookup"><span data-stu-id="0eff8-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="0eff8-147">使用不同（并且唯一）的策略名称（例如，“Lync Server Application Sharing”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="0eff8-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="0eff8-p113">将 DSCP 值设置为“24”\*\*\*\* 而不是 46。（同样，不一定要使用 DSCP 值 24。唯一的要求是对应用程序共享使用与用于音频或视频的 DSCP 值不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="0eff8-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="0eff8-p114">将以前配置的端口范围用于视频通信。例如，如果已为应用程序共享保留端口 40803 至 49151，则可将端口范围设置为：“40803:49151”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="0eff8-p115">在边缘服务器中刷新组策略之前，您已创建的新策略将不会生效。尽管组策略会定期地自行刷新，但可通过在需要刷新组策略的每台计算机上运行以下命令来强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="0eff8-p115">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="0eff8-155">此命令可从 Lync Server 中或在管理员凭据下运行的任何命令窗口中运行。</span><span class="sxs-lookup"><span data-stu-id="0eff8-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="0eff8-156">若要在管理员凭据下运行命令窗口，请单击“开始”\*\*\*\*，右键单击“命令提示符”\*\*\*\*，然后单击“以管理员身份运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="0eff8-157">请注意，即使在运行 Gpudate.exe 之后，您仍然可能需要重新启动边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="0eff8-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="0eff8-158">为了帮助确保用适当的 DSCP 值标记网络数据包，还应通过完成以下过程在每台计算机上创建一个新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="0eff8-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="0eff8-159">单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="0eff8-160">在“运行”\*\*\*\* 对话框中，键入“regedit”\*\*\*\*，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="0eff8-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="0eff8-161">在注册表编辑器中，展开 **"\_HKEY\_本地计算机**"，展开 "**系统**"，展开 " **CurrentControlSet**"，展开 "**服务**"，然后展开 " **Tcpip**"。</span><span class="sxs-lookup"><span data-stu-id="0eff8-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="0eff8-p117">右键单击“Tcpip”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“项”\*\*\*\*。创建新注册表项后，键入“QoS”\*\*\*\*，然后按 Enter 键以重命名该项。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="0eff8-p118">右键单击“QoS”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“字符串值”\*\*\*\*。在创建新的注册表值之后，键入“不使用 NLA”\*\*\*\*，然后按 Enter 键以重命名值。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="0eff8-p119">双击“不使用 NLA”\*\*\*\*。在“编辑字符串”\*\*\*\* 对话框的“数值数据”\*\*\*\* 框中，键入“1”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0eff8-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="0eff8-168">关闭注册表编辑器，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="0eff8-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

