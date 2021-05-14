---
title: Microsoft Teams 中的 Walkie Talkie 应用程序
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何从 ITAdmin 的角度Microsoft Teams Walkie Talkie 应用。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f86d40772eb067a561708c6170ef2354bae521b
ms.sourcegitcommit: 05411575d07d3eadc79d872d1cf81b36aae25621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "52479069"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="c1e61-103">Microsoft Teams 中的 Walkie Talkie 应用</span><span class="sxs-lookup"><span data-stu-id="c1e61-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="c1e61-104">Teams 中的 Walkie Talkie 应用为团队提供即时 (PTT) 通信，现在可在 Android 上使用。</span><span class="sxs-lookup"><span data-stu-id="c1e61-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="c1e61-105">Walkie Talkie 允许用户使用他们作为其成员的相同基础频道来与团队联系。</span><span class="sxs-lookup"><span data-stu-id="c1e61-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="c1e61-106">只有通过频道连接到 Walkie Talkie 的用户才能成为参与者，并且可以使用推送到交谈来相互通信，一次一个。</span><span class="sxs-lookup"><span data-stu-id="c1e61-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="c1e61-107">借助 Teams 中的 Walkie Talkie，一线员工现在无需携带大量无线电即可安全地与熟悉的 PTT 体验进行通信，Walkie Talkie 可在任何位置使用 WiFi 或移动电话 Internet 连接工作。</span><span class="sxs-lookup"><span data-stu-id="c1e61-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="c1e61-108">入门</span><span class="sxs-lookup"><span data-stu-id="c1e61-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="c1e61-109">部署 Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="c1e61-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="c1e61-110">目前，Walkie Talkie 适用于 Google 移动服务 (GMS) 且未预安装的 Android 设备。</span><span class="sxs-lookup"><span data-stu-id="c1e61-110">Currently, Walkie Talkie is available for Android devices with Google Mobile Services (GMS) and is not pre-installed.</span></span> <span data-ttu-id="c1e61-111">若要为组织中用户启用此功能，需要将 Walkie Talkie 添加到从管理中心 [](teams-app-setup-policies.md)分配给用户的应用   [Teams策略](https://admin.teams.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="c1e61-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span> <span data-ttu-id="c1e61-112">启用后，Walkie Talkie 将在 48 小时内在 Android 应用上可用。</span><span class="sxs-lookup"><span data-stu-id="c1e61-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="c1e61-113">将 Walkie Talkie 添加到应用列表</span><span class="sxs-lookup"><span data-stu-id="c1e61-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="c1e61-114">在 Microsoft Teams 管理中心中，Teams **应用** 设置策略"下，应将"允许用户  >  **固定**"设置为"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="c1e61-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="c1e61-115">然后，在"固定应用"部分下，单击 **"+添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="c1e61-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="显示"固定的应用"部分和要选择的"添加应用"按钮。":::

<span data-ttu-id="c1e61-117">在右侧 **出现的"添加固定** 应用"面板上，使用"搜索" **文本框查找** Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="c1e61-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="c1e61-118">将名称作为搜索结果时，选择名称右边的"添加"按钮，将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="c1e61-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示搜索结果中已输入 Walkie 的"添加固定应用"边栏和搜索结果中的 Walkie Talkie 应用，旁边有"添加"按钮。":::

<span data-ttu-id="c1e61-120">Walkie Talkie 应用现在应显示在"固定应用"列表中，单击"保存"按钮后 **即可使用。**</span><span class="sxs-lookup"><span data-stu-id="c1e61-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="显示已添加 Walkie Talkie 应用的"固定应用"列表，以及列表下方的"保存"按钮。":::

### <a name="network-documentation"></a><span data-ttu-id="c1e61-122">网络文档</span><span class="sxs-lookup"><span data-stu-id="c1e61-122">Network documentation</span></span>

<span data-ttu-id="c1e61-123">Teams中的 Walkie Talkie 需要 Internet 连接且低于网络条件才能获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="c1e61-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="c1e61-124">指标</span><span class="sxs-lookup"><span data-stu-id="c1e61-124">Metric</span></span> | <span data-ttu-id="c1e61-125">必需</span><span class="sxs-lookup"><span data-stu-id="c1e61-125">Required</span></span> |
|---|---|
|<span data-ttu-id="c1e61-126">RTT (延迟) </span><span class="sxs-lookup"><span data-stu-id="c1e61-126">Latency (RTT)</span></span> | <span data-ttu-id="c1e61-127">< 300 毫秒</span><span class="sxs-lookup"><span data-stu-id="c1e61-127">< 300ms</span></span> |
|<span data-ttu-id="c1e61-128">抖动</span><span class="sxs-lookup"><span data-stu-id="c1e61-128">Jitter</span></span> |<span data-ttu-id="c1e61-129">< 30 毫秒</span><span class="sxs-lookup"><span data-stu-id="c1e61-129">< 30ms</span></span> |
|<span data-ttu-id="c1e61-130">丢包</span><span class="sxs-lookup"><span data-stu-id="c1e61-130">Packet Loss</span></span> |<span data-ttu-id="c1e61-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="c1e61-131">< 1%</span></span> |

<span data-ttu-id="c1e61-132">如上所述，通过 IP 网络实时媒体的质量受到网络连接质量的很大影响，尤其是以下数量：</span><span class="sxs-lookup"><span data-stu-id="c1e61-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="c1e61-133">**延迟** - 这是从网络上点 A 到点 B 获取 IP 数据包所花的时间。</span><span class="sxs-lookup"><span data-stu-id="c1e61-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="c1e61-134">此网络传播延迟实质上与两个点之间的物理距离和光速有关，包括两者之间的各种路由器所取的更多开销。</span><span class="sxs-lookup"><span data-stu-id="c1e61-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="c1e61-135">延迟以 RTT 流量的往返 (时间) 。</span><span class="sxs-lookup"><span data-stu-id="c1e61-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="c1e61-136">**到达间抖动** - 这是连续数据包之间的延迟的平均变化。</span><span class="sxs-lookup"><span data-stu-id="c1e61-136">**Inter-Arrival Jitter** - This is the average change in delay between successive packets.</span></span>
- <span data-ttu-id="c1e61-137">**数据包** 丢失 - 这通常定义为给定时间窗口中丢失的数据包的百分比。</span><span class="sxs-lookup"><span data-stu-id="c1e61-137">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="c1e61-138">数据包丢失直接影响音频质量 -从小型、单个丢失的数据包几乎没有任何影响，到导致音频完全中断的背对背突发丢失。</span><span class="sxs-lookup"><span data-stu-id="c1e61-138">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>

<span data-ttu-id="c1e61-139">发送或接收音频时，Walkie Talkie 的预期数据使用量约为 20 Kb/s。</span><span class="sxs-lookup"><span data-stu-id="c1e61-139">Expected data usage from Walkie Talkie is around 20 Kb/s when sending or receiving audio.</span></span> <span data-ttu-id="c1e61-140">空闲时，Walkie Talkie 的预期数据使用量可忽略不计。</span><span class="sxs-lookup"><span data-stu-id="c1e61-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="c1e61-141">Walkie Talkie 设备</span><span class="sxs-lookup"><span data-stu-id="c1e61-141">Walkie Talkie devices</span></span>

<span data-ttu-id="c1e61-142">一线员工经常需要说话和接听 Walkie Talkie 呼叫，即使他们的电话已锁定。</span><span class="sxs-lookup"><span data-stu-id="c1e61-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="c1e61-143">此体验可以通过具有专用 PTT 按钮的专用设备获得。</span><span class="sxs-lookup"><span data-stu-id="c1e61-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="c1e61-144">**耳机**</span><span class="sxs-lookup"><span data-stu-id="c1e61-144">**Headsets**</span></span>
  - <span data-ttu-id="c1e61-145">无线耳机</span><span class="sxs-lookup"><span data-stu-id="c1e61-145">Wireless headsets</span></span> 
    - [<span data-ttu-id="c1e61-146">BlueParrott</span><span class="sxs-lookup"><span data-stu-id="c1e61-146">BlueParrott</span></span>](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - <span data-ttu-id="c1e61-147">有线耳机</span><span class="sxs-lookup"><span data-stu-id="c1e61-147">Wired headsets</span></span> 
    - [<span data-ttu-id="c1e61-148">Klein Electronics</span><span class="sxs-lookup"><span data-stu-id="c1e61-148">Klein Electronics</span></span>](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- <span data-ttu-id="c1e61-149">**粗式手机**</span><span class="sxs-lookup"><span data-stu-id="c1e61-149">**Rugged phones**</span></span>
  - <span data-ttu-id="c1e61-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)， [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)， [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span><span class="sxs-lookup"><span data-stu-id="c1e61-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span></span>
    -  <span data-ttu-id="c1e61-151">手动设置 - 安装Teams后，导航设置 > XCover/Active >高级功能。</span><span class="sxs-lookup"><span data-stu-id="c1e61-151">Manual setup - With Teams installed, navigate to Settings > Advanced Features > XCover/Active key.</span></span> <span data-ttu-id="c1e61-152">打开"使用应用控制 XCover 键"，然后选择"Teams"</span><span class="sxs-lookup"><span data-stu-id="c1e61-152">Turn on 'Control XCover key with app' and select 'Teams'</span></span>
    -  [<span data-ttu-id="c1e61-153">MDM 设置</span><span class="sxs-lookup"><span data-stu-id="c1e61-153">MDM setup</span></span>](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> <span data-ttu-id="c1e61-154">这些设备未经过Teams认证。</span><span class="sxs-lookup"><span data-stu-id="c1e61-154">These devices are not Teams certified.</span></span> <span data-ttu-id="c1e61-155">已验证它们与 Teams Talkie 一起工作。</span><span class="sxs-lookup"><span data-stu-id="c1e61-155">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="c1e61-156">许可证要求</span><span class="sxs-lookup"><span data-stu-id="c1e61-156">License requirements</span></span>

<span data-ttu-id="c1e61-157">Walkie Talkie 应用包含在所有订阅中Teams付费Office 365[许可证](/office365/servicedescriptions/teams-service-description)中。</span><span class="sxs-lookup"><span data-stu-id="c1e61-157">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="c1e61-158">有关获取访问权限Teams，请参阅如何 [获取对 Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)的访问权限？</span><span class="sxs-lookup"><span data-stu-id="c1e61-158">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="c1e61-159">某些高级功能可能需要额外的许可。</span><span class="sxs-lookup"><span data-stu-id="c1e61-159">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="c1e61-160">例如，与 Samsung Galaxy XCover Pro需要 Knox 许可证。</span><span class="sxs-lookup"><span data-stu-id="c1e61-160">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="c1e61-161">更多信息</span><span class="sxs-lookup"><span data-stu-id="c1e61-161">Further information</span></span>

- <span data-ttu-id="c1e61-162">ITAdmins 可以通过应用策略保持对谁使用 Walkie Talkie 的控制。</span><span class="sxs-lookup"><span data-stu-id="c1e61-162">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="c1e61-163">如果 FrontLine 工作人员使用移动数据通过 Teams 通信，Walkie Talkie 将使用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="c1e61-163">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="c1e61-164">Walkie Talkie 应在低带宽情况下或智能手机已连接且正常工作的情况下运行良好。</span><span class="sxs-lookup"><span data-stu-id="c1e61-164">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="c1e61-165">当没有任何连接时，Walkie Talkie 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="c1e61-165">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="c1e61-166">有关最终用户体验的进一步阅读，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c1e61-166">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="c1e61-167">Teams Walkie Talkie 入门</span><span class="sxs-lookup"><span data-stu-id="c1e61-167">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="c1e61-168">使用 Walkie Talkie 与团队沟通</span><span class="sxs-lookup"><span data-stu-id="c1e61-168">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
