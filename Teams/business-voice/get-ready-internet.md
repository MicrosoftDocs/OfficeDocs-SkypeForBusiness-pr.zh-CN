---
title: 检查用于企业语音的 Internet 连接
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: d2a158f8b43b4cf58e2c5c6c4a4248488f41973d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780281"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="e05c1-102">检查用于企业语音的 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="e05c1-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="e05c1-103">企业语音随 Microsoft 365 一起位于云中。</span><span class="sxs-lookup"><span data-stu-id="e05c1-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="e05c1-104">使用 Microsoft Teams 和企业语音的每台设备都需要连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="e05c1-104">Every device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="e05c1-105">若要获得最佳的企业语音体验，你需要足够快的宽带 Internet 连接，确保能够支持你的组织可能同时拨打的最多电话数量。</span><span class="sxs-lookup"><span data-stu-id="e05c1-105">To get the best Business Voice experience, you need a broadband Internet connection that can support the maximum number of phone calls that your organization might make at any one time.</span></span> <span data-ttu-id="e05c1-106">此外，还需确保网络上的计算机可以访问 Microsoft 365 服务器。</span><span class="sxs-lookup"><span data-stu-id="e05c1-106">You also need to make sure that the computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="e05c1-107">若要执行下面的步骤，必须有一个租户包含以下订阅之一：</span><span class="sxs-lookup"><span data-stu-id="e05c1-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="e05c1-108">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="e05c1-108">Microsoft 365 Business Basic</span></span>
* <span data-ttu-id="e05c1-109">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="e05c1-109">Microsoft 365 Business Standard</span></span>
* <span data-ttu-id="e05c1-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="e05c1-110">Office 365 E1</span></span>
* <span data-ttu-id="e05c1-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="e05c1-111">Office 365 E3</span></span>
* <span data-ttu-id="e05c1-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="e05c1-112">Office 365 F1</span></span>
* <span data-ttu-id="e05c1-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="e05c1-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="e05c1-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="e05c1-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="e05c1-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="e05c1-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="e05c1-116">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="e05c1-116">Microsoft 365 Business</span></span>

<span data-ttu-id="e05c1-117">无需企业语音许可证即可执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e05c1-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="e05c1-118">检查 Internet 连接速度</span><span class="sxs-lookup"><span data-stu-id="e05c1-118">Check your Internet connection speed</span></span>

<span data-ttu-id="e05c1-119">本文将帮助你确定自己的 Internet 连接速度是否能满足大量人员拨打电话以及主持视频会议的需求。</span><span class="sxs-lookup"><span data-stu-id="e05c1-119">This article helps determine whether your Internet connection is fast enough for the number of people who need to make phone calls and host video conferences.</span></span> <span data-ttu-id="e05c1-120">通过提供有关你的组织的信息，你便会获得返回的报告，其中显示 Teams 和企业语音将使用的 Internet 连接带宽。</span><span class="sxs-lookup"><span data-stu-id="e05c1-120">You'll provide information about your organization and get back a report that shows how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="e05c1-121">收集有关 Internet 连接和用户的信息</span><span class="sxs-lookup"><span data-stu-id="e05c1-121">Gather information about your Internet connection and users</span></span>

<span data-ttu-id="e05c1-122">开始之前，你需要以下信息：</span><span class="sxs-lookup"><span data-stu-id="e05c1-122">Before you start, you need the following information:</span></span>

* <span data-ttu-id="e05c1-123">Internet 连接速度</span><span class="sxs-lookup"><span data-stu-id="e05c1-123">The speed of your Internet connection</span></span>
* <span data-ttu-id="e05c1-124">有多少人主要在办公室使用企业语音</span><span class="sxs-lookup"><span data-stu-id="e05c1-124">How many people will use Business Voice mainly from your office</span></span>
* <span data-ttu-id="e05c1-125">有多少人主要从远程位置（例如家庭办公室）使用企业语音</span><span class="sxs-lookup"><span data-stu-id="e05c1-125">How many people will use Business Voice mainly from a remote location, such as a home office</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="e05c1-126">在网络规划器中输入你的信息</span><span class="sxs-lookup"><span data-stu-id="e05c1-126">Enter your information into the network planner</span></span>

<span data-ttu-id="e05c1-127">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="e05c1-127">Follow these steps:</span></span>

1. <span data-ttu-id="e05c1-128">在浏览器中，转到 https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e05c1-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="e05c1-129">使用具有全局管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e05c1-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="e05c1-130">用于注册 Office 365 的帐户便拥有这些权限。</span><span class="sxs-lookup"><span data-stu-id="e05c1-130">The account that you used to sign up for Office 365 has these permissions.</span></span>
2. <span data-ttu-id="e05c1-131">打开“**计划**”，然后选择“**网络规划器**”。</span><span class="sxs-lookup"><span data-stu-id="e05c1-131">Open **Planning** and select **Network planner**.</span></span>
3. <span data-ttu-id="e05c1-132">在“**网络计划**”下，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="e05c1-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="e05c1-133">输入计划的名称，然后选择“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="e05c1-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="e05c1-134">网络计划应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e05c1-134">Your network plan should look like this:</span></span>

    ![网络规划器主屏幕](../media/network-planner-main.png)
1. <span data-ttu-id="e05c1-136">选择网络计划的名称。</span><span class="sxs-lookup"><span data-stu-id="e05c1-136">Select the name of your network plan.</span></span> <span data-ttu-id="e05c1-137">（即上图中的**主要办公室**。）</span><span class="sxs-lookup"><span data-stu-id="e05c1-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="e05c1-138">在下一页上，选择“**网络站点**”选项卡上的“**添加网络站点**”。</span><span class="sxs-lookup"><span data-stu-id="e05c1-138">On the next page, select **Add a network site** on the **Network sites** tab.</span></span>
3. <span data-ttu-id="e05c1-139">仅填写以下屏幕截图中所示的字段，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e05c1-139">Fill in only the fields that are indicated in the following screenshot, and then select **Save**.</span></span> <span data-ttu-id="e05c1-140">将此屏幕上的其他字段留空，不要选择“**ExpressRoute**”或“**已连接到 WAN**”选项。</span><span class="sxs-lookup"><span data-stu-id="e05c1-140">Leave the other fields on this screen blank, and don't select the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![网络规划器站点信息](../media/network-planner-site-info.png)
1. <span data-ttu-id="e05c1-142">在“**报告**”选项卡上，选择“**启动报告**”。</span><span class="sxs-lookup"><span data-stu-id="e05c1-142">On the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="e05c1-143">输入以下信息，然后选择“**生成报告**”，从而创建一份显示 Teams 带宽要求的报告。</span><span class="sxs-lookup"><span data-stu-id="e05c1-143">Enter the following information, and then select **Generate report** to create a report that shows the bandwidth requirements for Teams.</span></span> <span data-ttu-id="e05c1-144">我们将在下一节中介绍如何阅读该报告。</span><span class="sxs-lookup"><span data-stu-id="e05c1-144">We show you how to read the report in the next section.</span></span>

    ![网络规划器报告信息](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="e05c1-146">查找最低的 Internet 连接速度</span><span class="sxs-lookup"><span data-stu-id="e05c1-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="e05c1-147">选择“**生成报告**”时，Office 365 将创建如下所示的报告：</span><span class="sxs-lookup"><span data-stu-id="e05c1-147">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![网络规划器报告详细信息](../media/network-planner-report.png)

<span data-ttu-id="e05c1-149">突出显示的数字显示了 Teams 和企业语音将使用的 Internet 连接带宽。</span><span class="sxs-lookup"><span data-stu-id="e05c1-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="e05c1-150">建议该数字不超过 Internet 总连接速度的 30%。</span><span class="sxs-lookup"><span data-stu-id="e05c1-150">We recommend that this number is no more than 30 percent of your total Internet connection speed.</span></span> <span data-ttu-id="e05c1-151">例如，如果 Internet 连接速度是 60 Mbps，则 Teams 和企业语音的使用量不应超过 18 Mbps。</span><span class="sxs-lookup"><span data-stu-id="e05c1-151">For example, if your Internet connection is 60 Mbps, Teams and Business Voice should use no more than 18 Mbps.</span></span>

<span data-ttu-id="e05c1-152">使用以下公式可以确定最低的 Internet 连接速度：*\<突出显示的数字> / 0.3*。</span><span class="sxs-lookup"><span data-stu-id="e05c1-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="e05c1-153">根据上图中突出显示的数字，计算结果为 *4.6875 / 0.3 = 15.6*。</span><span class="sxs-lookup"><span data-stu-id="e05c1-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="e05c1-154">在这种情况下，Internet 连接速度应至少为 15.6 Mbps。</span><span class="sxs-lookup"><span data-stu-id="e05c1-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="e05c1-155">如果 Teams 和企业语音的使用量将超过 Internet 总连接速度的 30%，则突出显示的数字将显示为红色。</span><span class="sxs-lookup"><span data-stu-id="e05c1-155">If Teams and Business Voice will use more than 30 percent of your total Internet connection speed, the highlighted number will appear red.</span></span> <span data-ttu-id="e05c1-156">在这种情况下，可能需要升级 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="e05c1-156">In that case, you may need to upgrade your Internet connection.</span></span>

![连接速度警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="e05c1-158">确保网络上的计算机和设备可以访问 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e05c1-158">Make sure the computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="e05c1-159">使用企业语音的计算机和设备必须使用特定的网络端口与 Microsoft 365 服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="e05c1-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="e05c1-160">这些端口本质上是一种“门”；设备通过这个门在网络或 Internet 上互相通信。</span><span class="sxs-lookup"><span data-stu-id="e05c1-160">These ports are essentially doors through which devices talk to each other over a network or the Internet.</span></span> <span data-ttu-id="e05c1-161">你的防火墙需要允许网络上的设备通过下列*出站*网络端口访问 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="e05c1-161">Your firewall needs to allow devices on your network to reach Microsoft 365 through the following *outbound* network ports:</span></span>

* <span data-ttu-id="e05c1-162">**TCP 端口** 80 和 443</span><span class="sxs-lookup"><span data-stu-id="e05c1-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="e05c1-163">**UDP 端口** 3478、3479、3480 和 3481</span><span class="sxs-lookup"><span data-stu-id="e05c1-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="e05c1-164">检查防火墙是否允许在这些网络端口上进行通信的最简单方法是在 Teams 中进行测试呼叫：</span><span class="sxs-lookup"><span data-stu-id="e05c1-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call in Teams:</span></span>

1. <span data-ttu-id="e05c1-165">在网络上的计算机上转到 https://aka.ms/getteams 并安装 Teams。</span><span class="sxs-lookup"><span data-stu-id="e05c1-165">Go to https://aka.ms/getteams on a computer on your network and install Teams.</span></span> <span data-ttu-id="e05c1-166">请确保计算机有扬声器和麦克风。</span><span class="sxs-lookup"><span data-stu-id="e05c1-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="e05c1-167">打开 Teams 并使用 Microsoft 365 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e05c1-167">Open Teams and sign in by using a Microsoft 365 account.</span></span>
3. <span data-ttu-id="e05c1-168">在 Teams 中，选择你的个人资料图片，然后转到“**设置**” > “**设备**”。</span><span class="sxs-lookup"><span data-stu-id="e05c1-168">In Teams, select your profile picture, and then go to **Settings** > **Devices**.</span></span>
4. <span data-ttu-id="e05c1-169">在“**音频设备**”下，选择“**进行测试呼叫**”。</span><span class="sxs-lookup"><span data-stu-id="e05c1-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="e05c1-170">按照相关步骤留言，然后回放给你自己听。</span><span class="sxs-lookup"><span data-stu-id="e05c1-170">Follow the steps to leave a message and have it played back to you.</span></span>

   * <span data-ttu-id="e05c1-171">如果呼叫已接通，并且可以听到自己的留言，则表示你的防火墙已正确设置。</span><span class="sxs-lookup"><span data-stu-id="e05c1-171">If the call connects and you hear your message, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="e05c1-172">如果呼叫已接通，但无法听到语音指示或留言，请确保已正确设置扬声器和麦克风，然后重试。</span><span class="sxs-lookup"><span data-stu-id="e05c1-172">If the call connects, but you can't hear the instructions or your message, make sure that your speakers and microphone are set up correctly, and then try again.</span></span>
   * <span data-ttu-id="e05c1-173">如果呼叫未接通，或已经接通但无法听到留言，则可能需要更新防火墙，以便允许访问所需的网络端口。</span><span class="sxs-lookup"><span data-stu-id="e05c1-173">If the call doesn't connect or it connects but you can't hear your message, you might need to update your firewall to allow access to the required network ports.</span></span> <span data-ttu-id="e05c1-174">请查看防火墙的文档，或联系 IT 专家获取帮助。</span><span class="sxs-lookup"><span data-stu-id="e05c1-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="e05c1-175">如果你是 IT 专业人员，想要详细了解如何准备大型或更复杂的网络来支持企业语音，请查看[评估环境](../3-envision-evaluate-my-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="e05c1-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, see [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="e05c1-176">这篇文章提供了有关带宽、代理和防火墙要求的信息，还介绍了如何使用[网络评估工具](../3-envision-evaluate-my-environment.md#test-the-network)来测试网络。</span><span class="sxs-lookup"><span data-stu-id="e05c1-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

