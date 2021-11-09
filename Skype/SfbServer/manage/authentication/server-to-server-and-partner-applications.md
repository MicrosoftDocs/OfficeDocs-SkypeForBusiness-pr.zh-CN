---
title: 管理 OAuth 服务器到服务器 (OAuth) 和合作伙伴应用程序Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 摘要：在应用程序中管理 OAuth 和合作伙伴Skype for Business Server。
ms.openlocfilehash: 5a5141af7473f1d49e1c19e2a454e1e46d9f65d5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856689"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>管理 OAuth 服务器到服务器 (OAuth) 和合作伙伴应用程序Skype for Business Server
 
**摘要：** 在应用程序中管理 OAuth 和合作伙伴Skype for Business Server。
  
Skype for Business Server必须能够安全且无缝地与其他应用程序和服务器产品通信。 例如，您可以配置Skype for Business Server，以便联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013;但是，只有在用户和Skype for Business Server Exchange能够安全地相互通信时，才能完成此操作。 同样，可以从 Skype for Business Server Web Apps Server 中安排Office会议;同样，只有在两台服务器相互信任 (SharePoint Skype for Business Server) 才能完成此操作。 虽然可以使用一种身份验证机制在 Skype for Business Server 和 Exchange 之间通信，但使用一种用于 Skype for Business Server 和 SharePoint 通信的单独机制，但更好、更高效的方法是对全部使用标准化方法服务器到服务器身份验证和授权。
  
使用单一的标准化方法进行服务器到服务器身份验证是 Skype for Business Server。 从 Office Server 2013 版本开始，Skype for Business Server (以及其他 Microsoft Server 产品（包括 Exchange Server 和 SharePoint Server) ）支持用于服务器到服务器身份验证和授权的 OAuth (Open Authorization) 协议。 使用 OAuth，这是一种由许多主要网站使用的标准授权协议，用户凭据和密码不会从一台计算机传递到另一台计算机。 但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。
  
OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。  (您还可以在无需使用授权服务器的情况下执行服务器到服务器身份验证，本文档稍后将讨论此过程。) 安全令牌由授权服务器 (（也称为安全令牌服务器) ）颁发给需要通信的两个领域;这些令牌验证源自一个领域的通信应受另一个领域信任。 例如，授权服务器可能会颁发令牌，以验证来自特定Skype for Business Server领域的用户能否访问指定的Exchange领域，反之亦然。
  
> [!NOTE]
> 领域只是一个安全容器。 默认情况下，Skype for Business Server将默认 SIP 域用作其 OAuth 域。 其他 SIP 命名空间将添加到 OAuth 证书中的"主题备用名称"列表中。 
  
Skype for Business Server支持三种服务器到服务器身份验证方案。 使用Skype for Business Server，您可以：
  
- 在内部部署安装的 Skype for Business Server 和/或 SharePoint Server 的本地安装之间配置服务器到Exchange身份验证。
    
- 配置一对 Microsoft 365 或 Office 365 组件之间的服务器到服务器身份验证 (例如 Microsoft Exchange Server 和 Skype for Business Server 之间，或 Skype for Business Server 和 SharePoint) 。
    
- 在跨界环境中配置服务器到服务器身份验证 (即本地服务器与 Microsoft 365 或 Office 365 组件之间的服务器到服务器) 。
    
请注意，目前只有 Exchange 2013、SharePoint Server、Lync Server 2013、Skype for Business Server 2015 和 Skype for Business 2019 支持服务器到服务器身份验证;如果未运行其中一个服务器，将无法完全实现 OAuth 身份验证。
  
还应指出的是，服务器到服务器身份验证是可选的：如果 Skype for Business Server 不需要与其他服务器（如 (）通信Exchange) 可以完全跳过服务器到服务器身份验证。 如果已针对 Lync Server 2013 和其他应用程序配置了服务器到服务器身份验证，则无需对 Skype for Business Server。 
  
但是，如果要在联系人集中使用某些功能（如"统一联系人存储Skype for Business Server，需要服务器到服务器身份验证。 使用统一的联系人Skype for Business Server，联系人信息将存储在Exchange而不是Skype for Business Server;这样，用户就具有一组易于从 Skype for Business、Outlook 或 Outlook访问的联系人。 由于统一联系人Skype for Business Server需要与 Exchange 共享信息，因此必须使用服务器到服务器身份验证才能部署该功能。 如果选择使用 Exchange 存档（其中即时消息会话的脚本保存为 Exchange 电子邮件而不是单个数据库记录），则还需要服务器到服务器身份验证。
  
若要使 Microsoft 365 或 Office 365 版本Skype for Business Server与对应的 Exchange 通信，Skype for Business Server必须先从授权服务器获取安全令牌。 Skype for Business Server然后使用该安全令牌来标识自身以Exchange。 Microsoft 365或Office 365版本的Exchange必须完成相同的过程才能与 Skype for Business Server。
  
但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。 服务器产品（如 Skype for Business Server 和 Exchange）具有内置的令牌服务器，该服务器可用于与其他支持服务器到服务器身份验证的 Microsoft 服务器 (（如 SharePoint Server) ）进行身份验证。 例如，Skype for Business Server本身颁发和签署安全令牌，然后使用该令牌与 Exchange。 在此类情况下，不需要第三方令牌服务器。
  
若要为内部部署实现配置服务器到服务器身份验证Skype for Business Server，必须执行两项操作：
  
- 向内置令牌颁发者分配Skype for Business Server令牌颁发者。
    
- 将要Skype for Business Server的服务器配置为"合作伙伴应用程序"。 例如，如果需要Skype for Business Server应用程序Exchange，则需要将Exchange配置为合作伙伴应用程序。
    
> [!NOTE]
> "合作伙伴应用程序"是任何Skype for Business Server可直接交换安全令牌的应用程序，而无需通过第三方安全令牌服务器。 
  
请注意，OAuth 是产品的核心部分，不能禁用或删除。
  
## <a name="see-also"></a>另请参阅

[将服务器到服务器身份验证证书分配给Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[在环境中配置Skype for Business Server](configure-a-hybrid-environment.md)
