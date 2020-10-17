---
title: 管理 (OAuth) 和合作伙伴应用程序的服务器到服务器身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bea847e1d0c4d9c42808a93f3c56bcd7391bece
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507159"
---
# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>在 Lync Server 2013 中管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-05-14_

Microsoft Lync Server 2013 必须能够与其他应用程序和服务器产品进行安全和无缝的通信。 例如，您可以配置 Lync Server 2013，以便将联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013 中;但是，只有当 Lync Server 和 Exchange 能够安全地相互通信时，才能执行此操作。 同样地，您可以在 Microsoft SharePoint Server 中安排 Lync Server 会议；这同样需要两台服务器（SharePoint 和 Lync Server）相互信任。 尽管可以对 Lync 与 Exchange 的通信使用一种身份验证机制，而对 Lync 与 SharePoint 的通信使用另一种身份验证机制，但更好也是更高效的方法是对服务器到服务器的身份验证和授权使用一种标准化方法。

使用单个标准化的服务器到服务器身份验证方法是 Lync Server 2013 采用的方法。 对于2013版本，Lync Server 2013 (以及其他 Microsoft Server 产品，包括 Exchange 2013 和 Microsoft SharePoint Server) 支持 OAuth (开放式授权) 协议用于服务器到服务器身份验证和授权。 使用 OAuth （一系列主要网站使用的标准授权协议），用户凭据和密码不会从一台计算机传递到另一台计算机。 但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。

OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。  (您还可以执行服务器到服务器身份验证，而无需使用授权服务器，此过程将在本文档后面讨论。 ) 安全令牌由授权服务器颁发 (也称为安全令牌服务器) 到需要通信的两个领域;这些令牌验证来自一个领域的通信是否应由另一个领域信任。 例如，授权服务器可能会颁发令牌，以验证特定 Lync Server 2013 领域中的用户是否能够访问指定的 Exchange 2013 领域，反之亦然。

<div>


> [!NOTE]
> 领域只是一个安全容器。 默认情况下，Lync Server 2013 使用您的默认 SIP 域作为其 OAuth 领域。 其他 SIP 命名空间将添加到 OAuth 证书中的 "使用者替换名称" 列表中。



</div>

Lync Server 2013 支持三种服务器到服务器身份验证方案。 使用 Lync Server 2013，可以执行以下操作：

  - 在本地安装 Lync Server 2013 和本地安装 Exchange 2013 和/或 Microsoft SharePoint Server 之间配置服务器到服务器的身份验证。

  - 在一对 Microsoft 365 组件之间配置服务器到服务器的身份验证 (例如，在 Microsoft Exchange 和 Microsoft Lync Server 之间，或在 Microsoft Lync Server 和 Microsoft SharePoint) 之间进行身份验证。

  - 在跨界环境中配置服务器到服务器身份验证 (也就是说，内部部署服务器和 Microsoft 365 组件之间的服务器到服务器身份验证) 。

请注意，在此时间点，只有 Exchange 2013、SharePoint Server 和 Lync Server 2013 支持服务器到服务器身份验证;如果没有运行这些服务器之一，则将无法完全实现 OAuth 身份验证。

还应指出，您不需要使用服务器到服务器身份验证：不需要使用服务器到服务器身份验证即可部署 Lync Server 2013。 如果 Lync Server 2013 不需要与其他服务器通信 (如 Exchange 2013) 则不需要服务器到服务器身份验证。

但是，如果您想使用 Lync Server 的某些新功能（例如“统一联系人存储”），则需要服务器到服务器身份验证。 使用统一的联系人存储，Lync Server 2013 联系人信息存储在 Exchange 2013 中，而不是存储在 Lync Server 中;这使用户可以在 Lync、Microsoft Outlook 或 Microsoft Outlook Web Access 中提供一组可随时访问的联系人。 由于统一联系人存储要求 Lync Server 2013 与 Exchange 2013 共享信息，因此必须使用服务器到服务器身份验证才能部署该功能。 如果您选择使用 Exchange 存档（其中即时消息会话的脚本保存为 Exchange 2013 电子邮件，而不是单个数据库记录），则也需要服务器到服务器身份验证。

对于 Microsoft 365 版本的 Lync Server，若要与其 Exchange 副本进行通信，Lync Server 2013 必须首先从授权服务器获取一个安全令牌。 然后，Lync Server 使用该安全令牌向 Exchange 标识自己。 Microsoft 365 版本的 Exchange 必须经过相同的过程才能与 Lync Server 2013 通信。

但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。 服务器产品（例如 Lync Server 2013 和 Exchange 2013）具有内置令牌服务器，可用于对其他 Microsoft 服务器 (（如支持服务器到服务器身份验证的 SharePoint Server) ）进行身份验证。 例如，Lync Server 2013 本身可以颁发和签署安全令牌，然后使用该令牌与 Exchange 2013 进行通信。 在此类情况下，不需要第三方令牌服务器。

为了为 Lync Server 2013 的本地实现配置服务器到服务器身份验证，您必须执行以下两项操作：

  - 向 Lync Server 内置的令牌颁发者分配证书。

  - 将 Lync Server 2013 将与之通信的服务器配置为 "合作伙伴应用程序"。 例如，如果 Lync Server 2013 需要与 Exchange 2013 通信，则需要将 Exchange 配置为合作伙伴应用程序。

<div>


> [!NOTE]
> "合作伙伴应用程序" 是 Lync Server 2013 可以直接与之交换安全令牌的任何应用程序，无需经过第三方安全令牌服务器。



</div>

请注意，OAuth 是产品的核心部分，无法禁用或删除。

<div>

## <a name="see-also"></a>另请参阅


[将服务器到服务器身份验证证书分配给 Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[在跨界环境中配置 Microsoft Lync Server 2013](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

