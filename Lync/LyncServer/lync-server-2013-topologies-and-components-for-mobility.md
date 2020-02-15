---
title: Lync Server 2013：移动性的拓扑和组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac03d6b98b0b209a50f08e660fe6665b975d2ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="e693f-102">Lync Server 2013 中的移动性拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="e693f-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e693f-103">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="e693f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="e693f-104">为了在移动设备上支持 Lync 移动应用程序，Lync Server 2013 提供了三种服务： Lync Server 2013 Mcx 移动服务、Lync Server 2013 自动发现服务和 Lync Server 2013 推送通知服务。</span><span class="sxs-lookup"><span data-stu-id="e693f-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="e693f-105">Lync Server 2013 的累积更新：二月份2013为 Lync 2013 移动客户端添加了免费的、高级的服务，并通过使用统一通信 Web API 或 UCWA 实现了移动性支持。</span><span class="sxs-lookup"><span data-stu-id="e693f-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="e693f-106">本节简要介绍了这些组件，并标识了支持移动性的 Lync Server 2013 拓扑。</span><span class="sxs-lookup"><span data-stu-id="e693f-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e693f-107">混合部署中也提供了移动服务。</span><span class="sxs-lookup"><span data-stu-id="e693f-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="e693f-108">如果您的用户驻留在联机部署中，则不要求您部署用于支持移动的服务。</span><span class="sxs-lookup"><span data-stu-id="e693f-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="e693f-109">您需要为自动发现服务定义一个设置，以使移动用户能够查找其联机标识。</span><span class="sxs-lookup"><span data-stu-id="e693f-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e693f-110">如果要规划任何外部用户连接（例如，联盟、外部用户访问或移动功能），则必须将边缘服务器与 Standard Edition server 和前端服务器或前端池结合使用。</span><span class="sxs-lookup"><span data-stu-id="e693f-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="e693f-111">Standard Edition server 和前端服务器或前端池不具有使外部用户能够访问内部部署的必要组件，或用于与外部用户进行通信的内部部署。</span><span class="sxs-lookup"><span data-stu-id="e693f-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="e693f-112">对于包括外部用户协作或与内部用户通信的所有方案，包括移动性，必须至少部署一个边缘服务器和一个反向代理。</span><span class="sxs-lookup"><span data-stu-id="e693f-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="e693f-113"><EM>推送通知</EM>使用 Lync Online services （承载推送通知交换所（PNCH））的一种类型的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="e693f-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="e693f-114">推送通知是指在移动设备处于非活动状态时，由应用程序推送到 Apple iPhone、iPad 和 Windows Phone 的声音警报、屏幕警报（文本）和徽章。</span><span class="sxs-lookup"><span data-stu-id="e693f-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="e693f-115">PNCH 从 Lync Server 接收推送通知。</span><span class="sxs-lookup"><span data-stu-id="e693f-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="e693f-116">当 PNCH 收到邮件通知时，PNCH 基于邮件所面向的移动客户端，通过 Apple 推送通知服务或 Lync Server 2013 推送通知服务，将通知转发给移动客户端。</span><span class="sxs-lookup"><span data-stu-id="e693f-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="e693f-117">PNCH 对于这些移动客户端而言是一项必需服务。</span><span class="sxs-lookup"><span data-stu-id="e693f-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="e693f-118">若要联合使用 Lync Online，PNCH 使用边缘服务器和证书来确保机密性和身份验证、策略以及正确配置的域名系统（DNS）记录。</span><span class="sxs-lookup"><span data-stu-id="e693f-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="e693f-119">Nokia Symbian 和基于 Android 的 Lync 移动客户端不使用 PNCH。</span><span class="sxs-lookup"><span data-stu-id="e693f-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="e693f-120">有关规划和部署边缘服务器的详细信息，请参阅在 lync server <A href="lync-server-2013-planning-for-external-user-access.md">2013 中规划外部用户访问</A>和<A href="lync-server-2013-deploying-external-user-access.md">在 lync Server 2013 中部署外部用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="e693f-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="e693f-121">Lync 2013 移动客户端（适用于使用 Lync Server 2013 的累积更新引入的 Apple 设备）：2月2013不再使用推送通知或推送通知交换所（PNCH）。</span><span class="sxs-lookup"><span data-stu-id="e693f-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="e693f-122">Windows Phone 上的 Lync 2013 移动客户端仍使用推送通知和（PNCH）。</span><span class="sxs-lookup"><span data-stu-id="e693f-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="e693f-123">移动组件</span><span class="sxs-lookup"><span data-stu-id="e693f-123">Mobility Components</span></span>

<span data-ttu-id="e693f-124">以下是支持移动的服务：</span><span class="sxs-lookup"><span data-stu-id="e693f-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="e693f-125">**Lync server 2013 统一通信 Web API （UCWA）**   提供了在 Lync Server 2013 中与移动和 Web 客户端进行实时通信的服务。</span><span class="sxs-lookup"><span data-stu-id="e693f-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="e693f-126">当您将 Lync Server 2013 2013 的累积更新部署到前端服务器和控制器时，安装程序会在内部和外部 web 服务（Ucwa）中创建一个虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="e693f-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="e693f-127">作为 Ucwa 虚拟目录一部分的 web 组件接受来自启用 UCWA 的客户端的调用。</span><span class="sxs-lookup"><span data-stu-id="e693f-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="e693f-128">客户端应用通过 REST 界面与状态、联系人、即时消息、VoIP、视频会议和协作进行通信。</span><span class="sxs-lookup"><span data-stu-id="e693f-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="e693f-129">UCWA 使用基于 P GET 的通道向客户端应用发送事件，例如传入呼叫、传入即时消息或邮件。</span><span class="sxs-lookup"><span data-stu-id="e693f-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e693f-130"><EM>REST</EM>或代表性状态传输是一种软件体系结构样式，适用于广泛采用多种形式的分布式系统，非常适合一般情况下的 Web 服务要求。</span><span class="sxs-lookup"><span data-stu-id="e693f-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="e693f-131">**Lync Server 2013 移动服务（Mcx）**   此服务支持移动设备上的 Lync 功能，如即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="e693f-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="e693f-132">移动服务安装在每个池中的每个前端服务器上，以支持移动设备上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="e693f-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="e693f-133">安装 Lync Server 2013 时，会在内部网站和前端服务器上的外部网站下创建一个新的虚拟目录（Mcx）。</span><span class="sxs-lookup"><span data-stu-id="e693f-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e693f-134">Lync Server 2013 with the lync Server 2013 的累积更新：2月2013支持 Lync Server 2011 2010 的累积更新中引入的移动服务（通常称为 Mcx）和 UCWA web 组件。</span><span class="sxs-lookup"><span data-stu-id="e693f-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="e693f-135">在 Lync Server 2013 上，这两种移动服务的组合提供了互操作性并供用户使用 Lync 2010 移动和 Lync 2013 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="e693f-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="e693f-136">**Lync server 2013 自动发现服务**   此服务标识用户的位置，并使移动设备和其他 Lync 客户端能够查找资源（例如 Lync Server 2013 Web 服务的内部和外部 url）以及 Mcx 或 UCWA 的 URL （无论网络位置如何）。</span><span class="sxs-lookup"><span data-stu-id="e693f-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="e693f-137">自动发现使用硬编码的主机名称（lyncdiscoverinternal. 在网络内部的用户; lyncdiscover. 为网络外部用户）和用户的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="e693f-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="e693f-138">它支持使用 HTTP 或 HTTPS 的客户端连接。</span><span class="sxs-lookup"><span data-stu-id="e693f-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="e693f-139">自动发现服务安装在每个前端服务器上和每个池中的每个控制器上，以支持移动设备上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="e693f-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="e693f-140">在安装自动发现服务时，会在前端服务器和控制器上的内部网站和外部网站下创建一个新的虚拟目录（自动发现）。</span><span class="sxs-lookup"><span data-stu-id="e693f-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e693f-141">自动发现服务在此处列出，因为它在提供移动客户端服务时仍是一个关键组件。</span><span class="sxs-lookup"><span data-stu-id="e693f-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="e693f-142">Lync Server 2013 中的自动发现角色已扩展为为所有客户端提供服务。</span><span class="sxs-lookup"><span data-stu-id="e693f-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="e693f-143">有关对自动发现服务进行规划的详细信息，请参阅<A href="lync-server-2013-planning-for-autodiscover.md">在 Lync Server 2013 中规划自动发现</A>。</span><span class="sxs-lookup"><span data-stu-id="e693f-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="e693f-144">**推送通知服务**   此服务是一个基于云的服务，它位于 Lync Online 数据中心。</span><span class="sxs-lookup"><span data-stu-id="e693f-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="e693f-145">当受支持的 Apple iOS 设备或 Windows Phone 上的 Lync 移动应用程序处于非活动状态时，它将无法响应新事件，例如新的即时消息（IM）邀请、错过的即时消息、未接来电或语音邮件，因为这些设备不支持在后台运行的移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="e693f-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="e693f-146">在这些情况下，会将新事件通知（称为*推送通知*）发送到移动设备。</span><span class="sxs-lookup"><span data-stu-id="e693f-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="e693f-147">移动服务将通知发送到基于云的推送通知服务，后者随后将通知发送到 Apple 推送通知服务（APNS）（对于受支持的 Apple iOS 设备）或 Microsoft 推送通知服务（MPNS）（对于 Windows Phone），然后将其发送到移动设备。</span><span class="sxs-lookup"><span data-stu-id="e693f-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="e693f-148">然后，用户可以在移动设备上响应通知以激活应用程序。</span><span class="sxs-lookup"><span data-stu-id="e693f-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="e693f-149">Apple 和 Windows Phone 设备上的 Lync 2010 Mobile 使用推送通知。</span><span class="sxs-lookup"><span data-stu-id="e693f-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="e693f-150">Lync 2013 移动客户端（适用于使用 Lync Server 2013 的累积更新引入的 Apple 设备）：二月2013不再使用推送通知或推送通知交换所（PNCH）。</span><span class="sxs-lookup"><span data-stu-id="e693f-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="e693f-151">下图说明了推送通知服务在使用 UCWA 和 Lync 2013 移动客户端的 Lync Server 2013 拓扑中的适合程度。</span><span class="sxs-lookup"><span data-stu-id="e693f-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="e693f-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="e693f-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="e693f-153">在 Lync Server 2010 的累积更新中引入：11月2011，Mcx 服务为 Lync 2010 移动客户端提供服务。</span><span class="sxs-lookup"><span data-stu-id="e693f-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="e693f-154">下图演示了推送通知服务，因为它适用于使用 Mcx 和 Lync 2010 移动客户端的拓扑。</span><span class="sxs-lookup"><span data-stu-id="e693f-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="e693f-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="e693f-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="e693f-156">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="e693f-156">Supported Topologies</span></span>

<span data-ttu-id="e693f-157">对 Lync Server 2013 应用累积更新：二月份2013添加 UCWA web 组件以支持以下拓扑中的 Lync 2013 移动客户端功能的移动性：</span><span class="sxs-lookup"><span data-stu-id="e693f-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="e693f-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e693f-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="e693f-159">Lync Server 2013 企业版</span><span class="sxs-lookup"><span data-stu-id="e693f-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="e693f-160">边缘服务器可以是 Lync Server 2010 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="e693f-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="e693f-161">没有 Lync Server 2013 累积更新的 Lync Server 2013 部署：2月2013将使用 Mcx 移动服务，并且只能为 Lync 2010 Mobile 提供服务。</span><span class="sxs-lookup"><span data-stu-id="e693f-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e693f-162">移动服务在并置的前端服务器上受支持，后者与具有两个网络接口的中介服务器角色一起使用，但您必须采取相应的步骤来配置这些接口。</span><span class="sxs-lookup"><span data-stu-id="e693f-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="e693f-163">您必须将 IP 地址分配给将作为中介服务器进行通信的特定接口，以及将作为前端服务器进行通信的网络接口 IP。</span><span class="sxs-lookup"><span data-stu-id="e693f-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="e693f-164">您可以在拓扑生成器中执行此操作，方法是为每个服务选择正确的 IP 地址，而不是使用默认值 "<STRONG>使用所有已配置的 ip 地址</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="e693f-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e693f-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e693f-165">See Also</span></span>


[<span data-ttu-id="e693f-166">在 Lync Server 2013 中规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="e693f-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="e693f-167">在 Lync Server 2013 中部署外部用户访问</span><span class="sxs-lookup"><span data-stu-id="e693f-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="e693f-168">在 Lync Server 2013 中规划自动发现</span><span class="sxs-lookup"><span data-stu-id="e693f-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

