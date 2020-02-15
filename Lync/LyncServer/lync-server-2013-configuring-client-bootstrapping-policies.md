---
title: Lync Server 2013：配置客户端引导策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3827bf913c4108c1105376a6f178598a2fb45a06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="53452-102">在 Lync Server 2013 中配置客户端引导策略</span><span class="sxs-lookup"><span data-stu-id="53452-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53452-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="53452-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="53452-104">组策略管理控制台（GPMC）和组策略对象编辑器是用于管理组策略的工具。</span><span class="sxs-lookup"><span data-stu-id="53452-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="53452-105">Office 组策略管理模板包含 Lync 2013 （ADMX）和 adml （ADML）管理模板，其中包含您为域中的组策略对象配置的基于注册表的策略设置。</span><span class="sxs-lookup"><span data-stu-id="53452-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="53452-106">ADML 文件是特定于语言的对 ADMX 文件的补充。</span><span class="sxs-lookup"><span data-stu-id="53452-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="53452-107">每个 ADMX 和 ADML 文件都包含单个 Office 应用程序的策略设置。</span><span class="sxs-lookup"><span data-stu-id="53452-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="53452-108">有关详细信息，请参阅 Office 2013 文档中的 "Office 2013 管理模板文件（ADMX、ADML）" <http://go.microsoft.com/fwlink/p/?linkid=267516>。</span><span class="sxs-lookup"><span data-stu-id="53452-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="53452-109">对于 Lync 2013，有几个客户端启动策略，在用户首次登录到服务器之前，应考虑进行配置。</span><span class="sxs-lookup"><span data-stu-id="53452-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="53452-110">例如，客户端在登录完成之前应使用的默认服务器和安全模式。</span><span class="sxs-lookup"><span data-stu-id="53452-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="53452-111">在用户登录并开始从服务器接收带内设置设置之前，您可以使用组策略在用户的计算机注册表中建立这些设置。</span><span class="sxs-lookup"><span data-stu-id="53452-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="53452-112">下表列出了可用于 Lync 2013 的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="53452-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="53452-113">Lync 2013 的组策略设置</span><span class="sxs-lookup"><span data-stu-id="53452-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53452-114">组策略设置</span><span class="sxs-lookup"><span data-stu-id="53452-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="53452-115">说明</span><span class="sxs-lookup"><span data-stu-id="53452-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53452-116">指定服务器</span><span class="sxs-lookup"><span data-stu-id="53452-116">Specify Server</span></span><br />
<span data-ttu-id="53452-117">(ConfigurationMode)</span><span class="sxs-lookup"><span data-stu-id="53452-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="53452-118">指定 Lync 2013 如何标识登录期间要使用的传输和服务器。</span><span class="sxs-lookup"><span data-stu-id="53452-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="53452-119">在此设置中，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="53452-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="53452-120">ServerAddressExternal：指定从外部防火墙外部连接时，客户端和联盟联系人使用的服务器名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="53452-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="53452-121">ServerAddressInternal：指定当客户端从组织的防火墙内部进行连接时使用的服务器名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="53452-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="53452-122">Transport：指定传输控制协议（TCP）或传输层安全性（TLS）。</span><span class="sxs-lookup"><span data-stu-id="53452-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53452-123">支持的其他服务器版本</span><span class="sxs-lookup"><span data-stu-id="53452-123">Additional server versions supported</span></span><br />
<span data-ttu-id="53452-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="53452-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="53452-125">指定除了默认情况下受支持的服务器版本之外，Lync Server 2013 将登录到的服务器版本名称的列表。</span><span class="sxs-lookup"><span data-stu-id="53452-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53452-126">禁用登录失败日志的自动上载（DisableAutomaticSendTracing）</span><span class="sxs-lookup"><span data-stu-id="53452-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="53452-127">自动将登录失败日志上传到 Lync Server 进行分析。</span><span class="sxs-lookup"><span data-stu-id="53452-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="53452-128">如果登录成功，则不会自动上载任何日志。</span><span class="sxs-lookup"><span data-stu-id="53452-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="53452-129">如果未配置此策略，则会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="53452-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="53452-130">对于 Lync Online 用户：将自动上载登录失败日志。</span><span class="sxs-lookup"><span data-stu-id="53452-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="53452-131">对于 Lync 本地用户：在上载前向用户显示确认对话框。</span><span class="sxs-lookup"><span data-stu-id="53452-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="53452-132">如果禁用此设置，则会为 Lync 本地和 Lync Online 用户自动将登录日志上载到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="53452-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="53452-133">如果启用此设置，则不会自动上载登录日志。</span><span class="sxs-lookup"><span data-stu-id="53452-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53452-134">禁用 SIP 连接的 HTTP 回退</span><span class="sxs-lookup"><span data-stu-id="53452-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="53452-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="53452-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="53452-136">如果 TLS 或 TCP 不可用，则阻止 Lync Server 尝试使用 HTTP 连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="53452-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="53452-137">默认情况下，Lync 首先尝试使用 TLS 或 TCP 连接到服务器，如果这些传输方法中的两个都不成功，Lync 将尝试使用 HTTP 进行连接。</span><span class="sxs-lookup"><span data-stu-id="53452-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="53452-138">使用此策略可禁止回退 HTTP 连接尝试。</span><span class="sxs-lookup"><span data-stu-id="53452-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53452-139">需要登录凭据</span><span class="sxs-lookup"><span data-stu-id="53452-139">Require logon credentials</span></span><br />
<span data-ttu-id="53452-140">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="53452-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="53452-141">要求用户提供 Lync 的登录凭据，而不是在登录 SIP 服务器期间自动使用 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="53452-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53452-142">禁用服务器版本检查</span><span class="sxs-lookup"><span data-stu-id="53452-142">Disable server version check</span></span><br />
<span data-ttu-id="53452-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="53452-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="53452-144">如果将此策略设置为1，则阻止 Lync 在登录前检查服务器名称和版本。</span><span class="sxs-lookup"><span data-stu-id="53452-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="53452-145">默认情况下，Lync 会在登录前进行这些检查。</span><span class="sxs-lookup"><span data-stu-id="53452-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53452-146">允许使用 BITS 下载通讯簿服务文件</span><span class="sxs-lookup"><span data-stu-id="53452-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="53452-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="53452-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="53452-148">使 Lync 能够使用后台智能传输服务（BITS）下载通讯簿服务文件。</span><span class="sxs-lookup"><span data-stu-id="53452-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53452-149">配置 SIP 安全模式</span><span class="sxs-lookup"><span data-stu-id="53452-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="53452-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="53452-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="53452-151">使 Lync 能够更安全地发送和接收即时消息。</span><span class="sxs-lookup"><span data-stu-id="53452-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="53452-152">此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。</span><span class="sxs-lookup"><span data-stu-id="53452-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="53452-153">如果未配置此策略设置，则 Lync 可以使用任何传输。</span><span class="sxs-lookup"><span data-stu-id="53452-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="53452-154">但是，如果它不使用 TLS，并且如果服务器对用户进行身份验证，则 Lync 必须使用 NTLM 或 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="53452-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53452-155">全局通讯簿下载初始延迟</span><span class="sxs-lookup"><span data-stu-id="53452-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="53452-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="53452-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="53452-157">指定在全局地址列表（GAL）下载发生之前的时间段。</span><span class="sxs-lookup"><span data-stu-id="53452-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="53452-158">默认值为60分钟，这意味着服务器延迟在0到60分钟之间的随机时间段内下载 GAL 文件。</span><span class="sxs-lookup"><span data-stu-id="53452-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53452-159">阻止用户运行 Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="53452-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="53452-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="53452-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="53452-161">阻止用户运行 Lync。</span><span class="sxs-lookup"><span data-stu-id="53452-161">Prevents users from running Lync.</span></span> <span data-ttu-id="53452-162">可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。</span><span class="sxs-lookup"><span data-stu-id="53452-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53452-163">允许存储用户密码</span><span class="sxs-lookup"><span data-stu-id="53452-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="53452-164">SavePassword</span><span class="sxs-lookup"><span data-stu-id="53452-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="53452-165">启用 Lync 以存储密码。</span><span class="sxs-lookup"><span data-stu-id="53452-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53452-166">配置 SIP 压缩模式</span><span class="sxs-lookup"><span data-stu-id="53452-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="53452-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="53452-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="53452-168">指定何时启用 SIP 压缩。</span><span class="sxs-lookup"><span data-stu-id="53452-168">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="53452-169">默认情况下，根据适配器速度启用 SIP 压缩。</span><span class="sxs-lookup"><span data-stu-id="53452-169">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="53452-170">请注意，设置此策略可能会导致登录时间延长。</span><span class="sxs-lookup"><span data-stu-id="53452-170">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53452-171">受信任域列表</span><span class="sxs-lookup"><span data-stu-id="53452-171">Trusted Domain List</span></span><br />
<span data-ttu-id="53452-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="53452-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="53452-173">列出与客户 SIP 域的前缀不匹配的受信任域。</span><span class="sxs-lookup"><span data-stu-id="53452-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="53452-p113">服务器上所配置的策略优先于用户所配置的组策略设置和客户端选项。下表汇总了在发生冲突时各个设置的优先顺序。</span><span class="sxs-lookup"><span data-stu-id="53452-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="53452-176">组策略优先级</span><span class="sxs-lookup"><span data-stu-id="53452-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53452-177">Precedence</span><span class="sxs-lookup"><span data-stu-id="53452-177">Precedence</span></span></th>
<th><span data-ttu-id="53452-178">设置的位置或方法</span><span class="sxs-lookup"><span data-stu-id="53452-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53452-179">1 </span><span class="sxs-lookup"><span data-stu-id="53452-179">1</span></span></p></td>
<td><p><span data-ttu-id="53452-180">Lync Server 2013 带内配置</span><span class="sxs-lookup"><span data-stu-id="53452-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53452-181">2 </span><span class="sxs-lookup"><span data-stu-id="53452-181">2</span></span></p></td>
<td><p><span data-ttu-id="53452-182">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="53452-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53452-183">3 </span><span class="sxs-lookup"><span data-stu-id="53452-183">3</span></span></p></td>
<td><p><span data-ttu-id="53452-184">HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="53452-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53452-185">4 </span><span class="sxs-lookup"><span data-stu-id="53452-185">4</span></span></p></td>
<td><p><span data-ttu-id="53452-186">Lync 2013 中的 "Lync 选项" 对话框</span><span class="sxs-lookup"><span data-stu-id="53452-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="53452-187">使用 Lync 2013 管理模板文件定义组策略设置的具体方法</span><span class="sxs-lookup"><span data-stu-id="53452-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="53452-188">创建一个根级别文件夹，以包含所有非特定语言的 ADMX 文件。</span><span class="sxs-lookup"><span data-stu-id="53452-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="53452-189">例如，可在域控制器上的以下位置创建中央存储的根文件夹：</span><span class="sxs-lookup"><span data-stu-id="53452-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53452-190">此过程假定您要管理域中的多台计算机。</span><span class="sxs-lookup"><span data-stu-id="53452-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="53452-191">在这种情况下，将模板存储在主域控制器上的 Sysvol 文件夹中的中央存储中。</span><span class="sxs-lookup"><span data-stu-id="53452-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="53452-192">这为域管理模板提供了中央存储位置的副本。</span><span class="sxs-lookup"><span data-stu-id="53452-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="53452-193">为您将使用的每种语言创建一个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="53452-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="53452-194">这些子文件夹将包含特定于语言的 ADML 资源文件。</span><span class="sxs-lookup"><span data-stu-id="53452-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="53452-195">例如，在以下位置为美国英语（EN-US）创建子文件夹：</span><span class="sxs-lookup"><span data-stu-id="53452-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

