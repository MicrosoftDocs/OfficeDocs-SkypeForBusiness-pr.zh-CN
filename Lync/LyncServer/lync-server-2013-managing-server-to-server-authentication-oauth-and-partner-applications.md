---
title: 在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序
TOCTitle: 在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204817(v=OCS.15)
ms:contentKeyID: 49312534
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序

 

_**上一次修改主题：** 2015-05-14_

Microsoft Lync Server 2013 必须能够安全、顺畅地与其他应用程序和服务器产品通信。例如，可以对 Lync Server 2013 进行配置，以便将联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013 中；但是，仅当 Lync Server 和 Exchange 能够安全地相互通信时，才能实现这一点。同样地，您可以在 Microsoft SharePoint Server 中安排 Lync Server 会议；这同样需要两台服务器（SharePoint 和 Lync Server）相互信任。尽管可以对 Lync 与 Exchange 的通信使用一种身份验证机制，而对 Lync 与 SharePoint 的通信使用另一种身份验证机制，但更好也是更高效的方法是对服务器到服务器的身份验证和授权使用一种标准化方法。

Lync Server 2013 采用的方法是对服务器到服务器身份验证使用单个标准化方法。对于 2013 版本，Lync Server 2013（以及其他 Microsoft 服务器产品，包括 Exchange 2013 和 Microsoft SharePoint Server）都支持对服务器到服务器身份验证和授权使用 OAuth（开放式授权）协议。OAuth 是许多重要网站使用的标准授权协议，使用该协议时，用户凭据和密码不会从一台计算机传递到另一台计算机，而是通过交换安全令牌来进行身份验证和授权；这些令牌会授予在特定时间段内对一组特定资源的访问权限。

OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。（也可以在不使用授权服务器的情况下执行服务器到服务器身份验证，下文中将会讨论这一过程。）安全令牌由授权服务器（也称为安全令牌服务器）颁发给需要通信的两个领域；这些令牌会确认一个领域是否应信任源自另一个领域的通信。例如，授权服务器颁发的令牌可能验证来自 Lync Server 2013 领域的用户是否能够访问指定的 Exchange 2013 领域，以及相反情况。

> [!NOTE]  
> 领域只是一个安全容器。默认情况下，Lync Server 2013 将您的默认 SIP 域用作其 OAuth 领域。



Lync Server 2013 支持三种服务器到服务器身份验证方案。使用 Lync Server 2013，您可以：

  - 在 Lync Server 2013 的本地部署和 Exchange 2013 以及/或者 Microsoft SharePoint Server 的本地部署之间配置服务器到服务器身份验证。

  - 在一对 Office 365 组件（例如，在 Microsoft Exchange 与 Microsoft Lync Server 之间或 Microsoft Lync Server 与 Microsoft SharePoint 之间）配置服务器到服务器身份验证。

  - 在跨域环境中配置服务器到服务器身份验证（即，本地服务器和 Office 365 组件之间的服务器到服务器身份验证）。

请注意，目前只有 Exchange 2013、SharePoint Server 和 Lync Server 2013 支持服务器到服务器身份验证；如果您没有运行这些服务器之一，将无法充分实现 OAuth 身份验证。

还应指出的是，您不需要使用服务器到服务器身份验证：只有在部署 Lync Server 2013 时才需要服务器到服务器身份验证。如果 Lync Server 2013 不需要与其他服务器（如 Exchange 2013）通信，则不需要服务器到服务器身份验证。

但是，如果您想使用 Lync Server 的某些新功能（例如“统一联系人存储”），则需要服务器到服务器身份验证。使用统一联系人存储，Lync Server 2013 联系人信息存储在 Exchange 2013 中而不是 Lync Server 中；这使用户具有一组可随时从 Lync、Microsoft Outlook 或 Microsoft Outlook Web Access 访问的联系人。由于统一联系人存储要求 Lync Server 2013 与 Exchange 2013 共享信息，因此您必须使用服务器到服务器身份验证才能部署该功能。如果选择使用 Exchange 存档（其中，即时消息会话的脚本保存为 Exchange 2013 电子邮件而不是单个数据库记录），也需要服务器到服务器身份验证。

要使 Office 365 版本的 Lync Server 与其对应版本的 Exchange 通信，Lync Server 2013 必须首先从授权服务器获取安全令牌。Lync Server 然后使用该安全令牌向 Exchange 标明自己的身份。Office 365 版本的 Exchange 必须经历相同的过程才能与 Lync Server 2013 通信。

但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。诸如 Lync Server 2013 和 Exchange 2013 之类的服务器产品具有内置的令牌服务器，可用于向其他支持服务器到服务器身份验证的 Microsoft 服务器（例如 SharePoint 服务器）进行身份验证。例如，Lync Server 2013 本身可以颁发和签署安全令牌，然后使用该令牌与 Exchange 2013 通信。在此类情况下，不需要第三方令牌服务器。

为了对 Lync Server 2013 本地实现配置服务器到服务器身份验证，您必须执行以下操作：

  - 向 Lync Server 内置的令牌颁发者分配证书。

  - 将 Lync Server 2013 将与之通信的服务器配置为“合作伙伴应用程序”。例如，如果 Lync Server 2013 需要与 Exchange 2013 通信，则需要将 Exchange 配置为合作伙伴应用程序。

> [!NOTE]  
> “合作伙伴应用程序”是 Lync Server 2013 需要/无需通过第三方安全令牌服务器即可与之直接交换安全令牌的任何应用程序。



请注意，OAuth 是产品的核心部分，不可禁用或删除。

## 另请参阅

#### 概念

[将服务器到服务器身份验证证书分配到 Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[在交叉部署环境中配置 Microsoft Lync Server 2013](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)

