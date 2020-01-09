---
title: 计划集成 Skype for Business 和 Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 摘要：查看本主题，了解有关如何将 Skype for Business 服务器与 Exchange Server 2016 或 Exchange Server 2013 集成的信息。
ms.openlocfilehash: 54a079a550b1c915d9ffc124b1608a3fd3f2a5ef
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991477"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>计划集成 Skype for Business 和 Exchange
 
**摘要：** 有关如何将 Skype for Business 服务器与 Exchange Server 2016 或 Exchange Server 2013 集成的信息，请参阅本主题。
  
在集成 Skype for Business 服务器和 Exchange Server 之前，必须确保 Exchange Server 和 Skype for business 服务器已完全安装并运行。 
  
有关安装 Exchange Server 的详细信息，请参阅 exchange Server 版本的 Exchange Server 规划和部署文档。 
   
在服务器启动并运行后，必须为 Skype for business 服务器和 Exchange Server 分配服务器到服务器身份验证证书;这些证书允许 Skype for business 服务器和 Exchange Server 交换信息，并与其他人进行通信。 安装 Exchange Server 时，将为你创建一个名称为 Microsoft Exchange Server 身份验证证书的自签名证书。 此证书（可在本地计算机证书存储中找到）应用于 Exchange Server 上的服务器到服务器身份验证。 有关在 Exchange Server 中分配证书的详细信息，请参阅[配置邮件流和客户端访问](https://go.microsoft.com/fwlink/p/?LinkId=268540)。
  
对于 Skype for Business 服务器，你可以将现有 Skype for Business 服务器证书用作服务器到服务器身份验证证书;例如，你的默认证书也可以用作 OAuthTokenIssuer 证书。 Skype for Business 服务器允许你将任何 Web 服务器证书用作服务器到服务器身份验证的证书，前提是：
  
- 该证书包括主题字段中 SIP 域的名称。
    
- 在所有前端服务器上配置与 OAuthTokenIssuer 证书相同的证书。
    
- 该证书长度至少为 2048 字节。
    
有关 Skype for business Server 的服务器到服务器身份验证证书的详细信息，请参阅向[Skype for Business 服务器分配服务器到服务器身份验证证书](../../manage/authentication/assign-a-server-to-server-certificate.md)。
  
分配证书后，必须在 Exchange Server 上配置自动发现服务。 在 Exchange Server 中，自动发现服务配置用户配置文件，并在用户登录到系统时提供对 Exchange 服务的访问权限。 用户为自动发现服务提供其电子邮件地址和密码，而这些服务为用户提供诸如以下信息：
  
- Exchange Server 的内部和外部连接的连接信息。
    
- 用户邮箱服务器的位置。
    
- 用于 Outlook 功能的 URL，例如忙/闲信息、统一消息和脱机通讯簿。
    
- Outlook 无处不在服务器设置。
    
必须先配置自动发现服务，然后才能集成 Skype for Business 服务器和 Exchange Server。 你可以通过从 Exchange Server Management Shell 运行以下命令来验证是否已配置自动发现服务，并检查 AutoDiscoverServiceInternalUri 属性的值：
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

如果此值为空，必须将 URI 分配到自动发现服务。 通常，此 URI 如下所示：https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
可通过运行类似以下命令分配自动发现 URI：
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

有关自动发现服务的详细信息，请参阅[自动发现服务](https://go.microsoft.com/fwlink/p/?LinkId=268542)。
  
配置自动发现服务后，必须修改 Skype for business 服务器 OAuth 配置设置;这可确保 Skype for business 服务器知道发现自动发现服务的位置。 若要在 Skype for Business Server 中修改 OAuth 配置设置，请在 Skype for business Server 命令行管理程序中运行以下命令。 运行此命令时，请确保指定你的 Exchange Server 上运行的自动发现服务的 URI，并使用**自动发现**来指向服务位置（而不是 "自动发现"），而不是 "**自动发现" xml** （指向服务使用的 xml 文件）：
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 上述命令中的 Identity 参数是可选的;这是因为 Skype for business 服务器仅允许你拥有一个全局的 OAuth 配置设置集合。 除了其他含义之外，这还表示您可使用这种略为简单的命令配置自动发现 URL： 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> 如果您不熟悉该技术，OAuth 是由大量网站使用的标准身份验证协议。借助 OAuth，不会将用户凭据和密码从一台计算机传递到另一台计算机。但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。 
  
除了配置自动发现服务，你还必须为指向 Exchange Server 的服务创建 DNS 记录。 例如，如果你的自动发现服务位于 autodiscover.litwareinc.com，你将需要为解析为你的 Exchange Server 的完全限定域名的 autodiscover.litwareinc.com 创建 DNS 记录（例如atl-exchange-001.litwareinc.com）。
  
如果您要将 Skype for Business 服务器与 Exchange Online 集成，则接下来的步骤是[配置本地 skype for Business 服务器和 Outlook Web App 之间的集成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)，否则请参阅将[Skype for Business 服务器与 Exchange Server 集成](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。
  
## <a name="feature-support"></a>功能支持
<a name="feature_support"> </a>

下表详细介绍了 Exchange 和 Skype for business 的联机或内部部署的各种组合支持的功能。
  
||**Exchange 2016/2013/2010 （内部部署） + Skype for Business 服务器（内部部署）**|**Exchange Online + Skype for Business 服务器（内部部署）**|**Exchange 2010 （内部部署） + Skype for Business Online**|**Exchange 2016/2013 （内部部署） + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
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
|高分辨率联系人照片（至少需要 Lync 2013 或 Skype for business 客户端。 不支持 LWA、移动应用、Lync 2010、Lync for Mac 和其他较旧的客户端。）  <br/> |是（需要 Exchange 2016/2013）  <br/> |Y  <br/> |否  <br/> |Y  <br/> |Y  <br/> |
|会议委派  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|在 Exchang 中存档内容（IM 和会议）  <br/> |是（需要 Exchange 2016/2013）  <br/> |Y  <br/> |N  <br/> |否  <br/> |Y  <br/> |
|搜索存档内容  <br/> |是（需要 Exchange 2016/2013）  <br/> |Y  <br/> |N  <br/> |否  <br/> |是  <br/> |
|Exchange UM 语音邮件  <br/> |Y  <br/> |Y  <br/> |N  <br/> |否  <br/> |否  <br/> |
|服务器端对话历史记录  <br/> |是  <br/> |Y  <br/> |否  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> 有一种云语音邮件服务支持 Skype for Business Online、Skype for business Server 2019、Skype for business Server 2015 和 Lync Server 2013。
> 

## <a name="see-also"></a>另请参阅
<a name="feature_support"> </a>

[配置本地 Skype for business 服务器和 Outlook Web App 之间的集成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[在 Skype for Business Online 和 Exchange 本地之间配置 OAuth](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[将 Skype for Business 服务器与 Exchange Server 集成](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[如何将 Exchange Server 2013 与 Lync Server 2013、Skype for Business Online 或 Lync Server 2013 混合部署结合使用](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[在 Skype for Business Server 和 Microsoft Exchange Server 中配置合作伙伴应用程序](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
