---
title: 管理服务器到服务器身份验证 (OAuth) 和 Skype 中的业务服务器的合作伙伴应用程序
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 摘要： 管理 OAuth 和合作伙伴应用程序中 Skype 业务服务器。
ms.openlocfilehash: c4b4e7344351563219f0f64e0fa0c2e34e5829b2
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294687"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>管理服务器到服务器身份验证 (OAuth) 和 Skype 中的业务服务器的合作伙伴应用程序
 
**摘要：** 管理 OAuth 和合作伙伴应用程序中 Skype 业务服务器。
  
Skype 业务服务器必须能够安全地，和无缝，与其他应用程序和服务器产品进行通信。 例如，可以配置 Skype 的业务服务器，因此该联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013;但是，仅进行这种能够安全地相互通信的业务服务器和 Exchange Skype 时。 同样，可以安排 Business Server 会议从 Office Web Apps Server; 内 Skype同样，只是这种如果两个服务器 （SharePoint 和 Skype 业务服务器） 信任另一。 尽管该办法可行 Business Server 和 Exchange Skype 但业务 Server 和 SharePoint 通信的 Skype 单独的机制之间的通信使用一个身份验证机制，更好、 更高效的方法是使用所有服务器到服务器身份验证和授权的标准化的方法。
  
使用单个，用于服务器到服务器身份验证的标准化的方法是业务服务器执行 Skype 的方法。 从 2013年版本、 业务服务器 Skype （以及其他 Microsoft 服务器产品，包括 Exchange 2013 和 SharePoint Server） 支持 OAuth (Open Authorization) 协议服务器到服务器身份验证和授权。 使用 OAuth，用大量主要网站的标准授权协议用户凭据和密码不传递从一台计算机到另一个。 但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。
  
OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。 （您还可以执行服务器到服务器身份验证而不使用授权服务器，将讨论本文档后面的过程。）对需要进行通信; 的两个领域安全令牌颁发授权服务器 （也称为安全令牌服务器）这些令牌验证其他领域应信任来自一个领域的通信。 例如，授权服务器可能颁发令牌验证用户的企业服务器领域特定 Skype 能够访问指定的 Exchange 领域，反之亦然。
  
> [!NOTE]
> 领域只是一个安全容器。 默认情况下，Skype 业务服务器使用默认 SIP 域作为其 OAuth 领域。 其他 SIP 命名空间添加到 OAuth 证书中的“使用者替代名称”列表。 
  
Skype 业务 server 支持三种服务器到服务器身份验证方案。 使用 Skype 业务服务器，您可以：
  
- 配置服务器到服务器身份验证之间的 Skype 业务服务器本地安装的 Exchange 和/或 SharePoint Server 的本地安装。
    
- 配置一对 Office 365 组件 （例如，Microsoft Exchange Server 和 Skype 业务服务器之间或 Skype 业务 server 和 SharePoint 之间） 之间的服务器到服务器身份验证。
    
- 在跨内部部署环境 （即，本地服务器和 Office 365 组件之间服务器到服务器身份验证） 中配置服务器到服务器身份验证。
    
请注意，，在此时间点，仅 Exchange 2013、 SharePoint Server、 Lync Server 2013、 业务服务器 2015年的 Skype 和 Skype 的业务 2019年支持服务器到服务器身份验证;如果未运行这些服务器之一，您将不能完全实现的 OAuth 身份验证。
  
它还应指向出的服务器到服务器身份验证为可选： 如果 Skype 业务服务器不需要与其他服务器 （例如 Exchange) 通信，则可以完全跳过服务器到服务器身份验证。 如果已配置为 Lync Server 2013 和其他应用程序服务器到服务器身份验证，则无需对重新执行此操作的 Skype 业务服务器。 
  
但是，服务器到服务器身份验证是必需的如果您想要使用的一些功能在 Skype 对于业务服务器，如"统一联系人存储库。" 使用统一联系人存储库，Skype 业务服务器联系信息存储在 Exchange 而不是在 Skype 业务服务器;这使用户可以在业务、 Outlook 或 Outlook Web Access 的 Skype 内轻松访问一单个联系人组。 由于统一联系人存储库要求 Business Server 与 Exchange 共享信息的 Skype，您必须使用服务器到服务器身份验证才能部署功能。 如果您选择使用的 Exchange 存档，为 Exchange 电子邮件，而不是作为单个数据库记录保存即时消息会话的脚本，则还需要服务器到服务器身份验证。
  
Skype 业务服务器进行通信与其 Exchange 对应项的 Office 365 版本，业务服务器 Skype 首先必须获得一个安全令牌从授权服务器。 Skype 业务服务器然后使用该安全令牌到 Exchange 标识自身。 Office 365 的 Exchange 版本必须经历相同的过程才能与 Skype 的业务服务器进行通信。
  
但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。 如 Skype Business Server 和 Exchange server 产品有一个内置的令牌服务器可以用于与其他 Microsoft 服务器 （如 SharePoint Server) 支持服务器到服务器身份验证的身份验证。 例如，Skype 业务服务器可以问题和本身，登录安全令牌然后使用该令牌与 Exchange 进行通信。 在此类情况下，不需要第三方令牌服务器。
  
若要配置的 Skype 的本地实现业务服务器的服务器到服务器身份验证，您必须执行两项操作：
  
- 为 Business Server 令牌颁发者分配内置 Skype 证书。
    
- 配置的服务器的 Skype 业务服务器将与之通信的"合作伙伴应用程序。" 例如，如果 Skype 业务服务器需要与 Exchange 进行通信，您需要将 Exchange 配置为合作伙伴应用程序。
    
> [!NOTE]
> Skype 业务服务器可以直接交换安全令牌，而无需通过第三方安全令牌服务器的任何应用程序的"合作伙伴应用程序"。 
  
请注意，OAuth 是产品的核心部分，不可禁用或删除。
  
## <a name="see-also"></a>另请参阅

[为业务服务器分配 Skype 的服务器到服务器身份验证证书](assign-a-server-to-server-certificate.md)
  
[在 Skype for Business Server 中配置混合环境](configure-a-hybrid-environment.md)