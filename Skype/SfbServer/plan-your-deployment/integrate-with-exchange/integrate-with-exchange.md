---
title: 计划集成 Skype for Business 和 Exchange
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 摘要： 查看有关如何为业务 Server 与 Exchange Server 2016 或 Exchange Server 2013 中集成 Skype 本主题。
ms.openlocfilehash: 3e94e1ab399e8a8a825826e37a281b377a31037e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213926"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>计划集成 Skype for Business 和 Exchange
 
**摘要：** 查看此主题以获取有关如何为业务 Server 与 Exchange Server 2016 或 Exchange Server 2013 中集成 Skype 的信息。
  
您可以将 Skype 集成的业务 Server 和 Exchange Server 之前，您必须确保 Exchange Server 和 Skype 业务服务器的完全安装和启动并运行。 
  
有关安装 Exchange Server 详细信息，请参阅为您的 Exchange 版本的 Exchange Server 规划和部署文档。 
   
服务器启动并正在运行后，必须为服务器到服务器身份验证证书分配这两个 Skype 的业务 Server 和 Exchange Server;这些证书允许 Skype 的业务 Server 和 Exchange Server 以交换信息以及相互进行通信。 当您安装 Exchange Server 时，自签名的证书名称为 Microsoft Exchange Server 身份验证证书会为您创建。 此证书，可以在本地计算机证书存储中找到，应用于 Exchange 服务器上的服务器到服务器身份验证。 有关分配 Exchange Server 中的证书的详细信息，请参阅[配置邮件流和客户端访问](https://go.microsoft.com/fwlink/p/?LinkId=268540)。
  
对于业务服务器 Skype 您可以使用现有的 Skype 业务服务器证书作为您的服务器到服务器身份验证证书;例如，默认证书也可以用作 OAuthTokenIssuer 证书。 Skype 业务服务器可以使用任何 Web 服务器证书，如提供的服务器到服务器身份验证证书：
  
- 该证书包括主题字段中 SIP 域的名称。
    
- 在所有前端服务器上配置与 OAuthTokenIssuer 证书相同的证书。
    
- 该证书长度至少为 2048 字节。
    
有关 Skype 业务服务器的服务器到服务器身份验证证书的详细信息，请参阅[分配到 Skype 业务服务器的服务器到服务器身份验证证书](../../manage/authentication/assign-a-server-to-server-certificate.md)。
  
已分配证书后，然后必须在 Exchange 服务器上配置自动发现服务。 Exchange Server 中的自动发现服务配置用户配置文件，并提供 Exchange 服务的访问，当用户在登录到系统。 用户为自动发现服务提供其电子邮件地址和密码，而这些服务为用户提供诸如以下信息：
  
- 内部和外部连接到 Exchange 服务器的连接信息。
    
- 用户的邮箱服务器的位置。
    
- 用于 Outlook 功能的 URL，例如忙/闲信息、统一消息和脱机通讯簿。
    
- Outlook 无处不在服务器设置。
    
您可以将 Skype 集成的业务 Server 和 Exchange Server 之前，必须配置自动发现服务。 您可以验证已通过从 Exchange Server Management Shell 中运行以下命令并检查 AutoDiscoverServiceInternalUri 属性的值配置自动发现服务：
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

如果此值为空，必须将 URI 分配到自动发现服务。 通常此 URI 类似于此：https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
可通过运行类似以下命令分配自动发现 URI：
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

有关自动发现服务的详细信息，请参阅[自动发现服务](https://go.microsoft.com/fwlink/p/?LinkId=268542)。
  
在配置自动发现服务后，您必须修改业务服务器 OAuth 配置设置; Skype这样可确保业务服务器 Skype 知道查找自动发现服务的位置。 要修改的 OAuth 配置设置中 Skype 业务服务器，请运行 Business Server 命令行管理程序从 Skype 中的以下命令。 当运行此命令，确保您指定您的 Exchange 服务器上运行的自动发现服务的 URI，并且您使用**autodiscover.svc**指向而不是**autodiscover.xml** （它指向的 XML 文件的服务位置由服务）：
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 上述命令中的 Identity 参数是可选的;这是因为 Skype 业务服务器仅允许您具有 OAuth 配置设置的单个的全局集合。 除了其他含义之外，这还表示您可使用这种略为简单的命令配置自动发现 URL： 
> 
> [!NOTE]
> 设置-CsOAuthConfiguration ExchangeAutodiscoverUrl"<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> 如果您不熟悉该技术，OAuth 是由大量网站使用的标准身份验证协议。借助 OAuth，不会将用户凭据和密码从一台计算机传递到另一台计算机。但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。 
  
除了配置自动发现服务，您还必须创建指向您的 Exchange 服务器的服务的 DNS 记录。 例如，如果您自动发现服务位于 autodiscover.litwareinc.com 您将需要创建 autodiscover.litwareinc.com 解析为您的 Exchange 服务器的完全限定的域名 （例如的 DNS 记录atl-exchange-001.litwareinc.com)。
  
如果要与 Exchange Online 的业务服务器集成 Skype，则后续步骤是[配置内部部署 Skype 业务服务器和 Outlook Web App 之间](../../deploy/integrate-with-exchange-server/outlook-web-app.md)的集成，否则请[Business Server 的集成 Skype 参阅与 Exchange服务器](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。
  
## <a name="feature-support"></a>功能支持
<a name="feature_support"> </a>

下表详细介绍在各种组合的联机或本地 Exchange 和 for Business 的 Skype 支持的功能。
  
||**Exchange 2016/2013年/2010 （本地） + Skype 业务服务器 （本地）**|**Exchange Online + Skype 业务服务器 （本地） (英文）**|**Exchange 2010 （本地） + Skype 业务 online**|**Exchange 2016/2013(on premises) + Skype 业务 online**|**Exchange Online + for Business 联机 Skype**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook 中的状态  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|通过 IM 响应、PSTN 呼叫、Skype 通话或从 Outlook 电子邮件进行视频通话  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|通过 Outlook 安排和加入联机会议  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook Web App 中的状态  <br/> |Y  <br/> |Y  <br/> |N  <br/> |否  <br/> |Y  <br/> |
|通过 IM 响应、PSTN 呼叫、Skype 通话或从 OWA 电子邮件进行视频通话  <br/> |Y  <br/> |Y  <br/> |N  <br/> |否  <br/> |Y  <br/> |
|通过 Outlook Web App 安排和加入联机会议  <br/> |Y  <br/> |Y  <br/> |N  <br/> |否  <br/> |Y  <br/> |
|移动客户端中的 IM/状态  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|在移动客户端中加入联机会议  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|根据 Outlook 日历闲/忙信息发布状态  <br/> |是  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |是  <br/> |
|联系人列表（通过统一联系人存储）  <br/> |是（需要 Exchange 2016/2013）  <br/> |Y  <br/> |N  <br/> |否  <br/> |Y  <br/> |
|高分辨率联系人照片 （需要 Lync 2013 或 Skype 最少的业务客户端。 不支持 LWA、 移动应用程序、 Lync 2010，Lync for Mac 和其他旧客户端的。）  <br/> |是（需要 Exchange 2016/2013）  <br/> |Y  <br/> |否  <br/> |Y  <br/> |Y  <br/> |
|会议委派  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|错过的对话历史记录和呼叫日志写入到用户的 exchange 邮箱  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|在 Exchang 中存档内容（IM 和会议）  <br/> |是（需要 Exchange 2016/2013）  <br/> |Y  <br/> |N  <br/> |否  <br/> |Y  <br/> |
|搜索存档内容  <br/> |是（需要 Exchange 2016/2013）  <br/> |Y  <br/> |N  <br/> |否  <br/> |是  <br/> |
|Exchange UM 语音邮件  <br/> |Y  <br/> |Y  <br/> |N  <br/> |否  <br/> |否  <br/> |
|服务器端对话历史记录  <br/> |是  <br/> |Y  <br/> |否  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> 没有云语音邮件服务，这受支持的 Skype 业务 Online、 Skype 业务服务器 2019年、 Skype 业务服务器 2015年和 Lync Server 2013。
> 

## <a name="see-also"></a>另请参阅
<a name="feature_support"> </a>

[配置业务服务器的内部部署 Skype 和 Outlook Web App 之间的集成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[在 Skype for Business Online 和 Exchange 本地之间配置 OAuth](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[为业务 Server 与 Exchange Server 集成 Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[如何将 Exchange Server 2013 与 Lync Server 2013、 Skype 业务 online 或 Lync Server 2013 混合部署](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[在 Skype for Business Server 和 Microsoft Exchange Server 中配置合作伙伴应用程序](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
