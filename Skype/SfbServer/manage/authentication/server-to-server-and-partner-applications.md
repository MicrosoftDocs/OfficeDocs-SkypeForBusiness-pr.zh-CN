---
title: 在 Skype for Business Server 2015 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 摘要： 管理 OAuth 和合作伙伴应用程序中 Skype 业务服务器 2015年。
ms.openlocfilehash: acbc8cfa9fd43bdc73752278d1da805d5b4a31ef
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504395"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序
 
**摘要：** 管理 OAuth 和合作伙伴应用程序中 Skype 业务服务器 2015年。
  
Skype 的业务服务器 2015年必须能够安全地，和无缝，与其他应用程序和服务器产品进行通信。 例如，可以配置 Skype 的业务服务器 2015 以便该联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013;但是，仅进行这种能够安全地相互通信的业务服务器和 Exchange Skype 时。 同样，可以安排 Business Server 会议从 Office Web Apps Server; 内 Skype同样，只是这种如果两个服务器 （SharePoint 和 Skype 业务服务器） 信任另一。 尽管该办法可行 Business Server 和 Exchange Skype 但业务 Server 和 SharePoint 通信的 Skype 单独的机制之间的通信使用一个身份验证机制，更好、 更高效的方法是使用所有服务器到服务器身份验证和授权的标准化的方法。
  
使用单个，用于服务器到服务器身份验证的标准化的方法是执行的业务服务器 2015 Skype 的方法。 2013 版本、 业务服务器 2015年的 Skype （以及其他 Microsoft 服务器产品，包括 Exchange 2013 和 SharePoint Server） 支持用于服务器到服务器身份验证和授权的 OAuth (Open Authorization) 协议。 使用 OAuth，用大量主要网站的标准授权协议用户凭据和密码不传递从一台计算机到另一个。 但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。
  
OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。 （您还可以执行服务器到服务器身份验证而不使用授权服务器，将讨论本文档后面的过程。）对需要进行通信; 的两个领域安全令牌颁发授权服务器 （也称为安全令牌服务器）这些令牌验证其他领域应信任来自一个领域的通信。 例如，授权服务器可能颁发令牌验证中的业务服务器 2015年领域特定 Skype 的用户能够访问指定的 Exchange 2013 领域，反之亦然。
  
> [!NOTE]
> 领域只是一个安全容器。 默认情况下，业务服务器 2015年的 Skype 使用默认 SIP 域作为其 OAuth 领域。 其他 SIP 命名空间添加到 OAuth 证书中的“使用者替代名称”列表。 
  
Skype 的业务服务器 2015年支持三种服务器到服务器身份验证方案。 使用业务服务器 2015年的 Skype 可以：
  
- 配置业务服务器 2015年的 Skype 的本地安装和内部部署安装 Exchange 2013 和/或 SharePoint Server 之间的服务器到服务器身份验证。
    
- 配置一对 Office 365 组件 （例如，Microsoft Exchange Server 和 Skype 业务服务器之间或业务服务器 2015年的 Skype 和 SharePoint 之间） 之间的服务器到服务器身份验证。
    
- 在跨内部部署环境 （即，本地服务器和 Office 365 组件之间服务器到服务器身份验证） 中配置服务器到服务器身份验证。
    
请注意，在此时间点，仅 Exchange 2013、 SharePoint Server、 Lync Server 2013 和 Skype 业务服务器 2015年支持服务器到服务器身份验证;如果您未运行这些服务器之一您将无法完全实现的 OAuth 身份验证。
  
它还应指向出的服务器到服务器身份验证为可选： 如果 Skype 的业务服务器 2015年不需要与其他服务器 （如 Exchange 2013) 通信，则可以完全跳过服务器到服务器身份验证。 如果已配置为 Lync Server 2013 和其他应用程序服务器到服务器身份验证，则无需对重新执行此操作的 Skype 的业务服务器 2015年。 
  
但是，服务器到服务器身份验证是必需的如果您想要使用的一些功能中 Skype 业务服务器 2015，如"统一联系人存储库。" 使用统一联系人存储库，Skype 业务服务器 2015年联系信息存储在 Skype 而不是 Exchange 2013 中业务服务器;这使用户可以在业务、 Outlook 或 Outlook Web Access 的 Skype 内轻松访问一单个联系人组。 由于统一联系人存储库要求业务服务器 2015 与 Exchange 2013 共享信息的 Skype，您必须使用服务器到服务器身份验证才能部署功能。 如果您选择使用的 Exchange 存档、 即时消息会话的脚本将在其中保存为 Exchange 2013 的电子邮件，而不是作为单个数据库记录，则还需要服务器到服务器身份验证。
  
Skype 业务服务器进行通信与其 Exchange 对应项的 Office 365 版本，业务服务器 2015年的 Skype 首先必须获得一个安全令牌从授权服务器。 Skype 业务服务器然后使用该安全令牌到 Exchange 标识自身。 Office 365 的 Exchange 版本必须经历相同的过程才能与 Skype 的业务服务器 2015年进行通信。
  
但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。 如 Skype 业务服务器 2015年和 Exchange 2013 服务器产品有一个内置的令牌服务器可以用于与其他 Microsoft 服务器 （如 SharePoint Server) 支持服务器到服务器身份验证的身份验证。 例如，业务服务器 2015年的 Skype 可以问题和安全令牌签名本身，然后使用该令牌与 Exchange 2013 进行通信。 在此类情况下，不需要第三方令牌服务器。
  
若要配置针对业务服务器 2015年程序 Skype 的本地实现服务器到服务器身份验证，您必须执行两项操作：
  
- 为业务服务器 2015年令牌颁发者分配内置 Skype 证书。
    
- 配置的服务器的业务服务器 2015年的 Skype 将与之通信的"合作伙伴应用程序。" 例如，如果需要与 Exchange 2013 通信的业务服务器 2015 Skype 您将需要将 Exchange 配置为合作伙伴应用程序。
    
> [!NOTE]
> "合作伙伴应用程序"是任何应用程序的业务服务器 2015 Skype 可以直接交换安全令牌，而无需通过第三方安全令牌服务器。 
  
请注意，OAuth 是产品的核心部分，不可禁用或删除。
  
## <a name="see-also"></a>另请参阅

[为业务服务器 2015年分配 Skype 的服务器到服务器身份验证证书](assign-a-server-to-server-certificate.md)
  
[为业务服务器 2015 Skype 中配置混合环境](configure-a-hybrid-environment.md)