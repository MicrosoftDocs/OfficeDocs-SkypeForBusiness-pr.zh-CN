---
title: 计划集成 Skype for Business 和 Exchange
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 摘要： 仔细阅读有关如何为 Exchange Server 2016年或 Exchange Server 2013年具有的业务服务器 2015年集成 Skype 本主题。
ms.openlocfilehash: 6d3d88183cfb99597829f01aae70b1c5cdd6f09a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>计划集成 Skype for Business 和 Exchange
 
**摘要：**查看此主题了解有关如何为 Exchange Server 2016年或 Exchange Server 2013年具有的业务服务器 2015年集成 Skype。
  
您可以将 Skype 业务服务器 2015年和 Exchange Server 集成之前，必须确保 Exchange Server 和业务服务器 2015年的 Skype 是完全安装并运行起来。 
  
有关安装 Exchange Server 的详细信息，请参阅您的 Exchange 版本的 Exchange Server 规划和部署文档。 
  
为业务服务器 2015年安装 Skype 的详细信息，请参阅[部署的业务服务器 2015年的 Skype](../../deploy/deploy.md)。
  
服务器启动并运行之后，您必须为服务器到服务器身份验证证书两个 Skype 业务服务器 2015年和 Exchange Server;这些证书允许 Skype 业务服务器 2015年和 Exchange Server 交换信息以及相互交流。 安装 Exchange Server 时，自行签署式证书名称与 Microsoft Exchange Server 身份验证证书会为您创建。 该证书，可以在本地计算机证书存储中找到，应当用于上 Exchange Server 的服务器的身份验证。 有关指定 Exchange Server 中的证书的详细信息，请参阅[配置邮件流和客户端访问](https://go.microsoft.com/fwlink/p/?LinkId=268540)。
  
对于业务服务器 2015年的 Skype 可以使用现有的 Skype 业务服务器证书作为您的服务器到服务器身份验证证书;例如，默认证书也可以用作 OAuthTokenIssuer 证书。 商业服务器 2015年的 Skype 可用作任何 Web 服务器证书的证书进行服务器到服务器的身份验证提供程序：
  
- 该证书包括主题字段中 SIP 域的名称。
    
- 在所有前端服务器上配置与 OAuthTokenIssuer 证书相同的证书。
    
- 该证书长度至少为 2048 字节。
    
有关业务服务器 2015年的 Skype 的服务器到服务器身份验证证书的详细信息，请参阅[指派给业务服务器 2015年的 Skype 的服务器到服务器身份验证证书](../../manage/authentication/assign-a-server-to-server-certificate.md)。
  
在分配证书后，必须在 Exchange Server 然后配置自动发现服务。 在 Exchange Server 自动发现服务配置用户配置文件，并提供访问 Exchange 服务，当用户登录到系统。 用户为自动发现服务提供其电子邮件地址和密码，而这些服务为用户提供诸如以下信息：
  
- 内部和外部连接到 Exchange Server 的连接信息。
    
- 用户的邮箱服务器的位置。
    
- 用于 Outlook 功能的 URL，例如忙/闲信息、统一消息和脱机通讯簿。
    
- Outlook 无处不在服务器设置。
    
您可以将 Skype 业务服务器 2015年和 Exchange Server 集成之前，必须配置自动发现服务。 您可以验证已配置自动发现服务通过从 Exchange Server 管理外壳程序运行下列命令并检查 AutoDiscoverServiceInternalUri 属性的值：
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

如果此值为空，必须将 URI 分配到自动发现服务。 通常此 URI 将类似于这样：https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
可通过运行类似以下命令分配自动发现 URI：
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

关于自动发现服务的详细信息，请参阅[了解自动发现服务](https://go.microsoft.com/fwlink/p/?LinkId=268542)。
  
在配置自动发现服务后，您必须修改 Skype 业务服务器 OAuth 配置设置;这将确保该 Skype 业务服务器知道在哪里可以找到自动发现服务。 要修改业务服务器 2015年在 Skype 的 OAuth 配置设置，请运行业务服务器管理外壳内 Skype 下面的命令。 时运行此命令，请确保您指定您 Exchange Server 上, 运行的自动发现服务的 URI 而使用**autodiscover.svc**来指向服务而不是**autodiscover.xml** （它指向 XML 文件的位置由服务）：
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 上面的命令中的标识参数是可选的;这是因为 Skype 业务服务器只允许具有单一的全局 OAuth 配置设置的集合。 除了其他含义之外，这还表示您可使用这种略为简单的命令配置自动发现 URL： 
  
> [!NOTE]
> 组-CsOAuthConfiguration-ExchangeAutodiscoverUrl"https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
  
> [!NOTE]
> 如果您不熟悉该技术，OAuth 是由大量网站使用的标准身份验证协议。借助 OAuth，不会将用户凭据和密码从一台计算机传递到另一台计算机。但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。 
  
除了配置自动发现服务，您还必须创建指向 Exchange Server 服务的 DNS 记录。 例如，如果自动发现服务位于 autodiscover.litwareinc.com 您将需要创建对应于您的 Exchange Server 的完全限定的域名 （例如，autodiscover.litwareinc.com 的 DNS 记录atl-交换-001.litwareinc.com)。
  
如果您正在使用 Exchange Online 的业务服务器集成 Skype，接下来在[内部业务服务器 2015年和 Outlook Web App 的 Skype 之间的配置集成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)时，否则看到[业务服务器 2015年的集成 Skype 与Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。
  
## <a name="feature-support"></a>功能支持
<a name="feature_support"> </a>

下表详细说明了用于交换和业务的 Skype 在联机的或内部的各种组合下所支持的功能。
  
||**交换 2016年/2013年/2010 （内部部署） + Skype 的业务服务器 2015 （内部部署）**|**Exchange Online + Skype 的业务服务器 2015 （内部部署）**|**（内部部署） 的 Exchange 2010 + Skype 的在线业务**|**交换 2016年/2013(on premises) + Skype 的在线业务**|**Exchange 的联机 + Skype 的在线业务**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook 中的状态  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|通过 IM 响应、PSTN 呼叫、Skype 通话或从 Outlook 电子邮件进行视频通话  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|通过 Outlook 安排和加入联机会议  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|Outlook Web App 中的状态  <br/> |是  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|通过 IM 响应、PSTN 呼叫、Skype 通话或从 OWA 电子邮件进行视频通话  <br/> |是  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|通过 Outlook Web App 安排和加入联机会议  <br/> |是  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|移动客户端中的 IM/状态  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|在移动客户端中加入联机会议  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|根据 Outlook 日历闲/忙信息发布状态  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|联系人列表（通过统一联系人存储）  <br/> |是（需要 Exchange 2016/2013）  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|高分辨率联系人照片 （需要 Lync 2013 或 Skype 业务客户最少的。 不支持 LWA、 移动应用程序、 Lync 2010，Lync 为 Mac 和其他早期的客户端的。）  <br/> |是（需要 Exchange 2016/2013）  <br/> |是  <br/> |否  <br/> |是  <br/> |是  <br/> |
|会议委派  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|错过的对话历史记录和调用日志写入到用户的 exchange 邮箱  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|在 Exchang 中存档内容（IM 和会议）  <br/> |是（需要 Exchange 2016/2013）  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|搜索存档内容  <br/> |是（需要 Exchange 2016/2013）  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|Exchange UM 语音邮件  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|服务器端对话历史记录  <br/> |是  <br/> |是  <br/> |否  <br/> |是  <br/> |是  <br/> |
   
## <a name="see-also"></a>另请参阅
<a name="feature_support"> </a>

#### 

[配置 Outlook Web App 业务服务器 2015年的内部部署 Skype 之间的集成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[在部署配置 OAuth 之间 Skype 的在线业务和交换](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)
#### 

[对于 Exchange Server 具有的业务服务器 2015年集成 Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[如何将 Exchange Server 2013年集成使用 Lync Server 2013、 Skype 的在线业务或 Lync Server 2013 混合部署](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[在 Skype 为业务服务器 2015年和 Microsoft Exchange Server 配置合作伙伴应用程序](https://go.microsoft.com/fwlink/p/?LinkId=746495)

