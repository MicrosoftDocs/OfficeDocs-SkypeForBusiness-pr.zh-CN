---
title: 在 Microsoft Teams 客户端中实施服务质量
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 实现 Microsoft 团队客户端服务质量 (QoS)。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1f80ede0432c3666a1974b1e0c8d7fa3dc2bbfc
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408264"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="70357-103">设置 Windows 客户端上的 QoS</span><span class="sxs-lookup"><span data-stu-id="70357-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="70357-104">您可以使用基于策略的 QoS 组策略中设置团队客户端中的预定义的 DSCP 值的源端口范围。</span><span class="sxs-lookup"><span data-stu-id="70357-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="70357-105">下表中指定的端口范围是要创建的每个工作负荷策略的起始点。</span><span class="sxs-lookup"><span data-stu-id="70357-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="70357-106">_建议初始端口范围_</span><span class="sxs-lookup"><span data-stu-id="70357-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="70357-107">媒体通信类型</span><span class="sxs-lookup"><span data-stu-id="70357-107">Media traffic type</span></span>| <span data-ttu-id="70357-108">客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="70357-108">Client source port range</span></span> |<span data-ttu-id="70357-109">协议</span><span class="sxs-lookup"><span data-stu-id="70357-109">Protocol</span></span>|<span data-ttu-id="70357-110">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="70357-110">DSCP value</span></span>|<span data-ttu-id="70357-111">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="70357-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="70357-112">音频</span><span class="sxs-lookup"><span data-stu-id="70357-112">Audio</span></span>| <span data-ttu-id="70357-113">50000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="70357-113">50,000–50,019</span></span>|<span data-ttu-id="70357-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="70357-114">TCP/UDP</span></span>|<span data-ttu-id="70357-115">46</span><span class="sxs-lookup"><span data-stu-id="70357-115">46</span></span>|<span data-ttu-id="70357-116">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="70357-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="70357-117">视频</span><span class="sxs-lookup"><span data-stu-id="70357-117">Video</span></span>| <span data-ttu-id="70357-118">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="70357-118">50,020–50,039</span></span>|<span data-ttu-id="70357-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="70357-119">TCP/UDP</span></span>|<span data-ttu-id="70357-120">34</span><span class="sxs-lookup"><span data-stu-id="70357-120">34</span></span>|<span data-ttu-id="70357-121">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="70357-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="70357-122">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="70357-122">Application/Screen Sharing</span></span>| <span data-ttu-id="70357-123">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="70357-123">50,040–50,059</span></span>|<span data-ttu-id="70357-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="70357-124">TCP/UDP</span></span>|<span data-ttu-id="70357-125">18</span><span class="sxs-lookup"><span data-stu-id="70357-125">18</span></span>|<span data-ttu-id="70357-126">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="70357-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="70357-127">只要有可能，配置组策略对象中基于策略的 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="70357-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="70357-128">以下步骤是非常类似于[配置端口范围和客户端 Skype 业务服务器上的服务质量策略](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)，上面有可能不需要某些其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="70357-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="70357-129">若要创建的 domian 加入 Windows 10 计算机音频 QoS 策略，首次登录到计算机上安装的组策略管理。</span><span class="sxs-lookup"><span data-stu-id="70357-129">To create a QoS audio policy for domian-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="70357-130">打开组策略管理 （单击开始、 管理工具，，然后单击组策略管理），然后完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="70357-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="70357-131">在组策略管理中，找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="70357-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="70357-132">例如，如果您的所有客户端计算机位于名为**客户端**OU，应客户端 OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="70357-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="70357-133">右键单击相应的容器，然后单击**创建在这个域 GPO 并在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="70357-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="70357-134">**新建 GPO**对话框中，在**名称**框中，键入新的组策略对象的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="70357-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="70357-135">右键单击新建的策略，，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="70357-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="70357-136">在组策略管理编辑器中，展开**计算机配置**，展开**Windows 设置**、**基于策略的 QoS**，右键单击，然后单击**新建策略**。</span><span class="sxs-lookup"><span data-stu-id="70357-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="70357-137">在**基于策略的 QoS**对话框中，在打开页上，键入**名称**框中的新策略的名称。</span><span class="sxs-lookup"><span data-stu-id="70357-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="70357-138">选择**指定 DSCP 值**并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="70357-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="70357-139">保留未选择，**指定出站调节率**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="70357-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="70357-140">在下一页上，选择**仅使用此可执行文件名称的应用程序**和输入**Teams.exe**的名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="70357-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="70357-141">此设置指示要仅设置优先级团队客户端的匹配流量的策略。</span><span class="sxs-lookup"><span data-stu-id="70357-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="70357-142">在第三页上，确保同时**任何源 IP 地址**和**任何目标 IP 地址**选中，则，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="70357-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="70357-143">这两个设置确保将管理数据包而不考虑哪台计算机 （IP 地址） 发送数据包和哪台计算机 （IP 地址） 将接收数据包。</span><span class="sxs-lookup"><span data-stu-id="70357-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="70357-144">在四页中，从**选择此 QoS 策略应用于的协议**下拉列表中选择**TCP 和 UDP** 。</span><span class="sxs-lookup"><span data-stu-id="70357-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="70357-145">TCP （传输控制协议） 和 UDP （用户数据报协议） 是最常使用的两个网络协议。</span><span class="sxs-lookup"><span data-stu-id="70357-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="70357-146">在标题下**指定源端口号**，**从此源端口或范围**中进行选择。</span><span class="sxs-lookup"><span data-stu-id="70357-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="70357-147">在相应的文本框中，键入供音频传输的端口范围。</span><span class="sxs-lookup"><span data-stu-id="70357-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="70357-148">例如，如果预留端口 50000 到音频流量的端口 50019，输入使用以下格式的端口范围： **50000:50019**。</span><span class="sxs-lookup"><span data-stu-id="70357-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="70357-149">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="70357-149">Click **Finish**.</span></span>

11. <span data-ttu-id="70357-150">重复步骤 5-10，以创建策略的视频和应用程序/桌面共享，替换步骤 6 和 10 中的相应值。</span><span class="sxs-lookup"><span data-stu-id="70357-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="70357-151">已在客户端计算机上刷新组策略之前，您已创建的新策略不会生效。</span><span class="sxs-lookup"><span data-stu-id="70357-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="70357-152">虽然自己定期刷新组策略，您可以通过执行以下步骤来强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="70357-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="70357-153">在您要刷新组策略的每台计算机上打开命令控制台。</span><span class="sxs-lookup"><span data-stu-id="70357-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="70357-154">确保命令控制台设置以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="70357-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="70357-155">在命令提示符处，输入</span><span class="sxs-lookup"><span data-stu-id="70357-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="70357-156">验证 DSCP 标记中的组策略对象</span><span class="sxs-lookup"><span data-stu-id="70357-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="70357-157">若要验证已设置的组策略对象的值，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="70357-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="70357-158">打开一个命令控制台。</span><span class="sxs-lookup"><span data-stu-id="70357-158">Open a command console.</span></span> <span data-ttu-id="70357-159">确保命令控制台设置以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="70357-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="70357-160">在命令提示符处，输入：</span><span class="sxs-lookup"><span data-stu-id="70357-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="70357-161">这将生成一个报告，并将其发送到一个名为 gp.txt 文本文件。</span><span class="sxs-lookup"><span data-stu-id="70357-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="70357-162">或者，您可以输入以下命令以生成更容易阅读 HTML 报表名为 gp.html 中相同的数据：</span><span class="sxs-lookup"><span data-stu-id="70357-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="70357-163">![运行 gpresult 命令控制台窗口的屏幕截图。](media/Qos-in-Teams-Image3.png "运行 gpresult 命令控制台窗口的屏幕截图。")</span><span class="sxs-lookup"><span data-stu-id="70357-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="70357-164">在生成的文件中，查找的标题**应用组策略对象**和验证前面创建的组策略对象的名称位于应用策略的列表。</span><span class="sxs-lookup"><span data-stu-id="70357-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="70357-165">打开注册表编辑器中，并转到：</span><span class="sxs-lookup"><span data-stu-id="70357-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="70357-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="70357-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

   <span data-ttu-id="70357-167">验证表 4 中列出的注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="70357-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="70357-168">_表 4。QoS 程序的 Windows 注册表项的值_</span><span class="sxs-lookup"><span data-stu-id="70357-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="70357-169">名称</span><span class="sxs-lookup"><span data-stu-id="70357-169">Name</span></span>          |  <span data-ttu-id="70357-170">类型</span><span class="sxs-lookup"><span data-stu-id="70357-170">Type</span></span>  |    <span data-ttu-id="70357-171">数据</span><span class="sxs-lookup"><span data-stu-id="70357-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="70357-172">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="70357-172">Application Name</span></span>    | <span data-ttu-id="70357-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-173">REG_SZ</span></span> |  <span data-ttu-id="70357-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="70357-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="70357-175">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="70357-175">DSCP Value</span></span>       | <span data-ttu-id="70357-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-176">REG_SZ</span></span> |     <span data-ttu-id="70357-177">46</span><span class="sxs-lookup"><span data-stu-id="70357-177">46</span></span>      |
   |        <span data-ttu-id="70357-178">本地 IP</span><span class="sxs-lookup"><span data-stu-id="70357-178">Local IP</span></span>        | <span data-ttu-id="70357-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="70357-180">本地 IP 前缀长度</span><span class="sxs-lookup"><span data-stu-id="70357-180">Local IP Prefix Length</span></span> | <span data-ttu-id="70357-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="70357-182">本地端口</span><span class="sxs-lookup"><span data-stu-id="70357-182">Local Port</span></span>       | <span data-ttu-id="70357-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-183">REG_SZ</span></span> | <span data-ttu-id="70357-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="70357-184">50000-50019</span></span> |
   |        <span data-ttu-id="70357-185">协议</span><span class="sxs-lookup"><span data-stu-id="70357-185">Protocol</span></span>        | <span data-ttu-id="70357-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="70357-187">远程 IP</span><span class="sxs-lookup"><span data-stu-id="70357-187">Remote IP</span></span>        | <span data-ttu-id="70357-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="70357-189">远程 IP 前缀</span><span class="sxs-lookup"><span data-stu-id="70357-189">Remote IP Prefix</span></span>    | <span data-ttu-id="70357-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="70357-191">远程端口</span><span class="sxs-lookup"><span data-stu-id="70357-191">Remote Port</span></span>       | <span data-ttu-id="70357-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="70357-193">限制率</span><span class="sxs-lookup"><span data-stu-id="70357-193">Throttle Rate</span></span>      | <span data-ttu-id="70357-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="70357-194">REG_SZ</span></span> |     <span data-ttu-id="70357-195">-1</span><span class="sxs-lookup"><span data-stu-id="70357-195">-1</span></span>      |

5. <span data-ttu-id="70357-196">验证应用程序名称条目的值正确客户端使用，并确认的 DSCP 值和本地端口条目反映中的组策略对象的设置。</span><span class="sxs-lookup"><span data-stu-id="70357-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
