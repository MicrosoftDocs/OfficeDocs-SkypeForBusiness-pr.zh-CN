---
title: 在 Lync Server 2013 中配置客户端引导策略
TOCTitle: 在 Lync Server 2013 中配置客户端引导策略
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425941(v=OCS.15)
ms:contentKeyID: 49312698
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置客户端引导策略

 

_**上一次修改主题：** 2016-12-08_

组策略管理控制台 (GPMC) 和组策略对象编辑器是用于管理组策略的工具。Office 组策略管理模板附带了 Lync 2013.admx (ADMX) 和 .adml (ADML) 管理模板，其中包含为域中的组策略对象配置的基于注册表的策略设置。ADML 文件是针对 ADMX 文件的特定语言的补充。每个 ADMX 和 ADML 文件均包含单个 Office 应用程序的策略设置。

对于 Lync 2013，在用户首次登录到服务器之前，您应考虑配置几个客户端引导策略。例如，客户端在登录完成之前应使用的默认服务器和安全模式。在用户登录并开始从服务器接收带内设置之前，您可以使用组策略在用户计算机上的注册表中建立这些设置。下表列出了可用于 Lync 2013 的组策略设置。

### Lync 2013 的组策略设置

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
<td><p>指定 Lync 2013 如何标识登录期间要使用的传输和服务器。在此设置中，您可以指定：</p>
<ul>
<li><p>ServerAddressExternal：指定在从外部防火墙之外连接时由客户端和联盟联系人使用的服务器名称或 IP 地址。</p></li>
<li><p>ServerAddressInternal：指定在客户端从组织的防火墙内部连接时使用的服务器名称或 IP 地址。</p></li>
<li><p>Transport：指定传输控制协议 (TCP) 或传输层安全性 (TLS)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>支持的其他服务器版本<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>指定 Lync Server 2013 将登录到的服务器版本的名称列表（用分号隔开）以及默认支持的服务器版本。</p></td>
</tr>
<tr class="odd">
<td><p>禁止自动上载登录失败日志 (DisableAutomaticSendTracing)</p></td>
<td><p>自动将登录失败日志上载到 Lync Server 以进行分析。如果登录成功，则不会自动上载任何日志。如果未配置此策略，则会出现下列情况：</p>
<dl>
<dd><p>对于 Lync Online 用户：自动上载登录失败日志。</p>
</dd>
<dd><p>对于 Lync 本地用户：在上载之前将为用户显示一个确认对话框。</p>
</dd>
</dl>
<p>如果禁用此设置，则将为 Lync 本地和 Lync Online 用户自动将登录日志上载到 Lync Server。如果启用此设置，则绝不会自动上载登录日志。</p></td>
</tr>
<tr class="even">
<td><p>为 SIP 连接禁用 HTTP 回滚<br />
(DisableHttpConnect)</p></td>
<td><p>如果 TLS 或 TCP 不可用，则将阻止 Lync Server 尝试通过使用 HTTP 连接到服务器。默认情况下，Lync 首先会尝试使用 TLS 或 TCP 连接到服务器，如果这两种传输方法都失败，则 Lync 会尝试使用 HTTP 进行连接。使用此策略可禁止回滚 HTTP 连接尝试。</p></td>
</tr>
<tr class="odd">
<td><p>需要登录凭据<br />
(DisableNTCredentials)</p></td>
<td><p>在登录 SIP 服务器的过程中，要求用户提供 Lync 的登录凭据，而不是自动使用 Windows 凭据。</p></td>
</tr>
<tr class="even">
<td><p>禁用服务器版本检查<br />
(DisableServerCheck)</p></td>
<td><p>如果将此策略设置为 1，则将防止 Lync 在登录前检查服务器名称和版本。默认情况下，Lync 会在登录前检查服务器名称和版本。</p></td>
</tr>
<tr class="odd">
<td><p>允许使用 BITS 下载通讯簿服务文件<br />
(EnableBitsForGalDownload)</p></td>
<td><p>允许 Lync 使用后台智能传输服务 (BITS) 下载通讯簿服务文件。</p></td>
</tr>
<tr class="even">
<td><p>配置 SIP 安全模式<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>允许 Lync 更安全地发送和接收即时消息。此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。</p>
<p>如果不配置此策略设置，Lync 可以使用任何传输。但是，如果它不使用 TLS，而服务器要对用户进行身份验证，Lync 就必须使用 NTLM 或 Kerberos 身份验证。</p></td>
</tr>
<tr class="odd">
<td><p>全局通讯簿下载初始延迟<br />
(GalDownloadInitialDelay)</p></td>
<td><p>指定全局地址列表 (GAL) 下载发生之前的时间。默认值为 60 分钟，这表示服务器可将 GAL 文件的下载延迟 0 到 60 分钟之间的任意时间。</p></td>
</tr>
<tr class="even">
<td><p>禁止用户运行 Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>禁止用户运行 Lync。可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。</p></td>
</tr>
<tr class="odd">
<td><p>允许存储用户密码<br />
(SavePassword)</p></td>
<td><p>允许 Lync 存储密码。</p></td>
</tr>
<tr class="even">
<td><p>配置 SIP 压缩模式<br />
(SipCompression)</p></td>
<td><p>指定何时打开 SIP 压缩。默认情况下，根据适配器速度启用 SIP 压缩。请注意，设置此策略可能会导致登录时间延长。</p></td>
</tr>
<tr class="odd">
<td><p>受信任的域列表<br />
(TrustModelData)</p></td>
<td><p>列出与客户 SIP 域的前缀不匹配的受信任域。</p></td>
</tr>
</tbody>
</table>


服务器上所配置的策略优先于用户所配置的组策略设置和客户端选项。下表汇总了在发生冲突时各个设置的优先顺序。

### 组策略优先级

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
<td><p>Lync Server 2013 带内设置</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Lync 2013 中的“Lync - 选项”对话框</p></td>
</tr>
</tbody>
</table>


## 使用 Lync 2013 管理模板文件定义组策略设置

1.  创建根级别文件夹以包含所有与语言无关的 ADMX 文件。例如，在位于以下位置的域控制器上创建中央存储的根文件夹：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]  
    > 此过程假定您需要管理域中的多台计算机。在此情况下，您将模板存储在主域控制器上的 Sysvol 文件夹中的中央存储中。这将为域管理模板提供复制的中央存储位置。
    


2.  为您将使用的每种语言创建一个子文件夹。这些子文件夹将包含特定语言的 ADML 资源文件。例如，在以下位置为美国英语 (EN-US) 创建一个子文件夹：
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

有关 ADMX 文件的详细信息，请参阅“管理组策略 ADMX 文件分步指南”，网址为 [http://go.microsoft.com/fwlink/?linkid=75124\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=75124%26clcid=0x804)。

