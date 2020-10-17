---
title: 在 Lync Server 2013 和 Exchange Server 2013 中配置合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8743b012042738ea25653cf49a804e08d59a423
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532509"
---
# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-12_

服务器到服务器身份验证通常涉及三个实体：两台需要相互通信的服务器以及一台第三方安全令牌服务器。如果两台服务器（例如，服务器 A 和服务器 B）需要通信，则这两台服务器一般通过联系令牌服务器并获取相互信任的安全令牌来启动。之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。

但是，这是一般规则。 Lync Server 2013、Microsoft Exchange Server 2013 和 Microsoft SharePoint Server 2013 在彼此通信时不需要使用第三方令牌服务器;这是因为这些服务器产品可以创建可以接受的安全令牌，而无需单独的令牌服务器。  (此功能仅在 Lync Server 2013、Exchange 2013 和 SharePoint Server 2013 中可用。 如果需要设置与其他服务器（包括其他 Microsoft 服务器产品）的服务器到服务器身份验证，则需要使用第三方令牌服务器执行此操作。 ) 

若要在 Lync Server 和 Exchange 之间设置服务器到服务器身份验证，您必须执行以下两项操作： 1) 您必须为每台服务器分配适当的证书;2) 您必须将每台服务器配置为另一台服务器的合作伙伴应用程序：这意味着您必须将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序，并且必须将 Exchange 2013 配置为 Lync Server 2013 的合作伙伴应用程序。

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序

将 Lync Server 2013 配置为具有 Exchange 2013 的合作伙伴应用程序的最简单方法是运行 Configure-EnterprisePartnerApplication.ps1 脚本，该脚本是 Exchange 2013 附带的 Windows PowerShell 脚本。 若要运行此脚本，您必须提供 Lync Server 身份验证元数据文档的 URL;这通常是 Lync Server 2013 池的完全限定的域名，后跟后缀/metadata/json/1。 例如：

    https://atl-cs-001.litwareinc.com/metadata/json/1

若要将 Lync Server 配置为合作伙伴应用程序，请打开 Exchange 命令行管理程序，并运行与此 (类似的命令，假设 Exchange 已安装在驱动器 C：上，并且它使用默认文件夹路径) ：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

在配置合作伙伴应用程序之后，建议您在 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet 信息服务 (IIS) 。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：

    iisreset atl-exchange-001

可以在 Exchange 命令行管理程序或任何其他命令窗口中从管理员权限下运行此命令。

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>将 Exchange 2013 配置为 Lync Server 2013 的合作伙伴应用程序

将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序后，必须将 Exchange 配置为 Lync Server 的合作伙伴应用程序。 这可以通过使用 Lync Server 命令行管理程序并为 Exchange 指定身份验证元数据文档来实现;这通常是 Exchange 自动发现服务的 URI，后跟后缀/metadata/json/1。 例如：

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

在 Lync Server 中，通过使用 [CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet 配置合作伙伴应用程序。 除了指定元数据 URI 之外，还应将应用程序信任级别设置为 "完全";这将允许 Exchange 代表其自身和领域中的任何授权用户。 例如：

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

或者，您可以通过复制和修改在 Lync Server 2013 服务器到服务器身份验证文档中找到的脚本代码来创建合作伙伴应用程序。 有关详细信息，请参阅 [管理 Lync server 2013 中的服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序一](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 文。

如果你已为 Lync Server 和 Exchange 成功配置了合作伙伴应用程序，这意味着你还在两个产品之间成功配置了服务器到服务器的身份验证。 Lync Server 2013 包括一个 Windows PowerShell cmdlet [CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))，可让你验证是否已正确配置服务器到服务器身份验证，以及 Lync Server Storage Service 是否可以连接到 Exchange 2013。 通过连接到 Exchange 2013 用户的邮箱，向该用户的对话历史记录文件夹中写入一个项目，然后删除该项目（可选），cmdlet 可执行此项。

若要测试 Lync Server 2013 和 Exchange 2013 的集成，请在 Lync Server 命令行管理程序中运行与以下内容类似的命令：

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

在上面的命令中，SipUri 表示在 Exchange 2013 上具有帐户的用户的 SIP 地址;在这不是一个有效的用户帐户时，您的命令将失败。

如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。

</div>

</div>

<span> </span>

</div>

</div>

</div>

