---
title: 'Lync Server 2013: 配置客户端引导策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06119d5488b47adfe01a934aca9a55581feaf33e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>在 Lync Server 2013 中配置客户端引导策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

组策略管理控制台 (GPMC) 和组策略对象编辑器是用于管理组策略的工具。 Office 组策略管理模板包括 Lync 2013 (ADMX) 和 adml (ADML) 管理模板, 其中包含您为域中的组策略对象配置的基于注册表的策略设置。 ADML 文件是针对 ADMX 文件的特定语言的补充。 每个 ADMX 和 ADML 文件均包含单个 Office 应用程序的策略设置。 有关详细信息, 请参阅 Office 2013 文档中的 "Office 2013 管理模板文件 (ADMX、ADML)" <http://go.microsoft.com/fwlink/p/?linkid=267516>。

对于 Lync 2013, 在用户首次登录到服务器之前, 有多个客户端引导策略应考虑进行配置。 例如，客户端在登录完成之前应使用的默认服务器和安全模式。 在用户登录并开始从服务器接收带内设置之前，可以使用组策略在用户计算机上的注册表中建立这些设置。 下表列出了适用于 Lync 2013 的组策略设置。

### <a name="group-policy-settings-for-lync-2013"></a>Lync 2013 的组策略设置

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>组策略设置</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>指定服务器<br />
(ConfigurationMode)</p></td>
<td><p>指定 Lync 2013 如何标识在登录期间使用的传输和服务器。 在此设置中，可以指定：</p>
<ul>
<li><p>ServerAddressExternal：指定在从外部防火墙之外连接时由客户端和联盟联系人使用的服务器名称或 IP 地址。</p></li>
<li><p>ServerAddressInternal：指定在客户端从组织的防火墙内部连接时使用的服务器名称或 IP 地址。</p></li>
<li><p>Transport：指定传输控制协议 (TCP) 或传输层安全性 (TLS)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>支持的其他服务器版本<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>指定服务器版本名称的列表, 除了默认支持的服务器版本外, Lync Server 2013 还将登录到该服务器版本的分号。</p></td>
</tr>
<tr class="odd">
<td><p>禁止自动上载登录失败日志 (DisableAutomaticSendTracing)</p></td>
<td><p>自动将登录失败日志上载到 Lync Server 进行分析。 如果登录成功，则不会自动上载任何日志。 如果未配置此策略，则会出现下列情况：</p>
<dl>
<dt><span></span></dt>
<dd><p>对于 Lync Online 用户: 将自动上载登录失败日志。</p>
</dd>
<dt><span></span></dt>
<dd><p>对于 Lync 本地用户: 上载前向用户显示确认对话框。</p>
</dd>
</dl>
<p>如果禁用此设置, 将为 Lync 本地和 Lync Online 用户自动将登录日志上载到 Lync 服务器。 如果启用此设置，则绝不会自动上载登录日志。</p></td>
</tr>
<tr class="even">
<td><p>禁用 SIP 连接的 HTTP 回退<br />
(DisableHttpConnect)</p></td>
<td><p>如果 TLS 或 TCP 不可用, 则阻止 Lync 服务器尝试使用 HTTP 连接到服务器。 默认情况下, Lync 首先尝试使用 TLS 或 TCP 连接到服务器, 并且如果两个传输方法均未成功, Lync 将尝试使用 HTTP 进行连接。 使用此策略可禁止回滚 HTTP 连接尝试。</p></td>
</tr>
<tr class="odd">
<td><p>需要登录凭据<br />
(DisableNTCredentials)</p></td>
<td><p>要求用户提供 Lync 的登录凭据, 而不是在登录 SIP 服务器期间自动使用 Windows 凭据。</p></td>
</tr>
<tr class="even">
<td><p>禁用服务器版本检查<br />
(DisableServerCheck)</p></td>
<td><p>如果将此策略设置为 "1", 则在登录前阻止 Lync 检查服务器名称和版本。 默认情况下, Lync 在登录前进行检查。</p></td>
</tr>
<tr class="odd">
<td><p>启用 "使用 BITS 下载通讯簿服务文件"<br />
(EnableBitsForGalDownload)</p></td>
<td><p>使 Lync 能够使用后台智能传送服务 (BITS) 下载通讯簿服务文件。</p></td>
</tr>
<tr class="even">
<td><p>配置 SIP 安全模式<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>使 Lync 能够更安全地发送和接收即时消息。 此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。</p>
<p>如果未配置此策略设置, Lync 可以使用任何传输。 但是, 如果它不使用 TLS, 并且服务器对用户进行身份验证, 则 Lync 必须使用 NTLM 或 Kerberos 身份验证。</p></td>
</tr>
<tr class="odd">
<td><p>全球通讯簿下载初始延迟<br />
(GalDownloadInitialDelay)</p></td>
<td><p>指定全局地址列表 (GAL) 下载发生之前的时间。默认值为 60 分钟，这表示服务器可将 GAL 文件的下载延迟 0 到 60 分钟之间的任意时间。</p></td>
</tr>
<tr class="even">
<td><p>阻止用户运行 Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>阻止用户运行 Lync。 可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。</p></td>
</tr>
<tr class="odd">
<td><p>允许存储用户密码<br />
(SavePassword)</p></td>
<td><p>使 Lync 能够存储密码。</p></td>
</tr>
<tr class="even">
<td><p>配置 SIP 压缩模式<br />
(SipCompression)</p></td>
<td><p>指定何时打开 SIP 压缩。默认情况下，根据适配器速度启用 SIP 压缩。请注意，设置此策略可能会导致登录时间延长。</p></td>
</tr>
<tr class="odd">
<td><p>受信任域列表<br />
TrustModelData</p></td>
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
<th>优先级</th>
<th>设置的位置或方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Lync Server 2013 带内预配</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Lync 2013 中的 "Lync-选项" 对话框</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>使用 Lync 2013 管理模板文件定义组策略设置

1.  创建根级别文件夹以包含所有与语言无关的 ADMX 文件。例如，在位于以下位置的域控制器上创建中央存储的根文件夹：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > 此过程假定您需要管理域中的多台计算机。在此情况下，您将模板存储在主域控制器上的 Sysvol 文件夹中的中央存储中。这将为域管理模板提供复制的中央存储位置。

    
    </div>

2.  为您将使用的每种语言创建一个子文件夹。这些子文件夹将包含特定语言的 ADML 资源文件。例如，在以下位置为美国英语 (EN-US) 创建一个子文件夹：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

