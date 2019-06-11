---
title: 'Lync Server 2013: 集成 Lync Server 和 Outlook Web App 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a25e1d0a6410171201af578d6b28f496468e06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-03_

除了与 Microsoft Outlook 2013 集成, Microsoft Lync Server 2013 还可以与 Microsoft Outlook Web App 2013 完全集成;在其他情况下, 这将向 Outlook Web App 添加即时消息和状态, 并使你的统一联系人列表在 Outlook Web App 和 Microsoft Lync 2013 之间共享。 为了集成 Lync Server 2013 和 Outlook Web App, 必须首先验证您的 Microsoft Exchange Server 2013 后端服务器中是否已安装统一通信托管 API 4.0 运行时。 您可以通过确定存在以下注册表值来实现此目的：

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath 应指向文件 Microsoft.Rtc.Internal.Ucweb.dll 的文件夹位置。 如果不存在, 或者注册表值不存在, 则应从 Microsoft 下载中心下载并安装 UCMA 运行时设置程序<http://www.microsoft.com/en-us/download/details.aspx?id=34992>。 有关如何安装 UCMA 运行时的信息可在该相同网页上找到。

**向后兼容性**

Lync Server 2013 可以与统一消息和 Outlook Web App 的 Microsoft Exchange Server 2010 版本集成。 有关详细信息, 请参阅部署本地 Exchange UM 以在[http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)其上提供 Lync Server 2010 语音邮件的文章。 如果您与 Exchange 2010 集成, 则不会具有 Lync Server 特定功能, 如 "统一联系人存储" 和 "Lync 到 Exchange 存档"。

Microsoft Lync 2013 还可以与 Exchange 2010 和 Outlook 2010 结合使用。 但是, 同样, "统一联系人存储" 和 "高分辨率" 照片等新功能将不会提供给 Lync 2013 用户。 这些新功能需要 Lync Server 2013 和 Exchange 2013。

**为 Outlook Web App 创建受信任应用程序池**

如果在同一台计算机上安装了 Microsoft Exchange 统一消息呼叫路由器服务和 Microsoft Exchange 统一消息服务, 则无需为 Outlook Web App 创建受信任的应用程序池。 (这假设所述服务器托管 SipName UM 拨号计划。)如果你使用一台计算机来托管这两个服务, 则可以跳转到标题为 **"在 Outlook Web App 上启用即时消息**" 的本文档部分。

Lync Server 2013 可以自动发现任何托管 SipName UM 拨号计划的 Exchange 服务器;这些服务器将自动添加到 "Lync Server 已知服务器" 列表。 无需创建受信任应用程序池并将这些服务器添加到已知服务器列表中。 事实上，这样做将导致 Outlook Web App 集成停止工作。

<div>


> [!NOTE]  
> 这是因为 Lync Server 拓扑现在将为同一台计算机提供两个条目: autodiscovered 条目和手动添加的条目。 若要解决此问题并使 Outlook Web App 再次工作，请使用 Windows PowerShell 来移除服务器的受信任池和受信任应用程序条目。 有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> 和 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlet 的帮助主题。



</div>

如果这两个服务在单独的计算机上运行, 则在验证统一通信托管 API 4.0 运行时已安装后, 必须创建一个 Lync Server 受信任的应用程序池和与之关联的受信任的应用程序Outlook Web App;这会将服务器添加到 "已知服务器" 列表。 若要执行此操作, 请首先在 Lync Server Management Shell 中运行类似下面的命令:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

在上面的命令中，atl-owa-001.litwareinc.com 是 Outlook Web App 池的完全限定域名；此名称必须与提供对 Outlook Web App 的访问权的证书的“使用者名称”和“使用者替代名称 (SAN)”字段中显示的名称相同。 同样, atl-cs-001.litwareinc.com 是 Lync Server 2013 池的完全限定域名, 该域名将托管新的受信任的应用程序池。 请注意, 指定的站点 (Redmond) 表示 Lync Server 网站的 SiteID。 SiteID 不一定与网站的 DisplayName 相同;你可以通过从 Lync Server Management Shell 运行以下命令来检索 Lync Server 站点的 SiteIDs:

    Get-CsSite | Select-Object DisplayName, SiteID

在创建受信任应用程序池后，可使用类似于以下命令的命令为 Outlook Web App 配置应用程序标识和端口：

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

在上面的命令中，ApplicationID 只是一个用于区分各个受信任应用程序的友好标识符。ApplicationID 可以是任何不包含空格或其他禁用字符的文本字符串。（为了确保您创建有效标识符，建议您在指定 ApplicationId 时仅使用字母和数字。）赋给 Port 参数的值也将由管理员处理：它可以是任何可用网络端口。

创建受信任的应用程序后, 必须运行以下命令以启用对 Lync Server 拓扑的更改:

    Enable-CsTopology

请注意, 你还必须将 Exchange 客户端访问和邮箱服务器添加到你的所有 SIP Uri 拨号计划。 然后, 这会将服务器配置为受信任的 SIP 对等以及 Lync Server 的 ExUmRouting 拓扑。

**在 Outlook Web App 上启用即时消息**

成功配置 Lync Server 后, 即可开始配置 Outlook Web App。 该过程的第一步是对前端服务器上的所有 Outlook Web App 虚拟目录启用即时消息。 （无需为后端服务器上的虚拟目录启用即时消息。 事实上, 建议不要在后端服务器上启用即时消息。通过在 Exchange 命令行管理器中运行以下命令, 可以在客户端访问服务器上启用即时消息:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> 默认情况下，在您安装 Outlook Web App 时会启用即时消息；也就是说，InstantMessagingEnabled 属性设置为 True。不过，您仍必须运行上面的命令才能将即时消息类型设置为 OCS。默认情况下，InstantMessagingType 设置为 None。



</div>

接下来, 你必须将以下两行添加到 Outlook Web App web.config 文件 (此文件通常位于\\文件夹 C: 程序文件\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa) 中。 这两行应添加到 web.config 文件\<中\>的 AppSettings 节点下, 此过程应仅在安装了 Outlook Web App 的后端服务器上执行:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

在前面的示例中, IMCertificateThumbprint 的值必须是安装在后端服务器上的 Exchange 2013 证书的指纹。 你可以通过从 Exchange 命令行管理程序运行以下命令来检索该信息:

    Get-ExchangeCertificate

注意, 分配给 IMServerName 的值同样是 Lync 服务器池的完全限定的域名, 您可以在其中创建 Outlook Web App 的受信任应用程序池。

用于 Outlook Web App 的证书必须是由 Lync Server 信任的证书。 确保证书受 Lync Server 和 Exchange 信任的一种方法是使用内部证书颁发机构在邮箱服务器上创建证书, 确保服务器 FQDN 用于使用者名称, 并且该 FQDN 显示在 t 中。"证书备用名称" 字段。 在创建证书之后，可以将证书导入到后端服务器。 最终结果是, 相同的证书用于两个目的: 1) Exchange 统一消息和 Lync 服务器之间的通信;和 2) Outlook Web App 与 Lync Server 之间的集成。

更新 Web.config 文件后, 您应该在 Exchange 后端服务器上运行以下命令, 以便回收 Outlook Web App 池:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

如果循环操作成功, 您将在 Exchange 命令行管理程序中看到以下消息:

    "MSExchangeOWAAppPool" successfully recycled

**配置 Outlook Web App 邮箱策略**

此时，您可以使用以下命令为一个或多个相应 Outlook Web App 邮箱策略配置即时消息。例如，在您的某个邮箱服务器上运行的以下命令将为 Default 策略启用即时消息：

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

以下命令将为您的所有 Outlook Web App 邮箱策略启用即时消息：

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

启用邮箱策略后, 由该策略管理的所有用户都将在 Lync Server 和 Outlook Web App 之间具有完全集成, 前提是:

  - 用户在 Exchange 2013 上有邮箱。

  - 用户已针对 Lync Server 2013 启用。

  - 用户具有有效的 SIP 代理地址。

**在 Outlook Web App 中禁用即时消息**

如上所述，在 Outlook Web App 中，默认启用即时消息。 这意味着, 如果您不将 Outlook Web App 与 Lync Server 集成, 则用户每次登录到 Outlook Web App 时都会看到空白状态图标和错误消息。 若要避免此问题, 请使用以下 Exchange Management Shell 命令在 Outlook web App 中禁用即时消息:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**验证与 Outlook Web App 的集成**

若要验证即时消息和状态是否已与 Outlook Web App 集成，请登录到 Outlook Web App 2013。 在屏幕的右上角，您将看到 Exchange 显示名称。 如果你的名称旁边有 "状态" 图标 (例如, 绿色图标指示你的当前状态可用), 表示你已成功集成 Lync Server 和 Outlook Web App。

在初次登录到 Outlook Web App 之后，请检查以了解具有事件 ID 112（和源 MSExchange OWA）的事件是否已写入到邮箱服务器上的事件日志中。 此事件指示已成功初始化 Instant Messaging Endpoint Manager。 如果即时消息看起来没有正常工作, 请在邮箱服务器\\上的 "文件夹 C: 程序文件\\" 中查找日志文件 Microsoft\\Exchange server\\V15\\记录\\OWA\\InstantMessaging。 如果 Logging 或 InstantMessaging 文件夹不存在，则指示集成失败。 在这种情况下, 你可以使用 Lync Server 上的 SIPStack 跟踪 (所有级别和所有标志) 尝试并确定集成失败的原因。

</div>

<span> </span>

</div>

</div>

</div>

