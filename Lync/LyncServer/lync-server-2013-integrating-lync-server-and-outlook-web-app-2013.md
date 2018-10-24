---
title: 集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013
TOCTitle: 集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49888418
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013

 

_**上一次修改主题：** 2016-12-08_

除了与 Microsoft Outlook 2013 集成之外，Microsoft Lync Server 2013 还可与 Microsoft Outlook Web App 2013 完全集成；此外，这将向 Outlook Web App 添加即时消息和状态，并使您的统一联系人列表能够在 Outlook Web App 和 Microsoft Lync 2013 之间共享。若要集成 Lync Server 2013 和 Outlook Web App，您必须先确认已在 Microsoft Exchange Server 2013 后端服务器上安装统一通信托管 API 4.0 运行时。您可以通过确定存在以下注册表值来实现此目的：

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath 应指向文件 Microsoft.Rtc.Internal.Ucweb.dll 的文件夹位置。如果没有，或者如果该注册表值不存在，您应从 Microsoft 下载中心下载并安装 UCMA 运行时安装程序，网址为 <http://www.microsoft.com/zh-cn/download/details.aspx?id=34992>。有关如何安装 UCMA 运行时的信息可在该相同网页上找到。

**向后兼容性**

Lync Server 2013 可以与 Microsoft Exchange Server 2010 版本的统一消息和 Outlook Web App 集成。有关详细信息，请参阅 [http://technet.microsoft.com/zh-cn/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) 中的“部署内部 Exchange UM 以提供 Lync Server 2010 语音邮件”一文。如果您与 Exchange 2010 集成，则您不会具有 Lync Server 特定功能，例如统一联系人存储和 Lync 到 Exchange 存档。

Microsoft Lync 2013 还可以与 Exchange 2010 和 Outlook 2010 结合使用。不过，新功能（例如统一联系人存储和高分辨率照片）将再次无法供 Lync 2013 用户使用。这些新功能同时需要 Lync Server 2013 和 Exchange 2013。

**为 Outlook Web App 创建受信任应用程序池**

如果您已在同一计算机上安装了 Microsoft Exchange 统一消息呼叫路由器服务和 Microsoft Exchange 统一消息服务，则无需为 Outlook Web App 创建受信任应用程序池。（这假定所讨论的服务器托管 SipName UM 拨号计划。）如果您使用单台计算机来同时托管这些服务，则您可以跳到本文档中标题为**在 Outlook Web App 上启用即时消息**的一节。

Lync Server 2013 可以自动发现任何托管 SipName UM 拨号计划的 Exchange 服务器；这些服务器将自动添加到 Lync Server 已知服务器列表中。无需创建受信任应用程序池并将这些服务器添加到已知服务器列表中。事实上，这样做将导致 Outlook Web App 集成停止工作。

> [!NOTE]  
> 这是因为 Lync Server 拓扑现在将具有同一计算机的两个条目：自动发现的条目和手动添加的条目。若要解决此问题并使 Outlook Web App 再次工作，请使用 Windows PowerShell 来移除服务器的受信任池和受信任应用程序条目。有关详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</a> 和 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</a> cmdlet 的帮助主题。



如果这两个服务运行在单独的计算机上，则在确认已安装统一通信托管 API 4.0 运行时后，您必须创建与 Outlook Web App 关联的 Lync Server 受信任应用程序池和受信任应用程序；这会将服务器添加到已知服务器列表中。为此，请首先从 Lync Server 命令行管理程序中运行类似于以下命令的命令：

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

在上面的命令中，atl-owa-001.litwareinc.com 是 Outlook Web App 池的完全限定域名；此名称必须与提供对 Outlook Web App 的访问权的证书的“使用者名称”和“使用者替代名称(SAN)”字段中显示的名称相同。同样，atl-cs-001.litwareinc.com 是将托管新的受信任应用程序池的 Lync Server 2013 池的完全限定域名。另请注意，指定的网站 Redmond 表示 Lync Server 网站的 SiteID。SiteID 并不一定与网站的 DisplayName 相同；您可以通过从 Lync Server 命令行管理程序中运行以下命令来检索 Lync Server 网站的 SiteID：

    Get-CsSite | Select-Object DisplayName, SiteID

在创建受信任应用程序池后，可使用类似于以下命令的命令为 Outlook Web App 配置应用程序标识和端口：

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

在上面的命令中，ApplicationID 只是一个用于区分各个受信任应用程序的友好标识符。ApplicationID 可以是任何不包含空格或其他禁用字符的文本字符串。（为了确保您创建有效标识符，建议您在指定 ApplicationId 时仅使用字母和数字。）赋给 Port 参数的值也将由管理员处理：它可以是任何可用网络端口。

在创建受信任应用程序后，您必须运行以下命令来启用对 Lync Server 拓扑所做的更改：

    Enable-CsTopology

请注意，您还必须将 Exchange 客户端访问和邮箱服务器添加到所有 SIP Uri 拨号计划中。这又会将服务器配置为 Lync Server 的具有 ExUmRouting 拓扑的受信任 SIP 对等机。

**在 Outlook Web App 上启用即时消息**

正确配置 Lync Server 之后，您即可开始配置 Outlook Web App。该过程的第一步是对前端服务器上的所有 Outlook Web App 虚拟目录启用即时消息。（无需为后端服务器上的虚拟目录启用即时消息。事实上，建议您不要在后端服务器上启用即时消息。）可通过从 Exchange 命令行管理程序中运行以下命令来在客户端访问服务器上启用即时消息：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

> [!NOTE]  
> 默认情况下，在您安装 Outlook Web App 时会启用即时消息；也就是说，InstantMessagingEnabled 属性设置为 True。不过，您仍必须运行上面的命令才能将即时消息类型设置为 OCS。默认情况下，InstantMessagingType 设置为 None。



接下来，您必须向 Outlook Web App Web.config 文件（此文件通常位于文件夹 C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa 中）中添加以下两行。这两行应添加在 Web.config 文件中的 \<应用程序设置\> 节点之下，并且应仅在安装了 Outlook Web App 的后端服务器上执行此过程。

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

在上面的示例中，IMCertificateThumbprint 的值必须为安装在后端服务器上的 Exchange 2013 证书的指纹。您可以通过从 Exchange 命令行管理程序中运行以下命令来检索该信息：

    Get-ExchangeCertificate

另请注意，赋给 IMServerName 的值是您在其中为 Outlook Web App 创建受信任应用程序池的 Lync Server 池的完全限定域名。

用于 Outlook Web App 的证书必须是 Lync Server 信任的证书。确保证书将同时受 Lync Server 和 Exchange 信任的一种方法是使用内部证书颁发机构在邮箱服务器上创建证书，从而确保服务器 FQDN 用作使用者名称，并且此 FQDN 显示在证书替代名称字段中。在创建证书之后，可以将证书导入到后端服务器。最终结果是同一证书用于两种目的：1) Exchange 统一消息和 Lync Server 之间的通信；2) Outlook Web App 和 Lync Server 之间的集成。

更新 Web.config 文件之后，您应在 Exchange 后端服务器上运行以下命令以便回收 Outlook Web App 池：

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

如果回收操作成功，则 Exchange 命令行管理程序中将显示以下消息：

    "MSExchangeOWAAppPool" successfully recycled

**配置 Outlook Web App 邮箱策略**

此时，您可以使用以下命令为一个或多个相应 Outlook Web App 邮箱策略配置即时消息。例如，在您的某个邮箱服务器上运行的以下命令将为 Default 策略启用即时消息：

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

以下命令将为您的所有 Outlook Web App 邮箱策略启用即时消息：

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

启用邮箱策略之后，由该策略管理的所有用户将实现 Lync Server 与 Outlook Web App 之间的完全集成，前提是：

  - 用户在 Exchange 2013 上具有邮箱。

  - 已为用户启用 Lync Server 2013。

  - 用户具有有效的 SIP 代理地址。

**在 Outlook Web App 中禁用即时消息**

如上所述，在 Outlook Web App 中，默认启用即时消息。这意味着，如果您没有将 Outlook Web App 与 Lync Server 集成，则用户在每次登录到 Outlook Web App 时都会看到空白状态图标和错误消息。若要防止此问题，请使用以下 Exchange 命令行管理程序命令在 Outlook Web App 中禁用即时消息：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**验证与 Outlook Web App 的集成**

若要验证即时消息和状态是否已与 Outlook Web App 集成，请登录到 Outlook Web App 2013。在屏幕的右上角，您将看到 Exchange 显示名称。如果您的名称旁边有状态图标（例如，指示您的当前状态为“有空”的绿色图标），则指示您已成功地将 Lync Server 与 Outlook Web App 集成。

在初次登录到 Outlook Web App 之后，请检查以了解具有事件 ID 112（和源 MSExchange OWA）的事件是否已写入到邮箱服务器上的事件日志中。此事件指示已成功初始化 Instant Messaging Endpoint Manager。如果即时消息似乎没有工作，则在邮箱服务器上，查找文件夹 C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging 中的日志文件。如果 Logging 或 InstantMessaging 文件夹不存在，则指示集成失败。在此情况下，您可以使用 Lync Server 上的 SIPStack 跟踪（所有级别和所有标志）来尝试确定集成失败的原因。

