---
title: Lync Server 2013：集成 Lync Server 和 Outlook Web App 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44de5139d3ad8f38c5177a18260045fda7abdeea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-03_

除了与 Microsoft Outlook 2013 集成之外，Microsoft Lync Server 2013 还可以与 Microsoft Outlook Web App 2013 完全集成;此外，这将为 Outlook Web App 添加即时消息和状态，并使您的统一联系人列表在 Outlook Web App 和 Microsoft Lync 2013 之间共享。 为了集成 Lync Server 2013 和 Outlook Web App，您必须首先验证是否已在 Microsoft Exchange Server 2013 后端服务器中安装统一通信托管 API 4.0 运行时。 您可以通过查找是否存在以下注册表值来实现此目的：

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath 应指向文件 "Microsoft.rtc.ucweb.dll" 的 "文件夹位置"。 如果没有，或者如果注册表值不存在，则应从 Microsoft 下载中心下载并安装 UCMA 运行时安装程序<http://www.microsoft.com/download/details.aspx?id=34992>。 有关如何安装 UCMA 运行时的信息，可以在同一网页上找到。

**向后兼容性**

Lync Server 2013 可以与统一消息和 Outlook Web App 的 Microsoft Exchange Server 2010 版本集成。 有关详细信息，请参阅部署本地 Exchange UM 以在中提供 Lync Server 2010 语音邮件一[http://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)文。 如果与 Exchange 2010 集成，则不会具有 Lync Server 特定功能，例如统一联系人存储和 Lync 到 Exchange 存档。

Microsoft Lync 2013 还可以与 Exchange 2010 和 Outlook 2010 结合使用。 但同样，新功能（例如统一联系人存储和高分辨率照片）将不适用于 Lync 2013 用户。 这些新功能需要同时具有 Lync Server 2013 和 Exchange 2013。

**为 Outlook Web App 创建受信任的应用程序池**

如果已在同一台计算机上安装了 Microsoft Exchange 统一消息呼叫路由器服务和 Microsoft Exchange 统一消息服务，则无需为 Outlook Web App 创建受信任的应用程序池。 （这假定所讨论的服务器承载 SipName UM 拨号计划。）如果您使用一台计算机来托管这两个服务，则可以跳到本文档中标题为 **"在 Outlook Web App 上启用即时消息**" 的部分。

Lync Server 2013 可以自动发现任何承载 SipName UM 拨号计划的 Exchange 服务器;这些服务器将自动添加到 "Lync Server 已知服务器" 列表中。 无需创建受信任的应用程序池，并将这些服务器添加到已知服务器列表中。 事实上，这样做会导致 Outlook Web App 集成停止工作。

<div>


> [!NOTE]  
> 这是因为 Lync Server 拓扑现在将为同一台计算机提供两个条目： autodiscovered 条目和手动添加的条目。 若要解决此问题，并再次使用 Outlook Web App，请使用 Windows PowerShell 删除服务器的受信任池和受信任的应用程序条目。 有关详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">CsTrustedApplicationPool</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">CsTrustedApplication</A> cmdlet 的帮助主题。



</div>

如果这两个服务在单独的计算机上运行，则在您确认已安装统一通信托管 API 4.0 运行时后，必须创建一个 Lync Server 受信任应用程序池和与之关联的受信任应用程序Outlook Web App;将服务器添加到已知服务器列表中。 若要执行此操作，请首先在 Lync Server Management Shell 中运行与以下内容类似的命令：

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

在上面的命令中，atl-owa-001.litwareinc.com 是 Outlook Web App 池的完全限定的域名;此名称必须与提供对 Outlook Web App 的访问权限的证书的 "主题名称" 和 "主题备用名称（SAN）" 字段中显示的名称相同。 同样，atl-cs-001.litwareinc.com 是将承载新的受信任应用程序池的 Lync Server 2013 池的完全限定域名。 请注意，指定的 site （Redmond）表示 Lync Server 网站的 SiteID。 SiteID 不一定与网站的 DisplayName 相同;您可以通过在 Lync Server 命令行管理程序中运行以下命令来检索您的 Lync Server 站点的 SiteIDs：

    Get-CsSite | Select-Object DisplayName, SiteID

创建受信任的应用程序池后，请使用与以下内容类似的命令为 Outlook Web App 配置应用程序标识和端口：

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

在上面的命令中，ApplicationID 只是一个用于区分受信任应用程序的友好标识符。 ApplicationID 可以是任何不包含空格或其他禁止字符的文本字符串。 （为确保创建有效的标识符，建议在指定 ApplicationId 时仅使用字母和数字。）分配给 Port 参数的值也保留给管理员的决定：这可以是任何可用的网络端口。

在创建受信任的应用程序后，您必须运行以下命令来启用对 Lync Server 拓扑的更改：

    Enable-CsTopology

请注意，还必须将 Exchange 客户端访问和邮箱服务器添加到所有 SIP Uri 拨号计划中。 反过来，这会将服务器配置为受信任的 SIP 对等方以及 Lync Server 的 ExUmRouting 拓扑。

**在 Outlook Web App 上启用即时消息**

在 Lync Server 配置正确后，即可开始配置 Outlook Web App。 该过程中的第一步是在前端服务器上的所有 Outlook Web App 虚拟目录上启用即时消息。 （无需为后端服务器上的虚拟目录启用即时消息。 事实上，建议您不要在后端服务器上启用即时消息。通过在 Exchange 命令行管理程序中运行以下命令，可以在客户端访问服务器上启用即时消息：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> 默认情况下，在安装 Outlook Web App 时将启用即时消息;也就是说，InstantMessagingEnabled 属性设置为 True。 但是，仍必须运行前面的命令，才能将即时消息类型设置为 OCS。 默认情况下，InstantMessagingType 设置为 None。



</div>

接下来，您必须将以下两行添加到 Outlook Web App web.config 文件（此文件通常位于\\文件夹 C： Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa 中）。 应在 web.config 文件中的\<AppSettings\>节点下添加这两行，并且应仅在安装了 Outlook Web App 的后端服务器上执行此过程：

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

在上面的示例中，IMCertificateThumbprint 的值必须是安装在后端服务器上的 Exchange 2013 证书的指纹。 您可以通过在 Exchange 命令行管理程序中运行以下命令来检索该信息：

    Get-ExchangeCertificate

请注意，分配给 IMServerName 的值也是您在其中为 Outlook Web App 创建受信任应用程序池的 Lync Server 池的完全限定域名。

用于 Outlook Web App 的证书必须是由 Lync Server 信任的证书。 若要确保 Lync Server 和 Exchange 都信任证书的一种方法是使用内部证书颁发机构在邮箱服务器上创建证书，请确保服务器 FQDN 用于使用者名称，并且此 FQDN 出现在 t"证书备用名称" 字段。 创建证书之后，可以将其导入到后端服务器。 最终结果是，相同的证书用于两个目的：1） Exchange 统一消息和 Lync Server 之间的通信;和2） Outlook Web App 和 Lync Server 之间的集成。

更新 Web.config 文件后，应在 Exchange 后端服务器上运行以下命令，以便回收 Outlook Web App 池：

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

如果回收操作成功，您将在 Exchange 命令行管理程序中看到以下消息：

    "MSExchangeOWAAppPool" successfully recycled

**配置 Outlook Web App 邮箱策略**

此时，您可以使用以下命令在相应的 Outlook Web App 邮箱策略（或策略）上配置即时消息。 例如，此命令在您的某个邮箱服务器上运行，并在默认策略上启用即时消息：

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

此命令将为您的所有 Outlook Web App 邮箱策略启用即时消息：

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

启用邮箱策略之后，由该策略管理的所有用户都将在 Lync Server 和 Outlook Web App 之间实现完全集成，前提是：

  - 用户在 Exchange 2013 上拥有邮箱。

  - 已为用户启用 Lync Server 2013。

  - 用户具有有效的 SIP 代理地址。

**在 Outlook Web App 中禁用即时消息**

如前所述，默认情况下，在 Outlook Web App 中启用即时消息。 这意味着，如果不将 Outlook Web App 与 Lync Server 集成，则用户将在每次登录到 Outlook Web App 时看到空白的状态图标和错误消息。 若要避免此问题，请使用以下 Exchange 命令行管理程序命令在 Outlook web App 中禁用即时消息：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**验证与 Outlook Web App 的集成**

若要验证即时消息和状态是否已与 Outlook Web App 集成，请登录到 Outlook Web App 2013。 在屏幕的右上角，将看到您的 Exchange 显示名称。 如果您的名称旁边有一个状态图标（例如，绿色图标指示您的当前状态可用），表明您已成功集成 Lync Server 和 Outlook Web App。

在首次登录到 Outlook Web App 后，检查是否有事件 ID 为112的事件（和源 MSExchange OWA）是否已写入邮箱服务器上的事件日志。 此事件表示即时消息终结点管理器已成功初始化。 如果即时消息似乎不起作用，则在邮箱服务器上，在\\文件夹 C： Program files\\Microsoft\\Exchange server\\V15\\日志记录\\OWA\\InstantMessaging 中查找日志文件。 如果日志记录或 InstantMessaging 文件夹不存在，则表示集成失败。 在这种情况下，您可以在 Lync Server （所有级别和所有标记）上使用 SIPStack 跟踪，以尝试并确定集成失败的原因。

</div>

<span> </span>

</div>

</div>

</div>

