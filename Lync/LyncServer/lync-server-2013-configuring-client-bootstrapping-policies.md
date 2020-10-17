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
ms.openlocfilehash: 826f732f25996a9f8fcbd708f7e76157a5753a01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512769"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>在 Lync Server 2013 中配置客户端引导策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

组策略管理控制台 (GPMC) ，组策略对象编辑器是用于管理组策略的工具。 包含在 Office 组策略管理模板中，Lync 2013 (ADMX) 和 adml (ADML) 管理模板，其中包含您为域中的组策略对象配置的基于注册表的策略设置。 ADML 文件是特定于语言的对 ADMX 文件的补充。 每个 ADMX 和 ADML 文件都包含单个 Office 应用程序的策略设置。 有关详细信息，请参阅 Office 2013 文档中的 "Office 2013 管理模板文件 (ADMX，ADML) " <https://go.microsoft.com/fwlink/p/?linkid=267516> 。

对于 Lync 2013，有几个客户端启动策略，在用户首次登录到服务器之前，应考虑进行配置。 例如，客户端在登录完成之前应使用的默认服务器和安全模式。 在用户登录并开始从服务器接收带内设置设置之前，您可以使用组策略在用户的计算机注册表中建立这些设置。 下表列出了可用于 Lync 2013 的组策略设置。

### <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 的组策略设置

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>组策略设置</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>指定服务器<br />
 (ConfigurationMode) </p></td>
<td><p>指定 Lync 2013 如何标识登录期间要使用的传输和服务器。 在此设置中，指定以下内容：</p>
<ul>
<li><p>ServerAddressExternal：指定从外部防火墙外部连接时，客户端和联盟联系人使用的服务器名称或 IP 地址。</p></li>
<li><p>ServerAddressInternal：指定当客户端从组织的防火墙内部进行连接时使用的服务器名称或 IP 地址。</p></li>
<li><p>Transport：指定传输控制协议 (TCP) 或传输层安全性 (TLS) 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>支持的其他服务器版本<br />
 (ConfiguredServerCheckValues) </p></td>
<td><p>指定除了默认情况下受支持的服务器版本之外，Lync Server 2013 将登录到的服务器版本名称的列表。</p></td>
</tr>
<tr class="odd">
<td><p>禁止自动上载登录失败日志 (DisableAutomaticSendTracing) </p></td>
<td><p>自动将登录失败日志上传到 Lync Server 进行分析。 如果登录成功，则不会自动上载任何日志。 如果未配置此策略，则会发生以下情况：</p>
<dl>
<dt><span></span></dt>
<dd><p>对于 Lync Online 用户：将自动上载登录失败日志。</p>
</dd>
<dt><span></span></dt>
<dd><p>对于 Lync 本地用户：在上载前向用户显示确认对话框。</p>
</dd>
</dl>
<p>如果禁用此设置，则会为 Lync 本地和 Lync Online 用户自动将登录日志上载到 Lync Server。 如果启用此设置，则不会自动上载登录日志。</p></td>
</tr>
<tr class="even">
<td><p>禁用 SIP 连接的 HTTP 回退<br />
 (DisableHttpConnect) </p></td>
<td><p>如果 TLS 或 TCP 不可用，则阻止 Lync Server 尝试使用 HTTP 连接到服务器。 默认情况下，Lync 首先尝试使用 TLS 或 TCP 连接到服务器，如果这些传输方法中的两个都不成功，Lync 将尝试使用 HTTP 进行连接。 使用此策略可禁止回退 HTTP 连接尝试。</p></td>
</tr>
<tr class="odd">
<td><p>需要登录凭据<br />
 (DisableNTCredentials) </p></td>
<td><p>要求用户提供 Lync 的登录凭据，而不是在登录 SIP 服务器期间自动使用 Windows 凭据。</p></td>
</tr>
<tr class="even">
<td><p>禁用服务器版本检查<br />
 (DisableServerCheck) </p></td>
<td><p>如果将此策略设置为1，则阻止 Lync 在登录前检查服务器名称和版本。 默认情况下，Lync 会在登录前进行这些检查。</p></td>
</tr>
<tr class="odd">
<td><p>允许使用 BITS 下载通讯簿服务文件<br />
 (EnableBitsForGalDownload) </p></td>
<td><p>使 Lync 能够使用后台智能传输服务 (BITS) 下载通讯簿服务文件。</p></td>
</tr>
<tr class="even">
<td><p>配置 SIP 安全模式<br />
 (EnableSIPHighSecurityMode) </p></td>
<td><p>使 Lync 能够更安全地发送和接收即时消息。 此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。</p>
<p>如果未配置此策略设置，则 Lync 可以使用任何传输。 但是，如果它不使用 TLS，并且如果服务器对用户进行身份验证，则 Lync 必须使用 NTLM 或 Kerberos 身份验证。</p></td>
</tr>
<tr class="odd">
<td><p>全局通讯簿下载初始延迟<br />
 (GalDownloadInitialDelay) </p></td>
<td><p>指定在全局地址列表 (GAL) 发生之前的下载的时间段。 默认值为60分钟，这意味着服务器延迟在0到60分钟之间的随机时间段内下载 GAL 文件。</p></td>
</tr>
<tr class="even">
<td><p>阻止用户运行 Microsoft Lync<br />
 (PreventRun) </p></td>
<td><p>阻止用户运行 Lync。 可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。</p></td>
</tr>
<tr class="odd">
<td><p>允许存储用户密码<br />
 (SavePassword) </p></td>
<td><p>启用 Lync 以存储密码。</p></td>
</tr>
<tr class="even">
<td><p>配置 SIP 压缩模式<br />
 (SipCompression) </p></td>
<td><p>指定何时启用 SIP 压缩。 默认情况下，根据适配器速度启用 SIP 压缩。 请注意，设置此策略可能会导致登录时间延长。</p></td>
</tr>
<tr class="odd">
<td><p>受信任域列表<br />
 (TrustModelData) </p></td>
<td><p>列出与客户 SIP 域的前缀不匹配的受信任域。</p></td>
</tr>
</tbody>
</table>


服务器上所配置的策略优先于用户所配置的组策略设置和客户端选项。下表汇总了在发生冲突时各个设置的优先顺序。

### <a name="group-policy-precedence"></a>组策略优先级

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Precedence</th>
<th>设置的位置或方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Lync Server 2013 带内配置</p></td>
</tr>
<tr class="even">
<td><p>双面</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>第三章</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>Lync 2013 中的 "Lync 选项" 对话框</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>使用 Lync 2013 管理模板文件定义组策略设置的具体方法

1.  创建一个根级别文件夹，以包含所有非特定语言的 ADMX 文件。 例如，可在域控制器上的以下位置创建中央存储的根文件夹：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > 此过程假定您要管理域中的多台计算机。 在这种情况下，将模板存储在主域控制器上的 Sysvol 文件夹中的中央存储中。 这为域管理模板提供了中央存储位置的副本。

    
    </div>

2.  为您将使用的每种语言创建一个子文件夹。 这些子文件夹将包含特定于语言的 ADML 资源文件。 例如，在以下位置为美国英语 (EN-US) 创建子文件夹：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

