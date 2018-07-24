---
title: Plan for Mobility for Skype 业务服务器
ms.author: heidip
author: microsoftheidi
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Plan for Business 服务器的 Skype 移动的实现。
ms.openlocfilehash: 660f5013cd2e41ea08fdd2567fb9d51f58c1b8c6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003005"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a><span data-ttu-id="09d19-103">Plan for Mobility for Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="09d19-103">Plan for Mobility for Skype for Business Server</span></span>
 
<span data-ttu-id="09d19-104">Plan for Business 服务器的 Skype 移动的实现。</span><span class="sxs-lookup"><span data-stu-id="09d19-104">Plan for your implementation of Mobility for Skype for Business Server.</span></span>
  
<span data-ttu-id="09d19-105">与 Skype 的业务服务器，您可以部署移动功能，以提供用于在移动设备上的业务服务器功能的 Skype。</span><span class="sxs-lookup"><span data-stu-id="09d19-105">With Skype for Business Server, you can deploy the Mobility feature to provide Skype for Business Server functionality on mobile devices.</span></span> <span data-ttu-id="09d19-106">本文提供有关移动功能，详细信息，并帮助您规划您的部署。</span><span class="sxs-lookup"><span data-stu-id="09d19-106">This article provides details about the Mobility feature, and helps you plan for your deployment.</span></span>
  
<span data-ttu-id="09d19-107">能够支持的业务的 Skype 的移动客户端以及 Lync 客户端返回转到 2010年的业务服务器 Skype 的移动功能。</span><span class="sxs-lookup"><span data-stu-id="09d19-107">The Mobility feature for Skype for Business Server is able to support mobile clients for Skype for Business, as well as Lync clients going back to 2010.</span></span> <span data-ttu-id="09d19-108">为业务服务器部署使用支持的 iOS，它为部署之后，用户可以连接您 Skype Android 和 Windows Phone 移动设备利用几个不同的功能，包括企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="09d19-108">Once it's deployed, your users can connect to your Skype for Business Server deployment using supported iOS, Android and Windows Phone mobile devices to take advantage of several different features, including Enterprise Voice features.</span></span> <span data-ttu-id="09d19-109">我们提供了下面的部分列表，您还可以检查[的 Skype for Business 的桌面客户端功能比较](clients-and-devices/desktop-feature-comparison.md)的详细信息：</span><span class="sxs-lookup"><span data-stu-id="09d19-109">We've included a partial list below, and you can also check [Desktop client feature comparison for Skype for Business](clients-and-devices/desktop-feature-comparison.md) for more info:</span></span>
  
- <span data-ttu-id="09d19-110">发送和接收消息</span><span class="sxs-lookup"><span data-stu-id="09d19-110">Send and receive messages</span></span>
    
- <span data-ttu-id="09d19-111">查看状态</span><span class="sxs-lookup"><span data-stu-id="09d19-111">View presence</span></span>
    
- <span data-ttu-id="09d19-112">查看联系人</span><span class="sxs-lookup"><span data-stu-id="09d19-112">View contacts</span></span>
    
- <span data-ttu-id="09d19-113">单击加入会议</span><span class="sxs-lookup"><span data-stu-id="09d19-113">Click to join a conference</span></span>
    
- <span data-ttu-id="09d19-114">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="09d19-114">Call via work</span></span>
    
- <span data-ttu-id="09d19-115">一号通</span><span class="sxs-lookup"><span data-stu-id="09d19-115">Single number reach</span></span>
    
- <span data-ttu-id="09d19-116">语音邮件</span><span class="sxs-lookup"><span data-stu-id="09d19-116">Voice mail</span></span>
    
- <span data-ttu-id="09d19-117">未接电话通知</span><span class="sxs-lookup"><span data-stu-id="09d19-117">Missed call notification</span></span>
    
- <span data-ttu-id="09d19-118">IP 语音 (VoIP)</span><span class="sxs-lookup"><span data-stu-id="09d19-118">Voice over IP (VoIP)</span></span>
    
- <span data-ttu-id="09d19-119">与会者视频 (H.264)</span><span class="sxs-lookup"><span data-stu-id="09d19-119">Attendee video (H.264)</span></span>
    
- <span data-ttu-id="09d19-120">查看会议内容（PowerPoint 和桌面/应用程序共享）</span><span class="sxs-lookup"><span data-stu-id="09d19-120">Viewing meeting content (PowerPoint and desktop/application sharing)</span></span>
    
<span data-ttu-id="09d19-121">所有这些功能均通过统一通信 Web API (UCWA) 实现。</span><span class="sxs-lookup"><span data-stu-id="09d19-121">All this is accomplished through the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="09d19-122">UCWA 中首次引入 Lync Server 2013 和仍在使用 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="09d19-122">UCWA was first introduced in Lync Server 2013, and it's still in use for Skype for Business Server.</span></span> <span data-ttu-id="09d19-123">Lync 2010 客户端与进行通信的其他功能，并位于 Mobility Service (MCX)。</span><span class="sxs-lookup"><span data-stu-id="09d19-123">There's an additional functionality for communicating with Lync 2010 clients, and that's Mobility Service (MCX).</span></span> <span data-ttu-id="09d19-124">这些是互补服务允许 Lync Server 2010 和 2013年客户端，以及为业务客户端，成功访问业务服务器部署 Skype Skype。</span><span class="sxs-lookup"><span data-stu-id="09d19-124">These are complimentary services, allowing for Lync Server 2010 and 2013 clients, as well as Skype for Business clients, to access Skype for Business Server deployments successfully.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09d19-125">MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="09d19-125">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="09d19-126">您的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="09d19-126">Your users will need to upgrade to a current client.</span></span> 
  
<span data-ttu-id="09d19-127">请务必注意时已实现移动功能后，所有这些功能均可用，它们可能按有点不同某些设备上。</span><span class="sxs-lookup"><span data-stu-id="09d19-127">It's important to note that while all these features are available once Mobility has been implemented, they may work a little differently on some devices.</span></span> <span data-ttu-id="09d19-128">我们讨论功能从事哪些设备，在[移动客户端功能比较的 Skype for Business](clients-and-devices/mobile-feature-comparison.md)的网站。</span><span class="sxs-lookup"><span data-stu-id="09d19-128">We've got a website that discusses what features work on what devices, at [Mobile client feature comparison for Skype for Business](clients-and-devices/mobile-feature-comparison.md).</span></span> <span data-ttu-id="09d19-129">我们还在[规划客户端和设备](clients-and-devices/clients-and-devices.md)了一些出色的设备和操作系统信息。</span><span class="sxs-lookup"><span data-stu-id="09d19-129">We also have some great device and OS information at [Plan for clients and devices](clients-and-devices/clients-and-devices.md).</span></span>
  
<span data-ttu-id="09d19-130">移动利用自动发现功能，允许客户端自动找到 Skype 业务服务器 web 服务而无需输入任何 （它们不会甚至需要了解这些） 的 Url 中的用户。</span><span class="sxs-lookup"><span data-stu-id="09d19-130">Mobility makes use of the Autodiscover feature, which allows clients to automatically locate Skype for Business Server web services without users needing to enter in any URLs (they won't even need to know them).</span></span> <span data-ttu-id="09d19-131">如果你需要执行某些故障排除操作，仍支持手动输入 URL。</span><span class="sxs-lookup"><span data-stu-id="09d19-131">If you need to do some troubleshooting, manual entry of URLs is still supported.</span></span>
  
<span data-ttu-id="09d19-132">此外支持推送通知，当业务应用程序 Skype 不在后台运行 （或不支持在后台运行的应用程序的移动设备）。</span><span class="sxs-lookup"><span data-stu-id="09d19-132">Push notifications are also supported, for when the Skype for Business app isn't running in the background (or for mobile devices that don't support applications running in the background).</span></span> <span data-ttu-id="09d19-133">当设备或应用处于非活动状态时，向移动设备发送关于所发生事件的推送通知。</span><span class="sxs-lookup"><span data-stu-id="09d19-133">A push notification is sent to a mobile device about an event that occurs when the device or app is inactive.</span></span> <span data-ttu-id="09d19-134">例如，当手机处于非活动状态而错过 IM 消息时，就会发送推送通知（采用 Toast 或通知的形式，就像应用在后台运行时那样）。</span><span class="sxs-lookup"><span data-stu-id="09d19-134">A good example is missing an IM message when your phone's not active, which would result in a push notification being sent (this is presented as a toast or notification, like when the app is running in the background).</span></span> <span data-ttu-id="09d19-135">借助推送通知，用户就不会错过 IM 或语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="09d19-135">With push notifications, users won't miss IM or voice calls.</span></span>
  
<span data-ttu-id="09d19-136">有关详细信息，请参阅以下部分：</span><span class="sxs-lookup"><span data-stu-id="09d19-136">For more information, we have the following sections:</span></span>
  
- [<span data-ttu-id="09d19-137">移动组件</span><span class="sxs-lookup"><span data-stu-id="09d19-137">Mobility components</span></span>](mobility.md#MobilityComponents)
    
- [<span data-ttu-id="09d19-138">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="09d19-138">Supported topologies</span></span>](mobility.md#SupportedTopos)
    
- [<span data-ttu-id="09d19-139">技术要求</span><span class="sxs-lookup"><span data-stu-id="09d19-139">Technical requirements</span></span>](mobility.md#TechRequirements)
    
- [<span data-ttu-id="09d19-140">定义你的移动性需求</span><span class="sxs-lookup"><span data-stu-id="09d19-140">Defining your Mobility needs</span></span>](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a><span data-ttu-id="09d19-141">移动组件</span><span class="sxs-lookup"><span data-stu-id="09d19-141">Mobility components</span></span>
<span data-ttu-id="09d19-142"><a name="MobilityComponents"> </a></span><span class="sxs-lookup"><span data-stu-id="09d19-142"></span></span>

<span data-ttu-id="09d19-143">有四种服务组成移动的 Skype 业务服务器：</span><span class="sxs-lookup"><span data-stu-id="09d19-143">There are four services that comprise Mobility for Skype for Business Server:</span></span>
  
- <span data-ttu-id="09d19-144">**统一通信 Web API (UCWA)**</span><span class="sxs-lookup"><span data-stu-id="09d19-144">**Unified Communications Web API (UCWA)**</span></span>
    
    <span data-ttu-id="09d19-145">提供了 mobile 进行实时通信的服务和 web 客户端的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="09d19-145">Provides services for real-time communications with mobile and web clients for Skype for Business Server.</span></span> <span data-ttu-id="09d19-146">Skype 业务服务器部署时，内部和外部 web 服务中创建一个 UCWA 虚拟目录的。</span><span class="sxs-lookup"><span data-stu-id="09d19-146">When Skype for Business Server is deployed, a UCWA virtual directory's created in the internal and external web services.</span></span> <span data-ttu-id="09d19-147">此虚拟目录中的虚拟组件接受支持 UCWA 的客户端发出的呼叫。</span><span class="sxs-lookup"><span data-stu-id="09d19-147">A virtual component in this virtual directory that accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="09d19-148">客户端应用程序通过表述性状态转移 (REST) 接口进行通信，用于：</span><span class="sxs-lookup"><span data-stu-id="09d19-148">The client apps communicate over a representational state transfer (REST) interface for:</span></span>
    
  - <span data-ttu-id="09d19-149">presence － 状态</span><span class="sxs-lookup"><span data-stu-id="09d19-149">presence</span></span>
    
  - <span data-ttu-id="09d19-150">联系人</span><span class="sxs-lookup"><span data-stu-id="09d19-150">contacts</span></span>
    
  - <span data-ttu-id="09d19-151">即时消息 (IM)</span><span class="sxs-lookup"><span data-stu-id="09d19-151">instant messaging (IM)</span></span>
    
  - <span data-ttu-id="09d19-152">VoIP</span><span class="sxs-lookup"><span data-stu-id="09d19-152">VoIP</span></span>
    
  - <span data-ttu-id="09d19-153">视频会议</span><span class="sxs-lookup"><span data-stu-id="09d19-153">video conferencing</span></span>
    
  - <span data-ttu-id="09d19-154">协作</span><span class="sxs-lookup"><span data-stu-id="09d19-154">collaboration</span></span>
    
    <span data-ttu-id="09d19-155">UCWA 使用基于 P-GET 的通道发送事件，例如来电、传入的 IM 或者发送到客户端应用的消息。</span><span class="sxs-lookup"><span data-stu-id="09d19-155">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming IM, or a message to the client app.</span></span>
    
- <span data-ttu-id="09d19-156">**移动性服务 (MCX)**</span><span class="sxs-lookup"><span data-stu-id="09d19-156">**Mobility service (MCX)**</span></span>
    
    <span data-ttu-id="09d19-157">支持的业务服务器功能，例如，IM、 状态和联系人，移动设备上的 Skype。</span><span class="sxs-lookup"><span data-stu-id="09d19-157">Supports Skype for Business Server functionality, such as IM, presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="09d19-158">已用来支持的移动设备上的业务服务器功能的 Skype 每个池中每台前端服务器上安装 Mobility service。</span><span class="sxs-lookup"><span data-stu-id="09d19-158">The Mobility service is installed on every Front End Server in each pool that's intended to support Skype for Business Server functionality on mobile devices.</span></span> <span data-ttu-id="09d19-159">为业务服务器 2015年安装 Skype 时在前端服务器上内部和外部网站下创建一个新的虚拟目录 (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="09d19-159">When you install Skype for Business Server 2015 a new virtual directory (Mcx) is created under both the internal and external websites on your Front End Servers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09d19-160">MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="09d19-160">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="09d19-161">您的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="09d19-161">Your users will need to upgrade to a current client.</span></span>
  
- <span data-ttu-id="09d19-162">**自动发现服务**</span><span class="sxs-lookup"><span data-stu-id="09d19-162">**Autodiscover service**</span></span>
    
    <span data-ttu-id="09d19-163">标识用户的位置并在无论网络位置启用移动设备和其他 Skype 的业务客户端定位资源 （如业务服务器 Web 服务、 Mcx URL 或 UCWA URL 的 Skype 的内部和外部 URL)。</span><span class="sxs-lookup"><span data-stu-id="09d19-163">Identifies the location of the user and enables mobile devices and other Skype for Business clients to locate resources (such as the internal and external URLS for Skype for Business Server Web Services, the Mcx URL , or UCWA URL) regardless of network location.</span></span> <span data-ttu-id="09d19-164">自动发现功能使用硬编码的主机名（对于网络内部用户，为 lyncdiscoverinternal；对于网络外部用户，为 lyncdiscover）和用户的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="09d19-164">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network, lyncdiscover for users outside the network), and the SIP domain of the user.</span></span> <span data-ttu-id="09d19-165">它支持使用 HTTP 或 HTTPS 的客户端连接。</span><span class="sxs-lookup"><span data-stu-id="09d19-165">It supports client connections that use either HTTP or HTTPS.</span></span> 
    
    <span data-ttu-id="09d19-166">每个前端服务器上和在已用于在移动设备上的业务服务器功能支持 Skype 每个池中的每个控制器上安装的自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="09d19-166">The Autodiscover service is installed on every Front End Server and on every Director in each pool that's intended to support Skype for Business Server functionality on mobile devices.</span></span> <span data-ttu-id="09d19-167">当您安装服务时，在前端服务器和控制器上内部和外部网站下创建一个新的虚拟目录 (Autodiscover)。</span><span class="sxs-lookup"><span data-stu-id="09d19-167">When you install the service, a new virtual directory (Autodiscover) is created under both the internal and external websites on your Front End Servers and Directors.</span></span>
    
- <span data-ttu-id="09d19-168">**推送通知服务**</span><span class="sxs-lookup"><span data-stu-id="09d19-168">**Push notification service**</span></span>
    
    <span data-ttu-id="09d19-169">位于您的业务 Online 数据中心的 Skype 的基于云的服务。</span><span class="sxs-lookup"><span data-stu-id="09d19-169">A cloud-based service that's located in your Skype for Business Online data center.</span></span> <span data-ttu-id="09d19-170">没有 Skype 业务客户端在后台运行的电话上的新事件发生时，向移动设备改为获取发送 （称为推送通知） 的已错过事件通知。</span><span class="sxs-lookup"><span data-stu-id="09d19-170">On phones that don't have Skype for Business client running in the background, when a new event happens, notification of a missed event (called a push notification) gets sent to the mobile device instead.</span></span> <span data-ttu-id="09d19-171">Mobility service 到然后将其发送到移动设备的推送通知服务 (MPNS) 发送通知。</span><span class="sxs-lookup"><span data-stu-id="09d19-171">The Mobility service sends a notification to the push notification service (MPNS), which then sends it to the mobile device.</span></span> <span data-ttu-id="09d19-172">然后，用户可以在其移动设备上响应此通知，以激活应用。</span><span class="sxs-lookup"><span data-stu-id="09d19-172">The user can then respond to the notification on their mobile device to activate the app.</span></span> <span data-ttu-id="09d19-173">此功能需要边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="09d19-173">An Edge Server is required for this functionality.</span></span>
    
## <a name="supported-topologies"></a><span data-ttu-id="09d19-174">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="09d19-174">Supported topologies</span></span>
<span data-ttu-id="09d19-175"><a name="SupportedTopos"> </a></span><span class="sxs-lookup"><span data-stu-id="09d19-175"></span></span>

<span data-ttu-id="09d19-176">我们有业务服务器应用程序的拓扑规划以下支持的 Skype:</span><span class="sxs-lookup"><span data-stu-id="09d19-176">We have the following supported Skype for Business Server applications for your topology planning:</span></span>
  
- <span data-ttu-id="09d19-177">移动 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="09d19-177">Mobility Standard Edition</span></span>
    
- <span data-ttu-id="09d19-178">移动企业版</span><span class="sxs-lookup"><span data-stu-id="09d19-178">Mobility Enterprise Edition</span></span>
    
<span data-ttu-id="09d19-179">您应该能够与 Skype 业务 Server 边缘服务器或 Lync Server 2013 边缘服务器使用此功能。</span><span class="sxs-lookup"><span data-stu-id="09d19-179">You should be able to use this functionality with Skype for Business Server Edge Servers or Lync Server 2013 Edge Servers.</span></span>
  
<span data-ttu-id="09d19-180">前端服务器并置中介服务器角色，有两个网络接口上, 支持 Mobility service，但您需要采取相应的步骤配置这些接口。</span><span class="sxs-lookup"><span data-stu-id="09d19-180">The Mobility service is supported on Front End Servers when collocated with the Mediation Server role, with two network interfaces, but you need to take appropriate steps to configure those interfaces.</span></span> <span data-ttu-id="09d19-181">您需要分配给为中介服务器中，将会进行通信的特定接口和将作为前端服务器进行通信的网络 IP 接口的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="09d19-181">You'll need to assign IP addresses to the specific interface that will communicate as the Mediation Server, and the network IP interface that will communicate as the Front End Server.</span></span> <span data-ttu-id="09d19-182">您可以这样做拓扑生成器中通过选择每个服务，而不是使用默认**使用所有已配置的 IP 地址**选择正确的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="09d19-182">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default **Use all configured IP addresses** selection.</span></span>
  
## <a name="technical-requirements"></a><span data-ttu-id="09d19-183">技术要求</span><span class="sxs-lookup"><span data-stu-id="09d19-183">Technical requirements</span></span>
<span data-ttu-id="09d19-184"><a name="TechRequirements"> </a></span><span class="sxs-lookup"><span data-stu-id="09d19-184"></span></span>

<span data-ttu-id="09d19-185">针对移动用户可能遇到的各种移动应用程序方案做好规划非常重要。</span><span class="sxs-lookup"><span data-stu-id="09d19-185">It's important to plan for the various mobile application scenarios your mobile users may encounter.</span></span> <span data-ttu-id="09d19-186">例如，有些人可能在工作之余通过连接到 3G 网络使用移动应用，然后在工作时切换到公司 Wi-Fi 网络。</span><span class="sxs-lookup"><span data-stu-id="09d19-186">For example, someone might start using a mobile app outside of work by connecting through a 3G network, then switch to the corporate Wi-Fi network when they reach work.</span></span> <span data-ttu-id="09d19-187">离开其构建时，他们可以切换到 4 G。</span><span class="sxs-lookup"><span data-stu-id="09d19-187">They may switch to 4G when leaving their building.</span></span> <span data-ttu-id="09d19-188">现在进行规划有助于为这些网络转换提供支持并保证一致的用户体验。</span><span class="sxs-lookup"><span data-stu-id="09d19-188">Planning now will allow you to support these network transitions and guarantee a consistent user experience.</span></span>
  
### <a name="dns-configuration"></a><span data-ttu-id="09d19-189">DNS 配置</span><span class="sxs-lookup"><span data-stu-id="09d19-189">DNS configuration</span></span>

<span data-ttu-id="09d19-190">Mobility service Mcx 和 UCWA 相同的方式使用 DNS。</span><span class="sxs-lookup"><span data-stu-id="09d19-190">The Mobility services Mcx and UCWA use DNS in the same way.</span></span> <span data-ttu-id="09d19-191">利用自动发现，移动设备使用 DNS 定位资源。</span><span class="sxs-lookup"><span data-stu-id="09d19-191">With Automatic Discovery, mobile devices use DNS to locate resources.</span></span> <span data-ttu-id="09d19-192">在 DNS 查找期间，尝试连接到与内部 DNS 记录关联的 FQDN (lyncdiscoverinternal.[内部域名])。</span><span class="sxs-lookup"><span data-stu-id="09d19-192">During DNS lookup, a connection's attempted to the FQDN that's associated with the internal DNS record (lyncdiscoverinternal.[internal domain name]).</span></span> <span data-ttu-id="09d19-193">如果无法使用内部 DNS 记录实现连接，将尝试进行第二次连接，这次将连接到外部 DNS 记录 (lyncdiscover.[sipdomain])。</span><span class="sxs-lookup"><span data-stu-id="09d19-193">If the internal DNS record can't be used to make that connection, a second connection is attempted, this time to the external DNS record (lyncdiscover.[sipdomain]).</span></span> <span data-ttu-id="09d19-194">为什么会有两个呢？</span><span class="sxs-lookup"><span data-stu-id="09d19-194">So why have two?</span></span> <span data-ttu-id="09d19-195">位于网络内部的移动设备可以使用内部自动发现 URL。</span><span class="sxs-lookup"><span data-stu-id="09d19-195">A mobile device that's internal to your network will be able to use the internal Autodiscover URL.</span></span> <span data-ttu-id="09d19-196">外部移动设备将使用外部自动发现 URL。</span><span class="sxs-lookup"><span data-stu-id="09d19-196">External mobile devices will use the external Autodiscover URL.</span></span> <span data-ttu-id="09d19-197">在任一情况下，自动发现服务将返回用户的主池，其中包括 Mobility service （Mcx 和 UCWA） 的所有 Web 服务 Url。</span><span class="sxs-lookup"><span data-stu-id="09d19-197">In either case, the Autodiscover service will return all Web service URLs for the user's home pool, which includes the Mobility service (Mcx and UCWA).</span></span>
  
<span data-ttu-id="09d19-198">预计的外部自动发现请求将通过反向代理配置的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="09d19-198">It's expected that the external Autodiscover requests will go through the reverse proxy you've configured for Skype for Business Server.</span></span> <span data-ttu-id="09d19-199">但是，内部 Mobility service URL 和外部 Mobility service URL 是与外部 Web 服务 FQDN 关联。</span><span class="sxs-lookup"><span data-stu-id="09d19-199">However, both the internal Mobility service URL and the external Mobility service URL are associated with the external Web Services FQDN.</span></span> <span data-ttu-id="09d19-200">因此，无论是否移动设备，内部或外部到您的网络设备始终连接到外部业务服务器 Mobility service 的 Skype 通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="09d19-200">Therefore, regardless of whether a mobile device is internal or external to your network, the device always connects to the Skype for Business Server Mobility service externally, through your reverse proxy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09d19-201">正如我们只需说，所有 Mobility service 流量 （内部和外部） 将都通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="09d19-201">As we just noted, all Mobility service traffic (internal and external) will go through your reverse proxy.</span></span> <span data-ttu-id="09d19-202">但是，当内部通信通过某个接口离开，然后又只能返回到相同的接口时，偶尔会发生问题。</span><span class="sxs-lookup"><span data-stu-id="09d19-202">But sometimes an issue comes up when the internal traffic leaves through an interface, only to then try and come back in on the same interface.</span></span> <span data-ttu-id="09d19-203">这可能会违反欺骗（之前称为 TCP 数据包欺骗）安全规则。</span><span class="sxs-lookup"><span data-stu-id="09d19-203">This can violate your spoofing (formally it's called TCP packet spoofing) security rules.</span></span> <span data-ttu-id="09d19-204">您需要允许**字形驻留**具有移动函数。</span><span class="sxs-lookup"><span data-stu-id="09d19-204">You'll need to allow **Hair Pinning** to have Mobility function.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09d19-205">如果您已准备好执行此操作，您还可以选择使用反向代理的独立于您的防火墙 （对于安全目的，欺骗防护应始终会在防火墙上实施）。</span><span class="sxs-lookup"><span data-stu-id="09d19-205">If you're ready to do this, you can also choose to use a reverse proxy that's separate from your firewall (for security purposes, spoofing prevention should always be enforced at your firewall).</span></span> <span data-ttu-id="09d19-206">这种方式，发夹可以发生在您的反向代理的外部接口，而不是防火墙的外部接口。</span><span class="sxs-lookup"><span data-stu-id="09d19-206">This way, the hairpin can happen at the external interface of your reverse proxy, rather than your firewall's external interface.</span></span> <span data-ttu-id="09d19-207">这样，您可以检测欺骗正确在防火墙时在反向代理，放宽规则，并获取您的移动功能。</span><span class="sxs-lookup"><span data-stu-id="09d19-207">This allows you to detect the spoofing properly at your firewall while you relax the rule at your reverse proxy, and you get your Mobility functionality.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="09d19-208">如果您转此路由，请务必使用 DNS 主机或 CNAME 记录定义反向代理为发夹行为 （不防火墙），如果可能。</span><span class="sxs-lookup"><span data-stu-id="09d19-208">If you go this route, be sure to use the DNS host or CNAME records to define the reverse proxy for the hairpin behavior (not the firewall), if possible.</span></span> 
  
<span data-ttu-id="09d19-209">要支持企业网络内部和外部的用户，你需要执行几项配置操作。</span><span class="sxs-lookup"><span data-stu-id="09d19-209">There are some things you'll need to configure to support users inside and outside your corporate network.</span></span>
  
<span data-ttu-id="09d19-210">这些是用于内部和外部 Web FQDN 的规则：</span><span class="sxs-lookup"><span data-stu-id="09d19-210">These are the rules for internal and external web FQDNs:</span></span>
  
- <span data-ttu-id="09d19-211">新的 CNAME 或 A（主机，如果是 IPv6，则为 AAAA）DNS 记录（用于自动发现）。</span><span class="sxs-lookup"><span data-stu-id="09d19-211">New CNAME or A (host, if IPv6, AAAA) DNS records, for automatic discovery.</span></span>
    
- <span data-ttu-id="09d19-212">新防火墙规则（如果希望通过 Wi-Fi 网络支持推送通知）。</span><span class="sxs-lookup"><span data-stu-id="09d19-212">New firewall rule, if you want to support push notifications through your Wi-Fi network.</span></span>
    
- <span data-ttu-id="09d19-213">主题备用名称内部服务器证书和反向代理证书上的自动发现。</span><span class="sxs-lookup"><span data-stu-id="09d19-213">Subject alternative names on internal server certificates and reverse proxy certificates, for automatic discovery.</span></span>
    
- <span data-ttu-id="09d19-214">前端服务器硬件负载平衡配置更改源关联。</span><span class="sxs-lookup"><span data-stu-id="09d19-214">Front End Server hardware load balanced configuration changes source affinity.</span></span>
    
<span data-ttu-id="09d19-215">以下是支持 Mobility Service 和自动发现服务所需的拓扑要求：</span><span class="sxs-lookup"><span data-stu-id="09d19-215">These are the topology requirements needed to support the Mobility Service and Autodiscover Service:</span></span>
  
- <span data-ttu-id="09d19-216">前端池的内部 web FQDN 必须是前端池的外部 web FQDN 不同。</span><span class="sxs-lookup"><span data-stu-id="09d19-216">The Front End pool internal web FQDN must be distinct from the Front End pool external web FQDN.</span></span>
    
- <span data-ttu-id="09d19-217">内部 Web FQDN 必须仅解析为企业网络地址且仅能从企业网络内部进行访问。</span><span class="sxs-lookup"><span data-stu-id="09d19-217">The internal web FQDN must only resolve to, and be accessible from, inside the corporate network.</span></span>
    
- <span data-ttu-id="09d19-218">外部 Web FQDN 必须仅解析为 Internet 地址且仅能从 Internet 进行访问。</span><span class="sxs-lookup"><span data-stu-id="09d19-218">The external web FQDN must only resolve to, and be accessible from, the internet.</span></span>
    
- <span data-ttu-id="09d19-219">在企业网络内部用户，Mobility service URL 必须发往外部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="09d19-219">For a user inside the corporate network, the Mobility service URL must be addressed to the external web FQDN.</span></span> <span data-ttu-id="09d19-220">这一要求为 Mobility service，并且仅适用于此 URL。</span><span class="sxs-lookup"><span data-stu-id="09d19-220">This requirement is for the Mobility service, and applies only to this URL.</span></span>
    
- <span data-ttu-id="09d19-221">企业网络外部的用户，此请求必须转到的外部 web 前端池或控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="09d19-221">For a user outside the corporate network, the request must go to the external web FQDN of the Front End pool or Director.</span></span>
    
<span data-ttu-id="09d19-222">如果你支持自动发现，则需要为每个 SIP 域创建以下 DNS 记录：</span><span class="sxs-lookup"><span data-stu-id="09d19-222">If you support automatic discovery, you'll need to make the following DNS records for each SIP domain:</span></span>
  
- <span data-ttu-id="09d19-223">内部 DNS 记录，用于支持从组织网络内部进行连接的移动用户。</span><span class="sxs-lookup"><span data-stu-id="09d19-223">An internal DNS record to support mobile users who connect from inside your organization's network.</span></span>
    
- <span data-ttu-id="09d19-224">外部或公共 DNS 记录，用于支持从 Internet 进行连接的移动用户。</span><span class="sxs-lookup"><span data-stu-id="09d19-224">An external, or public, DNS record to support mobile users who connect from the internet.</span></span>
    
<span data-ttu-id="09d19-p121">应无法从内部网络外部对内部自动发现 URL 进行寻址。应无法从网络内部对外部自动发现 URL 进行寻址。但是，如果无法满足外部 URL 的此要求，可能也不会影响移动客户端的功能，因为始终会先尝试内部 URL。</span><span class="sxs-lookup"><span data-stu-id="09d19-p121">The internal automatic discovery URL shouldn't be addressable from outside your internal network. The external automatic discovery URL shouldn't be addressable from within your network. But if this isn't possible for the external URL, your mobile client functionality probably won't be affected, because the internal URL will always be tried first.</span></span>
  
### <a name="port-and-firewall-requirements"></a><span data-ttu-id="09d19-228">端口和防火墙要求</span><span class="sxs-lookup"><span data-stu-id="09d19-228">Port and Firewall requirements</span></span>

<span data-ttu-id="09d19-229">我们在我们其他文档中，介绍大部分这但专门以实现移动功能，您将需要以下端口上企业 Wi-fi 网络如果您有打开任何用户驻留在 Survivable Branch Appliance (SBA):</span><span class="sxs-lookup"><span data-stu-id="09d19-229">We've covered most of this in our other documentation, but specifically for Mobility, you're going to want to have the following ports open on your enterprise Wi-Fi network if you have any users homed on a Survivable Branch Appliance (SBA):</span></span>
  
- <span data-ttu-id="09d19-230">UcwaSipExternalListeningPort 需要 5088。</span><span class="sxs-lookup"><span data-stu-id="09d19-230">UcwaSipExternalListeningPort requires 5088.</span></span>
    
- <span data-ttu-id="09d19-231">UcwaSipPrimaryListeningPort 需要 5089。</span><span class="sxs-lookup"><span data-stu-id="09d19-231">UcwaSipPrimaryListeningPort requires 5089.</span></span>
    
### <a name="certificate-requirements"></a><span data-ttu-id="09d19-232">证书要求</span><span class="sxs-lookup"><span data-stu-id="09d19-232">Certificate requirements</span></span>

<span data-ttu-id="09d19-233">如果您为您 Skype 业务移动客户端使用自动发现，您需要修改证书以支持从移动客户端的安全连接的 SAN （使用者替代名称） 列表。</span><span class="sxs-lookup"><span data-stu-id="09d19-233">If you're using automatic discovery for your Skype for Business mobile clients, you'll need to modify the SAN (subject alternative name) lists on your certificates to support secure connections from your mobile clients.</span></span> <span data-ttu-id="09d19-234">如果已将证书准备就绪，则需要请求并分配包含此处所述 SAN 条目的新证书。</span><span class="sxs-lookup"><span data-stu-id="09d19-234">If you already have certificates in-place, you'll need to request and assign new certificates with the SAN entries described here.</span></span> <span data-ttu-id="09d19-235">这将需要为每个前端服务器和控制器 （如果环境中完成您） 运行自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="09d19-235">This will need to be done for each Front End Server and Director (if in your environment) that runs the Autodiscover service.</span></span> <span data-ttu-id="09d19-236">我们还建议修改 SAN 上的列表反向代理证书，您的组织中添加的每个 SIP 域的 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="09d19-236">We'd also recommend modifying the SAN lists on your reverse proxy certificates, adding SAN entries for every SIP domain in your organization.</span></span>
  
<span data-ttu-id="09d19-237">这应该是一个简单的过程，如果您正在请求新证书关闭内部 CA （证书颁发机构），但公共证书是更复杂，和重新请求，不必说可能、 添加大量 SIP 可能更高域到新的公共证书。在这种情况下，没有一种受支持，但**不是建议使用**。</span><span class="sxs-lookup"><span data-stu-id="09d19-237">This should be a straightforward process if you're requesting the new certs off an internal CA (certificate authority), but public certificates are more complex, and potentially a lot more expensive to re-request, not to mention it may be costly to add a lot of SIP domains to a new public cert. In that situation, there is an approach that's supported, but **not recommended**.</span></span> <span data-ttu-id="09d19-238">您可以配置反向代理进行的初始自动发现服务请求，通过端口 80，它将使用 HTTP，而不是端口 443，这是 HTTPS （和 443 是默认配置）。</span><span class="sxs-lookup"><span data-stu-id="09d19-238">You can configure your reverse proxy to make the initial Autodiscover service request over port 80, which will use HTTP, rather than port 443, which is HTTPS (and 443 is the default configuration).</span></span> <span data-ttu-id="09d19-239">该传入请求将被重定向到您的前端池或控制器上的端口 8080。</span><span class="sxs-lookup"><span data-stu-id="09d19-239">That incoming request will be redirected to port 8080 on your Front End pool or Director.</span></span> <span data-ttu-id="09d19-240">通过执行此操作，无需再更改任何证书，因为此通信为请求使用的不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="09d19-240">By doing this, you won't need to make any certificate changes, because this traffic isn't using HTTPS for requests.</span></span> <span data-ttu-id="09d19-241">再次说明，尽管你可以使用此方法，但我们不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="09d19-241">But again, we don't recommend this, although it will work for you.</span></span>
  
### <a name="windows-and-iis-requirements"></a><span data-ttu-id="09d19-242">Windows 和 IIS 要求</span><span class="sxs-lookup"><span data-stu-id="09d19-242">Windows and IIS requirements</span></span>

<span data-ttu-id="09d19-243">您应该是受支持的 Windows Server 版本的业务服务器环境您 Skype。</span><span class="sxs-lookup"><span data-stu-id="09d19-243">You should have a supported Windows Server version for your Skype for Business Server environment.</span></span> <span data-ttu-id="09d19-244">因此，你还需要具有 IIS 8 或 IIS 8.5 才能满足你的移动性需求。</span><span class="sxs-lookup"><span data-stu-id="09d19-244">As a result, you should also have IIS 8 or IIS 8.5 for your mobility needs.</span></span> <span data-ttu-id="09d19-245">那里需要来进行某些更改默认 ASP.NET 设置，但 Mobility service 安装程序将自动执行的。</span><span class="sxs-lookup"><span data-stu-id="09d19-245">There will need to be some changes to the default ASP.NET settings, but the Mobility service installer will do that automatically.</span></span>
  
### <a name="hlb-requirements"></a><span data-ttu-id="09d19-246">HLB 要求</span><span class="sxs-lookup"><span data-stu-id="09d19-246">HLB requirements</span></span>

<span data-ttu-id="09d19-247">如果您正在使用的拓扑的 Skype 业务服务器包含前端池 （其中将为任何拓扑包含多台前端服务器） HLB，需要配置外部 Web 服务虚拟 Ip (Vip) 的 Web Services 通信源。</span><span class="sxs-lookup"><span data-stu-id="09d19-247">If you're using a topology for Skype for Business Server that includes an HLB for your Front End pool (which would be any topology that includes more than one Front End Server), the external Web Services virtual IPs (VIPs) for Web Services traffic need to be configured for source.</span></span> <span data-ttu-id="09d19-248">源关联有助于确保将单个客户端的多个连接发送给同一台服务器以保持会话状态。</span><span class="sxs-lookup"><span data-stu-id="09d19-248">Source affinity helps to ensure that multiple connections from a single client are sent to the same server to maintain session state.</span></span>
  
<span data-ttu-id="09d19-249">如果您计划仅对内部 Wi-fi 网络支持的业务移动客户端的 Skype，您应为外部 Web 服务 Vip 所述配置源您内部 Web 服务 Vip。</span><span class="sxs-lookup"><span data-stu-id="09d19-249">If you plan to support Skype for Business mobile clients only over your internal Wi-Fi network, you should configure your internal Web Services VIPs for source as described for external Web Services VIPs.</span></span> <span data-ttu-id="09d19-250">在这种情况下，您应使用 source_addr （或 TCP） 的内部 Web 服务 Vip 上 HLB 的相关性。</span><span class="sxs-lookup"><span data-stu-id="09d19-250">In this situation, you should use source_addr (or TCP) affinity for the internal Web Services VIPs on the HLB.</span></span>
  
<span data-ttu-id="09d19-251">有关所有这的详细信息，请查看的[负载平衡的 Skype 的业务要求](network-requirements/load-balancing.md)的文档。</span><span class="sxs-lookup"><span data-stu-id="09d19-251">For details on all this, please review the [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md) documentation.</span></span>
  
### <a name="reverse-proxy-requirements"></a><span data-ttu-id="09d19-252">反向代理要求</span><span class="sxs-lookup"><span data-stu-id="09d19-252">Reverse Proxy requirements</span></span>

<span data-ttu-id="09d19-253">为了对业务移动客户端 Skype 支持自动发现，您需要更新当前发布规则，如下所示：</span><span class="sxs-lookup"><span data-stu-id="09d19-253">In order to support automatic discovery for Skype for Business mobile clients, you'll need to update the current publishing rule as follows:</span></span>
  
- <span data-ttu-id="09d19-254">如果您决定要更新您的反向代理证书上的 SAN 列表和您将 HTTPS 用于初始自动发现服务请求，您需要更新 lyncdiscover 的 web 发布规则。\<sipdomain\>。</span><span class="sxs-lookup"><span data-stu-id="09d19-254">If you decide to update the SAN lists on your reverse proxy certificates, and you're using HTTPS for the initial Autodiscover service request, you need to update the web publishing rule for lyncdiscover.\<sipdomain\>.</span></span> <span data-ttu-id="09d19-255">这通常与结合发布 rul 的前端池上的外部 Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="09d19-255">This is typically combined with the publishing rul for the external Web Services URL on the Front End pool.</span></span>
    
- <span data-ttu-id="09d19-256">如果您决定要使用 HTTP 用于初始自动发现服务请求可避免更新 SAN 列表的反向代理证书 （其不建议） 中，您将需要创建新的 web 发布规则为端口 HTTP/TCP 80，如果没有已。</span><span class="sxs-lookup"><span data-stu-id="09d19-256">If you've decided to use HTTP for the initial Autodiscover service request to avoid having to update the SAN list for your reverse proxy certificates (which we don't recommend), you'll need to create a new web publishing rule for port HTTP/TCP 80, if there isn't one already.</span></span> <span data-ttu-id="09d19-257">如果存在该规则，对其进行更新以包括 lyncdiscover。\<sipdomain\>条目。</span><span class="sxs-lookup"><span data-stu-id="09d19-257">If that rule exists, update it to include a lyncdiscover.\<sipdomain\> entry.</span></span>
    
## <a name="defining-your-mobility-needs"></a><span data-ttu-id="09d19-258">定义你的移动性需求</span><span class="sxs-lookup"><span data-stu-id="09d19-258">Defining your Mobility needs</span></span>
<span data-ttu-id="09d19-259"><a name="MobilityNeeds"> </a></span><span class="sxs-lookup"><span data-stu-id="09d19-259"></span></span>

<span data-ttu-id="09d19-260">现在，我们已审阅的拓扑、 组件和技术要求，让我们看您的组织可能需要方面的移动性实现。</span><span class="sxs-lookup"><span data-stu-id="09d19-260">Now that we've reviewed the topologies, components and technical requirements, let's look at what your organization may need in terms of a Mobility implementation.</span></span>
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a><span data-ttu-id="09d19-261">是否要为 Skype for Business 移动客户端使用自动发现功能？</span><span class="sxs-lookup"><span data-stu-id="09d19-261">Do you want to use automatic discovery for Skype for Business mobile clients?</span></span>

<span data-ttu-id="09d19-262">强烈建议你使用自动发现。</span><span class="sxs-lookup"><span data-stu-id="09d19-262">We do strongly recommend that you do use automatic discovery.</span></span> <span data-ttu-id="09d19-263">如上面的“技术要求”部分所述，这需要创建新的内部和外部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="09d19-263">It will require the creation of new internal and external DNS records, as documented in the Technical Requirements section above.</span></span> <span data-ttu-id="09d19-264">使用自动发现，业务客户端的 Skype 可以自动找到 Skype 业务服务器 Web 服务从任何位置，而无需手动输入 URL。</span><span class="sxs-lookup"><span data-stu-id="09d19-264">With automatic discovery, the Skype for Business clients can automatically locate Skype for Business Server Web Services from any location, without needing a URL to be entered in manually.</span></span>
  
<span data-ttu-id="09d19-p130">如果需要，你也可以使用手动设置。用户需要将以下 URL 输入到其移动设备中：</span><span class="sxs-lookup"><span data-stu-id="09d19-p130">You can use manual settings if you need to. These URLs will need to be entered by users into their mobile devices:</span></span>
  
- <span data-ttu-id="09d19-267">**https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root**外部访问。</span><span class="sxs-lookup"><span data-stu-id="09d19-267">**https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** for external access.</span></span>
    
- <span data-ttu-id="09d19-268">**https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root**供内部访问。</span><span class="sxs-lookup"><span data-stu-id="09d19-268">**https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** for internal access.</span></span>
    
<span data-ttu-id="09d19-p131">再次强调一下，我们建议使用自动发现。你会发现手动设置对于故障排除很有用。</span><span class="sxs-lookup"><span data-stu-id="09d19-p131">Again, we do recommend using automatic discovery. You may find manual settings useful for troubleshooting purposes.</span></span>
  
### <a name="are-you-going-to-support-push-notifications"></a><span data-ttu-id="09d19-271">你是否打算支持推送通知？</span><span class="sxs-lookup"><span data-stu-id="09d19-271">Are you going to support push notifications?</span></span>

<span data-ttu-id="09d19-272">推送通知用于支持此功能的移动应用程序，可以在应用处于非活动状态时将事件通知给用户。</span><span class="sxs-lookup"><span data-stu-id="09d19-272">Push notifications are used for mobile applications that support this functionality to notify a user of events while the app's not active.</span></span> <span data-ttu-id="09d19-273">边缘服务器将需要对业务服务器推送通知服务，它位于业务 Online 数据中心的 Skype 拥有与您的基于云的 Skype 联合身份验证关系。</span><span class="sxs-lookup"><span data-stu-id="09d19-273">Your Edge Server will need to have a federation relationship with your cloud-based Skype for Business Server Push Notification Service, which is found on the Skype for Business Online datacenter.</span></span> <span data-ttu-id="09d19-274">你需要运行 cmdlet 以启用推送通知。</span><span class="sxs-lookup"><span data-stu-id="09d19-274">You'll need to run a cmdlet to enable push notifications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09d19-275">如果您有任何人仍在使用 Lync Server 2010 客户端，他们将需要 TCP 端口 5223 打开出站企业 WiFi 网络上。</span><span class="sxs-lookup"><span data-stu-id="09d19-275">If you have anyone still using Lync Server 2010 clients, they will need TCP port 5223 open outbound on your enterprise WiFi network.</span></span> 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a><span data-ttu-id="09d19-276">要指定可以改为访问这些功能的用户或您希望访问所有移动功能，所有用户？</span><span class="sxs-lookup"><span data-stu-id="09d19-276">Do you want all your users accessing all Mobility features, or do you want to specify the users who can access these features instead?</span></span>

<span data-ttu-id="09d19-277">我们有一个表来帮助的一些功能可供所有用户，并是否他们正在方式或不通过设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="09d19-277">We have a table to help with some of the features that are available to all users, and whether they're set that way or not by default.</span></span> <span data-ttu-id="09d19-278">有关的完整列表，请查看[New-csmobilitypolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="09d19-278">For a complete list, please review [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="09d19-279">所有这些功能的适用范围为全局/站点/用户。</span><span class="sxs-lookup"><span data-stu-id="09d19-279">The scopes for all these features are Global/Site/User.</span></span> 
  
|<span data-ttu-id="09d19-280">**功能**</span><span class="sxs-lookup"><span data-stu-id="09d19-280">**Feature**</span></span>|<span data-ttu-id="09d19-281">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="09d19-281">**Parameter Name**</span></span>|<span data-ttu-id="09d19-282">**说明**</span><span class="sxs-lookup"><span data-stu-id="09d19-282">**Description**</span></span>|<span data-ttu-id="09d19-283">**默认设置**</span><span class="sxs-lookup"><span data-stu-id="09d19-283">**Default Setting**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09d19-284">支持移动性</span><span class="sxs-lookup"><span data-stu-id="09d19-284">Enable Mobility</span></span>  <br/> |<span data-ttu-id="09d19-285">EnableMobility</span><span class="sxs-lookup"><span data-stu-id="09d19-285">EnableMobility</span></span>  <br/> |<span data-ttu-id="09d19-286">控制给定范围内拥有 Skype 业务移动客户端安装的用户。</span><span class="sxs-lookup"><span data-stu-id="09d19-286">Controls users in a given scope who have Skype for Business mobile client installed.</span></span> <span data-ttu-id="09d19-287">如果该策略设置为 False，用户将无法登录其客户端。</span><span class="sxs-lookup"><span data-stu-id="09d19-287">If the policy is set to False, your users won't be able to sign in with their client.</span></span>  <br/> |<span data-ttu-id="09d19-288">True</span><span class="sxs-lookup"><span data-stu-id="09d19-288">True</span></span>  <br/> |
|<span data-ttu-id="09d19-289">外部语音</span><span class="sxs-lookup"><span data-stu-id="09d19-289">Outside Voice</span></span>  <br/> |<span data-ttu-id="09d19-290">EnableOutsideVoice</span><span class="sxs-lookup"><span data-stu-id="09d19-290">EnableOutsideVoice</span></span>  <br/> |<span data-ttu-id="09d19-p135">使用户可以使用“通过工号拨号”功能，该功能允许用户使用其工作号码而不是自己的移动号码来拨打和接听电话。如果设置为 False，用户在使用其工作电话号码时，将无法在其移动电话上拨打或接听电话。</span><span class="sxs-lookup"><span data-stu-id="09d19-p135">Enables a user's ability to use Call Via Work, which lets users send and receive calls by using their work number instead of their mobile number. If it's set to False, your users won't be able to make or receive calls on their mobile phone when using their work phone number.</span></span>  <br/> |<span data-ttu-id="09d19-293">True</span><span class="sxs-lookup"><span data-stu-id="09d19-293">True</span></span>  <br/> |
|<span data-ttu-id="09d19-294">支持 IP 音频和视频</span><span class="sxs-lookup"><span data-stu-id="09d19-294">Enable IP Audio and Video</span></span>  <br/> |<span data-ttu-id="09d19-295">EnableIPAudioVideo</span><span class="sxs-lookup"><span data-stu-id="09d19-295">EnableIPAudioVideo</span></span>  <br/> |<span data-ttu-id="09d19-p136">设置为默认值，允许用户在其移动设备上使用 VoIP 拨打或接听电话或视频电话。如果设置为 False，用户将无法使用其移动设备执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="09d19-p136">Set to the default, it allows a user to use VoIP to make or receive phone or video calls on their mobile device. When set to False, your users won't be able to use their mobile device to do either of those things.</span></span>  <br/> |<span data-ttu-id="09d19-298">True</span><span class="sxs-lookup"><span data-stu-id="09d19-298">True</span></span>  <br/> |
|<span data-ttu-id="09d19-299">IP 音频需要 WiFi</span><span class="sxs-lookup"><span data-stu-id="09d19-299">Require WiFi for IP Audio</span></span>  <br/> |<span data-ttu-id="09d19-300">RequireWiFiForIPAudio</span><span class="sxs-lookup"><span data-stu-id="09d19-300">RequireWiFiForIPAudio</span></span>  <br/> |<span data-ttu-id="09d19-p137">定义客户端是否需要通过 WiFi 而不是手机数据网络拨打和接听 VoIP 电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。</span><span class="sxs-lookup"><span data-stu-id="09d19-p137">Defines whether a client will need to make and receive calls over VoIP on WiFi instead of a cellular data network. If it's set to True, your users will only be able to make and receive VoIP calls when they're connected via WiFi.</span></span>  <br/> |<span data-ttu-id="09d19-303">False</span><span class="sxs-lookup"><span data-stu-id="09d19-303">False</span></span>  <br/> |
|<span data-ttu-id="09d19-304">IP 视频需要 WiFi</span><span class="sxs-lookup"><span data-stu-id="09d19-304">Require WiFi for IP Video</span></span>  <br/> |<span data-ttu-id="09d19-305">RequireWiFiForIPVideo</span><span class="sxs-lookup"><span data-stu-id="09d19-305">RequireWiFiForIPVideo</span></span>  <br/> |<span data-ttu-id="09d19-p138">定义客户端是否需要通过 WiFi 而不是手机数据网络拨打和接听视频电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。</span><span class="sxs-lookup"><span data-stu-id="09d19-p138">Defines whether a client will need to make and receive video calls on WiFi instead of a cellular data network. If it's set to True, your users will only be able to make and receive VoIP calls when they're connected via WiFi.</span></span>  <br/> |<span data-ttu-id="09d19-308">False</span><span class="sxs-lookup"><span data-stu-id="09d19-308">False</span></span>  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a><span data-ttu-id="09d19-309">未启用企业语音的用户能否使用“单击以加入”来加入会议？</span><span class="sxs-lookup"><span data-stu-id="09d19-309">Should users who aren't enabled for Enterprise Voice be able to use Click to Join to join conferences?</span></span>

<span data-ttu-id="09d19-310">对于用户有权访问移动功能和单位电话呼叫，它们需要为启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="09d19-310">For users to have access to Mobility features and Call via Work, they need to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="09d19-311">不过，即使没有为他们启用此功能，他们仍可以通过单击其移动设备上的链接来加入会议，但前提是为其分配了适当的语音策略。</span><span class="sxs-lookup"><span data-stu-id="09d19-311">But even if they aren't enabled, they can still join conferences by clicking on a link on their mobile device, but only if they have an appropriate Voice policy assigned to them.</span></span> <span data-ttu-id="09d19-312">你可以：</span><span class="sxs-lookup"><span data-stu-id="09d19-312">You can either:</span></span>
  
- <span data-ttu-id="09d19-313">向这些用户分配特定的语音策略，或者</span><span class="sxs-lookup"><span data-stu-id="09d19-313">assign a specific Voice policy to these users, or,</span></span>
    
- <span data-ttu-id="09d19-314">确保全局策略或站点级别的策略存在并且应用于这些用户。</span><span class="sxs-lookup"><span data-stu-id="09d19-314">make sure that a global policy or site-level policy exists and applies to them.</span></span>
    
<span data-ttu-id="09d19-315">不管使用哪种方法，你分配的语音策略必须具有公用电话交换网 (PSTN) 用法记录和定义用户为加入会议而将拨出到的区域的路由。</span><span class="sxs-lookup"><span data-stu-id="09d19-315">Either way, the Voice policy you assign needs to have public switched telephone network (PSTN) usage records and routes that will define where your users will be able to dial out to join conferences.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09d19-316">移动用户要加入到使用单击需要语音策略，以及相关的 PSTN 用法记录和语音路由，因为当他们单击其移动设备上的链接时，会导致从 Skype 业务服务器出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="09d19-316">Mobile users who want to use Click to Join require a Voice policy, along with the related PSTN usage records and voice routes, because when they click on that link on their mobile devices, an outbound call from Skype for Business Server will be the result.</span></span> 
  

