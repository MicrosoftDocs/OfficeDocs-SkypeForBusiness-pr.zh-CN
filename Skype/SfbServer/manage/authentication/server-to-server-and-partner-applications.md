---
title: 在 Skype for Business Server 中管理服务器到服务器的身份验证 (OAuth) 和合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: '摘要: 在 Skype for Business 服务器中管理 OAuth 和合作伙伴应用程序。'
ms.openlocfilehash: 37c2af8a089bcae4b974761616e1ecd67c9e500b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297566"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>在 Skype for Business Server 中管理服务器到服务器的身份验证 (OAuth) 和合作伙伴应用程序
 
**摘要:** 在 Skype for Business 服务器中管理 OAuth 和合作伙伴应用程序。
  
Skype for business 服务器必须能够与其他应用程序和服务器产品进行安全、无缝地通信。 例如, 您可以配置 Skype for Business 服务器, 以便联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013 中;但是, 仅当 Skype for Business 服务器和 Exchange 能够与另一个服务器进行安全通信时, 才可以执行此操作。 同样, 你可以在 Office Web Apps 服务器内安排 Skype for business 服务器会议;同样, 只有在两个服务器 (SharePoint 和 Skype for business 服务器) 相互信任时才能执行此操作。 尽管可以使用一种身份验证机制来在 Skype for business 服务器和 Exchange 之间进行通信, 但对于 Skype for business 服务器和 SharePoint 通信, 另一种是更高效的方法是使用适用于所有服务器到服务器身份验证和授权的标准化方法。
  
使用单个标准化的服务器到服务器身份验证方法是 Skype for business 服务器所采用的方法。 从 Office server 2013 版本开始, Skype for business 服务器 (以及其他 Microsoft Server 产品, 包括 Exchange Server 和 SharePoint Server) 支持服务器到服务器身份验证的 OAuth (开放授权) 协议, 以及权限. 使用 OAuth (由许多主要网站使用的标准授权协议), 用户凭据和密码不会从一台计算机传递到另一台计算机。 但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。
  
OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。 (您也可以不使用授权服务器执行服务器到服务器的身份验证, 此过程将在本文档后面部分讨论。)安全令牌由授权服务器 (也称为安全令牌服务器) 颁发给需要通信的两个领域;这些令牌验证来自一个领域的通信是否应由其他领域信任。 例如, 授权服务器可能会颁发令牌以验证特定 Skype for Business 服务器领域的用户是否能够访问指定的 Exchange 领域, 反之亦然。
  
> [!NOTE]
> 领域只是一个安全容器。 默认情况下, Skype for business 服务器使用默认 SIP 域作为其 OAuth 领域。 其他 SIP 命名空间添加到 OAuth 证书中的“使用者替代名称”列表。 
  
Skype for Business 服务器支持三种服务器到服务器身份验证方案。 通过 Skype for Business 服务器, 你可以:
  
- 在 Skype for business 服务器的本地安装和 Exchange 和/或 SharePoint Server 的本地安装之间配置服务器到服务器的身份验证。
    
- 在一对 Office 365 组件 (例如, 在 Microsoft Exchange Server 和 Skype for business 服务器之间或在 Skype for business Server 和 SharePoint 之间) 配置服务器到服务器的身份验证。
    
- 在跨平台环境中配置服务器到服务器身份验证 (即本地服务器与 Office 365 组件之间的服务器到服务器身份验证)。
    
请注意, 在此时间点, 仅限 Exchange 2013、SharePoint Server、Lync Server 2013、Skype for business Server 2015 和 Skype for Business 2019 支持服务器到服务器身份验证;如果未运行这些服务器之一, 则将无法完全实现 OAuth 身份验证。
  
还应指出服务器到服务器的身份验证是可选的: 如果 Skype for Business 服务器不需要与其他服务器 (如 Exchange) 通信, 则可以完全跳过服务器到服务器身份验证。 如果已为 Lync Server 2013 和其他应用程序配置了服务器到服务器身份验证, 则无需为 Skype for business 服务器重新执行此操作。 
  
但是, 如果要使用 Skype for Business 服务器中的某些功能 (例如 "统一联系人存储"), 则需要服务器到服务器的身份验证。 通过 "统一联系人存储", Skype for business 服务器联系人信息存储在 Exchange 中, 而不是存储在 Skype for business 服务器中;这使用户可以在 Skype for Business、Outlook 或 Outlook Web Access 中轻松访问单个联系人集。 由于 "统一联系人存储" 需要 Skype for Business 服务器才能与 Exchange 共享信息, 因此必须使用服务器到服务器身份验证才能部署该功能。 如果你选择使用 Exchange 存档 (在其中将即时消息会话的脚本另存为 Exchange 电子邮件, 而不是单个数据库记录), 也需要服务器到服务器的身份验证。
  
对于 Office 365 版本的 Skype for business 服务器, 若要与其交换对应, Skype for business 服务器必须首先从授权服务器获取安全令牌。 然后, Skype for Business 服务器使用该安全令牌向 Exchange 标识自身。 Office 365 版本的 Exchange 必须经过同一进程才能与 Skype for Business 服务器通信。
  
但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。 Skype for business Server 和 Exchange 之类的服务器产品具有内置的令牌服务器, 可用于支持服务器到服务器身份验证的其他 Microsoft 服务器 (如 SharePoint Server) 进行身份验证。 例如, Skype for Business 服务器可以自行发出和签名安全令牌, 然后使用该令牌与 Exchange 通信。 在此类情况下，不需要第三方令牌服务器。
  
为了为 Skype for business Server 的本地实现配置服务器到服务器身份验证, 您必须执行两项操作:
  
- 为内置的 Skype for business 服务器令牌颁发者分配证书。
    
- 将 Skype for business 服务器将与之通信的服务器配置为 "合作伙伴应用程序"。 例如, 如果 Skype for business 服务器需要与 Exchange 通信, 则需要将 Exchange 配置为合作伙伴应用程序。
    
> [!NOTE]
> "合作伙伴应用程序" 是 Skype for Business 服务器可以直接与之交换安全令牌的任何应用程序, 而无需经过第三方安全令牌服务器。 
  
请注意，OAuth 是产品的核心部分，不可禁用或删除。
  
## <a name="see-also"></a>另请参阅

[将服务器到服务器身份验证证书分配给 Skype for Business 服务器](assign-a-server-to-server-certificate.md)
  
[在 Skype for Business 服务器中配置混合环境](configure-a-hybrid-environment.md)
