---
title: '在 Microsoft 团队客户端中实施服务质量 (QoS) '
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何使用服务质量 (QoS) 优化 Microsoft 团队桌面客户端的网络流量。
ms.custom: seo-marvel-mar2020
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77f1754277cfeacd31de28dcee089a8f97991c87
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583681"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="81b7e-103">在 Microsoft 团队客户端中实施服务质量 (QoS) </span><span class="sxs-lookup"><span data-stu-id="81b7e-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="81b7e-104">你可以使用组策略中的基于策略的服务质量 (QoS) 设置团队客户端中预定义 DSCP 值的源端口范围。</span><span class="sxs-lookup"><span data-stu-id="81b7e-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="81b7e-105">下表中指定的端口范围是为每个工作负荷创建策略的起始点。</span><span class="sxs-lookup"><span data-stu-id="81b7e-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="81b7e-106">*表1。推荐的初始端口范围*</span><span class="sxs-lookup"><span data-stu-id="81b7e-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="81b7e-107">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="81b7e-107">Media traffic type</span></span>| <span data-ttu-id="81b7e-108">客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="81b7e-108">Client source port range</span></span> |<span data-ttu-id="81b7e-109">协议</span><span class="sxs-lookup"><span data-stu-id="81b7e-109">Protocol</span></span>|<span data-ttu-id="81b7e-110">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="81b7e-110">DSCP value</span></span>|<span data-ttu-id="81b7e-111">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="81b7e-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="81b7e-112">音频</span><span class="sxs-lookup"><span data-stu-id="81b7e-112">Audio</span></span>| <span data-ttu-id="81b7e-113">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="81b7e-113">50,000–50,019</span></span>|<span data-ttu-id="81b7e-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="81b7e-114">TCP/UDP</span></span>|<span data-ttu-id="81b7e-115">46</span><span class="sxs-lookup"><span data-stu-id="81b7e-115">46</span></span>|<span data-ttu-id="81b7e-116">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="81b7e-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="81b7e-117">视频</span><span class="sxs-lookup"><span data-stu-id="81b7e-117">Video</span></span>| <span data-ttu-id="81b7e-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="81b7e-118">50,020–50,039</span></span>|<span data-ttu-id="81b7e-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="81b7e-119">TCP/UDP</span></span>|<span data-ttu-id="81b7e-120">34</span><span class="sxs-lookup"><span data-stu-id="81b7e-120">34</span></span>|<span data-ttu-id="81b7e-121">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="81b7e-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="81b7e-122">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="81b7e-122">Application/Screen Sharing</span></span>| <span data-ttu-id="81b7e-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="81b7e-123">50,040–50,059</span></span>|<span data-ttu-id="81b7e-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="81b7e-124">TCP/UDP</span></span>|<span data-ttu-id="81b7e-125">18</span><span class="sxs-lookup"><span data-stu-id="81b7e-125">18</span></span>|<span data-ttu-id="81b7e-126">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="81b7e-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="81b7e-127">只要有可能，就会在组策略对象中配置基于策略的 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="81b7e-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="81b7e-128">以下步骤与[在 Skype for Business 服务器上配置客户端的端口范围和服务质量策略](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)非常相似，这种情况下可能不需要其他一些详细信息。</span><span class="sxs-lookup"><span data-stu-id="81b7e-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="81b7e-129">若要为加入域的 Windows 10 计算机创建 QoS 音频策略，请首先登录到已安装了组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="81b7e-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="81b7e-130">打开组策略管理 (单击 "开始"，指向 "管理工具"，然后单击 "组策略管理) "，然后完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="81b7e-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="81b7e-131">在 "组策略管理" 中，找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="81b7e-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="81b7e-132">例如，如果所有客户端计算机都位于一个名为 "**客户端**" 的 OU 中，则应在客户端 OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="81b7e-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="81b7e-133">右键单击相应的容器，然后单击 "**在此域中创建 GPO"，然后在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="81b7e-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="81b7e-134">在 "**新建 GPO** " 对话框中，在 "**名称**" 框中键入新组策略对象的名称，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="81b7e-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="81b7e-135">右键单击新创建的策略，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="81b7e-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="81b7e-136">在组策略管理编辑器中，展开 "**计算机配置**"，展开 " **Windows 设置**"，右键单击 "**基于策略的 QoS**"，然后单击 "**创建新策略**"。</span><span class="sxs-lookup"><span data-stu-id="81b7e-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="81b7e-137">在 "**基于策略的 QoS** " 对话框中的 "开始" 页面上，在 "**名称**" 框中键入新策略的名称。</span><span class="sxs-lookup"><span data-stu-id="81b7e-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="81b7e-138">选择 "**指定 DSCP 值**" 并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="81b7e-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="81b7e-139">"退出"**指定出站阻止率**未选中，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="81b7e-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="81b7e-140">在下一页上，选择 "**仅限具有此可执行名称的应用程序**" 并输入**Teams.exe**的名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="81b7e-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="81b7e-141">此设置指示策略仅优先考虑团队客户端的匹配流量。</span><span class="sxs-lookup"><span data-stu-id="81b7e-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="81b7e-142">在第三页上，确保选中了 "**任何来源 ip 地址**" 和 "**任何目标 ip 地址**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="81b7e-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="81b7e-143">这两个设置确保数据包将被管理，无论哪台计算机 (IP 地址) 发送数据包以及哪台计算机 (IP 地址) 将接收这些数据包。</span><span class="sxs-lookup"><span data-stu-id="81b7e-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="81b7e-144">在第4页上，从 "**选择此 QoS 策略应用**于的协议" 下拉列表中选择 " **TCP 和 UDP** "。</span><span class="sxs-lookup"><span data-stu-id="81b7e-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="81b7e-145">TCP (传输控制协议) 和 UDP (用户数据报协议) 是最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="81b7e-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="81b7e-146">在 "标题" 下，**指定源端口号**，选择 "**从此源端口或范围**"。</span><span class="sxs-lookup"><span data-stu-id="81b7e-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="81b7e-147">在 "随附文本" 框中，键入为音频传输保留的端口范围。</span><span class="sxs-lookup"><span data-stu-id="81b7e-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="81b7e-148">例如，如果您通过端口50019为音频流量保留了端口50000，请使用以下格式输入端口范围： **50000:50019**。</span><span class="sxs-lookup"><span data-stu-id="81b7e-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="81b7e-149">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="81b7e-149">Click **Finish**.</span></span>

1. <span data-ttu-id="81b7e-150">重复步骤5-10 以创建视频和应用程序/桌面共享的策略，在步骤6和10中替换相应的值。</span><span class="sxs-lookup"><span data-stu-id="81b7e-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="81b7e-151">在客户端计算机上刷新组策略之前，你创建的新策略不会生效。</span><span class="sxs-lookup"><span data-stu-id="81b7e-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="81b7e-152">虽然组策略定期定期刷新，但你可以通过执行以下步骤强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="81b7e-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="81b7e-153">在要刷新组策略的每台计算机上，以管理员身份打开命令提示符， (以*管理员身份运行*) 。</span><span class="sxs-lookup"><span data-stu-id="81b7e-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="81b7e-154">在命令提示符处，输入</span><span class="sxs-lookup"><span data-stu-id="81b7e-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="81b7e-155">验证组策略对象中的 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="81b7e-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="81b7e-156">若要验证是否已设置组策略对象中的值，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="81b7e-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="81b7e-157">以管理员身份打开命令提示符， (以*管理员身份运行*) 。</span><span class="sxs-lookup"><span data-stu-id="81b7e-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="81b7e-158">在命令提示符处，输入</span><span class="sxs-lookup"><span data-stu-id="81b7e-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="81b7e-159">这将生成已应用 Gpo 的报表，并将其发送到名为*gp.txt*的文本文件。</span><span class="sxs-lookup"><span data-stu-id="81b7e-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="81b7e-160">对于名为*gp.html*的更具可读性的 HTML 报表，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="81b7e-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="81b7e-161">在生成的文件中，查找标题**应用的组策略对象**，并验证之前创建的组策略对象的名称是否在已应用的策略列表中。</span><span class="sxs-lookup"><span data-stu-id="81b7e-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="81b7e-162">打开注册表编辑器，然后转到</span><span class="sxs-lookup"><span data-stu-id="81b7e-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="81b7e-163">\_ \_ \\ \\ \\ Microsoft \\ Windows \\ QoS HKEY 本地计算机软件策略</span><span class="sxs-lookup"><span data-stu-id="81b7e-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="81b7e-164">验证表2中列出的注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="81b7e-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="81b7e-165">*表2。QoS 的 Windows 注册表项的值*</span><span class="sxs-lookup"><span data-stu-id="81b7e-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="81b7e-166">名称</span><span class="sxs-lookup"><span data-stu-id="81b7e-166">Name</span></span>          |  <span data-ttu-id="81b7e-167">类型</span><span class="sxs-lookup"><span data-stu-id="81b7e-167">Type</span></span>  |    <span data-ttu-id="81b7e-168">数据</span><span class="sxs-lookup"><span data-stu-id="81b7e-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="81b7e-169">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="81b7e-169">Application Name</span></span>    | <span data-ttu-id="81b7e-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-170">REG_SZ</span></span> |  <span data-ttu-id="81b7e-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="81b7e-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="81b7e-172">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="81b7e-172">DSCP Value</span></span>       | <span data-ttu-id="81b7e-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-173">REG_SZ</span></span> |     <span data-ttu-id="81b7e-174">46</span><span class="sxs-lookup"><span data-stu-id="81b7e-174">46</span></span>      |
   |        <span data-ttu-id="81b7e-175">本地 IP</span><span class="sxs-lookup"><span data-stu-id="81b7e-175">Local IP</span></span>        | <span data-ttu-id="81b7e-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="81b7e-177">本地 IP 前缀长度</span><span class="sxs-lookup"><span data-stu-id="81b7e-177">Local IP Prefix Length</span></span> | <span data-ttu-id="81b7e-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="81b7e-179">本地端口</span><span class="sxs-lookup"><span data-stu-id="81b7e-179">Local Port</span></span>       | <span data-ttu-id="81b7e-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-180">REG_SZ</span></span> | <span data-ttu-id="81b7e-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="81b7e-181">50000-50019</span></span> |
   |        <span data-ttu-id="81b7e-182">协议</span><span class="sxs-lookup"><span data-stu-id="81b7e-182">Protocol</span></span>        | <span data-ttu-id="81b7e-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="81b7e-184">远程 IP</span><span class="sxs-lookup"><span data-stu-id="81b7e-184">Remote IP</span></span>        | <span data-ttu-id="81b7e-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="81b7e-186">远程 IP 前缀</span><span class="sxs-lookup"><span data-stu-id="81b7e-186">Remote IP Prefix</span></span>    | <span data-ttu-id="81b7e-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="81b7e-188">远程端口</span><span class="sxs-lookup"><span data-stu-id="81b7e-188">Remote Port</span></span>       | <span data-ttu-id="81b7e-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="81b7e-190">限制率</span><span class="sxs-lookup"><span data-stu-id="81b7e-190">Throttle Rate</span></span>      | <span data-ttu-id="81b7e-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="81b7e-191">REG_SZ</span></span> |     <span data-ttu-id="81b7e-192">-1</span><span class="sxs-lookup"><span data-stu-id="81b7e-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="81b7e-193">验证应用程序名称条目的值对于你正在使用的客户端是否正确，并验证 DSCP 值和本地端口条目是否反映了组策略对象中的设置。</span><span class="sxs-lookup"><span data-stu-id="81b7e-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="81b7e-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="81b7e-194">Related topics</span></span>

[<span data-ttu-id="81b7e-195">在团队中实施服务质量 (QoS) </span><span class="sxs-lookup"><span data-stu-id="81b7e-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)