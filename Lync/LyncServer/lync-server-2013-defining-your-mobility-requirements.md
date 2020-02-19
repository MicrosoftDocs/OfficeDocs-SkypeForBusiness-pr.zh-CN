---
title: Lync Server 2013：定义移动性要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15fe7352e4c2c5190bae27febeafcd57a94924f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="f33dd-102">定义 Lync Server 2013 的移动性要求</span><span class="sxs-lookup"><span data-stu-id="f33dd-102">Defining your mobility requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f33dd-103">_**上次修改的主题：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="f33dd-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="f33dd-104">在 Lync Server 2013 移动功能的规划阶段，当你使用 Lync 2010 移动版和 Lync 2013 移动客户端时，应做出决定以确定部署步骤。</span><span class="sxs-lookup"><span data-stu-id="f33dd-104">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="f33dd-105">下面是您必须考虑的决策：</span><span class="sxs-lookup"><span data-stu-id="f33dd-105">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="f33dd-106">**是否要对 Lync 移动客户端使用自动发现功能？**</span><span class="sxs-lookup"><span data-stu-id="f33dd-106">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="f33dd-107">如果要支持自动发现，则需要创建新的内部和外部域名系统（DNS）记录，向前端服务器、控制器和反向代理上的证书添加使用者备用名称，以及修改现有的发布规则在反向代理上。</span><span class="sxs-lookup"><span data-stu-id="f33dd-107">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="f33dd-108">有关详细信息，请参阅[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="f33dd-108">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="f33dd-109">通过自动发现，用户可以从公司网络内部或外部的任何位置自动找到 Lync Server 2013 Web 服务，而无需在其移动设备设置中输入 Url。</span><span class="sxs-lookup"><span data-stu-id="f33dd-109">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="f33dd-110">如果使用手动设置而不是自动发现，移动用户需要手动在其移动设备中输入以下 Url：</span><span class="sxs-lookup"><span data-stu-id="f33dd-110">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="f33dd-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root 用于外部访问</span><span class="sxs-lookup"><span data-stu-id="f33dd-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="f33dd-112">https://\<IntPoolFQDN\>/AutoDiscover/autodiscoverservice/Root for internal access</span><span class="sxs-lookup"><span data-stu-id="f33dd-112">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="f33dd-p102">强烈建议您使用自动发现功能。手动设置主要用于进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="f33dd-p102">We strongly recommend using automatic discovery. The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="f33dd-115">**如果您决定支持自动发现功能，那么您是否愿意使用每个 SIP 域的使用者替代名称更新反向代理上的证书？**</span><span class="sxs-lookup"><span data-stu-id="f33dd-115">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="f33dd-116">如果您具有多个 SIP 域，则更新反向代理上的公共证书的成本会非常高。</span><span class="sxs-lookup"><span data-stu-id="f33dd-116">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="f33dd-117">如果是这种情况，则可以选择实施自动发现，以便初始自动发现服务请求在端口80上使用 HTTP，而不是在端口443上使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="f33dd-117">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="f33dd-118">但是，这并不是推荐的方法。</span><span class="sxs-lookup"><span data-stu-id="f33dd-118">However, this is not the recommended approach.</span></span> <span data-ttu-id="f33dd-119">如果决定选择此替代方法，则无需在反向代理上更新证书，但需要在端口80上为 HTTP 创建 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="f33dd-119">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="f33dd-120">有关更多详细信息，请参阅[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="f33dd-120">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="f33dd-121">**是希望同时在企业网络的内部和外部支持 Lync 移动客户端，还是希望仅在企业网络内部支持这些客户端？**</span><span class="sxs-lookup"><span data-stu-id="f33dd-121">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="f33dd-p104">如果您希望同时在网络的内部和外部支持移动客户端，则移动设备可从任意位置访问移动功能。默认配置为，同时在企业网络的内部和外部支持客户端。</span><span class="sxs-lookup"><span data-stu-id="f33dd-p104">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location. The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="f33dd-124">尽管默认配置允许移动客户端通信通过外部网站，但您可以将移动客户端通信限制在内部企业网络内。</span><span class="sxs-lookup"><span data-stu-id="f33dd-124">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="f33dd-125">如果您将通信限制在内部网络内，则用户只有在位于网络内部时才能在其移动设备上使用 Lync 移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="f33dd-125">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="f33dd-126">有关使用 Mcx 移动服务和 Lync 2010 Mobile 支持移动性的部署，请运行**CsMcxConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f33dd-126">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="f33dd-127">若要将移动功能设置为仅供内部使用，请使用类似于以下的命令：</span><span class="sxs-lookup"><span data-stu-id="f33dd-127">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f33dd-128">UCWA 不需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="f33dd-128">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="f33dd-129">UCWA 没有等效的仅内部配置。</span><span class="sxs-lookup"><span data-stu-id="f33dd-129">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f33dd-130">如果使用的是 Lync Server 2013&nbsp;前端服务器或前端池，并且没有任何 Lync server 2010&nbsp;前端服务器或前端池，则不<STRONG>需要基于 cookie 的持久性</STRONG>。 <STRONG></STRONG></span><span class="sxs-lookup"><span data-stu-id="f33dd-130">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="f33dd-131">如果需要保留任何 Lync Server 2010&nbsp;前端服务器或前端池，则在 Lync server 2010 中的相同规则仍适用于基于 cookie 的持久性。</span><span class="sxs-lookup"><span data-stu-id="f33dd-131">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="f33dd-132">**是否希望支持针对 Apple iOS 设备和 Windows Phone 的推送通知？**</span><span class="sxs-lookup"><span data-stu-id="f33dd-132">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="f33dd-133">如果您支持推送通知，则受支持的 Apple iOS 设备和 Windows Phone 将收到在移动应用程序处于非活动状态时所发生的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="f33dd-133">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="f33dd-134">您必须将您的边缘服务器配置为与基于云的 Lync Server 推送通知服务（位于 Lync Online 数据中心中）具有联合身份验证关系，并运行 cmdlet 以启用推送通知。</span><span class="sxs-lookup"><span data-stu-id="f33dd-134">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="f33dd-135">如果要通过 Wlan 网络支持推送通知，除了通过移动设备提供商的3G 或数据网络支持推送通知之外，还必须在企业版 Wi-fi 网络上打开出站端口5223。</span><span class="sxs-lookup"><span data-stu-id="f33dd-135">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="f33dd-136">通过在 Wi-Fi 网络中支持推送通知，可支持仅使用 Wi-Fi 的移动设备和室内接收能力较差的移动设备。</span><span class="sxs-lookup"><span data-stu-id="f33dd-136">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f33dd-137">仅当支持运行 Lync 2010 移动客户端的 Apple 设备时，才需要打开端口 TCP 5223。</span><span class="sxs-lookup"><span data-stu-id="f33dd-137">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="f33dd-138">如果不支持推送通知，Apple 移动设备和 Windows phone 的用户将找不到有关在移动应用程序处于非活动状态时出现的事件（如即时消息邀请或丢失的邮件）。</span><span class="sxs-lookup"><span data-stu-id="f33dd-138">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f33dd-139">Apple 设备上的 Lync 2013 移动客户端不需要推送通知。</span><span class="sxs-lookup"><span data-stu-id="f33dd-139">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="f33dd-140">Windows Phone 上的 Lync 2013 移动客户端使用推送通知。</span><span class="sxs-lookup"><span data-stu-id="f33dd-140">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="f33dd-141">对推送通知和推送通知交换所做的规划对于不能运行 Lync 2013 移动客户端的 Windows Phone 和 Apple 设备上的 Lync Mobile 保持不变。</span><span class="sxs-lookup"><span data-stu-id="f33dd-141">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="f33dd-142">**您是否希望所有用户都有权访问移动功能，或者是否希望能够指定哪些用户有权访问这些功能？**</span><span class="sxs-lookup"><span data-stu-id="f33dd-142">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="f33dd-143">此表介绍了 Lync Server 2013 中用户可用的功能。</span><span class="sxs-lookup"><span data-stu-id="f33dd-143">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="f33dd-144">默认值允许通过工作呼叫，允许 IP 语音（VoIP），并启用移动性。</span><span class="sxs-lookup"><span data-stu-id="f33dd-144">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="f33dd-145">下面是一组完整的可用选项：</span><span class="sxs-lookup"><span data-stu-id="f33dd-145">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="f33dd-146">功能/参数名称/范围（策略参数名称可能不同）</span><span class="sxs-lookup"><span data-stu-id="f33dd-146">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="f33dd-147">说明</span><span class="sxs-lookup"><span data-stu-id="f33dd-147">Description</span></span></th>
    <th><span data-ttu-id="f33dd-148">引入</span><span class="sxs-lookup"><span data-stu-id="f33dd-148">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="f33dd-149">启用移动性</span><span class="sxs-lookup"><span data-stu-id="f33dd-149">Enable Mobility</span></span></p>
    <p><span data-ttu-id="f33dd-150">参数名称：<code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="f33dd-150">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="f33dd-151">作用域：全局/站点/用户</span><span class="sxs-lookup"><span data-stu-id="f33dd-151">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-152">用于控制安装了 Lync Mobile 的给定范围内用户的管理设置，如果将策略设置为 False，则用户将无法登录到客户端。</span><span class="sxs-lookup"><span data-stu-id="f33dd-152">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="f33dd-153">默认设置为 True。</span><span class="sxs-lookup"><span data-stu-id="f33dd-153">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-154">Lync Server 2010 的累积更新：11月2011</span><span class="sxs-lookup"><span data-stu-id="f33dd-154">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="f33dd-155">启用外部语音</span><span class="sxs-lookup"><span data-stu-id="f33dd-155">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="f33dd-156">参数名称：<code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="f33dd-156">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="f33dd-157">作用域：全局/站点/用户</span><span class="sxs-lookup"><span data-stu-id="f33dd-157">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-158">控制用户在工作中使用呼叫的能力，这是一项功能，允许用户使用其工作电话号码而不是移动电话号码拨打和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="f33dd-158">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="f33dd-159">如果设置为 False，则用户将无法使用其移动设备上的工作电话号码拨打或接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="f33dd-159">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="f33dd-160">默认设置为 True</span><span class="sxs-lookup"><span data-stu-id="f33dd-160">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-161">Lync Server 2010 的累积更新：11月2011</span><span class="sxs-lookup"><span data-stu-id="f33dd-161">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="f33dd-162">启用 IP 音频和视频</span><span class="sxs-lookup"><span data-stu-id="f33dd-162">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="f33dd-163">参数名称：<code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="f33dd-163">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="f33dd-164">作用域：全局/站点/用户</span><span class="sxs-lookup"><span data-stu-id="f33dd-164">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-165">控制用户是否可以在其移动设备上使用 VoIP 发出或接收语音或视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="f33dd-165">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="f33dd-166">如果设置为 False，则用户将无法在其设备上进行或接收 VoIP 或视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="f33dd-166">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="f33dd-167">默认设置为 True。</span><span class="sxs-lookup"><span data-stu-id="f33dd-167">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-168">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f33dd-168">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="f33dd-169">需要 IP 音频的 WiFi</span><span class="sxs-lookup"><span data-stu-id="f33dd-169">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="f33dd-170">参数名称：<code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="f33dd-170">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="f33dd-171">作用域：全局/站点/用户</span><span class="sxs-lookup"><span data-stu-id="f33dd-171">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-172">此设置定义客户端是否需要在 WiFi （而不是手机数据网络）上拨打和接听 VoIP 进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="f33dd-172">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="f33dd-173">如果设置为 True，则仅当连接到 WiFi 网络时，用户才可以拨打和接听 VoIP 呼叫。</span><span class="sxs-lookup"><span data-stu-id="f33dd-173">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="f33dd-174">默认设置为 False。</span><span class="sxs-lookup"><span data-stu-id="f33dd-174">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-175">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f33dd-175">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="f33dd-176">IP 视频需要 WiFi</span><span class="sxs-lookup"><span data-stu-id="f33dd-176">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="f33dd-177">参数名称：<code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="f33dd-177">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="f33dd-178">作用域：全局/站点/用户</span><span class="sxs-lookup"><span data-stu-id="f33dd-178">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-179">此设置定义客户端是否需要在 Wlan 上发出和接收视频呼叫，而不是在手机网络数据网络上进行。</span><span class="sxs-lookup"><span data-stu-id="f33dd-179">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="f33dd-180">如果设置为 True，则用户只能在连接到 Wi-fi 网络时发出和接收视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="f33dd-180">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="f33dd-181">默认设置为 False。</span><span class="sxs-lookup"><span data-stu-id="f33dd-181">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="f33dd-182">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f33dd-182">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="f33dd-183">有关可以配置的策略设置，以及如何管理策略的说明，请参阅[set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)、 [set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)、 [set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant 和 set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)。</span><span class="sxs-lookup"><span data-stu-id="f33dd-183">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="f33dd-184">**是否希望未启用企业语音的用户能够使用“单击以加入”来加入会议？**</span><span class="sxs-lookup"><span data-stu-id="f33dd-184">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="f33dd-185">对于可以访问移动功能和单位电话呼叫功能的用户，必须为他们启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="f33dd-185">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="f33dd-186">但是，如果未启用企业语音的用户可以通过单击其移动设备上的链接来加入会议，前提是他们已向其分配适当的语音策略。</span><span class="sxs-lookup"><span data-stu-id="f33dd-186">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="f33dd-187">您可以为这些用户分配特定的语音策略，也可以确保存在适用于它们的全局策略或网站级别策略。</span><span class="sxs-lookup"><span data-stu-id="f33dd-187">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="f33dd-188">您分配的语音策略必须具有公共交换电话网络（PSTN）使用记录和路由，这些记录定义用户可以拨出以加入会议的区域。</span><span class="sxs-lookup"><span data-stu-id="f33dd-188">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="f33dd-189">有关设置语音策略、PSTN 用法记录和路由的详细信息，请参阅[在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="f33dd-189">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f33dd-190">要使用单击加入的移动用户需要语音策略以及相关的 PSTN 用法记录和语音路由，因为单击移动设备上的链接将导致来自 Lync Server 2013 的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="f33dd-190">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="f33dd-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f33dd-191">See Also</span></span>


[<span data-ttu-id="f33dd-192">Lync Server 2013 中的移动性技术要求</span><span class="sxs-lookup"><span data-stu-id="f33dd-192">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="f33dd-193">在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="f33dd-193">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

