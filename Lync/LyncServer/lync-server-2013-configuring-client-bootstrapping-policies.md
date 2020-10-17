---
title: Lync Server 2013：配置客户端引导策略
description: Lync Server 2013：配置客户端引导策略。
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
ms.openlocfilehash: 3c03a9f7954d42f128dd6ae96296069ae5a515e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545628"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="eb627-103">在 Lync Server 2013 中配置客户端引导策略</span><span class="sxs-lookup"><span data-stu-id="eb627-103">Configuring client bootstrapping policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb627-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="eb627-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="eb627-105">组策略管理控制台 (GPMC) ，组策略对象编辑器是用于管理组策略的工具。</span><span class="sxs-lookup"><span data-stu-id="eb627-105">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="eb627-106">包含在 Office 组策略管理模板中，Lync 2013 (ADMX) 和 adml (ADML) 管理模板，其中包含您为域中的组策略对象配置的基于注册表的策略设置。</span><span class="sxs-lookup"><span data-stu-id="eb627-106">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="eb627-107">ADML 文件是特定于语言的对 ADMX 文件的补充。</span><span class="sxs-lookup"><span data-stu-id="eb627-107">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="eb627-108">每个 ADMX 和 ADML 文件都包含单个 Office 应用程序的策略设置。</span><span class="sxs-lookup"><span data-stu-id="eb627-108">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="eb627-109">有关详细信息，请参阅 Office 2013 文档中的 "Office 2013 管理模板文件 (ADMX，ADML) " <https://go.microsoft.com/fwlink/p/?linkid=267516> 。</span><span class="sxs-lookup"><span data-stu-id="eb627-109">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="eb627-110">对于 Lync 2013，有几个客户端启动策略，在用户首次登录到服务器之前，应考虑进行配置。</span><span class="sxs-lookup"><span data-stu-id="eb627-110">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="eb627-111">例如，客户端在登录完成之前应使用的默认服务器和安全模式。</span><span class="sxs-lookup"><span data-stu-id="eb627-111">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="eb627-112">在用户登录并开始从服务器接收带内设置设置之前，您可以使用组策略在用户的计算机注册表中建立这些设置。</span><span class="sxs-lookup"><span data-stu-id="eb627-112">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="eb627-113">下表列出了可用于 Lync 2013 的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="eb627-113">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="eb627-114">Lync 2013 的组策略设置</span><span class="sxs-lookup"><span data-stu-id="eb627-114">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb627-115">组策略设置</span><span class="sxs-lookup"><span data-stu-id="eb627-115">Group Policy setting</span></span></th>
<th><span data-ttu-id="eb627-116">说明</span><span class="sxs-lookup"><span data-stu-id="eb627-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb627-117">指定服务器</span><span class="sxs-lookup"><span data-stu-id="eb627-117">Specify Server</span></span><br />
<span data-ttu-id="eb627-118"> (ConfigurationMode) </span><span class="sxs-lookup"><span data-stu-id="eb627-118">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="eb627-119">指定 Lync 2013 如何标识登录期间要使用的传输和服务器。</span><span class="sxs-lookup"><span data-stu-id="eb627-119">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="eb627-120">在此设置中，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="eb627-120">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb627-121">ServerAddressExternal：指定从外部防火墙外部连接时，客户端和联盟联系人使用的服务器名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb627-121">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="eb627-122">ServerAddressInternal：指定当客户端从组织的防火墙内部进行连接时使用的服务器名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb627-122">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="eb627-123">Transport：指定传输控制协议 (TCP) 或传输层安全性 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="eb627-123">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb627-124">支持的其他服务器版本</span><span class="sxs-lookup"><span data-stu-id="eb627-124">Additional server versions supported</span></span><br />
<span data-ttu-id="eb627-125"> (ConfiguredServerCheckValues) </span><span class="sxs-lookup"><span data-stu-id="eb627-125">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="eb627-126">指定除了默认情况下受支持的服务器版本之外，Lync Server 2013 将登录到的服务器版本名称的列表。</span><span class="sxs-lookup"><span data-stu-id="eb627-126">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb627-127">禁止自动上载登录失败日志 (DisableAutomaticSendTracing) </span><span class="sxs-lookup"><span data-stu-id="eb627-127">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="eb627-128">自动将登录失败日志上传到 Lync Server 进行分析。</span><span class="sxs-lookup"><span data-stu-id="eb627-128">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="eb627-129">如果登录成功，则不会自动上载任何日志。</span><span class="sxs-lookup"><span data-stu-id="eb627-129">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="eb627-130">如果未配置此策略，则会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="eb627-130">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="eb627-131">对于 Lync Online 用户：将自动上载登录失败日志。</span><span class="sxs-lookup"><span data-stu-id="eb627-131">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="eb627-132">对于 Lync 本地用户：在上载前向用户显示确认对话框。</span><span class="sxs-lookup"><span data-stu-id="eb627-132">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="eb627-133">如果禁用此设置，则会为 Lync 本地和 Lync Online 用户自动将登录日志上载到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="eb627-133">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="eb627-134">如果启用此设置，则不会自动上载登录日志。</span><span class="sxs-lookup"><span data-stu-id="eb627-134">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb627-135">禁用 SIP 连接的 HTTP 回退</span><span class="sxs-lookup"><span data-stu-id="eb627-135">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="eb627-136"> (DisableHttpConnect) </span><span class="sxs-lookup"><span data-stu-id="eb627-136">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="eb627-137">如果 TLS 或 TCP 不可用，则阻止 Lync Server 尝试使用 HTTP 连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="eb627-137">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="eb627-138">默认情况下，Lync 首先尝试使用 TLS 或 TCP 连接到服务器，如果这些传输方法中的两个都不成功，Lync 将尝试使用 HTTP 进行连接。</span><span class="sxs-lookup"><span data-stu-id="eb627-138">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="eb627-139">使用此策略可禁止回退 HTTP 连接尝试。</span><span class="sxs-lookup"><span data-stu-id="eb627-139">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb627-140">需要登录凭据</span><span class="sxs-lookup"><span data-stu-id="eb627-140">Require logon credentials</span></span><br />
<span data-ttu-id="eb627-141"> (DisableNTCredentials) </span><span class="sxs-lookup"><span data-stu-id="eb627-141">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="eb627-142">要求用户提供 Lync 的登录凭据，而不是在登录 SIP 服务器期间自动使用 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="eb627-142">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb627-143">禁用服务器版本检查</span><span class="sxs-lookup"><span data-stu-id="eb627-143">Disable server version check</span></span><br />
<span data-ttu-id="eb627-144"> (DisableServerCheck) </span><span class="sxs-lookup"><span data-stu-id="eb627-144">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="eb627-145">如果将此策略设置为1，则阻止 Lync 在登录前检查服务器名称和版本。</span><span class="sxs-lookup"><span data-stu-id="eb627-145">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="eb627-146">默认情况下，Lync 会在登录前进行这些检查。</span><span class="sxs-lookup"><span data-stu-id="eb627-146">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb627-147">允许使用 BITS 下载通讯簿服务文件</span><span class="sxs-lookup"><span data-stu-id="eb627-147">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="eb627-148"> (EnableBitsForGalDownload) </span><span class="sxs-lookup"><span data-stu-id="eb627-148">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="eb627-149">使 Lync 能够使用后台智能传输服务 (BITS) 下载通讯簿服务文件。</span><span class="sxs-lookup"><span data-stu-id="eb627-149">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb627-150">配置 SIP 安全模式</span><span class="sxs-lookup"><span data-stu-id="eb627-150">Configure SIP security mode</span></span><br />
<span data-ttu-id="eb627-151"> (EnableSIPHighSecurityMode) </span><span class="sxs-lookup"><span data-stu-id="eb627-151">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="eb627-152">使 Lync 能够更安全地发送和接收即时消息。</span><span class="sxs-lookup"><span data-stu-id="eb627-152">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="eb627-153">此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。</span><span class="sxs-lookup"><span data-stu-id="eb627-153">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="eb627-154">如果未配置此策略设置，则 Lync 可以使用任何传输。</span><span class="sxs-lookup"><span data-stu-id="eb627-154">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="eb627-155">但是，如果它不使用 TLS，并且如果服务器对用户进行身份验证，则 Lync 必须使用 NTLM 或 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="eb627-155">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb627-156">全局通讯簿下载初始延迟</span><span class="sxs-lookup"><span data-stu-id="eb627-156">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="eb627-157"> (GalDownloadInitialDelay) </span><span class="sxs-lookup"><span data-stu-id="eb627-157">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="eb627-158">指定在全局地址列表 (GAL) 发生之前的下载的时间段。</span><span class="sxs-lookup"><span data-stu-id="eb627-158">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="eb627-159">默认值为60分钟，这意味着服务器延迟在0到60分钟之间的随机时间段内下载 GAL 文件。</span><span class="sxs-lookup"><span data-stu-id="eb627-159">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb627-160">阻止用户运行 Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="eb627-160">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="eb627-161"> (PreventRun) </span><span class="sxs-lookup"><span data-stu-id="eb627-161">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="eb627-162">阻止用户运行 Lync。</span><span class="sxs-lookup"><span data-stu-id="eb627-162">Prevents users from running Lync.</span></span> <span data-ttu-id="eb627-163">可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。</span><span class="sxs-lookup"><span data-stu-id="eb627-163">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb627-164">允许存储用户密码</span><span class="sxs-lookup"><span data-stu-id="eb627-164">Allow storage of user passwords</span></span><br />
<span data-ttu-id="eb627-165"> (SavePassword) </span><span class="sxs-lookup"><span data-stu-id="eb627-165">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="eb627-166">启用 Lync 以存储密码。</span><span class="sxs-lookup"><span data-stu-id="eb627-166">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb627-167">配置 SIP 压缩模式</span><span class="sxs-lookup"><span data-stu-id="eb627-167">Configure SIP compression mode</span></span><br />
<span data-ttu-id="eb627-168"> (SipCompression) </span><span class="sxs-lookup"><span data-stu-id="eb627-168">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="eb627-169">指定何时启用 SIP 压缩。</span><span class="sxs-lookup"><span data-stu-id="eb627-169">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="eb627-170">默认情况下，根据适配器速度启用 SIP 压缩。</span><span class="sxs-lookup"><span data-stu-id="eb627-170">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="eb627-171">请注意，设置此策略可能会导致登录时间延长。</span><span class="sxs-lookup"><span data-stu-id="eb627-171">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb627-172">受信任域列表</span><span class="sxs-lookup"><span data-stu-id="eb627-172">Trusted Domain List</span></span><br />
<span data-ttu-id="eb627-173"> (TrustModelData) </span><span class="sxs-lookup"><span data-stu-id="eb627-173">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="eb627-174">列出与客户 SIP 域的前缀不匹配的受信任域。</span><span class="sxs-lookup"><span data-stu-id="eb627-174">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eb627-p113">服务器上所配置的策略优先于用户所配置的组策略设置和客户端选项。下表汇总了在发生冲突时各个设置的优先顺序。</span><span class="sxs-lookup"><span data-stu-id="eb627-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="eb627-177">组策略优先级</span><span class="sxs-lookup"><span data-stu-id="eb627-177">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb627-178">Precedence</span><span class="sxs-lookup"><span data-stu-id="eb627-178">Precedence</span></span></th>
<th><span data-ttu-id="eb627-179">设置的位置或方法</span><span class="sxs-lookup"><span data-stu-id="eb627-179">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb627-180">1</span><span class="sxs-lookup"><span data-stu-id="eb627-180">1</span></span></p></td>
<td><p><span data-ttu-id="eb627-181">Lync Server 2013 带内配置</span><span class="sxs-lookup"><span data-stu-id="eb627-181">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb627-182">双面</span><span class="sxs-lookup"><span data-stu-id="eb627-182">2</span></span></p></td>
<td><p><span data-ttu-id="eb627-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="eb627-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb627-184">第三章</span><span class="sxs-lookup"><span data-stu-id="eb627-184">3</span></span></p></td>
<td><p><span data-ttu-id="eb627-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="eb627-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb627-186">4 </span><span class="sxs-lookup"><span data-stu-id="eb627-186">4</span></span></p></td>
<td><p><span data-ttu-id="eb627-187">Lync 2013 中的 "Lync 选项" 对话框</span><span class="sxs-lookup"><span data-stu-id="eb627-187">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="eb627-188">使用 Lync 2013 管理模板文件定义组策略设置的具体方法</span><span class="sxs-lookup"><span data-stu-id="eb627-188">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="eb627-189">创建一个根级别文件夹，以包含所有非特定语言的 ADMX 文件。</span><span class="sxs-lookup"><span data-stu-id="eb627-189">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="eb627-190">例如，可在域控制器上的以下位置创建中央存储的根文件夹：</span><span class="sxs-lookup"><span data-stu-id="eb627-190">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb627-191">此过程假定您要管理域中的多台计算机。</span><span class="sxs-lookup"><span data-stu-id="eb627-191">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="eb627-192">在这种情况下，将模板存储在主域控制器上的 Sysvol 文件夹中的中央存储中。</span><span class="sxs-lookup"><span data-stu-id="eb627-192">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="eb627-193">这为域管理模板提供了中央存储位置的副本。</span><span class="sxs-lookup"><span data-stu-id="eb627-193">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="eb627-194">为您将使用的每种语言创建一个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="eb627-194">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="eb627-195">这些子文件夹将包含特定于语言的 ADML 资源文件。</span><span class="sxs-lookup"><span data-stu-id="eb627-195">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="eb627-196">例如，在以下位置为美国英语 (EN-US) 创建子文件夹：</span><span class="sxs-lookup"><span data-stu-id="eb627-196">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

