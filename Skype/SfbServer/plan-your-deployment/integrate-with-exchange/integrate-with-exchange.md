---
title: 计划集成 Skype for Business 和 Exchange
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 摘要：查看本主题，了解如何将 Skype for Business Server 2016 Exchange Server 2013 Exchange Server集成。
ms.openlocfilehash: 81217886028db9e8cb04296e5d665aada3a3337683f4b8276fb13d454cdc4b76
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284642"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>计划集成 Skype for Business 和 Exchange
 
**摘要：** 查看本主题，了解如何将 Skype for Business Server 2016 Exchange Server 2013 Exchange Server集成。
  
在集成 Skype for Business Server 和 Exchange Server 之前，必须确保 Exchange Server 和 Skype for Business Server 已完全安装并启动并运行。 
  
有关安装Exchange Server的详细信息，请参阅 Exchange Server 版本的规划和部署文档Exchange。 
   
服务器启动并运行后，必须将服务器到服务器身份验证证书分配给 Skype for Business Server 和 Exchange Server;这些证书Skype for Business Server和Exchange Server交换信息并相互通信。 安装 Exchange Server时，会创建一个Microsoft Exchange Server身份验证证书名称的自签名证书。 此证书（可在本地计算机证书存储中找到）应该用于 Exchange Server 上的服务器到服务器身份验证。 有关在邮箱中分配证书Exchange Server，请参阅配置邮件Flow[客户端访问](/exchange/configure-mail-flow-and-client-access-exchange-2013-help)。
  
例如Skype for Business Server可以使用现有 Skype for Business Server 证书作为服务器到服务器身份验证证书;例如，默认证书还可以用作 OAuthTokenIssuer 证书。 Skype for Business Server，您可以使用任何 Web 服务器证书作为用于服务器到服务器身份验证的证书，但需要：
  
- 该证书包括主题字段中 SIP 域的名称。
    
- 在所有前端服务器上配置与 OAuthTokenIssuer 证书相同的证书。
    
- 该证书长度至少为 2048 字节。
    
有关服务器到服务器身份验证证书的详细信息Skype for Business Server，请参阅 Assign [a server-to-server authentication certificate to Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md)。
  
分配证书后，必须在部署上配置自动发现Exchange Server。 在Exchange Server中，自动发现服务将配置用户配置文件，并提供Exchange登录到系统时对服务的访问权限。 用户为自动发现服务提供其电子邮件地址，而这些服务为用户提供诸如以下信息：
  
- 与外部连接的内部和外部连接的连接Exchange Server。
    
- 用户的邮箱服务器的位置。
    
- 用于 Outlook 功能的 URL，例如忙/闲信息、统一消息和脱机通讯簿。
    
- Outlook 无处不在服务器设置。
    
必须先配置自动发现服务，然后才能集成Skype for Business Server Exchange Server。 您可以通过从 Exchange Server 命令行管理程序 运行以下命令并检查 AutoDiscoverServiceInternalUri 属性的值来验证是否已配置自动发现服务：
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

如果此值为空，必须将 URI 分配到自动发现服务。 通常，此 URI 将类似于： https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
可通过运行类似以下命令分配自动发现 URI：
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

有关自动发现服务的详细信息，请参阅 [自动发现服务](/Exchange/architecture/client-access/autodiscover)。
  
配置自动发现服务后，您必须修改 OAuth Skype for Business Server设置;这可确保Skype for Business Server在哪里找到自动发现服务。 若要在命令行管理程序Skype for Business Server OAuth 配置设置，请从命令行管理程序Skype for Business Server命令。 运行此命令时，请确保为 Exchange Server 上运行的自动发现服务指定 URI，并使用 **autodiscover.svc** 指向服务位置，而不是 **指向autodiscover.xml** (它指向服务) ：
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 上述命令中的 Identity 参数是可选的;这是因为，Skype for Business Server仅允许您具有一个 OAuth 配置设置的全局集合。 在其他情况下，这表示您可使用此稍简单的命令配置自动发现 URL： 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> 如果您不熟悉该技术，OAuth 是由大量网站使用的标准身份验证协议。借助 OAuth，不会将用户凭据和密码从一台计算机传递到另一台计算机。但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。 
  
除了配置自动发现服务之外，还必须为指向您的自动发现服务的 DNS Exchange Server。 例如，如果自动发现服务位于 autodiscover.litwareinc.com 则需要为解析为 Exchange Server (的完全限定域名的 autodiscover.litwareinc.com 创建 DNS 记录，例如 atl-exchange-001.litwareinc.com) 。
  
如果要将 Skype for Business Server 与 Exchange Online 集成，则下一步将在本地[Skype for Business Server](../../deploy/integrate-with-exchange-server/outlook-web-app.md)和 Outlook Web App 之间配置集成，否则请参阅将 Skype for Business Server 与[Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)集成。
  
## <a name="feature-support"></a>功能支持
<a name="feature_support"> </a>

>[!Important]
> Skype for Business2021 年 7 月 31 日将停用联机Exchange下面列出的包含该服务的集成将不再受支持。

下表详细介绍了各种联机或本地组合下支持的功能，Exchange Skype for Business。
  
||**Exchange 2016/2013/2010 () + Skype for Business Server (本地)**|**Exchange Online + Skype for Business Server (本地)**|**Exchange 2010 (本地) + Skype for Business Online**|**Exchange 2016/2013 () + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|状态Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|通过 IM、PSTN 呼叫、Skype呼叫或视频呼叫从电子邮件Outlook响应  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|通过会议安排和加入联机Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|状态Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|通过 IM、PSTN 呼叫、Skype OWA 电子邮件进行呼叫或视频呼叫进行响应  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|通过会议安排和加入联机Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|移动客户端中的 IM/状态  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|在移动客户端中加入联机会议  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|根据日历忙/Outlook信息发布状态  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|联系人列表 (统一联系人存储)   <br/> |Y (2016 Exchange 2013 年 10 月)   <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|高分辨率联系人照片 (至少需要 Lync 2013 Skype for Business客户端。 不支持 LWA、移动应用、Lync 2010、Lync for Mac 和其他较旧的客户端)   <br/> |Y (2016 Exchange 2013 年 10 月)   <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|会议委派  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|错过的对话历史记录和呼叫日志将写入到用户的 Exchange 邮箱  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|存档 (IM 和会议) 内容Exchange  <br/> |Y (2016 Exchange 2013 年 10 月)   <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|搜索存档内容  <br/> |Y (2016 Exchange 2013 年 10 月)   <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|ExchangeUM 语音邮件  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|服务器端对话历史记录  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015 和 Lync Server 2013 支持 云语音邮件 服务。
> 

## <a name="see-also"></a>另请参阅
<a name="feature_support"> </a>

[配置本地部署和Skype for Business Server之间的Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[在本地 Skype for Business 和 Exchange 之间配置 OAuth](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[将Skype for Business Server与Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[如何将 Exchange Server 2013 与 Lync Server 2013、Skype for Business Online 或 Lync Server 2013 混合部署集成](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[在 Skype for Business Server 和 Microsoft Exchange Server 中配置合作伙伴应用程序](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)