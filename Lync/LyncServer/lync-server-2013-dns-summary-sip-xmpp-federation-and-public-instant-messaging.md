---
title: DNS 摘要-SIP、XMPP 联合身份验证和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 253a00a07d1d76e77c9a753f6442151beda7c801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="6d267-102">Lync Server 2013 中的 DNS 摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="6d267-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d267-103">_**上次修改的主题：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="6d267-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="6d267-104">定义与 Office 通信服务器或 Lync Server 合作伙伴的联合身份验证所需的域名系统（DNS）记录由您决定允许其他视角合作伙伴对您的域进行自动 DNS 发现。</span><span class="sxs-lookup"><span data-stu-id="6d267-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="6d267-105">如果发布\_sipfederationtls。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="6d267-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="6d267-106">\* \<SIP 域名\> \*SRV 记录，任何其他 SIP 联盟域都将能够 "发现" 你的联盟。</span><span class="sxs-lookup"><span data-stu-id="6d267-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="6d267-107">您可以通过使用 Lync Server 控制面板中的 "允许域和阻止域" 设置，或者通过使用 Lync Server 命令行管理程序和**Get**、 **Set**、 **New**、 **CsAllowedDomain**和 **-CsBlockedDomain** PowerShell cmdlet 来控制哪些联盟域可以与您通信。</span><span class="sxs-lookup"><span data-stu-id="6d267-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="6d267-108">有关如何配置这些设置以及如何使用 PowerShell cmdlet 的其他信息，请参阅本主题结尾的**相关主题**。</span><span class="sxs-lookup"><span data-stu-id="6d267-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="6d267-109">DNS 记录摘要表描述开放或可发现联盟所需要的条目。</span><span class="sxs-lookup"><span data-stu-id="6d267-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="6d267-110">如果您不想实现联合发现，则可以决定不配置\_sipfederationtls。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="6d267-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="6d267-111">*SIP 域名\> \<*</span><span class="sxs-lookup"><span data-stu-id="6d267-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6d267-112">在某些特定情况下，您必须具有 _sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="6d267-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="6d267-113"><EM> &lt;SIP 域名&gt; </EM>SRV 记录，但不希望具有可检测到的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="6d267-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="6d267-114">其中一种情况是，您已经为用户部署了移动性。</span><span class="sxs-lookup"><span data-stu-id="6d267-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="6d267-115">移动推送通知 clearinghouse （PNCH）是一种特殊类型的联盟，用于 Apple iPhone 或 iPad 上使用 lync 2010 移动客户端或使用 lync 2010 移动客户端或 Windows Phone 的 Microsoft Lync Mobile 客户端或 Lync 2013 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="6d267-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="6d267-116">如果同时部署了移动性和 PNCH，则需要使用 _sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="6d267-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="6d267-117"><EM> &lt;SIP 域名&gt; </EM>SRV 记录在移动性和推送通知的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="6d267-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="6d267-118">若要缓解此问题并控制可发现性，请清除设置“启用合作伙伴域发现”<STRONG></STRONG>以关闭发现功能。</span><span class="sxs-lookup"><span data-stu-id="6d267-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="6d267-119">若要为您的部署配置可扩展消息和状态协议（XMPP），请在外部 DNS 服务器中创建两个域名系统（DNS）记录，以将这些记录解析为您的边缘服务器或边缘池的访问边缘服务。</span><span class="sxs-lookup"><span data-stu-id="6d267-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="6d267-120">为公共即时消息连接配置域名系统（DNS）时，将会发现支持外部用户的配置将支持公用 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="6d267-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="6d267-121">如果已配置了边缘服务器或边缘池，则应具有支持公用 IM 连接所必需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="6d267-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="6d267-122">DNS 摘要-SIP 联盟，包括公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="6d267-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d267-123">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="6d267-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="6d267-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="6d267-124">FQDN</span></span></th>
<th><span data-ttu-id="6d267-125">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="6d267-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="6d267-126">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="6d267-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d267-127">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="6d267-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="6d267-128">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="6d267-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6d267-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6d267-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6d267-130">访问边缘服务外部接口，将联合身份验证自动 DNS 发现到其他潜在联合合作伙伴，并将其称为 "允许的 SIP 域" （在以前的版本中称为 "增强联盟"）。根据需要对启用了 Lync 的用户的所有 SIP 域重复此操作</span><span class="sxs-lookup"><span data-stu-id="6d267-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="6d267-131">移动性和推送通知交换所需要此 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="6d267-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="6d267-132">在有多个 SIP 域的情况下，为将拥有 Lync 移动客户端的每个域创建并发布一个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="6d267-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="6d267-133">如果部署支持的每个 SIP 域没有明确的 SRV 记录，则推送通知服务和 Apple 推送通知服务可能无法按预期运行。</span><span class="sxs-lookup"><span data-stu-id="6d267-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="6d267-134">DNS 摘要-可扩展消息传递和状态协议（XMPP）</span><span class="sxs-lookup"><span data-stu-id="6d267-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d267-135">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="6d267-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="6d267-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="6d267-136">FQDN</span></span></th>
<th><span data-ttu-id="6d267-137">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="6d267-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="6d267-138">映射目标/注释</span><span class="sxs-lookup"><span data-stu-id="6d267-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d267-139">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="6d267-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="6d267-140">_xmpp-_tcp .com</span><span class="sxs-lookup"><span data-stu-id="6d267-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6d267-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6d267-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6d267-142">访问边缘服务或边缘池上的 XMPP 代理外部接口。根据需要对启用了 Lync 的用户使用通过全局策略、用户所在的网站策略或应用于 XMPP 联系人的外部访问策略的配置，对所有内部 SIP 域重复此操作。启用了 Lync 的用户。</span><span class="sxs-lookup"><span data-stu-id="6d267-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="6d267-143">还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。</span><span class="sxs-lookup"><span data-stu-id="6d267-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="6d267-144">有关其他详细信息，请参阅<strong>另请参阅</strong>主题中的主题</span><span class="sxs-lookup"><span data-stu-id="6d267-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d267-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="6d267-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6d267-146">xmpp.contoso.com（举例）</span><span class="sxs-lookup"><span data-stu-id="6d267-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="6d267-147">边缘服务器或边缘池托管 XMPP 代理上的访问边缘服务的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="6d267-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="6d267-148">指向承载 XMPP 代理服务的访问边缘服务或边缘池。</span><span class="sxs-lookup"><span data-stu-id="6d267-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="6d267-149">一般而言，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录</span><span class="sxs-lookup"><span data-stu-id="6d267-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d267-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d267-150">See Also</span></span>


[<span data-ttu-id="6d267-151">在 Lync Server 2013 中设置 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="6d267-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="6d267-152">在 Lync Server 2013 中配置推送通知</span><span class="sxs-lookup"><span data-stu-id="6d267-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="6d267-153">在 Lync Server 2013 中启用或禁用联盟伙伴发现</span><span class="sxs-lookup"><span data-stu-id="6d267-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="6d267-154">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="6d267-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="6d267-155">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="6d267-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="6d267-156">在 Lync Server 2013 中管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="6d267-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

