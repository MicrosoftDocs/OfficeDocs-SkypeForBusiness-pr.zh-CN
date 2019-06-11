---
title: 在 Lync Server 2013 和 Exchange Server 2013 中配置合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-12_

服务器到服务器身份验证通常涉及三个实体: 两台需要相互通信的服务器, 以及第三方安全令牌服务器。 如果两台服务器 (如服务器 A 和服务器 B) 需要通信, 则这两个服务器通常都通过联系令牌服务器并获取相互信任的安全令牌开始。 然后, 服务器 A 将该安全令牌呈现给服务器 B (反之亦然), 以确保其真实性及其可信性。

但是, 这是一个一般规则。 Lync Server 2013、Microsoft Exchange Server 2013 和 Microsoft SharePoint Server 2013 在彼此通信时不需要使用第三方令牌服务器;这是因为这些服务器产品可以创建彼此不需要单独的令牌服务器即可接受的安全令牌。 (此功能仅在 Lync Server 2013、Exchange 2013 和 SharePoint Server 2013 中可用。 如果需要与其他服务器 (包括其他 Microsoft 服务器产品) 设置服务器到服务器的身份验证, 则需要使用第三方令牌服务器执行此操作。

为了在 Lync Server 和 Exchange 之间设置服务器到服务器身份验证, 您必须执行两项操作: 1) 您必须为每台服务器分配相应的证书;和 2), 您必须将每台服务器配置为另一台服务器的合作伙伴应用程序: 这意味着您必须将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序, 并且您必须将 Exchange 2013 配置为适用于 Lync Server 2013 的合作伙伴应用程序。

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>将 Lync Server 2013 配置为适用于 Exchange 2013 的合作伙伴应用程序

将 Lync Server 2013 配置为具有 Exchange 2013 的合作伙伴应用程序的最简单方法是运行 Configure-EnterprisePartnerApplication 脚本, 该脚本是随 Exchange 2013 一起提供的 Windows PowerShell 脚本。 若要运行此脚本, 必须提供 Lync Server 身份验证元数据文档的 URL;这通常是 Lync Server 2013 池的完全限定的域名, 后跟后缀/metadata/json/1。 例如：

    https://atl-cs-001.litwareinc.com/metadata/json/1

若要将 Lync Server 配置为合作伙伴应用程序, 请打开 Exchange 命令行管理程序并运行与此类似的命令 (假设 Exchange 已安装在驱动器 C: 上, 并且它使用默认文件夹路径):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

配置合作伙伴应用程序后, 建议您在 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet 信息服务 (IIS)。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：

    iisreset atl-exchange-001

此命令可以从 Exchange 命令行管理程序中运行, 也可以从任何其他命令窗口中通过管理员权限运行。

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>将 Exchange 2013 配置为 Lync Server 2013 的合作伙伴应用程序

将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序后, 必须将 Exchange 配置为 Lync Server 的合作伙伴应用程序。 这可以通过使用 Lync Server 命令行管理程序并指定 Exchange 的身份验证元数据文档来完成;这通常是 Exchange 自动发现服务的 URI, 后跟后缀/metadata/json/1。 例如：

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

在 Lync Server 中, 通过使用[CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) cmdlet 配置合作伙伴应用程序。 除了指定元数据 URI 之外, 还应将应用程序信任级别设置为 "完全";这将允许 Exchange 同时代表领域中的自身和任何授权用户。 例如：

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

或者, 你可以通过复制和修改 Lync Server 2013 服务器到服务器身份验证文档中找到的脚本代码来创建合作伙伴应用程序。 有关详细信息, 请参阅[管理 Lync server 2013 中的服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序一](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)文。

如果你已成功配置 Lync Server 和 Exchange 的合作伙伴应用程序, 这意味着你还在两个产品之间成功配置了服务器到服务器的身份验证。 Lync Server 2013 包括一个 Windows PowerShell cmdlet [CsExStorageConnectivity 测试](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))版, 该 cmdlet 使你能够验证是否已正确配置服务器到服务器身份验证以及 Lync Server 存储服务是否可以连接到 Exchange2013。 该 cmdlet 通过以下方式执行此操作: 连接到 Exchange 2013 用户的邮箱, 向该用户的 "对话历史记录" 文件夹中写入一个项目, 然后也可以删除该项目。

若要测试 Lync Server 2013 和 Exchange 2013 的集成, 请在 Lync Server 命令行管理程序中运行类似下面的命令:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

在前面的命令中, SipUri 表示在 Exchange 2013 上具有帐户的用户的 SIP 地址;您的命令将失败, 这不是有效的用户帐户。

如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。

</div>

</div>

<span> </span>

</div>

</div>

</div>

