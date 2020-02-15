---
title: Lync Server 2013：与 Exchange Server 2013 集成的先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92f88d35e573f0914698db28ddcf1fa54967f97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-22_

在集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 之前，必须确保所有先决条件步骤都已完成。 正如您所料，在 Exchange 2013 和 Lync Server 2013 完全安装并运行之前，不会发生集成。 有关安装 Exchange 的详细信息，请参阅位于[http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)的 Exchange 2013 规划和部署文档。 有关安装 Lync Server 2013 的详细信息，请参阅中的规划和[http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)部署文档。

在服务器启动并运行之后，您必须为 Lync Server 2013 和 Exchange 2013 分配服务器到服务器身份验证证书;这些证书允许 Lync Server 和 Exchange 交换信息，并与其他人通信。 当您安装 Exchange 2013 时，将为您创建名称为 Microsoft Exchange Server 身份验证证书的自签名证书。 此证书（可在本地计算机证书存储中找到）应用于 Exchange 2013 上的服务器到服务器身份验证。 有关在 Exchange 2013 中分配证书的详细信息，请参阅处[http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)的 "配置邮件流和客户端访问"。

对于 Lync Server 2013，您可以使用现有的 Lync Server 证书作为服务器到服务器身份验证证书;例如，您的默认证书也可以用作 OAuthTokenIssuer 证书。 Lync Server 2013 允许您将任何 Web 服务器证书用作服务器到服务器身份验证的证书，前提是：

  - 该证书包括主题字段中 SIP 域的名称。

  - 在所有前端服务器上配置与 OAuthTokenIssuer 证书相同的证书。

  - 该证书长度至少为 2048 字节。

有关 Microsoft Lync Server 2013 的服务器到服务器身份验证证书的详细信息，请参阅[向 Microsoft Lync server 2013 分配服务器到服务器身份验证证书](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)。

在分配证书后，您必须在 Exchange 2013 上配置自动发现服务。 在 Exchange 2013 中，自动发现服务配置用户配置文件，并在用户登录到系统时提供对 Exchange 服务的访问权限。 用户为自动发现服务提供其电子邮件地址，而这些服务为用户提供诸如以下信息：

  - Exchange 2013 的内部和外部连接的连接信息。

  - 用户的邮箱服务器的位置。

  - 用于 Outlook 功能的 URL，例如忙/闲信息、统一消息和脱机通讯簿。

  - Outlook 无处不在服务器设置。

必须先配置自动发现服务，然后才能集成 Lync Server 2013 和 Exchange 2013。 您可以通过在 Exchange 命令行管理程序中运行以下命令并检查确认 autodiscoverserviceinternaluri 属性的值来验证是否已配置自动发现服务：

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

如果此值为空，必须将 URI 分配到自动发现服务。通常此 URI 将看上去类似于：

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

可通过运行类似以下命令分配自动发现 URI：

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

有关自动发现服务的详细信息，请参阅处[http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)的 "了解自动发现服务"。

配置自动发现服务后，必须修改 Lync Server OAuth 配置设置;这将确保 Lync Server 知道在哪里可以找到自动发现服务。 若要在 Lync Server 2013 中修改 OAuth 配置设置，请在 Lync Server 命令行管理程序中运行以下命令。 运行此命令时，请确保指定在 Exchange 服务器上运行的自动发现服务的 URI，并使用**自动发现**来指向服务位置，而不是**自动发现**（指向服务使用的 xml 文件）：

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> 上述命令中的 Identity 参数是可选的;这是因为 Lync Server 仅允许您拥有一个单一的全局 OAuth 配置设置集合。 在其他情况下，这表示您可使用此稍简单的命令配置自动发现 URL：<BR>Set-csoauthconfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>如果您不熟悉该技术，OAuth 是由大量网站使用的标准身份验证协议。借助 OAuth，不会将用户凭据和密码从一台计算机传递到另一台计算机。但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。



</div>

除了配置自动发现服务之外，还必须为指向您的 Exchange 服务器的服务创建 DNS 记录。 例如，如果您的自动发现服务位于 autodiscover.litwareinc.com，则需要为 autodiscover.litwareinc.com 创建一个 DNS 记录，该记录可解析为您的 Exchange 服务器的完全限定域名（例如，atl-exchange-001.litwareinc.com）。

</div>

<span> </span>

</div>

</div>

</div>

