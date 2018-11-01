---
title: 集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件
TOCTitle: 集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49888655
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件

 

_**上一次修改主题：** 2016-12-08_

在您集成到 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 之前，必须确保已完成所有先决条件步骤。如您所预期，在 Exchange 2013 和 Lync Server 2013 完全安装并正常运行前无法集成。有关安装 Exchange 的详细信息，请参阅“Exchange 2013 规划和部署”文档，网址为：[http://go.microsoft.com/fwlink/?linkid=268539\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268539%26clcid=0x804)。有关安装 Lync Server 2013 的详细信息，请参阅规划和部署文档，网址为 [http://go.microsoft.com/fwlink/?linkid=254806\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=254806%26clcid=0x804)。

在服务器正常运行后，必须将服务器到服务器的身份验证证书分配到 Lync Server 2013 和 Exchange 2013；这些证书允许 Lync Server 和 Exchange 交换信息并与另一个进行通信。在您安装 Exchange 2013 时，会为您创建名为 Microsoft Exchange Server Auth 证书的自签名证书。应将此证书（可在本地计算机证书存储中找到）用于 Exchange 2013 上服务器到服务器的身份验证。有关在 Exchange 2013 中分配证书的详细信息，请参阅“配置邮件流和客户端访问”，网址为：[http://go.microsoft.com/fwlink/?linkid=268540\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268540%26clcid=0x804)。

对于 Lync Server 2013，您可以使用现有的 Lync Server 证书作为服务器到服务器的身份验证证书；例如，还可将默认证书用作 OAuthTokenIssuer 证书。Lync Server 2013 允许您使用任何 Web 服务器证书作为用于服务器到服务器身份验证的证书，条件是：

  - 该证书包括主题字段中 SIP 域的名称。

  - 在所有前端服务器上配置与 OAuthTokenIssuer 证书相同的证书。

  - 该证书长度至少为 2048 字节。

有关 Microsoft Lync Server 2013 的服务器到服务器身份验证证书的详细信息，请参阅[将服务器到服务器身份验证证书分配到 Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)。

分配证书后，则必须在 Exchange 2013 上配置自动发现服务。在 Exchange 2013 中，当用户登录到该系统时，自动发现服务会配置用户配置文件并提供对 Exchange 服务的访问权限。用户为自动发现服务提供其电子邮件地址，而这些服务为用户提供诸如以下信息：

  - 到 Exchange 2013 的内部连接和外部连接的连接信息。

  - 用户的邮箱服务器的位置。

  - 用于 Outlook 功能的 URL，例如忙/闲信息、统一消息和脱机通讯簿。

  - Outlook 无处不在服务器设置。

在您集成 Lync Server 2013 和 Exchange 2013 前，必须配置自动发现服务。可验证是否已通过从 Exchange Management Shell 运行下列命令和检查 AutoDiscoverServiceInternalUri 属性的值配置了自动发现服务：

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

如果此值为空，必须将 URI 分配到自动发现服务。通常此 URI 将看上去类似于：

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

可通过运行类似以下命令分配自动发现 URI：

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

有关自动发现服务的详细信息，请参阅“了解自动发现服务”，网址为：[http://go.microsoft.com/fwlink/?linkid=268542\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268542%26clcid=0x804)。

配置自动发现服务后，必须修改 Lync Server OAuth 配置设置；这可确保 Lync Server 知道在哪里找到自动发现服务。要修改 Lync Server 2013 中的 OAuth 配置设置，请从 Lync Server 命令行管理程序 内运行下列命令。运行此命令时，确保将 URI 指定到 Exchange 服务器上运行的自动发现服务，并确保使用 **autodiscover.svc** 代替 **autodiscover.xml**（它指定由该服务使用的 XML 文件）指定服务位置：

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc

> [!NOTE]  
> 上述命令中的 Identity 参数为可选；这是因为 Lync Server 仅允许您单个 OAuth 配置设置的全局集合。在其他情况下，这表示您可使用此稍简单的命令配置自动发现 URL：<br />
Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl &quot;https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc&quot;<br />
如果您不熟悉该技术，OAuth 是由大量网站使用的标准身份验证协议。借助 OAuth，不会将用户凭据和密码从一台计算机传递到另一台计算机。但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。



除了配置自动发现服务外，还必须为指向 Exchange 服务器的服务创建 DNS 记录。例如，如果您的自动发现服务位于 autodiscover.litwareinc.com，则需要为解析为 Exchange 服务器（例如，atl-exchange-001.litwareinc.com）的完全限定域名的 autodiscover.litwareinc.com 创建 DNS 记录。

