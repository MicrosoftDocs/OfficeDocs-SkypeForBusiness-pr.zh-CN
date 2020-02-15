---
title: Lync Server 2013：为在 Windows 7 或 Windows 8 上运行的客户端配置服务质量策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05835b74f12d5e2d28036b100fd84f207a64e67c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="f79f5-102">为在 Windows 7 或 Windows 8 上运行的客户端配置 Lync Server 2013 中的服务质量策略</span><span class="sxs-lookup"><span data-stu-id="f79f5-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f79f5-103">_**上次修改的主题：** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="f79f5-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="f79f5-104">除了指定用于 Lync 客户端的端口范围之外，还必须创建将应用于客户端计算机的单独服务策略质量。</span><span class="sxs-lookup"><span data-stu-id="f79f5-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="f79f5-105">（不应将为会议、应用程序和中介服务器创建的服务质量策略应用于客户端计算机。）此信息仅适用于运行 Lync 2013 客户端的计算机以及 Windows 7 或 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="f79f5-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="f79f5-106">以下示例使用此端口范围的设置创建音频策略和视频策略：</span><span class="sxs-lookup"><span data-stu-id="f79f5-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f79f5-107">客户端通信类型</span><span class="sxs-lookup"><span data-stu-id="f79f5-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="f79f5-108">起始端口</span><span class="sxs-lookup"><span data-stu-id="f79f5-108">Port Start</span></span></th>
<th><span data-ttu-id="f79f5-109">端口范围</span><span class="sxs-lookup"><span data-stu-id="f79f5-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f79f5-110">音频</span><span class="sxs-lookup"><span data-stu-id="f79f5-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="f79f5-111">50020</span><span class="sxs-lookup"><span data-stu-id="f79f5-111">50020</span></span></p></td>
<td><p><span data-ttu-id="f79f5-112">20</span><span class="sxs-lookup"><span data-stu-id="f79f5-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f79f5-113">视频</span><span class="sxs-lookup"><span data-stu-id="f79f5-113">Video</span></span></p></td>
<td><p><span data-ttu-id="f79f5-114">58000</span><span class="sxs-lookup"><span data-stu-id="f79f5-114">58000</span></span></p></td>
<td><p><span data-ttu-id="f79f5-115">20</span><span class="sxs-lookup"><span data-stu-id="f79f5-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f79f5-116">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="f79f5-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f79f5-117">42000</span><span class="sxs-lookup"><span data-stu-id="f79f5-117">42000</span></span></p></td>
<td><p><span data-ttu-id="f79f5-118">20</span><span class="sxs-lookup"><span data-stu-id="f79f5-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f79f5-119">文件传输</span><span class="sxs-lookup"><span data-stu-id="f79f5-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="f79f5-120">42020</span><span class="sxs-lookup"><span data-stu-id="f79f5-120">42020</span></span></p></td>
<td><p><span data-ttu-id="f79f5-121">20</span><span class="sxs-lookup"><span data-stu-id="f79f5-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f79f5-122">若要为 Windows 7 或 Windows 8 计算机创建服务质量音频策略，请首先登录到安装了组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="f79f5-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="f79f5-123">打开组策略管理（单击“开始”\*\*\*\*，指向“管理工具”\*\*\*\*，然后单击“组策略管理”\*\*\*\*），然后完成下列过程：</span><span class="sxs-lookup"><span data-stu-id="f79f5-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="f79f5-p103">在组策略管理中，找到其中应创建新策略的容器。例如，如果所有客户端计算机位于名为客户端的 OU 中，则应在客户端 OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p103">In Group Policy Management, locate the container where the new policy should be created. For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="f79f5-126">右键单击相应的容器，然后单击“在这个域中创建 GPO 并在此处链接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="f79f5-127">在“新 GPO”\*\*\*\* 对话框中，为“名称”\*\*\*\* 框（例如，“Lync 音频”\*\*\*\*）中的新组策略对象输入一个名称，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="f79f5-128">右键单击新创建的策略，然后单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="f79f5-129">在组策略管理编辑器中，依次展开“计算机配置”\*\*\*\*、“策略”\*\*\*\* 和“Windows 设置”\*\*\*\*， 右键单击“基于策略的 QoS”\*\*\*\*，然后单击“创建新策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="f79f5-p104">在“基于策略的 QoS”\*\*\*\* 对话框中的打开的页面上，在“名称”\*\*\*\* 框中键入新策略（即：“Lync 音频”\*\*\*\*）的名称。选择“指定 DSCP 值”\*\*\*\*，并将该值设置为“46”\*\*\*\*。将“指定出站调节率”\*\*\*\* 保留为未选中状态，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p104">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="f79f5-133">在下一页上，选择 "**仅限具有此可执行文件名称的应用程序**" 并输入名称**Lync .exe**，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f79f5-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="f79f5-134">此设置指示策略仅将 Lync 客户端的匹配流量排定优先级。</span><span class="sxs-lookup"><span data-stu-id="f79f5-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="f79f5-p106">在第三页上，确保选中“任意源 IP 地址”\*\*\*\* 和“任意目标 IP 地址”\*\*\*\*，然后单击“下一步”\*\*\*\*。这两个设置确保将管理这些数据包，与哪台计算机（IP 地址）发送这些数据包及哪台计算机（IP 地址）将接收这些数据包无关。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="f79f5-137">在第四页上，从“选择此 QoS 策略所适用的协议”\*\*\*\* 下拉列表中选择“TCP 和 UDP”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="f79f5-138">TCP （传输控制协议）和 UDP （用户数据报协议）是 Lync Server 及其客户端应用程序最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="f79f5-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="f79f5-p108">在标题“指定源端口号”\*\*\*\* 下，选择“从此源端口或范围”\*\*\*\*。在附带的文本框中，键入为音频传输保留的端口范围。例如，如果您为音频流量保留端口 50020 到端口 50039，则使用以下格式输入端口范围：“50020:50039”\*\*\*\*。单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p108">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="f79f5-p109">在您为音频创建了 QoS 策略后，然后应该为视频创建第二个策略。要为视频创建策略，请按照您创建音频策略时遵循的相同基本过程，进行下列替换项：</span><span class="sxs-lookup"><span data-stu-id="f79f5-p109">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="f79f5-145">使用其他（及唯一）策略名称（例如，“Lync 视频”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="f79f5-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="f79f5-p110">将 DSCP 值设置为“34”\*\*\*\* 代替 46。（如先前所述，您不必使用为 34 的 DSCP 值；只是必须分配一个与用于音频不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="f79f5-p110">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="f79f5-p111">使用先前为视频流量配置的端口范围。例如，如果已为视频保留端口 58000 到 58019，然后将端口范围设置为：“58000:58019”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p111">Use the previously-configured port range for video traffic. For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="f79f5-150">如果您决定创建用于管理应用程序共享流量的策略，请进行下列替换项：</span><span class="sxs-lookup"><span data-stu-id="f79f5-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="f79f5-151">使用其他（及唯一）策略名称（例如，“Lync Server 应用程序共享”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="f79f5-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="f79f5-p112">将 DSCP 设置为“24”\*\*\*\* 代替 46。（另外，此值不必为 24；只是必须用于不同于音频和视频的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="f79f5-p112">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="f79f5-p113">使用先前为视频流量配置的端口范围。例如，如果已为应用程序共享保留端口 42000 到 42019，然后将端口范围设置为：“42000:42019”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p113">Use the previously-configured port range for video traffic. For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="f79f5-156">对于文件传输策略：</span><span class="sxs-lookup"><span data-stu-id="f79f5-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="f79f5-157">使用其他（及唯一）策略名称（例如，“Lync Server 文件传输”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="f79f5-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="f79f5-p114">将 DSCP 值设置为“14”\*\*\*\*。（另外，此值不必为 14；只是它必须为唯一 DSCP 代码。）</span><span class="sxs-lookup"><span data-stu-id="f79f5-p114">Set the DSCP value to **14**. (Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="f79f5-160">对应用程序使用先前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="f79f5-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="f79f5-161">例如，如果已为应用程序共享保留端口 42020 到 42039，然后将端口范围设置为：“42020:42039”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="f79f5-p116">在客户端计算机上刷新组策略之前，已创建的新策略不会生效。尽管组策略会定期自行刷新，但是您可以通过在需要刷新的组策略所在的每台计算机上运行下列命令来强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="f79f5-p116">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="f79f5-p117">可从在管理员凭据下运行的任何命令窗口运行此命令。要在管理员凭据下运行命令窗口，请单击“开始”\*\*\*\*，右键单击“命令提示符”\*\*\*\*，然后单击“以管理员身份运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p117">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="f79f5-166">请记住，应该将这些策略指向客户端计算机目标。</span><span class="sxs-lookup"><span data-stu-id="f79f5-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="f79f5-167">不应将它们应用于运行 Lync Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="f79f5-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="f79f5-168">要确保将网络数据包标记为相应的 DSCP 值，还应该通过完成以下过程在每台计算机上创建新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="f79f5-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="f79f5-169">单击“开始”\*\*\*\*，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="f79f5-170">在“运行”\*\*\*\* 对话框中，键入“regedit”\*\*\*\*，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="f79f5-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="f79f5-171">在注册表编辑器中，展开 **"\_HKEY\_本地计算机**"，展开 "**系统**"，展开 " **CurrentControlSet**"，展开 "**服务**"，然后展开 " **Tcpip**"。</span><span class="sxs-lookup"><span data-stu-id="f79f5-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="f79f5-p119">右键单击“Tcpip”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“项”\*\*\*\*。创建新注册表项后，键入“QoS”\*\*\*\*，然后按 Enter 键以重命名该项。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="f79f5-p120">右键单击“QoS”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“字符串值”\*\*\*\*。在创建新的注册表值之后，键入“不使用 NLA”\*\*\*\*，然后按 Enter 键以重命名值。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="f79f5-p121">双击“不使用 NLA”\*\*\*\*。在“编辑字符串”\*\*\*\* 对话框的“数值数据”\*\*\*\* 框中，键入“1”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p121">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="f79f5-178">关闭注册表编辑器，然后重新启动您的计算机。</span><span class="sxs-lookup"><span data-stu-id="f79f5-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="f79f5-179">在具有多个网络适配器的计算机上配置服务质量</span><span class="sxs-lookup"><span data-stu-id="f79f5-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="f79f5-p122">如果您的计算机有多个网络适配器，可能会偶尔遇到问题，即，DSCP 值显示为 0x00，而不是配置的值。此错误通常会发生在一个或多个网络适配器无法访问 Active Directory 域的计算机上（例如，如果这些适配器用于专用网络）。如果出现这种情况，则将 DSCP 值标记为使这些适配器可以访问该域，但不会标记为使这些适配器无法访问该域。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p122">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value. This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network). In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="f79f5-p123">如果想在计算机中为所有网络适配器标记 DSCP 值，包括对您的域没有访问权限的适配器，则需要将值添加到注册表并进行配置。这可通过执行下列过程来完成：</span><span class="sxs-lookup"><span data-stu-id="f79f5-p123">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry. That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="f79f5-185">单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="f79f5-186">在“运行”\*\*\*\* 对话框中，键入“regedit”\*\*\*\*，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="f79f5-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="f79f5-187">在注册表编辑器中，展开 **"\_HKEY\_本地计算机**"，展开 "**系统**"，展开 " **CurrentControlSet**"，展开 "**服务**"，然后展开 " **Tcpip**"。</span><span class="sxs-lookup"><span data-stu-id="f79f5-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="f79f5-p124">如果没有看到标记为“QoS”\*\*\*\* 的注册表项，则右键单击“Tcpip”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“项”\*\*\*\*。创建新项后，键入“QoS”\*\*\*\*，然后按 Enter 键来重命名该项。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p124">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**. After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="f79f5-p125">右键单击“QoS”\*\*\*\*，指向“新建”\*\*\*\*，然后单击“字符串值”\*\*\*\*。在创建新的注册表值之后，键入“不使用 NLA”\*\*\*\*，然后按 Enter 键以重命名值。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="f79f5-p126">双击“不使用 NLA”\*\*\*\*。在“编辑字符串”\*\*\*\* 对话框的“数值数据”\*\*\*\* 框中，键入“1”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f79f5-p126">Double-click **Do not use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="f79f5-194">创建并配置新注册表值后，将需要重新启动计算机才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="f79f5-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

