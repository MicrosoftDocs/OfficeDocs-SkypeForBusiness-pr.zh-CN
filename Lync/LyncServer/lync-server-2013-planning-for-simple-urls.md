---
title: Lync Server 2013：规划简单 URL
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="de804-102">在 Lync Server 2013 中规划简单 URL</span><span class="sxs-lookup"><span data-stu-id="de804-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de804-103">_**主题上次修改时间：** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="de804-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="de804-104">简单的 Url 使你的用户加入会议更容易，并且让你的管理员更容易获得 Lync Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="de804-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="de804-105">Lync 服务器支持三个简单的 Url：</span><span class="sxs-lookup"><span data-stu-id="de804-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="de804-106">"**开会**" 用作网站或组织中的所有会议的基本 URL。</span><span class="sxs-lookup"><span data-stu-id="de804-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="de804-107">一个 "匹配" 简单 URL 的示例https://meet.contoso.com是。</span><span class="sxs-lookup"><span data-stu-id="de804-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="de804-108">特定会议的 URL 可能是https://meet.contoso.com/ *username*/7322994。</span><span class="sxs-lookup"><span data-stu-id="de804-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="de804-109">通过 "满足简单 URL"，加入会议的链接易于理解，并且易于沟通和分发。</span><span class="sxs-lookup"><span data-stu-id="de804-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="de804-110">通过**拨入功能**，可以访问 "电话拨入式会议设置" 网页。</span><span class="sxs-lookup"><span data-stu-id="de804-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="de804-111">此页面显示会议拨入号码，其中包含其可用语言、分配的会议信息（即，对于不需要安排的会议）和会议 DTMF 控件，并支持个人识别码的管理（PIN）和分配的会议信息。</span><span class="sxs-lookup"><span data-stu-id="de804-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="de804-112">拨入式简单 URL 包含在所有会议邀请中，以便希望拨入会议的用户可以访问必要的电话号码和 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="de804-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="de804-113">拨入式简单 URL 的示例是https://dialin.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="de804-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="de804-114">**管理员**可快速访问 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="de804-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="de804-115">在你组织的防火墙内的任何计算机中，管理员可以通过在浏览器中键入管理员简单的 URL 来打开 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="de804-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="de804-116">管理员简单的 URL 是您的组织内部的。</span><span class="sxs-lookup"><span data-stu-id="de804-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="de804-117">管理员简单的 URL 的一个示例是https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="de804-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="de804-118">简单的 URL 范围</span><span class="sxs-lookup"><span data-stu-id="de804-118">Simple URL Scope</span></span>

<span data-ttu-id="de804-119">你可以将简单 Url 配置为具有全局范围，或者你可以为你的组织中的每个中心网站指定不同的简单 Url。</span><span class="sxs-lookup"><span data-stu-id="de804-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="de804-120">如果同时指定全局范围简单 URL 和网站范围简单 URL，则网站范围的简单 URL 优先。</span><span class="sxs-lookup"><span data-stu-id="de804-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="de804-121">在大多数情况下，我们建议你仅在全局级别设置简单的 Url，以便用户的 "满足简单 URL" 从一个网站移动到另一个网站时不会更改。</span><span class="sxs-lookup"><span data-stu-id="de804-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="de804-122">例外情况是需要对不同站点上的电话拨入用户使用不同电话号码的组织。</span><span class="sxs-lookup"><span data-stu-id="de804-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="de804-123">请注意，如果在网站上将一个简单的 URL （如拨入式简单 URL）设置为网站级简单 URL，则还必须将该网站上的其他简单 Url 设置为网站级别。</span><span class="sxs-lookup"><span data-stu-id="de804-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de804-124">如果你选择使用网站范围简单的 Url，你的用户将无法在不同网站中的前端池之间移动，并且这些用户无需重新计划所有计划会议，因为会议的简单 Url 在网站之间不同。</span><span class="sxs-lookup"><span data-stu-id="de804-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="de804-125">这包括故障转移方案，其中备份关系中的池位于不同的网站中。</span><span class="sxs-lookup"><span data-stu-id="de804-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="de804-126">如果需要在部署网站范围内的简单 Url 的网站之间进行故障转移，用户将无法加入其会议，因为 URL 的范围。</span><span class="sxs-lookup"><span data-stu-id="de804-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="de804-127">有关详细信息，请查看<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">CsSimpleUrlConfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="de804-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="de804-128">可以在拓扑生成器中设置全局简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="de804-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="de804-129">若要在网站级别设置简单的 URL，必须使用 CsSimpleURLConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de804-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="de804-130">命名简单 Url</span><span class="sxs-lookup"><span data-stu-id="de804-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="de804-131">有三个推荐选项可用于命名简单 Url。</span><span class="sxs-lookup"><span data-stu-id="de804-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="de804-132">选择哪个选项对您设置 DNS A 记录和支持简单 Url 的证书有何影响。</span><span class="sxs-lookup"><span data-stu-id="de804-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="de804-133">在每个选项中，必须为组织中的每个 SIP 域配置一个 "满足简单 URL"。</span><span class="sxs-lookup"><span data-stu-id="de804-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="de804-134">你始终只需要在整个组织中使用一个简单的 URL 进行拨入，一个用于管理，无论你拥有多少个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="de804-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="de804-135">有关必要的 DNS A 记录和证书的详细信息，请参阅[Lync server 2013 中的简单 url 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)和规划文档中[lync server 2013 内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="de804-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="de804-136">在选项1中，为每个简单的 URL 创建一个新的 SIP 域名。</span><span class="sxs-lookup"><span data-stu-id="de804-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="de804-137">如果使用此选项，则每个简单 URL 都需要一个单独的 DNS A 记录，并且每个 "满足简单 URL" 都必须在证书中命名。</span><span class="sxs-lookup"><span data-stu-id="de804-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="de804-138">简单的 URL 命名选项1</span><span class="sxs-lookup"><span data-stu-id="de804-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de804-139"><strong>简单的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="de804-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="de804-140"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="de804-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de804-141">会议</span><span class="sxs-lookup"><span data-stu-id="de804-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="de804-142">https://meet.contoso.com， https://meet.fabrikam.com等等（组织中的每个 SIP 域一个）</span><span class="sxs-lookup"><span data-stu-id="de804-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de804-143">拨入</span><span class="sxs-lookup"><span data-stu-id="de804-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de804-144">Iis</span><span class="sxs-lookup"><span data-stu-id="de804-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="de804-145">通过选项2，简单 Url 基于域名 lync.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="de804-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="de804-146">因此，只需一个 DNS A 记录即可启用所有三种类型的简单 Url。</span><span class="sxs-lookup"><span data-stu-id="de804-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="de804-147">此 DNS A 记录引用 lync.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="de804-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="de804-148">此外，你的组织中的其他 SIP 域仍需要单独的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="de804-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="de804-149">简单的 URL 命名选项2</span><span class="sxs-lookup"><span data-stu-id="de804-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de804-150"><strong>简单的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="de804-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="de804-151"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="de804-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de804-152">会议</span><span class="sxs-lookup"><span data-stu-id="de804-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="de804-153">https://lync.contoso.com/Meet， https://lync.fabrikam.com/Meet等等（组织中的每个 SIP 域一个）</span><span class="sxs-lookup"><span data-stu-id="de804-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de804-154">拨入</span><span class="sxs-lookup"><span data-stu-id="de804-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de804-155">Iis</span><span class="sxs-lookup"><span data-stu-id="de804-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="de804-156">如果你有多个 SIP 域，而你希望它们具有单独的符合简单的 Url，但希望尽量减少这些简单 Url 的 DNS 记录和证书要求，则选项3非常有用。</span><span class="sxs-lookup"><span data-stu-id="de804-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="de804-157">简单的 URL 命名选项3</span><span class="sxs-lookup"><span data-stu-id="de804-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de804-158"><strong>简单的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="de804-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="de804-159"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="de804-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de804-160">会议</span><span class="sxs-lookup"><span data-stu-id="de804-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de804-161">拨入</span><span class="sxs-lookup"><span data-stu-id="de804-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de804-162">Iis</span><span class="sxs-lookup"><span data-stu-id="de804-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="de804-163">简单的 URL 命名和验证规则</span><span class="sxs-lookup"><span data-stu-id="de804-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="de804-164">拓扑生成器和 Lync Server Management Shell cmdlet 针对你的简单 Url 强制执行几条验证规则。</span><span class="sxs-lookup"><span data-stu-id="de804-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="de804-165">您需要为 "满足" 和 "拨入" 设置简单的 Url，但为 "管理员" 设置一个是可选的。</span><span class="sxs-lookup"><span data-stu-id="de804-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="de804-166">每个 SIP 域都必须具有单独的 "匹配" 的 "匹配" 简单 URL，但对于整个组织，只需一个拨入简单的 url 和一个管理员简单的 URL。</span><span class="sxs-lookup"><span data-stu-id="de804-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="de804-167">组织中的每个简单 URL 都必须具有唯一的名称，并且不能是另一个简单 URL 的前缀（例如，不能将 lync.contoso.com/Meet 设置为您的 "满足简单 url" 和 "lync.contoso.com/Meet/Dialin" 作为拨入简单 URL）。</span><span class="sxs-lookup"><span data-stu-id="de804-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="de804-168">简单的 URL 名称不能包含任何池的 FQDN，也不能包含任何端口信息（例如https://FQDN:88/meet ，不允许）。</span><span class="sxs-lookup"><span data-stu-id="de804-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="de804-169">所有简单的 Url 必须以 https://前缀开头。</span><span class="sxs-lookup"><span data-stu-id="de804-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="de804-170">简单 Url 只能包含字母数字字符（即 a-z、a-z、0-9 和句号（.）。</span><span class="sxs-lookup"><span data-stu-id="de804-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="de804-171">如果使用其他字符，则简单 Url 可能不会按预期工作。</span><span class="sxs-lookup"><span data-stu-id="de804-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="de804-172">在部署后更改简单的 Url</span><span class="sxs-lookup"><span data-stu-id="de804-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="de804-173">如果你在初始部署后更改简单的 URL，你必须知道更改对简单 Url 的 DNS 记录和证书有何影响。</span><span class="sxs-lookup"><span data-stu-id="de804-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="de804-174">如果简单 URL 的基础发生更改，则您还必须更改 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="de804-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="de804-175">例如，从https://lync.contoso.com/Meet https://meet.contoso.com lync.contoso.com 更改为 meet.contoso.com 的基本 URL，因此你需要更改 DNS 记录和证书才能引用 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="de804-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="de804-176">如果将简单 URL 更改https://lync.contoso.com/Meet为 "与https://lync.contoso.com/Meetings"，lync.contoso.com 的基 url 保持不变，因此不需要任何 DNS 或证书更改。</span><span class="sxs-lookup"><span data-stu-id="de804-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="de804-177">但是，当您更改简单的 URL 名称时，必须在每个 Director 和前端服务器上运行**Enable-CsComputer**以注册更改。</span><span class="sxs-lookup"><span data-stu-id="de804-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="de804-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de804-178">See Also</span></span>


[<span data-ttu-id="de804-179">Lync Server 2013 中简单 URL 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="de804-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

