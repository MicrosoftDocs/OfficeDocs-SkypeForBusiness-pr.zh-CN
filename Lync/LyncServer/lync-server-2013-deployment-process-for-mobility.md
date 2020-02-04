---
title: Lync Server 2013：移动功能的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f9f7994981a860aaa02d4674d6a3248c3593d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="8fb89-102">Lync Server 2013 中移动功能的部署过程</span><span class="sxs-lookup"><span data-stu-id="8fb89-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fb89-103">_**主题上次修改时间：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="8fb89-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="8fb89-104">本部分介绍部署 Lync Server 2013 移动功能所需步骤的顺序。</span><span class="sxs-lookup"><span data-stu-id="8fb89-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="8fb89-105">移动性部署过程</span><span class="sxs-lookup"><span data-stu-id="8fb89-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fb89-106">阶段</span><span class="sxs-lookup"><span data-stu-id="8fb89-106">Phase</span></span></th>
<th><span data-ttu-id="8fb89-107">步骤</span><span class="sxs-lookup"><span data-stu-id="8fb89-107">Steps</span></span></th>
<th><span data-ttu-id="8fb89-108">权限</span><span class="sxs-lookup"><span data-stu-id="8fb89-108">Permissions</span></span></th>
<th><span data-ttu-id="8fb89-109">部署文档</span><span class="sxs-lookup"><span data-stu-id="8fb89-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fb89-110">创建域名系统（DNS）记录</span><span class="sxs-lookup"><span data-stu-id="8fb89-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8fb89-111">创建内部 DNS CNAME 或 A （host，if IPv6，AAAA）记录来解析内部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="8fb89-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="8fb89-112">创建外部 DNS CNAME 或 A （host，if IPv6，AAAA）记录以解析外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="8fb89-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8fb89-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="8fb89-113">Domain Admins</span></span></p>
<p><span data-ttu-id="8fb89-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="8fb89-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="8fb89-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">在 Lync Server 2013 中为自动发现服务创建 DNS 记录</a></span><span class="sxs-lookup"><span data-stu-id="8fb89-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fb89-116">修改证书</span><span class="sxs-lookup"><span data-stu-id="8fb89-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="8fb89-117">将 "主题备用名称" 条目添加到以下证书以支持移动用户的安全连接：</span><span class="sxs-lookup"><span data-stu-id="8fb89-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="8fb89-118">导演证书</span><span class="sxs-lookup"><span data-stu-id="8fb89-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="8fb89-119">前端池证书</span><span class="sxs-lookup"><span data-stu-id="8fb89-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="8fb89-120">反向代理证书</span><span class="sxs-lookup"><span data-stu-id="8fb89-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8fb89-121">本地管理员</span><span class="sxs-lookup"><span data-stu-id="8fb89-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="8fb89-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改证书以实现移动功能</a></span><span class="sxs-lookup"><span data-stu-id="8fb89-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fb89-123">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="8fb89-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8fb89-124">将使用 "使用者备用名称" 更新的证书分配给安全套接字层（SSL）侦听器。</span><span class="sxs-lookup"><span data-stu-id="8fb89-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="8fb89-125">重新配置外部自动发现服务 URL 的 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="8fb89-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="8fb89-126">请确保你的前端池中的外部 Lync Server 2013 Web 服务 URL 存在 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="8fb89-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="8fb89-127">或</span><span class="sxs-lookup"><span data-stu-id="8fb89-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="8fb89-128">如果你选择将 HTTP 用于初始自动发现请求，并且不更新证书上的使用者备用名称列表，请为端口 80 HTTP 配置新的 web 发布规则或重新配置现有发布规则。</span><span class="sxs-lookup"><span data-stu-id="8fb89-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8fb89-129">本地管理员</span><span class="sxs-lookup"><span data-stu-id="8fb89-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="8fb89-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中配置反向代理以实现移动功能</a></span><span class="sxs-lookup"><span data-stu-id="8fb89-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fb89-131">使用 Mcx 移动服务测试适用于 Lync 2010 Mobile 的移动部署</span><span class="sxs-lookup"><span data-stu-id="8fb89-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="8fb89-132">运行<strong>test-CsMcxP2PIM</strong>以测试将即时消息从一个人发送到另一个人。</span><span class="sxs-lookup"><span data-stu-id="8fb89-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="8fb89-133">有关选项的完整列表，请参阅 Lync Server Management Shell cmdlet 文档中的<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">CsMcxP2PIM</a> 。</span><span class="sxs-lookup"><span data-stu-id="8fb89-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="8fb89-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8fb89-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8fb89-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证您的移动功能部署</a></span><span class="sxs-lookup"><span data-stu-id="8fb89-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fb89-136">使用 UCWA Web 组件测试适用于 Lync 2013 移动客户端的移动部署</span><span class="sxs-lookup"><span data-stu-id="8fb89-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="8fb89-137">使用<strong>CsUcwaConference</strong> cmdlet 测试和验证预定义的测试用户或一对实际用户是否可以使用 UCWA 创建和参与会议。</span><span class="sxs-lookup"><span data-stu-id="8fb89-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="8fb89-138">有关选项的完整列表，请参阅 Lync Server Management Shell cmdlet 文档中的<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">CsUcwaConference</a> 。</span><span class="sxs-lookup"><span data-stu-id="8fb89-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="8fb89-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8fb89-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8fb89-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证您的移动功能部署</a></span><span class="sxs-lookup"><span data-stu-id="8fb89-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fb89-141">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="8fb89-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8fb89-142">对于 Lync Server 2013 Edge 服务器，添加 Lync Server online 托管提供商和配置托管提供商联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="8fb89-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="8fb89-143">对于 Lync Server 2010 Edge 服务器，添加 Lync Server online 托管提供商和配置托管提供商联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="8fb89-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="8fb89-144">对于 Office 通信服务器 2007 R2 Edge 服务器，请添加联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="8fb89-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="8fb89-145">如果想要通过 Wi-fi 网络支持推送通知，请为 TCP 端口5223配置出站防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="8fb89-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="8fb89-146">使用<strong>CsPushNotificationConfiguration</strong> Cmdlet 启用 Apple 推送通知服务（APNS）和 Microsoft 推送通知服务（MPNS）的推送通知。</span><span class="sxs-lookup"><span data-stu-id="8fb89-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="8fb89-147">默认情况下，此功能处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="8fb89-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="8fb89-148">使用<strong>CsFederatedPartner</strong> cmdlet 测试联合身份验证配置和<strong>CsMCXPushNotification</strong> cmdlet 以测试推送通知。</span><span class="sxs-lookup"><span data-stu-id="8fb89-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8fb89-149">推送通知用于 Apple 设备和 Windows Phone 上的 Lync 2010 移动客户端</span><span class="sxs-lookup"><span data-stu-id="8fb89-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="8fb89-150">仅 Windows Phone 上的 Lync 2013 移动客户端需要推送通知</span><span class="sxs-lookup"><span data-stu-id="8fb89-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="8fb89-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8fb89-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="8fb89-152"><a href="lync-server-2013-configuring-for-push-notifications.md">在 Lync Server 2013 中配置推送通知</a></span><span class="sxs-lookup"><span data-stu-id="8fb89-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fb89-153">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="8fb89-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="8fb89-154">将<strong>CsMobilityPolicy</strong> cmdlet 用于允许或禁止：</span><span class="sxs-lookup"><span data-stu-id="8fb89-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="8fb89-155">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="8fb89-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="8fb89-156">启用 IP 音频和 IP 视频</span><span class="sxs-lookup"><span data-stu-id="8fb89-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="8fb89-157">IP 音频和/或 IP 视频需要 WiFi</span><span class="sxs-lookup"><span data-stu-id="8fb89-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8fb89-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8fb89-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8fb89-159"><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中配置移动策略</a></span><span class="sxs-lookup"><span data-stu-id="8fb89-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

