---
title: 检查 Internet 连接。
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653548"
---
# <a name="check-your-internet-connection"></a><span data-ttu-id="13b9a-102">检查 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="13b9a-102">Check your Internet connection</span></span>

<span data-ttu-id="13b9a-103">企业语音随 Microsoft 365 一起位于云中。</span><span class="sxs-lookup"><span data-stu-id="13b9a-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="13b9a-104">使用 Microsoft Teams 和企业语音的每台计算机和设备都需要连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="13b9a-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span> <span data-ttu-id="13b9a-105">若要获得最佳的企业语音体验，你需要足够快的宽带 Internet 连接，确保能够支持所需的并发电话呼叫数量。</span><span class="sxs-lookup"><span data-stu-id="13b9a-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="13b9a-106">此外，还需确保网络上的计算机可以访问 Microsoft 365 服务器。</span><span class="sxs-lookup"><span data-stu-id="13b9a-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="13b9a-107">若要执行下面的步骤，必须有一个租户包含以下订阅之一：</span><span class="sxs-lookup"><span data-stu-id="13b9a-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="13b9a-108">Office 365 商业协作版</span><span class="sxs-lookup"><span data-stu-id="13b9a-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="13b9a-109">Office 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="13b9a-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="13b9a-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="13b9a-110">Office 365 E1</span></span>
* <span data-ttu-id="13b9a-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="13b9a-111">Office 365 E3</span></span>
* <span data-ttu-id="13b9a-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="13b9a-112">Office 365 F1</span></span>
* <span data-ttu-id="13b9a-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="13b9a-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="13b9a-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="13b9a-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="13b9a-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="13b9a-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="13b9a-116">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="13b9a-116">Microsoft 365 Business</span></span>

<span data-ttu-id="13b9a-117">无需企业语音许可证即可执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="13b9a-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="13b9a-118">检查 Internet 连接速度</span><span class="sxs-lookup"><span data-stu-id="13b9a-118">Check your Internet connection speed</span></span>

<span data-ttu-id="13b9a-119">本文将帮助你确定自己的 Internet 连接速度是否能满足大量人员打电话、主持视频会议等的需求。</span><span class="sxs-lookup"><span data-stu-id="13b9a-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="13b9a-120">你需要输入有关你的组织的一些信息，然后便会获得返回的一个报告，其中包含 Teams 和企业语音将使用的 Internet 连接带宽。</span><span class="sxs-lookup"><span data-stu-id="13b9a-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="get-information-about-your-internet-connection-and-users"></a><span data-ttu-id="13b9a-121">获取有关 Internet 连接和用户的信息</span><span class="sxs-lookup"><span data-stu-id="13b9a-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="13b9a-122">开始之前，你需要了解以下信息：</span><span class="sxs-lookup"><span data-stu-id="13b9a-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="13b9a-123">Internet 连接速度。</span><span class="sxs-lookup"><span data-stu-id="13b9a-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="13b9a-124">有多少人主要在办公室使用企业语音。</span><span class="sxs-lookup"><span data-stu-id="13b9a-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="13b9a-125">有多少人主要从远程位置（例如家庭办公室）使用企业语音。</span><span class="sxs-lookup"><span data-stu-id="13b9a-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="13b9a-126">在网络规划器中输入你的信息</span><span class="sxs-lookup"><span data-stu-id="13b9a-126">Enter your information into the network planner</span></span>

<span data-ttu-id="13b9a-127">下面是需要完成的操作：</span><span class="sxs-lookup"><span data-stu-id="13b9a-127">Here's what you need to do:</span></span>

1. <span data-ttu-id="13b9a-128">打开浏览器，转到 https://admin.teams.microsoft.com，然后使用拥有全局管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="13b9a-128">Open a browser and go to https://admin.teams.microsoft.com and sign in with an account that has Global Administrator permissions.</span></span> <span data-ttu-id="13b9a-129">用于注册 Office 365 的帐户便拥有这些权限。</span><span class="sxs-lookup"><span data-stu-id="13b9a-129">The account you used to sign up for Office 365 has these permissions.</span></span>
1. <span data-ttu-id="13b9a-130">打开“计划”\*\*\*\*，然后选择“网络规划器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b9a-130">Open **Org-wide settings** and then select **Network planner**.</span></span>
1. <span data-ttu-id="13b9a-131">在“**网络计划**”下，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="13b9a-131">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="13b9a-132">为你的计划命名，然后选择“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="13b9a-132">Give your plan a name, and then select **Apply**.</span></span> <span data-ttu-id="13b9a-133">网络计划应如下所示：</span><span class="sxs-lookup"><span data-stu-id="13b9a-133">Your network plan should look like this:</span></span>

    ![网络规划器主屏幕](../media/network-planner-main.png)
1. <span data-ttu-id="13b9a-135">单击网络计划的名称（上图中的“**主要办公室**”）。</span><span class="sxs-lookup"><span data-stu-id="13b9a-135">Click on your network plan's name (**Main office** in the picture above).</span></span>
1. <span data-ttu-id="13b9a-136">在下一页上，选择“**网络站点**”选项卡下的“**添加网络站点**”。</span><span class="sxs-lookup"><span data-stu-id="13b9a-136">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
1. <span data-ttu-id="13b9a-137">仅填写以下屏幕截图中所示的字段，然后选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13b9a-137">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="13b9a-138">将此屏幕上的其他字段留空，不要选择“ExpressRoute”\*\*\*\* 或“已连接到 WAN”\*\*\*\* 选项。</span><span class="sxs-lookup"><span data-stu-id="13b9a-138">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![网络规划器站点信息](../media/network-planner-site-info.png)
1. <span data-ttu-id="13b9a-140">在“**报告**”选项卡下，选择“**启动报告**”。</span><span class="sxs-lookup"><span data-stu-id="13b9a-140">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="13b9a-141">填写以下信息，然后选择“生成报表”\*\*\*\*，创建一个显示 Teams 带宽要求的报表。</span><span class="sxs-lookup"><span data-stu-id="13b9a-141">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="13b9a-142">我们将在下一节中介绍如何阅读该报表。</span><span class="sxs-lookup"><span data-stu-id="13b9a-142">We'll show you how to read the report in the next section.</span></span>

    ![网络规划器报告信息](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="13b9a-144">查找最低的 Internet 连接速度</span><span class="sxs-lookup"><span data-stu-id="13b9a-144">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="13b9a-145">选择“**生成报告**”时，Office 365 将创建如下所示的报告：</span><span class="sxs-lookup"><span data-stu-id="13b9a-145">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![网络规划器报告详细信息](../media/network-planner-report.png)

<span data-ttu-id="13b9a-147">突出显示的数字显示了 Teams 和企业语音将使用的 Internet 连接带宽。</span><span class="sxs-lookup"><span data-stu-id="13b9a-147">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="13b9a-148">建议该数字不超过 Internet 总连接速度的 30%。</span><span class="sxs-lookup"><span data-stu-id="13b9a-148">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="13b9a-149">例如，如果 Internet 连接是 60Mbps，则 Teams 和企业语音的占用量不应超过 18Mbps。</span><span class="sxs-lookup"><span data-stu-id="13b9a-149">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="13b9a-150">通过执行以下计算可以查找最低的 Internet 连接速度：`<highlighted number> / .3`。</span><span class="sxs-lookup"><span data-stu-id="13b9a-150">You can find your minimum Internet connection speed by doing this calculation: `<highlighted number> / .3`.</span></span> <span data-ttu-id="13b9a-151">使用上图中突出显示的数字，计算将是：`4.6875 / .3 = 15.6`。</span><span class="sxs-lookup"><span data-stu-id="13b9a-151">Using the highlighted number in the picture above, the calculation would be `4.6875 / .3 = 15.6`.</span></span> <span data-ttu-id="13b9a-152">这意味着最低的 Internet 连接速度需要至少为 15.6Mbps。</span><span class="sxs-lookup"><span data-stu-id="13b9a-152">This means your minimum Internet connection speed needs to be at least 15.6Mbps.</span></span>

<span data-ttu-id="13b9a-153">如果 Teams 和企业语音的使用量将超过 Internet 总连接速度的 30%，则突出显示的数字将显示为红色。</span><span class="sxs-lookup"><span data-stu-id="13b9a-153">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="13b9a-154">如果发生这种情况，可能需要升级 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="13b9a-154">If this happens, you might need to upgrade your Internet connection.</span></span>

![连接速度警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="13b9a-156">确保网络上的计算机和设备可以访问 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="13b9a-156">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="13b9a-157">为确保正常工作，要用于商业语音的计算机和设备需要使用特定网络端口与 Microsoft 365 服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="13b9a-157">To work correctly, computers and devices you want to use with Business Voice need to communicate with Microsoft 365 servers using specific network ports.</span></span> <span data-ttu-id="13b9a-158">网络端口本质上是一种“门”；计算机和设备可以通过这个门在网络或 Internet 上互相通信。</span><span class="sxs-lookup"><span data-stu-id="13b9a-158">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="13b9a-159">你的防火墙需要允许网络上的计算机和设备使用下列出站网络端口访问 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="13b9a-159">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="13b9a-160">**TCP 端口** 80 和 443</span><span class="sxs-lookup"><span data-stu-id="13b9a-160">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="13b9a-161">**UDP 端口** 3478、3479、3480 和 3481</span><span class="sxs-lookup"><span data-stu-id="13b9a-161">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="13b9a-162">检查防火墙是否允许在这些网络端口上进行通信的最简单方法是使用 Teams 进行测试呼叫。</span><span class="sxs-lookup"><span data-stu-id="13b9a-162">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span> <span data-ttu-id="13b9a-163">若要进行测试呼叫，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13b9a-163">To make a test call, do the following:</span></span>

1. <span data-ttu-id="13b9a-164">在网络上的计算机上转到 https://aka.ms/getteams 以安装 Teams。</span><span class="sxs-lookup"><span data-stu-id="13b9a-164">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="13b9a-165">请确保扬声器和麦克风已连接到此计算机。</span><span class="sxs-lookup"><span data-stu-id="13b9a-165">Make sure speakers and a microphone are connected to this computer.</span></span>
2. <span data-ttu-id="13b9a-166">打开 Teams 并使用 Microsoft 365 帐户登录</span><span class="sxs-lookup"><span data-stu-id="13b9a-166">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="13b9a-167">在 Teams 中，选择你的个人资料图片，然后选择“**设置**” > “**设备**”</span><span class="sxs-lookup"><span data-stu-id="13b9a-167">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="13b9a-168">在“**音频设备**”下选择“**进行测试呼叫**”</span><span class="sxs-lookup"><span data-stu-id="13b9a-168">Choose **Make a test call** under **Audio devices**</span></span>
5. <span data-ttu-id="13b9a-169">按照提示留言，然后回放给你自己</span><span class="sxs-lookup"><span data-stu-id="13b9a-169">Follow the prompts to leave a message and have it played back to you</span></span>

* <span data-ttu-id="13b9a-170">如果呼叫已接通，并且你可以听到自己的留言，则表示你的防火墙已正确设置。</span><span class="sxs-lookup"><span data-stu-id="13b9a-170">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
* <span data-ttu-id="13b9a-171">如果呼叫已接通，但无法听到提示或未能回放你的留言，请确保扬声器和麦克风已正确设置并由计算机检测到。</span><span class="sxs-lookup"><span data-stu-id="13b9a-171">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span> <span data-ttu-id="13b9a-172">再试一次。</span><span class="sxs-lookup"><span data-stu-id="13b9a-172">Try again.</span></span>
* <span data-ttu-id="13b9a-173">如果呼叫未接通，或已经接通，但你无法听到自己的留言，则可能需要更新防火墙，以便允许上面列出的网络端口。</span><span class="sxs-lookup"><span data-stu-id="13b9a-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="13b9a-174">请查看防火墙的文档，了解如何允许网络端口访问 Internet，或者联系 IT 专家来帮助你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="13b9a-174">Check your firewall's documentation on how to allow network ports to reach the Internet, or contact an IT specialist to help you.</span></span>

<span data-ttu-id="13b9a-175">如果你是 IT 专业人员，想要详细了解如何准备大型或更复杂的网络来支持企业语音，请查看[评估环境](../3-envision-evaluate-my-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="13b9a-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="13b9a-176">[评估环境](../3-envision-evaluate-my-environment.md)文章中提供了有关带宽、代理和防火墙要求的其他信息，还介绍了如何使用[网络评估工具](../3-envision-evaluate-my-environment.md#test-the-network)来测试网络。</span><span class="sxs-lookup"><span data-stu-id="13b9a-176">The [Evaluate my environment](../3-envision-evaluate-my-environment.md) article gives additional information about bandwidth, proxy, and firewall requirements and also how to test your network using the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network).</span></span>
