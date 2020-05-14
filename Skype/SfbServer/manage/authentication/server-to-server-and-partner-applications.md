---
title: 在 Skype for Business Server 中管理服务器到服务器的身份验证（OAuth）和合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 摘要：在 Skype for Business Server 中管理 OAuth 和合作伙伴应用程序。
ms.openlocfilehash: f784dd0a2dab05fb3b97497fab7d3866dda1a753
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221666"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>在 Skype for Business Server 中管理服务器到服务器的身份验证（OAuth）和合作伙伴应用程序
 
**摘要：** 在 Skype for Business Server 中管理 OAuth 和合作伙伴应用程序。
  
Skype for Business Server 必须能够与其他应用程序和服务器产品进行安全和无缝的通信。 例如，您可以配置 Skype for Business Server，以便将联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013 中;但是，只有在 Skype for business Server 和 Exchange 能够与其他人进行安全通信时，才能执行此操作。 同样，您可以从 Office Web Apps Server 中计划 Skype for Business Server 会议;同样，只有在两台服务器（SharePoint 和 Skype for Business Server）相互信任的情况下，才能执行此操作。 尽管可以使用一种身份验证机制进行 Skype for business Server 和 Exchange 之间的通信，而不是用于 Skype for business Server 和 SharePoint 通信的单独机制，但更好且更有效的方法是对所有服务器到服务器的身份验证和授权使用标准化的方法。
  
使用单个标准化的服务器到服务器身份验证方法是 Skype for business Server 采用的方法。 从 Office server 2013 版本开始，Skype for Business Server （以及其他 Microsoft Server 产品，包括 Exchange Server 和 SharePoint Server）支持用于服务器到服务器身份验证和授权的 OAuth （开放式授权）协议。 使用 OAuth （一系列主要网站使用的标准授权协议），用户凭据和密码不会从一台计算机传递到另一台计算机。 但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。
  
OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。 （您还可以执行服务器到服务器身份验证，而无需使用授权服务器，本文档后面将讨论的过程。）安全令牌由授权服务器（也称为安全令牌服务器）颁发给需要通信的两个领域;这些令牌验证来自一个领域的通信是否应由另一个领域信任。 例如，授权服务器可能会颁发令牌，以验证特定 Skype for Business Server 领域中的用户是否能够访问指定的 Exchange 领域，反之亦然。
  
> [!NOTE]
> 领域只是一个安全容器。 默认情况下，Skype for Business Server 使用您的默认 SIP 域作为其 OAuth 领域。 其他 SIP 命名空间将添加到 OAuth 证书中的 "使用者替换名称" 列表中。 
  
Skype for Business Server 支持三种服务器到服务器身份验证方案。 使用 Skype for Business Server，可以执行以下操作：
  
- 在本地安装 Skype for Business Server 和本地安装 Exchange 和/或 SharePoint Server 之间配置服务器到服务器的身份验证。
    
- 在一对 Microsoft 365 或 Office 365 组件（例如，介于 Microsoft Exchange Server 和 Skype for business Server 之间，或在 Skype for business Server 和 SharePoint 之间）配置服务器到服务器的身份验证。
    
- 在跨界环境中配置服务器到服务器身份验证（即，本地服务器与 Microsoft 365 或 Office 365 组件之间的服务器到服务器身份验证）。
    
请注意，在此时间点，仅限 Exchange 2013、SharePoint Server、Lync Server 2013、Skype for business Server 2015 和 Skype for Business 2019 支持服务器到服务器身份验证;如果没有运行这些服务器之一，将无法完全实现 OAuth 身份验证。
  
此外，还应指出服务器到服务器身份验证是可选的：如果 Skype for Business Server 不需要与其他服务器（如 Exchange）通信，则可以完全跳过服务器到服务器身份验证。 如果已为 Lync Server 2013 和其他应用程序配置了服务器到服务器身份验证，则无需为 Skype for business Server 重新执行此操作。 
  
但是，如果您想要使用 Skype for Business Server 中的某些功能（如 "统一联系人存储"），则需要服务器到服务器身份验证。 使用统一联系人存储，Skype for Business Server 联系人信息存储在 Exchange 中，而不是存储在 Skype for Business Server 中;这使用户可以在 Skype for Business、Outlook 或 Outlook Web Access 中使用一组可随时访问的联系人。 由于统一联系人存储要求 Skype for Business Server 与 Exchange 共享信息，因此必须使用服务器到服务器身份验证才能部署该功能。 如果您选择使用 Exchange 存档（其中即时消息会话的脚本保存为 Exchange 电子邮件，而不是作为单个数据库记录），则也需要服务器到服务器身份验证。
  
若要使 Microsoft 365 或 Office 365 版本的 Skype for Business Server 与其 Exchange 对应副本通信，Skype for Business Server 必须首先从授权服务器获取安全令牌。 然后，Skype for Business Server 使用该安全令牌向 Exchange 标识自己。 Microsoft 365 或 Office 365 版本的 Exchange 必须经过相同的过程才能与 Skype for Business Server 进行通信。
  
但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。 服务器产品（例如 Skype for Business Server 和 Exchange）具有内置令牌服务器，可用于与支持服务器到服务器身份验证的其他 Microsoft 服务器（如 SharePoint Server）进行身份验证。 例如，Skype for Business Server 本身可以颁发和签名安全令牌，然后使用该令牌与 Exchange 进行通信。 在此类情况下，不需要第三方令牌服务器。
  
为了为 Skype for business Server 的本地实施配置服务器到服务器身份验证，您必须执行以下两项操作：
  
- 将证书分配给内置 Skype for Business Server 令牌颁发者。
    
- 将 Skype for Business Server 将与之通信的服务器配置为 "合作伙伴应用程序"。 例如，如果 Skype for Business Server 需要与 Exchange 进行通信，则需要将 Exchange 配置为合作伙伴应用程序。
    
> [!NOTE]
> "合作伙伴应用程序" 是 Skype for Business Server 可以直接与之交换安全令牌的任何应用程序，无需经过第三方安全令牌服务器。 
  
请注意，OAuth 是产品的核心部分，无法禁用或删除。
  
## <a name="see-also"></a>另请参阅

[为 Skype for Business Server 分配服务器到服务器身份验证证书](assign-a-server-to-server-certificate.md)
  
[在 Skype for Business Server 中配置混合环境](configure-a-hybrid-environment.md)
