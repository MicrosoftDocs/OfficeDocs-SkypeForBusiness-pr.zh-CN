---
title: 在 Skype for Business Server (OAuth) 和合作伙伴应用程序管理服务器到服务器身份验证
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: ff926440d1f00601eacfb77aadb858063b3e48b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828296"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>在 Skype for Business Server (OAuth) 和合作伙伴应用程序管理服务器到服务器身份验证
 
**摘要：** 在 Skype for Business Server 中管理 OAuth 和合作伙伴应用程序。
  
Skype for Business Server 必须能够安全且无缝地与其他应用程序和服务器产品进行通信。 例如，可以配置 Skype for Business Server，以便联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013 中;但是，只有当 Skype for Business Server 和 Exchange 能够安全地相互通信时，才能完成此操作。 同样，可以从 Office Web Apps Server 中安排 Skype for Business Server 会议;同样，只有在 SharePoint 和 Skype for Business Server (服务器相互信任) 才能完成此操作。 虽然可以使用一种身份验证机制在 Skype for Business Server 和 Exchange 之间通信，但使用一个单独的机制用于 Skype for Business Server 和 SharePoint 通信，但更好、更有效的方法是使用标准化方法进行所有服务器到服务器身份验证和授权。
  
使用单一的标准化方法进行服务器到服务器身份验证是 Skype for Business Server 采用的方法。 从 Office Server 2013 版本开始，Skype for Business Server (以及其他 Microsoft Server 产品（包括 Exchange Server 和 SharePoint Server) ）支持用于服务器到服务器身份验证和授权的 OAuth (Open Authorization) 协议。 使用 OAuth，这是一种由许多主要网站使用的标准授权协议，用户凭据和密码不会从一台计算机传递到另一台计算机。 但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。
  
OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。  (您还可以使用授权服务器执行服务器到服务器身份验证，本文档稍后将讨论此过程。) 安全令牌由授权服务器 (也称为安全令牌服务器) 颁发给需要通信的两个领域;这些令牌验证源自一个领域的通信应受另一领域信任。 例如，授权服务器可能会颁发令牌来验证特定 Skype for Business Server 领域的用户能否访问指定的 Exchange 领域，反之亦然。
  
> [!NOTE]
> 领域只是一个安全容器。 默认情况下，Skype for Business Server 将默认 SIP 域用作其 OAuth 领域。 其他 SIP 命名空间将添加到 OAuth 证书中的"主题备用名称"列表中。 
  
Skype for Business Server 支持三种服务器到服务器身份验证方案。 使用 Skype for Business Server，你可以：
  
- 在 Skype for Business Server 本地安装和 Exchange 和/或 SharePoint Server 本地安装之间配置服务器到服务器身份验证。
    
- 在一对 Microsoft 365 或 Office 365 组件之间配置服务器到服务器身份验证 (例如，Microsoft Exchange Server 和 Skype for Business Server 之间，或者 Skype for Business Server 和 SharePoint) 。
    
- 在跨界环境中配置服务器到服务器身份验证 (即本地服务器与 Microsoft 365 或 Office 365 组件之间的服务器到服务器身份验证) 。
    
请注意，此时仅 Exchange 2013、SharePoint Server、Lync Server 2013、Skype for Business Server 2015 和 Skype for Business 2019 支持服务器到服务器身份验证;如果未运行其中一个服务器，将无法完全实现 OAuth 身份验证。
  
还应指出，服务器到服务器身份验证是可选的：如果 Skype for Business Server 不需要与其他服务器 (如 Exchange) ，可以完全跳过服务器到服务器身份验证。 如果已经为 Lync Server 2013 和其他应用程序配置了服务器到服务器身份验证，则无需为 Skype for Business Server 重新进行配置。 
  
但是，如果要使用 Skype for Business Server 中的某些功能（如"统一联系人存储"），需要服务器到服务器身份验证。 使用统一的联系人存储，Skype for Business Server 联系人信息存储在 Exchange 中，而不是存储在 Skype for Business Server 中;这使用户能够拥有一组可从 Skype for Business、Outlook 或 Outlook Web Access 中轻松访问的联系人。 由于统一联系人存储要求 Skype for Business Server 与 Exchange 共享信息，因此必须使用服务器到服务器身份验证才能部署该功能。 如果选择使用 Exchange 存档，还需要服务器到服务器身份验证，在这种情况下，即时消息会话的脚本将另存为 Exchange 电子邮件，而不是单个数据库记录。
  
若要让 Microsoft 365 或 Office 365 版本的 Skype for Business Server 与对应的 Exchange 进行通信，Skype for Business Server 必须先从授权服务器获取安全令牌。 然后，Skype for Business Server 使用该安全令牌向 Exchange 标识自身。 Exchange 的 Microsoft 365 或 Office 365 版本必须经过相同的过程才能与 Skype for Business Server 进行通信。
  
但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。 服务器产品（如 Skype for Business Server 和 Exchange）具有一个内置令牌服务器，可用于与支持服务器到服务器身份验证的其他 Microsoft 服务器 (例如 SharePoint Server) 进行身份验证。 例如，Skype for Business Server 可以自行颁发和签署安全令牌，然后使用该令牌与 Exchange 进行通信。 在此类情况下，不需要第三方令牌服务器。
  
若要为 Skype for Business Server 本地实现配置服务器到服务器身份验证，必须执行两项操作：
  
- 将证书分配给内置的 Skype for Business Server 令牌颁发者。
    
- 将 Skype for Business Server 将通信的服务器配置为"合作伙伴应用程序"。 例如，如果 Skype for Business Server 需要与 Exchange 进行通信，则需要将 Exchange 配置为合作伙伴应用程序。
    
> [!NOTE]
> "合作伙伴应用程序"是 Skype for Business Server 可直接与任何应用程序交换安全令牌，而无需通过第三方安全令牌服务器。 
  
请注意，OAuth 是产品的核心部分，不能禁用或删除。
  
## <a name="see-also"></a>另请参阅

[将服务器到服务器身份验证证书分配给 Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[在 Skype for Business Server 中配置混合环境](configure-a-hybrid-environment.md)
