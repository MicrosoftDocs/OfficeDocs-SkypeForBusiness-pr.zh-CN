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
description: 摘要： 管理 OAuth 和合作伙伴应用程序在 Skype 业务服务器 2015年。
ms.openlocfilehash: 41886b0275bd7284f6716c322595f1c360171360
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序
 
**摘要：**管理应用在 Skype 的业务服务器 2015 OAuth 和合作伙伴程序。
  
Skype 的业务服务器 2015年必须能够可靠，而无缝地，与其他应用程序和服务器产品进行通信。 例如，可以配置 Skype 业务服务器 2015 这样的联系数据和/或存档数据存储在 Microsoft Exchange Server 2013;但是，这只能如果 Skype 业务服务器和 Exchange 能够与另一个安全地进行通信。 同样，您可以安排 Skype 业务服务器大会从内 Office Web 应用程序服务器;再次，这只能如果两个服务器 （SharePoint 和 Skype 业务服务器） 能够彼此信任。 虽然可以使用 Skype 业务服务器和 Exchange 但 Skype 业务服务器和 SharePoint 通信的独立机制之间进行通信的一个身份验证机制，更好和更有效的方法是使用为所有服务器到服务器的身份验证和授权的标准化的方法。
  
使用单一，标准化的方法服务器到服务器的身份验证是通过 Skype 的业务服务器 2015年而采取的做法。 对于 2013年版、 业务服务器 2015年的 Skype （以及其他 Microsoft 服务器产品，包括 Exchange 2013 和 SharePoint 服务器） 支持 OAuth （打开授权） 协议的服务器到服务器的身份验证和授权。 使用 OAuth，由大量的主要网站，是标准的授权协议用户凭据和密码是不从一个设备传递到另一个。 但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。
  
OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。 （您还可以执行服务器到服务器的身份验证而不使用授权服务器，将在本文稍后讨论的进程。）安全令牌通过授权服务器 （也称为安全令牌服务器） 颁发给两个领域，需要进行通信;这些令牌验证通信源自一个领域应受其他领域。 例如，授权服务器可能颁发令牌验证业务服务器 2015年领域特定 Skype 的用户可以访问指定的 Exchange 2013 领域，反之亦然。
  
> [!NOTE]
> 领域只是一个安全容器。 默认情况下，业务服务器 2015年的 Skype 作为其 OAuth 领域使用您默认的 SIP 域。 其他 SIP 命名空间添加到 OAuth 证书中的“使用者替代名称”列表。 
  
Skype 的业务服务器 2015年支持三个服务器到服务器的身份验证方案。 具有的业务服务器 2015年的 Skype，您可以：
  
- 配置服务器的业务服务器 2015年的 Skype 的内部部署安装和内部安装的 Exchange 2013 和/或 SharePoint 服务器之间的身份验证。
    
- 配置一对 Office 365 组件 （例如，Microsoft Exchange Server 和 Skype 业务服务器之间或业务服务器 2015年的 Skype 之间的 SharePoint） 之间的服务器到服务器身份验证。
    
- 配置跨部署环境 （即服务器到服务器之间的身份验证内部部署服务器和 Office 365 组件） 中的服务器到服务器的身份验证。
    
注意，在此时间点，仅交换 2013年、 SharePoint 服务器、 Lync Server 2013 和 Skype 业务服务器 2015年支持服务器的身份验证;如果您没有运行这些服务器之一您将无法完全实现 OAuth 身份验证。
  
它还应曾指出该服务器到服务器身份验证为可选： 如果 Skype 的业务服务器 2015年不需要与其他服务器 （如 Exchange 2013) 进行通信，然后可以完全跳过服务器到服务器的身份验证。 如果 Lync Server 2013 和其他应用程序已经配置了服务器到服务器的身份验证，则无需对重新进行的 Skype 业务服务器 2015年。 
  
但是，服务器到服务器的身份验证是必需的如果您想要使用的某些功能在 Skype 业务服务器 2015，如"统一联系人存储。 用统一的联系人存储库，Skype 业务服务器 2015年联系信息存储在 Exchange 2013 而不是在 Skype 业务服务器;这使用户可以有一套单一的联系人从 Skype 业务、 Outlook 中或 Outlook Web Access 中可以轻易地访问。 由于统一的联系人存储库需要业务服务器 2015 2013 交换与共享信息的 Skype，您必须使用服务器到服务器的身份验证才能部署功能。 如果您选择使用作为交换 2013年电子邮件而不是单独的数据库记录保存聊天记录的即时消息会话存档，Exchange 服务器的身份验证也是必需的。
  
Skype 业务服务器与 Exchange 的对应的 Office 365 版本，Skype 的业务服务器 2015年首先必须获得安全令牌从授权服务器。 Skype 业务服务器然后使用该安全令牌更换标识自身。 Office 365 版本的 Exchange 必须经历相同的过程才能与 Skype 业务服务器 2015年进行通信。
  
但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。 服务器产品如 Skype 业务服务器 2015年和 Exchange 2013 具有内置的令牌服务器可以用于与支持服务器间身份验证其他 Microsoft 服务器 （如 SharePoint 服务器） 进行身份验证。 例如，业务服务器 2015年的 Skype 可以发出和签名的安全令牌本身，然后使用该标记来交换 2013年与通信。 在此类情况下，不需要第三方令牌服务器。
  
为了配置服务器到服务器的身份验证的内部实现的 Skype 业务服务器 2015年必须做两件事情：
  
- 将证书分配给内置的 Skype 业务服务器 2015年令牌颁发者。
    
- 配置服务器业务服务器 2015年的 Skype 通信具有为"合作伙伴应用程序。 例如，如果需要与 Exchange 2013 通信业务服务器 2015年的 Skype 您将需要配置交换作为合作伙伴应用程序。
    
> [!NOTE]
> "合作伙伴应用程序"是业务服务器 2015年的 Skype 可以直接交换安全令牌，而无需通过第三方安全令牌服务器的任何应用程序。 
  
请注意，OAuth 是产品的核心部分，不可禁用或删除。
  
## <a name="see-also"></a>另请参阅

#### 

[为业务服务器 2015年赋予 Skype 的服务器到服务器身份验证证书](assign-a-server-to-server-certificate.md)
  
[在 Skype 为业务服务器 2015年配置混合环境](configure-a-hybrid-environment.md)

