---
title: Microsoft 团队中的 Walkie Talkie 应用程序
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何从 ITAdmin 角度配置 Microsoft 团队中的 Walkie Talkie 应用。
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
ms.openlocfilehash: 4154a3ad30bf18de934f0fe5a23bbabc94fc76eb
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229048"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="7ba1b-103">Microsoft 团队中的 Walkie Talkie 应用</span><span class="sxs-lookup"><span data-stu-id="7ba1b-103">Walkie Talkie app in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="7ba1b-104">团队中的 Walkie Talkie 应用为你的团队提供即时推送通话（PTT）通信，并且在 Android 上的公共预览版中可用。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is available in Public Preview on Android.</span></span> <span data-ttu-id="7ba1b-105">Walkie Talkie 允许用户使用与其成员相同的基础频道连接其团队。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="7ba1b-106">仅在频道中连接到 Walkie Talkie 的用户成为参与者，并且可以使用 "按下" 与他人进行通信，每次一个通话。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="7ba1b-107">通过 Walkie Talkie，一线的工作人员现在可以安全地与熟悉的 PTT 体验进行通信，而无需携带有容量的无线收发器，并且使用 WiFi 或手机互联网连接，Walkie Talkie 可以工作。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="7ba1b-108">入门</span><span class="sxs-lookup"><span data-stu-id="7ba1b-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="7ba1b-109">部署 Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="7ba1b-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="7ba1b-110">在公共预览版期间，Walkie Talkie 尚未预安装。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-110">During the Public Preview, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="7ba1b-111">若要为你的组织中的用户启用此功能，你需要将 Walkie Talkie [App Setup Policy](teams-app-setup-policies.md)添加到   分配给[团队管理中心](https://admin.teams.microsoft.com/)中的用户的应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="7ba1b-112">启用后，Walkie Talkie 将在48小时内的 Android 应用中可用。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="7ba1b-113">将 Walkie Talkie 添加到你的应用列表</span><span class="sxs-lookup"><span data-stu-id="7ba1b-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="7ba1b-114">在 Microsoft 团队管理中心的 "**团队应用**  >  **设置策略**" 下，应将 "**允许用户固定**" 设置为 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="7ba1b-115">然后，在 "固定应用" 部分下，单击 " **+ 添加应用**"。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="显示 "固定应用" 部分和要选择的 "添加应用" 按钮。":::

<span data-ttu-id="7ba1b-117">在右侧显示的 "**添加固定应用**" 面板上，使用 "**搜索**" 文本框查找 Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="7ba1b-118">当您将其作为搜索结果时，请单击名称右侧的 "**添加**" 按钮，将其添加到您的列表。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示 "添加已固定的应用" 边栏，其中 Walkie 输入到搜索窗格中，在搜索结果中显示 Walkie Talkie 应用，旁边显示 "添加" 按钮。":::

<span data-ttu-id="7ba1b-120">Walkie Talkie 应用现在应显示在 "已附加的应用" 列表中，并且在你单击 "**保存**" 按钮后才可使用。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="显示添加了 Walkie Talkie 应用的固定应用列表，以及列表下方的 "保存" 按钮。":::

### <a name="network-documentation"></a><span data-ttu-id="7ba1b-122">网络文档</span><span class="sxs-lookup"><span data-stu-id="7ba1b-122">Network documentation</span></span>

<span data-ttu-id="7ba1b-123">团队中的 Walkie Talkie 需要 Internet 连接，并且必须满足网络条件才能获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

<span data-ttu-id="7ba1b-124">延迟（RTT） < 300ms |抖动 < 30ms |数据包丢失 < 1%</span><span class="sxs-lookup"><span data-stu-id="7ba1b-124">Latency (RTT) < 300ms | Jitter < 30ms | Packet Loss < 1%</span></span>

<span data-ttu-id="7ba1b-125">如上所述，通过 IP 网络的实时媒体质量很大程度上受到网络连接质量的影响，但特别是：</span><span class="sxs-lookup"><span data-stu-id="7ba1b-125">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="7ba1b-126">**延迟**-这是将 IP 数据包从点 A 转到网络上的点 B 所需的时间。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-126">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="7ba1b-127">此网络传播延迟实质上与两个点之间的物理距离和光之间的距离保持联系，包括不同路由器所用的额外开销。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-127">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="7ba1b-128">延迟按往返时间（RTT）测量。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-128">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="7ba1b-129">**数据包丢失**-这通常定义为在给定时间段内丢失的数据包的百分比。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-129">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="7ba1b-130">数据包丢失直接影响音频质量—从少量的单个丢失的数据包几乎没有影响，到导致完整的音频切出的后端到后爆发损失。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-130">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="7ba1b-131">**抖动**-这是连续数据包之间的延迟的平均变化。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-131">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="7ba1b-132">在发送或接收音频时，Walkie Talkie 的预期数据使用量在 20KB/s 周围。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-132">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="7ba1b-133">当空闲时，Walkie Talkie 中的预期数据使用量可以忽略。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-133">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="7ba1b-134">Walkie Talkie 设备</span><span class="sxs-lookup"><span data-stu-id="7ba1b-134">Walkie Talkie devices</span></span>

<span data-ttu-id="7ba1b-135">即使在手机处于锁定状态时，一线工作人员也经常需要说和接听 Walkie Talkie 通话。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-135">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="7ba1b-136">通过具有专用 PTT 按钮的专用设备，可实现此体验。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-136">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="7ba1b-137">头</span><span class="sxs-lookup"><span data-stu-id="7ba1b-137">Headsets</span></span>
  - <span data-ttu-id="7ba1b-138">有线耳机（[Klein 电子设备](https://www.kleinelectronics.com/poc-accessories/mtwt/)）</span><span class="sxs-lookup"><span data-stu-id="7ba1b-138">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="7ba1b-139">无线耳机（[Jabra evolve BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)）</span><span class="sxs-lookup"><span data-stu-id="7ba1b-139">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="7ba1b-140">坚固的手机</span><span class="sxs-lookup"><span data-stu-id="7ba1b-140">Rugged phones</span></span>
  - <span data-ttu-id="7ba1b-141">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="7ba1b-141">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="7ba1b-142">[详细信息](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-142">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="7ba1b-143">[设置指南](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-143">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="7ba1b-144">这些设备不是团队认证的设备。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-144">These devices are not Teams certified.</span></span> <span data-ttu-id="7ba1b-145">他们已经过验证，可与 Walkie Talkie 的团队协作。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-145">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="7ba1b-146">许可证要求</span><span class="sxs-lookup"><span data-stu-id="7ba1b-146">License requirements</span></span>

<span data-ttu-id="7ba1b-147">Walkie Talkie 应用均包含在[Office 365 订阅](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)中的所有已收费许可证团队中。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-147">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="7ba1b-148">有关获取团队的详细信息，请查看 [如何获取 Microsoft 团队的访问权限](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？</span><span class="sxs-lookup"><span data-stu-id="7ba1b-148">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="7ba1b-149">某些高级功能可能需要额外的许可。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-149">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="7ba1b-150">例如，与 Samsung Galaxy XCover Pro 的集成需要安装 Knox 许可证。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-150">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="7ba1b-151">详细信息</span><span class="sxs-lookup"><span data-stu-id="7ba1b-151">Further information</span></span>

- <span data-ttu-id="7ba1b-152">ITAdmins 可以通过应用策略保持控制哪些人正在使用 Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-152">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="7ba1b-153">如果你的一线工作者使用移动数据通过团队进行通信，Walkie Talkie 将使用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-153">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="7ba1b-154">Walkie Talkie 应在低带宽情况下运行，或者智能手机已连接并正常工作的情况。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-154">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="7ba1b-155">如果根本没有连接，Walkie Talkie 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="7ba1b-155">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="7ba1b-156">有关最终用户体验的进一步阅读，请参阅：</span><span class="sxs-lookup"><span data-stu-id="7ba1b-156">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="7ba1b-157">团队 Walkie Talkie 入门</span><span class="sxs-lookup"><span data-stu-id="7ba1b-157">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="7ba1b-158">通过 Walkie Talkie 与你的团队进行通信</span><span class="sxs-lookup"><span data-stu-id="7ba1b-158">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
