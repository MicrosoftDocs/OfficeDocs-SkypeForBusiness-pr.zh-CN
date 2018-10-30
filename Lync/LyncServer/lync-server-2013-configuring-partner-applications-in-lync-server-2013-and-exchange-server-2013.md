---
title: 在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序
TOCTitle: 在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49888531
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序

 

_**上一次修改主题：** 2016-12-08_

服务器到服务器身份验证通常涉及三个实体：两台需要相互通信的服务器以及一台第三方安全令牌服务器。如果两台服务器（例如，服务器 A 和服务器 B）需要通信，则这两台服务器一般通过联系令牌服务器并获取相互信任的安全令牌来启动。之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。

但这只是一般规则。Lync Server 2013、Microsoft Exchange Server 2013 和 Microsoft SharePoint Server 2013 相互通信时无需使用第三方令牌服务器；这是因为这些服务器产品创建了互相可接受的安全令牌，因此无需单独的令牌服务器。（仅 Lync Server 2013、Exchange 2013 和 SharePoint Server 2013 中提供了此功能。如果您需要设置与其他服务器（包括其他 Microsoft 服务器产品）的服务器到服务器身份验证，则需要使用第三方令牌服务器来执行此操作。）

为了设置 Lync Server 和 Exchange 之间的服务器到服务器身份验证，您必须执行下列两项操作：1) 您必须为每台服务器分配适当的证书；2) 您必须将每台服务器配置为另一台服务器的合作伙伴应用程序：这意味着您必须将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序，并且必须将 Exchange 2013 配置为 Lync Server 2013 的合作伙伴应用程序。

## 将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序

将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序的一种最简单的方式是运行 Configure-EnterprisePartnerApplication.ps1 脚本（Exchange 2013 附带的 Windows PowerShell 脚本）。若要运行此脚本，您必须提供 Lync Server 身份验证元数据文档的 URL；这一般是 SharePoint 池的完全限定域名后跟后缀 /metadata/json/1。例如：

    https://atl-cs-001.litwareinc.com/metadata/json/1

若要将 Lync Server 配置为合作伙伴应用程序，请打开 Exchange 命令行管理程序，然后运行类似于以下命令的命令（假定已将 Exchange 安装在驱动器 C: 上并且其使用默认文件夹路径）：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

配置合作伙伴应用程序之后，建议您在 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet Information Services (IIS)。您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：

    iisreset atl-exchange-001

此命令可从 Exchange 命令行管理程序运行，也可从在管理员权限下运行的任何其他命令窗口运行。

## 将 Exchange 2013 配置为 Lync Server 2013 的合作伙伴应用程序

将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序之后，您必须将 Exchange 配置为 Lync Server 的合作伙伴应用程序。这可通过使用 Lync Server 命令行管理程序并指定 Exchange 的身份验证元数据文档来完成；这通常是 Exchange 自动发现服务的 URI 后跟后缀 /metadata/json/1。例如：

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

在 Lync Server 中，将使用 [New-CsPartnerApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPartnerApplication) cmdlet 配置合作伙伴应用程序。除了指定元数据 URI 之外，还应将应用程序信任级别设置为“完全”；这将允许 Exchange 表示自身和领域中的任何已授权用户。例如：

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

此外，您还可通过复制和修改在 Lync Server 2013 服务器到服务器身份验证文档中找到的脚本代码来创建合作伙伴应用程序。有关详细信息，请参阅文章[在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

如果您已成功为 Lync Server 和 Exchange 配置了合作伙伴应用程序，则意味着您同样已成功配置了这两个产品之间的服务器到服务器身份验证。Lync Server 2013 包含一条 Windows PowerShell cmdlet [Test-CsExStorageConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExStorageConnectivity)，这使您可验证是否已正确配置服务器到服务器身份验证，以及 Lync Server 存储服务是否可连接到 Exchange 2013。此 cmdlet 是通过连接到 Exchange 2013 用户的邮箱、将某个项目写入用户的对话历史记录文件夹，然后（可选）删除该项目来进行验证的。

若要测试 Lync Server 2013 和 Exchange 2013 的集成，请在 Lync Server 命令行管理程序中运行一条类似于以下命令的命令：

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

在上面的命令中，SipUri 表示使用 Exchange 2013 帐户的用户的 SIP 地址；您的命令将失败，因为这不是一个有效的用户帐户。

如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。

