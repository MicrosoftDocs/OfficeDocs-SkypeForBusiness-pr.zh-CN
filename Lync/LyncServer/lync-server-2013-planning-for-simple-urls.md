---
title: Lync Server 2013：规划简单 Url
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36e730aeef637c12102fbf425c04235d72eb382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="c9c95-102">在 Lync Server 2013 中规划简单 Url</span><span class="sxs-lookup"><span data-stu-id="c9c95-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9c95-103">_**上次修改的主题：** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="c9c95-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="c9c95-104">简单 Url 使用户加入会议变得更加容易，并使管理员更轻松地进入 Lync Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="c9c95-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="c9c95-105">Lync Server 支持三个简单的 Url：</span><span class="sxs-lookup"><span data-stu-id="c9c95-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="c9c95-106">\*\*\*\*“会议”用作站点或组织中所有会议的基 URL。</span><span class="sxs-lookup"><span data-stu-id="c9c95-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="c9c95-107">一个符合简单 URL 的示例是https://meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c9c95-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="c9c95-108">特定会议的 URL 可能为https://meet.contoso.com/ *username*/7322994。</span><span class="sxs-lookup"><span data-stu-id="c9c95-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="c9c95-109">通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。</span><span class="sxs-lookup"><span data-stu-id="c9c95-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="c9c95-110">\*\*\*\*“拨入”允许访问“电话拨入式会议设置”网页。</span><span class="sxs-lookup"><span data-stu-id="c9c95-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="c9c95-111">此页显示会议的拨入号码及其可用语言、分配的会议信息（即，对于不需要预定的会议）以及会议中的 DTMF 控制，并支持对个人标识号 (PIN) 和分配的会议信息的管理。</span><span class="sxs-lookup"><span data-stu-id="c9c95-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="c9c95-112">拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="c9c95-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="c9c95-113">拨入式简单 URL 的一个示例是https://dialin.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c9c95-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="c9c95-114">**管理员**可以快速访问 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="c9c95-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="c9c95-115">通过组织的防火墙中的任何计算机，管理员都可以通过在浏览器中键入管理员简单的 URL 来打开 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="c9c95-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="c9c95-116">管理简单 URL 是组织内部的。</span><span class="sxs-lookup"><span data-stu-id="c9c95-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="c9c95-117">管理员简单 URL 的一个示例是https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9c95-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="c9c95-118">简单 URL 作用域</span><span class="sxs-lookup"><span data-stu-id="c9c95-118">Simple URL Scope</span></span>

<span data-ttu-id="c9c95-119">可以将简单 URL 配置为具有 global 作用域，也可以为组织中的每个中央站点指定不同的简单 URL。</span><span class="sxs-lookup"><span data-stu-id="c9c95-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="c9c95-120">如果同时指定全局范围简单 URL 和网站范围简单 URL，则网站范围简单 URL 具有优先权。</span><span class="sxs-lookup"><span data-stu-id="c9c95-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="c9c95-p105">在大多数情况下，我们建议您只设置全局级别的简单 URL，这样，如果从一个站点移至另一个站点，用户的会议简单 URL 不会更改。例外情况是对于不同站点的拨入用户需要使用不同电话号码的组织。请注意，如果要将某个站点上的一个简单 URL（如拨入简单 URL）设置为站点级别的简单 URL，您还必须将该站点上的其他简单 URL 设置为站点级别。</span><span class="sxs-lookup"><span data-stu-id="c9c95-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9c95-124">如果选择使用网站范围的简单 Url，则用户将无法在不同网站中的前端池之间移动，而不会导致这些用户在会议简单 Url 不同的网站之间进行重新计划所有计划会议。</span><span class="sxs-lookup"><span data-stu-id="c9c95-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="c9c95-125">这包括故障转移方案，其中备份关系中的池位于不同的网站中。</span><span class="sxs-lookup"><span data-stu-id="c9c95-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="c9c95-126">如果需要在部署网站范围简单 Url 的网站之间进行故障转移，则用户将无法加入其会议，因为 URL 的范围。</span><span class="sxs-lookup"><span data-stu-id="c9c95-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="c9c95-127">有关详细信息，请检查<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">CsSimpleUrlConfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="c9c95-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="c9c95-128">您可以在拓扑生成器中设置全局简单 Url。</span><span class="sxs-lookup"><span data-stu-id="c9c95-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="c9c95-129">要在站点级别设置简单 URL，必须使用 Set-CsSimpleURLConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c9c95-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="c9c95-130">命名简单 URL</span><span class="sxs-lookup"><span data-stu-id="c9c95-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="c9c95-p108">有三种推荐的选项可用于命名简单 URL。您选择的选项会暗示设置支持简单 URL 的 DNS A 记录和证书的方式。在每个选项中，您必须为组织中的每个 SIP 域配置一个会议简单 URL。</span><span class="sxs-lookup"><span data-stu-id="c9c95-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="c9c95-134">无论具有多少个 SIP 域，整个组织始终只需要一个拨入简单 URL 和一个管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="c9c95-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="c9c95-135">有关所需 DNS A 记录和证书的详细信息，请参阅规划文档中的 lync server 2013 中的[针对简单 url](lync-server-2013-dns-requirements-for-simple-urls.md)和在[lync server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)中的 dns 要求。</span><span class="sxs-lookup"><span data-stu-id="c9c95-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="c9c95-136">在选项 1 中，为每个简单 URL 创建新的 SIP 域名。</span><span class="sxs-lookup"><span data-stu-id="c9c95-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="c9c95-137">如果使用此选项，则需要为每个简单 URL 配置单独的 DNS A 记录，而且必须在证书中命名每个会议简单 URL。</span><span class="sxs-lookup"><span data-stu-id="c9c95-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="c9c95-138">简单 URL 命名选项 1</span><span class="sxs-lookup"><span data-stu-id="c9c95-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9c95-139"><strong>简单 URL</strong></span><span class="sxs-lookup"><span data-stu-id="c9c95-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c9c95-140"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="c9c95-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c95-141">法规</span><span class="sxs-lookup"><span data-stu-id="c9c95-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="c9c95-142">https://meet.contoso.com、 https://meet.fabrikam.com等，依此类推（组织中的每个 SIP 域一个）</span><span class="sxs-lookup"><span data-stu-id="c9c95-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9c95-143">拨入</span><span class="sxs-lookup"><span data-stu-id="c9c95-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c95-144">管理员</span><span class="sxs-lookup"><span data-stu-id="c9c95-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9c95-p109">对于选项 2，简单 URL 基于域名 lync.contoso.com。因此，只需一个可启用全部三种类型简单 URL 的 DNS A 记录。此 DNS A 记录会引用 lync.contoso.com。此外，仍需要为组织中的其他 SIP 域配置单独的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="c9c95-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="c9c95-149">简单 URL 命名选项 2</span><span class="sxs-lookup"><span data-stu-id="c9c95-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9c95-150"><strong>简单 URL</strong></span><span class="sxs-lookup"><span data-stu-id="c9c95-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c9c95-151"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="c9c95-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c95-152">法规</span><span class="sxs-lookup"><span data-stu-id="c9c95-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="c9c95-153">https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meet等，依此类推（组织中的每个 SIP 域一个）</span><span class="sxs-lookup"><span data-stu-id="c9c95-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9c95-154">拨入</span><span class="sxs-lookup"><span data-stu-id="c9c95-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c95-155">管理员</span><span class="sxs-lookup"><span data-stu-id="c9c95-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9c95-156">如果具有许多 SIP 域，并且希望每个 SIP 域具有单独的会议简单 URL，但希望最大程度地减少这些简单 URL 所要求的 DNS 记录和证书，则选项 3 是最有用的。</span><span class="sxs-lookup"><span data-stu-id="c9c95-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="c9c95-157">简单 URL 命名选项 3</span><span class="sxs-lookup"><span data-stu-id="c9c95-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9c95-158"><strong>简单 URL</strong></span><span class="sxs-lookup"><span data-stu-id="c9c95-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c9c95-159"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="c9c95-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c95-160">法规</span><span class="sxs-lookup"><span data-stu-id="c9c95-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9c95-161">拨入</span><span class="sxs-lookup"><span data-stu-id="c9c95-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c95-162">管理员</span><span class="sxs-lookup"><span data-stu-id="c9c95-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="c9c95-163">简单 URL 命名和验证规则</span><span class="sxs-lookup"><span data-stu-id="c9c95-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="c9c95-164">拓扑生成器和 Lync Server 命令行管理程序 cmdlet 对简单 Url 强制实施几种验证规则。</span><span class="sxs-lookup"><span data-stu-id="c9c95-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="c9c95-165">您必须设置会议简单 URL 和拨入简单 URL，但可以选择设置管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="c9c95-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="c9c95-166">每个 SIP 域都必须具有单独的会议简单 URL，但整个组织只需要一个拨入简单 URL 和一个管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="c9c95-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="c9c95-167">组织中的每个简单 URL 必须具有唯一的名称，且不能是其他简单 URL 的前缀（例如，不能将 lync.contoso.com/Meet 设置为会议简单 URL，也不能将 lync.contoso.com/Meet/Dialin 设置为拨入简单 URL）。</span><span class="sxs-lookup"><span data-stu-id="c9c95-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="c9c95-168">简单 URL 名称不能包含任何池的 FQDN，也不能包含任何端口信息（例如， https://FQDN:88/meet不允许）。</span><span class="sxs-lookup"><span data-stu-id="c9c95-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="c9c95-169">所有简单 URL 都必须以 https:// 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="c9c95-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="c9c95-p112">简单 URL 只能包含字母数字字符（即，a-z、A-Z、0-9 和圆点 (.)）。如果使用其他字符，则简单 URL 可能不会正常工作。</span><span class="sxs-lookup"><span data-stu-id="c9c95-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="c9c95-172">部署后更改简单 URL</span><span class="sxs-lookup"><span data-stu-id="c9c95-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="c9c95-173">如果在初始部署后更改简单 URL，您必须注意更改如何影响简单 URL 的 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="c9c95-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="c9c95-174">如果简单 URL 的基础发生更改，则还必须更改 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="c9c95-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="c9c95-175">例如，从https://lync.contoso.com/Meet更改为将https://meet.contoso.com基 URL 从 lync.contoso.com 更改为 meet.contoso.com，因此您需要将 DNS 记录和证书更改为引用 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c9c95-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="c9c95-176">如果将简单 URL 从https://lync.contoso.com/Meet更改为https://lync.contoso.com/Meetings，lync.contoso.com 的基 url 将保持不变，因此不需要任何 DNS 或证书更改。</span><span class="sxs-lookup"><span data-stu-id="c9c95-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="c9c95-177">但是，只要您更改简单的 URL 名称，就必须在每个控制器和前端服务器上运行**CsComputer**以注册更改。</span><span class="sxs-lookup"><span data-stu-id="c9c95-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9c95-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9c95-178">See Also</span></span>


[<span data-ttu-id="c9c95-179">Lync Server 2013 中简单 Url 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="c9c95-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

