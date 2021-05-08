---
title: 在客户端中实现服务质量 (QoS) Microsoft Teams服务
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何使用服务质量 (QoS) 优化桌面客户端Microsoft Teams网络流量。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094780"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="4b88e-103">在客户端中实现服务质量 (QoS) Microsoft Teams服务</span><span class="sxs-lookup"><span data-stu-id="4b88e-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="4b88e-104">可以在组策略内使用基于策略的服务质量 (QoS) ，为 Teams 客户端中的预定义 DSCP 值设置源端口范围。</span><span class="sxs-lookup"><span data-stu-id="4b88e-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="4b88e-105">下表中指定的端口范围是为每个工作负荷创建策略的起点。</span><span class="sxs-lookup"><span data-stu-id="4b88e-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="4b88e-106">*表 1.建议的初始端口范围*</span><span class="sxs-lookup"><span data-stu-id="4b88e-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="4b88e-107">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="4b88e-107">Media traffic type</span></span>| <span data-ttu-id="4b88e-108">客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="4b88e-108">Client source port range</span></span> |<span data-ttu-id="4b88e-109">协议</span><span class="sxs-lookup"><span data-stu-id="4b88e-109">Protocol</span></span>|<span data-ttu-id="4b88e-110">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="4b88e-110">DSCP value</span></span>|<span data-ttu-id="4b88e-111">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="4b88e-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="4b88e-112">音频</span><span class="sxs-lookup"><span data-stu-id="4b88e-112">Audio</span></span>| <span data-ttu-id="4b88e-113">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="4b88e-113">50,000–50,019</span></span>|<span data-ttu-id="4b88e-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="4b88e-114">TCP/UDP</span></span>|<span data-ttu-id="4b88e-115">46</span><span class="sxs-lookup"><span data-stu-id="4b88e-115">46</span></span>|<span data-ttu-id="4b88e-116">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="4b88e-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="4b88e-117">视频</span><span class="sxs-lookup"><span data-stu-id="4b88e-117">Video</span></span>| <span data-ttu-id="4b88e-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="4b88e-118">50,020–50,039</span></span>|<span data-ttu-id="4b88e-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="4b88e-119">TCP/UDP</span></span>|<span data-ttu-id="4b88e-120">34</span><span class="sxs-lookup"><span data-stu-id="4b88e-120">34</span></span>|<span data-ttu-id="4b88e-121">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="4b88e-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="4b88e-122">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="4b88e-122">Application/Screen Sharing</span></span>| <span data-ttu-id="4b88e-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="4b88e-123">50,040–50,059</span></span>|<span data-ttu-id="4b88e-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="4b88e-124">TCP/UDP</span></span>|<span data-ttu-id="4b88e-125">18</span><span class="sxs-lookup"><span data-stu-id="4b88e-125">18</span></span>|<span data-ttu-id="4b88e-126">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="4b88e-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="4b88e-127">尽可能在组策略对象中配置基于策略的 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="4b88e-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="4b88e-128">以下步骤非常类似于在 Skype for Business Server[](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)上为客户端配置端口范围和服务质量策略，该策略具有一些可能不需要的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b88e-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="4b88e-129">若要为已加入域的计算机Windows 10 QoS 音频策略，请首先登录到已安装组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="4b88e-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="4b88e-130">打开"组策略管理 (单击"开始"，指向"管理工具"，并单击"组策略管理") ，然后完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4b88e-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="4b88e-131">在"组策略管理"中，找到应创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="4b88e-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="4b88e-132">例如，如果所有客户端计算机都位于名为 **"** 客户端"的 OU 中，应在"客户端 OU"中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="4b88e-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="4b88e-133">右键单击相应的容器，并单击"在此域中创建 **GPO"，并在此处链接它**。</span><span class="sxs-lookup"><span data-stu-id="4b88e-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="4b88e-134">在"**新建 GPO"** 对话框中的"名称"框中键入新组策略 **对象的名称，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="4b88e-135">右键单击新建的策略，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="4b88e-136">在组策略管理编辑器中，展开"**计算机** 配置"，展开Windows 设置，右键单击"基于策略的 **QoS"，** 然后单击"**创建新策略"。** </span><span class="sxs-lookup"><span data-stu-id="4b88e-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="4b88e-137">在" **基于策略的 QoS"** 对话框的打开页上，在"名称"框中键入新 **策略** 的名称。</span><span class="sxs-lookup"><span data-stu-id="4b88e-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="4b88e-138">选择 **"指定 DSCP 值**"，将值设置为 **46。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="4b88e-139">将 **"指定出站限制速率"** 保留未选择，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="4b88e-140">下一页上，选择"**仅具有此可执行文件** 名称的应用程序"，Teams.exe **名称，** 然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="4b88e-141">此设置指示策略仅优先处理来自客户端的Teams流量。</span><span class="sxs-lookup"><span data-stu-id="4b88e-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="4b88e-142">第三页上，确保同时选中"任何 **源 IP** 地址"和"任何 **目标 IP** 地址"，并单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="4b88e-143">这两个设置可确保无论哪个计算机 (IP 地址) 数据包，以及哪个计算机 (IP 地址) 数据包都将进行管理。</span><span class="sxs-lookup"><span data-stu-id="4b88e-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="4b88e-144">在"第 4 页"的"**选择此 QoS** 策略应用于的协议"下拉列表中选择"TCP 和 **UDP"。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="4b88e-145">TCP (传输控制协议) UDP (用户数据报协议) 是最常用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="4b88e-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="4b88e-146">在标题"**指定源端口号"下**，选择 **"从此源端口或范围"。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="4b88e-147">在随附的文本框中，键入为音频传输保留的端口范围。</span><span class="sxs-lookup"><span data-stu-id="4b88e-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="4b88e-148">例如，如果通过音频流量的端口 50019 保留端口 50000，则使用此格式输入端口范围 **：50000：50019。**</span><span class="sxs-lookup"><span data-stu-id="4b88e-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="4b88e-149">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4b88e-149">Click **Finish**.</span></span>

1. <span data-ttu-id="4b88e-150">重复步骤 5-10，为视频和应用程序/桌面共享创建策略，用步骤 6 和 10 中的相应值进行表示。</span><span class="sxs-lookup"><span data-stu-id="4b88e-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="4b88e-151">在客户端计算机上刷新组策略之前，已创建的新策略不会生效。</span><span class="sxs-lookup"><span data-stu-id="4b88e-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="4b88e-152">尽管组策略会定期自行刷新，但可以通过执行以下步骤来强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="4b88e-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="4b88e-153">在要刷新组策略的每台计算机中，以管理员角色打开命令提示符 (以管理员) 。 </span><span class="sxs-lookup"><span data-stu-id="4b88e-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="4b88e-154">在命令提示符下，输入</span><span class="sxs-lookup"><span data-stu-id="4b88e-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="4b88e-155">验证组策略对象中的 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="4b88e-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="4b88e-156">若要验证组策略对象中的值是否已设置，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4b88e-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="4b88e-157">以管理员角色打开命令提示符 (*以管理员角色运行) 。*</span><span class="sxs-lookup"><span data-stu-id="4b88e-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="4b88e-158">在命令提示符下，输入</span><span class="sxs-lookup"><span data-stu-id="4b88e-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="4b88e-159">这会生成应用 GPO 的报告，并将其发送到名为gp.txt *的文本文件*。</span><span class="sxs-lookup"><span data-stu-id="4b88e-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="4b88e-160">对于名为gp.htm *l 的* 更具可读性的 HTML 报表，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="4b88e-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="4b88e-161">在生成的文件中，查找标题"已应用组 **策略** 对象"，并验证之前创建的组策略对象的名称是否在应用的策略列表中。</span><span class="sxs-lookup"><span data-stu-id="4b88e-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="4b88e-162">打开注册表编辑器，然后转到</span><span class="sxs-lookup"><span data-stu-id="4b88e-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="4b88e-163">HKEY \_ 本地 \_ 计算机 \\ 软件策略 Microsoft Windows \\ \\ \\ \\ QoS</span><span class="sxs-lookup"><span data-stu-id="4b88e-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="4b88e-164">验证表 2 中列出的注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="4b88e-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="4b88e-165">*表 2.QoS Windows注册表项的值*</span><span class="sxs-lookup"><span data-stu-id="4b88e-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="4b88e-166">名称</span><span class="sxs-lookup"><span data-stu-id="4b88e-166">Name</span></span>          |  <span data-ttu-id="4b88e-167">类型</span><span class="sxs-lookup"><span data-stu-id="4b88e-167">Type</span></span>  |    <span data-ttu-id="4b88e-168">数据</span><span class="sxs-lookup"><span data-stu-id="4b88e-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="4b88e-169">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="4b88e-169">Application Name</span></span>    | <span data-ttu-id="4b88e-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-170">REG_SZ</span></span> |  <span data-ttu-id="4b88e-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="4b88e-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="4b88e-172">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="4b88e-172">DSCP Value</span></span>       | <span data-ttu-id="4b88e-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-173">REG_SZ</span></span> |     <span data-ttu-id="4b88e-174">46</span><span class="sxs-lookup"><span data-stu-id="4b88e-174">46</span></span>      |
   |        <span data-ttu-id="4b88e-175">本地 IP</span><span class="sxs-lookup"><span data-stu-id="4b88e-175">Local IP</span></span>        | <span data-ttu-id="4b88e-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="4b88e-177">本地 IP 前缀长度</span><span class="sxs-lookup"><span data-stu-id="4b88e-177">Local IP Prefix Length</span></span> | <span data-ttu-id="4b88e-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="4b88e-179">本地端口</span><span class="sxs-lookup"><span data-stu-id="4b88e-179">Local Port</span></span>       | <span data-ttu-id="4b88e-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-180">REG_SZ</span></span> | <span data-ttu-id="4b88e-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="4b88e-181">50000-50019</span></span> |
   |        <span data-ttu-id="4b88e-182">协议</span><span class="sxs-lookup"><span data-stu-id="4b88e-182">Protocol</span></span>        | <span data-ttu-id="4b88e-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="4b88e-184">远程 IP</span><span class="sxs-lookup"><span data-stu-id="4b88e-184">Remote IP</span></span>        | <span data-ttu-id="4b88e-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="4b88e-186">远程 IP 前缀</span><span class="sxs-lookup"><span data-stu-id="4b88e-186">Remote IP Prefix</span></span>    | <span data-ttu-id="4b88e-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="4b88e-188">远程端口</span><span class="sxs-lookup"><span data-stu-id="4b88e-188">Remote Port</span></span>       | <span data-ttu-id="4b88e-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="4b88e-190">限制率</span><span class="sxs-lookup"><span data-stu-id="4b88e-190">Throttle Rate</span></span>      | <span data-ttu-id="4b88e-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="4b88e-191">REG_SZ</span></span> |     <span data-ttu-id="4b88e-192">-1</span><span class="sxs-lookup"><span data-stu-id="4b88e-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="4b88e-193">验证"应用程序名称"条目的值是否适用于使用的客户端，并验证 DSCP 值和本地端口条目是否反映组策略对象中的设置。</span><span class="sxs-lookup"><span data-stu-id="4b88e-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4b88e-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="4b88e-194">Related topics</span></span>

[<span data-ttu-id="4b88e-195">在 Teams 中 (QoS) 服务质量Teams</span><span class="sxs-lookup"><span data-stu-id="4b88e-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)