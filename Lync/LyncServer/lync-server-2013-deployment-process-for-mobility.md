---
title: Lync Server 2013：移动性部署过程
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
ms.openlocfilehash: 337e85520cb2a285f4e4743837aafa4136c89f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="8b416-102">Lync Server 2013 中的移动性部署过程</span><span class="sxs-lookup"><span data-stu-id="8b416-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b416-103">_**上次修改的主题：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="8b416-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="8b416-104">本节介绍部署 Lync Server 2013 移动功能所需的步骤序列。</span><span class="sxs-lookup"><span data-stu-id="8b416-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="8b416-105">移动功能部署过程</span><span class="sxs-lookup"><span data-stu-id="8b416-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b416-106">阶段</span><span class="sxs-lookup"><span data-stu-id="8b416-106">Phase</span></span></th>
<th><span data-ttu-id="8b416-107">步骤</span><span class="sxs-lookup"><span data-stu-id="8b416-107">Steps</span></span></th>
<th><span data-ttu-id="8b416-108">Permissions</span><span class="sxs-lookup"><span data-stu-id="8b416-108">Permissions</span></span></th>
<th><span data-ttu-id="8b416-109">部署文档</span><span class="sxs-lookup"><span data-stu-id="8b416-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b416-110">创建域名系统 (DNS) 记录</span><span class="sxs-lookup"><span data-stu-id="8b416-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8b416-111">创建内部 DNS CNAME 或 A （host，如果 IPv6，AAAA）记录以解析内部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="8b416-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="8b416-112">创建外部 DNS CNAME 或 A （host，如果 IPv6，AAAA）记录以解析外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="8b416-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8b416-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="8b416-113">Domain Admins</span></span></p>
<p><span data-ttu-id="8b416-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="8b416-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="8b416-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">在 Lync Server 2013 中为自动发现服务创建 DNS 记录</a></span><span class="sxs-lookup"><span data-stu-id="8b416-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-116">修改证书</span><span class="sxs-lookup"><span data-stu-id="8b416-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="8b416-117">向以下证书添加使用者替代名称条目以支持移动用户的安全连接：</span><span class="sxs-lookup"><span data-stu-id="8b416-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b416-118">控制器证书</span><span class="sxs-lookup"><span data-stu-id="8b416-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="8b416-119">前端池证书</span><span class="sxs-lookup"><span data-stu-id="8b416-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="8b416-120">反向代理证书</span><span class="sxs-lookup"><span data-stu-id="8b416-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8b416-121">本地管理员</span><span class="sxs-lookup"><span data-stu-id="8b416-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="8b416-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改证书的移动性</a></span><span class="sxs-lookup"><span data-stu-id="8b416-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-123">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="8b416-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8b416-124">将利用使用者替代名称更新的证书分配给安全套接字层 (SSL) 侦听器。</span><span class="sxs-lookup"><span data-stu-id="8b416-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="8b416-125">重新配置外部自动发现服务 URL 的 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="8b416-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="8b416-126">请确保前端池上的外部 Lync Server 2013 Web 服务 URL 存在 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="8b416-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="8b416-127">或</span><span class="sxs-lookup"><span data-stu-id="8b416-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="8b416-128">如果选择将 HTTP 用于初始自动发现请求，并且不更新证书上的主题备用名称列表，请为端口 80 HTTP 配置新的 web 发布规则或重新配置现有发布规则。</span><span class="sxs-lookup"><span data-stu-id="8b416-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8b416-129">本地管理员</span><span class="sxs-lookup"><span data-stu-id="8b416-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="8b416-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中配置反向代理以实现移动功能</a></span><span class="sxs-lookup"><span data-stu-id="8b416-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-131">使用 Mcx 移动服务测试 Lync 2010 Mobile 的移动部署</span><span class="sxs-lookup"><span data-stu-id="8b416-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="8b416-132">运行 <strong>Test-CsMcxP2PIM</strong> 以测试将即时消息从一个用户发送给另一个用户的情况。</span><span class="sxs-lookup"><span data-stu-id="8b416-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="8b416-133">有关选项的完整列表，请参阅 Lync Server 命令行管理程序 cmdlet 文档中的<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-csmcxp2pim</a> 。</span><span class="sxs-lookup"><span data-stu-id="8b416-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="8b416-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8b416-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8b416-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证移动性部署</a></span><span class="sxs-lookup"><span data-stu-id="8b416-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-136">使用 UCWA Web 组件测试 Lync 2013 移动客户端的移动性部署</span><span class="sxs-lookup"><span data-stu-id="8b416-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="8b416-137">使用<strong>test-csucwaconference</strong> cmdlet 测试并验证预定义的测试用户或一对实际用户是否可以使用 UCWA 创建和参与会议。</span><span class="sxs-lookup"><span data-stu-id="8b416-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="8b416-138">有关选项的完整列表，请参阅 Lync Server 命令行管理程序 cmdlet 文档中的<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-csucwaconference</a> 。</span><span class="sxs-lookup"><span data-stu-id="8b416-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="8b416-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8b416-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8b416-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证移动性部署</a></span><span class="sxs-lookup"><span data-stu-id="8b416-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-141">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="8b416-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8b416-142">对于 Lync Server 2013 边缘服务器，添加 Lync Server online 承载提供程序并配置托管提供程序联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="8b416-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="8b416-143">对于 Lync Server 2010 边缘服务器，添加 Lync Server online 承载提供程序并配置托管提供程序联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="8b416-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="8b416-144">对于 Office 通信服务器 2007 R2 边缘服务器，添加联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="8b416-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="8b416-145">如果您希望通过 Wi-Fi 网络支持推送通知，请为 TCP 端口 5223 配置防火墙出站规则。</span><span class="sxs-lookup"><span data-stu-id="8b416-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="8b416-146">使用 <strong>Set-CsPushNotificationConfiguration</strong> cmdlet 启用 Apple 推送通知服务 (APNS) 和 Microsoft 推送通知服务 (MPNS) 的推送通知。</span><span class="sxs-lookup"><span data-stu-id="8b416-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="8b416-147">默认情况下，此功能已禁用。</span><span class="sxs-lookup"><span data-stu-id="8b416-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="8b416-148">使用 <strong>Test-CsFederatedPartner</strong> cmdlet 测试联盟配置，并使用 <strong>Test-CsMCXPushNotification</strong> cmdlet 测试推送通知。</span><span class="sxs-lookup"><span data-stu-id="8b416-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8b416-149">推送通知用于 Apple 设备和 Windows Phone 上的 Lync 2010 移动客户端</span><span class="sxs-lookup"><span data-stu-id="8b416-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="8b416-150">仅 Windows Phone 上的 Lync 2013 移动客户端需要推送通知</span><span class="sxs-lookup"><span data-stu-id="8b416-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="8b416-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8b416-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="8b416-152"><a href="lync-server-2013-configuring-for-push-notifications.md">在 Lync Server 2013 中配置推送通知</a></span><span class="sxs-lookup"><span data-stu-id="8b416-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-153">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="8b416-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="8b416-154">使用<strong>set-csmobilitypolicy</strong> cmdlet 可以允许或禁止：</span><span class="sxs-lookup"><span data-stu-id="8b416-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b416-155">通过工作进行呼叫</span><span class="sxs-lookup"><span data-stu-id="8b416-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="8b416-156">启用 IP 音频和 IP 视频</span><span class="sxs-lookup"><span data-stu-id="8b416-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="8b416-157">要求提供 IP 音频和/或 IP 视频的 WiFi</span><span class="sxs-lookup"><span data-stu-id="8b416-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8b416-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8b416-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8b416-159"><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中配置移动策略</a></span><span class="sxs-lookup"><span data-stu-id="8b416-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

