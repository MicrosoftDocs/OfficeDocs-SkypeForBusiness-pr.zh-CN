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
ms.openlocfilehash: 90d5135196de9ecf62085e88053d80299b6e5a58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097458"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="7a09a-103">Microsoft Teams 中的 Walkie Talkie 应用</span><span class="sxs-lookup"><span data-stu-id="7a09a-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="7a09a-104">Teams 中的 Walkie Talkie 应用为团队提供即时 (PTT) 通信，现在可在 Android 上使用。</span><span class="sxs-lookup"><span data-stu-id="7a09a-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="7a09a-105">Walkie Talkie 允许用户使用他们作为其成员的相同基础频道来与团队联系。</span><span class="sxs-lookup"><span data-stu-id="7a09a-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="7a09a-106">只有通过频道连接到 Walkie Talkie 的用户才能成为参与者，并且可以使用推送到交谈来相互通信，一次一个。</span><span class="sxs-lookup"><span data-stu-id="7a09a-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="7a09a-107">借助 Teams 中的 Walkie Talkie，一线员工现在无需携带大量无线电即可安全地与熟悉的 PTT 体验进行通信，Walkie Talkie 可在任何位置使用 WiFi 或移动电话 Internet 连接工作。</span><span class="sxs-lookup"><span data-stu-id="7a09a-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="7a09a-108">入门</span><span class="sxs-lookup"><span data-stu-id="7a09a-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="7a09a-109">部署 Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="7a09a-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="7a09a-110">目前，未预安装 Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="7a09a-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="7a09a-111">若要为组织中用户启用此功能，需要将 Walkie Talkie 添加到从管理中心 [](teams-app-setup-policies.md)分配给用户的应用   [Teams策略](https://admin.teams.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="7a09a-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="7a09a-112">启用后，Walkie Talkie 将在 48 小时内在 Android 应用上可用。</span><span class="sxs-lookup"><span data-stu-id="7a09a-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="7a09a-113">将 Walkie Talkie 添加到应用列表</span><span class="sxs-lookup"><span data-stu-id="7a09a-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="7a09a-114">在 Microsoft Teams 管理中心中，Teams **应用** 设置策略"下，应将"允许用户  >  **固定**"设置为"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="7a09a-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="7a09a-115">然后，在"固定应用"部分下，单击 **"+添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="7a09a-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="显示"固定的应用"部分和要选择的"添加应用"按钮。":::

<span data-ttu-id="7a09a-117">在右侧 **出现的"添加固定** 应用"面板上，使用"搜索" **文本框查找** Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="7a09a-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="7a09a-118">将名称作为搜索结果时，选择名称右边的"添加"按钮，将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="7a09a-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示搜索结果中已输入 Walkie 的"添加固定应用"边栏和搜索结果中的 Walkie Talkie 应用，旁边有"添加"按钮。":::

<span data-ttu-id="7a09a-120">Walkie Talkie 应用现在应显示在"固定应用"列表中，单击"保存"按钮后 **即可使用。**</span><span class="sxs-lookup"><span data-stu-id="7a09a-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="显示已添加 Walkie Talkie 应用的"固定应用"列表，以及列表下方的"保存"按钮。":::

### <a name="network-documentation"></a><span data-ttu-id="7a09a-122">网络文档</span><span class="sxs-lookup"><span data-stu-id="7a09a-122">Network documentation</span></span>

<span data-ttu-id="7a09a-123">Teams中的 Walkie Talkie 需要 Internet 连接且低于网络条件才能获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="7a09a-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="7a09a-124">指标</span><span class="sxs-lookup"><span data-stu-id="7a09a-124">Metric</span></span> | <span data-ttu-id="7a09a-125">必需</span><span class="sxs-lookup"><span data-stu-id="7a09a-125">Required</span></span> |
|---|---|
|<span data-ttu-id="7a09a-126">RTT (延迟) </span><span class="sxs-lookup"><span data-stu-id="7a09a-126">Latency (RTT)</span></span> | <span data-ttu-id="7a09a-127">< 300 毫秒</span><span class="sxs-lookup"><span data-stu-id="7a09a-127">< 300ms</span></span> |
|<span data-ttu-id="7a09a-128">抖动</span><span class="sxs-lookup"><span data-stu-id="7a09a-128">Jitter</span></span> |<span data-ttu-id="7a09a-129">< 30 毫秒</span><span class="sxs-lookup"><span data-stu-id="7a09a-129">< 30ms</span></span> |
|<span data-ttu-id="7a09a-130">丢包</span><span class="sxs-lookup"><span data-stu-id="7a09a-130">Packet Loss</span></span> |<span data-ttu-id="7a09a-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="7a09a-131">< 1%</span></span> |

<span data-ttu-id="7a09a-132">如上所述，通过 IP 网络实时媒体的质量受到网络连接质量的很大影响，尤其是以下数量：</span><span class="sxs-lookup"><span data-stu-id="7a09a-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="7a09a-133">**延迟** - 这是从网络上点 A 到点 B 获取 IP 数据包所花的时间。</span><span class="sxs-lookup"><span data-stu-id="7a09a-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="7a09a-134">此网络传播延迟实质上与两个点之间的物理距离和光速有关，包括两者之间的各种路由器所取的更多开销。</span><span class="sxs-lookup"><span data-stu-id="7a09a-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="7a09a-135">延迟以 RTT 流量的往返 (时间) 。</span><span class="sxs-lookup"><span data-stu-id="7a09a-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="7a09a-136">**数据包** 丢失 - 这通常定义为给定时间窗口中丢失的数据包的百分比。</span><span class="sxs-lookup"><span data-stu-id="7a09a-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="7a09a-137">数据包丢失直接影响音频质量 -从小型、单个丢失的数据包几乎没有任何影响，到导致音频完全中断的背对背突发丢失。</span><span class="sxs-lookup"><span data-stu-id="7a09a-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="7a09a-138">**抖动** - 这是连续数据包之间的延迟的平均变化。</span><span class="sxs-lookup"><span data-stu-id="7a09a-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="7a09a-139">发送或接收音频时，Walkie Talkie 的预期数据使用量约为 20KB/s。</span><span class="sxs-lookup"><span data-stu-id="7a09a-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="7a09a-140">空闲时，Walkie Talkie 的预期数据使用量可忽略不计。</span><span class="sxs-lookup"><span data-stu-id="7a09a-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="7a09a-141">Walkie Talkie 设备</span><span class="sxs-lookup"><span data-stu-id="7a09a-141">Walkie Talkie devices</span></span>

<span data-ttu-id="7a09a-142">一线员工经常需要说话和接听 Walkie Talkie 呼叫，即使他们的电话已锁定。</span><span class="sxs-lookup"><span data-stu-id="7a09a-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="7a09a-143">此体验可以通过具有专用 PTT 按钮的专用设备获得。</span><span class="sxs-lookup"><span data-stu-id="7a09a-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="7a09a-144">耳机</span><span class="sxs-lookup"><span data-stu-id="7a09a-144">Headsets</span></span>
  - <span data-ttu-id="7a09a-145">Klein Electronics ([有线耳机](https://www.kleinelectronics.com/poc-accessories/mtwt/)) </span><span class="sxs-lookup"><span data-stu-id="7a09a-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="7a09a-146">[Jabra BlueParrott (无线耳机) ](https://www.blueparrott.com/microsoft-teams-walkie-talkie)</span><span class="sxs-lookup"><span data-stu-id="7a09a-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="7a09a-147">粗式手机</span><span class="sxs-lookup"><span data-stu-id="7a09a-147">Rugged phones</span></span>
  - <span data-ttu-id="7a09a-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="7a09a-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="7a09a-149">[详细信息](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)。</span><span class="sxs-lookup"><span data-stu-id="7a09a-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="7a09a-150">[设置指南](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。</span><span class="sxs-lookup"><span data-stu-id="7a09a-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="7a09a-151">这些设备未经过Teams认证。</span><span class="sxs-lookup"><span data-stu-id="7a09a-151">These devices are not Teams certified.</span></span> <span data-ttu-id="7a09a-152">已验证它们与 Teams Talkie 一起工作。</span><span class="sxs-lookup"><span data-stu-id="7a09a-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="7a09a-153">许可证要求</span><span class="sxs-lookup"><span data-stu-id="7a09a-153">License requirements</span></span>

<span data-ttu-id="7a09a-154">Walkie Talkie 应用包含在所有订阅中Teams付费Office 365[许可证](/office365/servicedescriptions/teams-service-description)中。</span><span class="sxs-lookup"><span data-stu-id="7a09a-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="7a09a-155">有关获取访问权限Teams，请参阅如何 [获取对 Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)的访问权限？</span><span class="sxs-lookup"><span data-stu-id="7a09a-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="7a09a-156">某些高级功能可能需要额外的许可。</span><span class="sxs-lookup"><span data-stu-id="7a09a-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="7a09a-157">例如，与 Samsung Galaxy XCover Pro需要 Knox 许可证。</span><span class="sxs-lookup"><span data-stu-id="7a09a-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="7a09a-158">更多信息</span><span class="sxs-lookup"><span data-stu-id="7a09a-158">Further information</span></span>

- <span data-ttu-id="7a09a-159">ITAdmins 可以通过应用策略保持对谁使用 Walkie Talkie 的控制。</span><span class="sxs-lookup"><span data-stu-id="7a09a-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="7a09a-160">如果 FrontLine 工作人员使用移动数据通过 Teams 通信，Walkie Talkie 将使用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="7a09a-160">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="7a09a-161">Walkie Talkie 应在低带宽情况下或智能手机已连接且正常工作的情况下运行良好。</span><span class="sxs-lookup"><span data-stu-id="7a09a-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="7a09a-162">当没有任何连接时，Walkie Talkie 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="7a09a-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="7a09a-163">有关最终用户体验的进一步阅读，请参阅：</span><span class="sxs-lookup"><span data-stu-id="7a09a-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="7a09a-164">Teams Walkie Talkie 入门</span><span class="sxs-lookup"><span data-stu-id="7a09a-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="7a09a-165">使用 Walkie Talkie 与团队沟通</span><span class="sxs-lookup"><span data-stu-id="7a09a-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)