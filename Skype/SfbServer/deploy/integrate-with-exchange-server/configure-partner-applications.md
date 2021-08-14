---
title: 在 Skype for Business Server 2015 和 Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 摘要：为 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 配置服务器到服务器身份验证。
ms.openlocfilehash: 19e24e610f67109f79139c7f7a0d6d13972d97abdb259b4e08de85d030856d2a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330516"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>在 Skype for Business Server 和 Exchange Server
 
**摘要：** 为 2016 或 Exchange Server 2013 Exchange Server配置服务器到服务器Skype for Business Server。
  
服务器到服务器身份验证通常需要两台需要相互通信的服务器和第三方安全令牌服务器。 如果服务器 A 和服务器 B 需要通信，则这两台服务器通常首先联系令牌服务器并获取相互信任的安全令牌。 然后，服务器 A 向服务器 B (安全令牌) ，以确保其真实性和可信度。
  
但是，这是一般规则。 Skype for Business Server、Exchange Server 2016、Exchange Server 2013 和 SharePoint Server 2013 在相互通信时不需要使用第三方令牌服务器;这是因为这些服务器产品可以创建彼此都可以接受的安全令牌，而无需使用单独的令牌服务器。  (此功能仅在 Skype for Business Server、Exchange Server 2016、Exchange Server 2013 和 SharePoint Server 2013 中可用。 如果需要设置与其他服务器（包括其他 Microsoft 服务器产品）的服务器到服务器身份验证，则需要使用第三方令牌服务器) 
  
为了在 Skype for Business Server 和 Exchange Server 之间设置服务器到服务器身份验证Exchange Server必须执行以下两项操作：1) 必须为每个服务器分配相应的证书;2) 必须将每台服务器配置为另一台服务器的合作伙伴应用程序：这意味着必须将 Skype for Business Server 配置为 Exchange Server 的合作伙伴应用程序，并且必须将 Exchange Server 配置为 Skype for Business Server 的合作伙伴应用程序。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>将Skype for Business Server配置为合作伙伴应用程序Exchange Server

将 Skype for Business Server 配置为 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序的最简单方法是运行 Configure-EnterprisePartnerApplication.ps1 脚本，这是 Exchange Server 附带一个 Windows PowerShell 脚本。 若要运行此脚本，您必须提供身份验证元数据Skype for Business Server URL;这通常是池的完全限定域名Skype for Business Server后跟后缀 /metadata/json/1。 例如：
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

若要将 Skype for Business Server 配置为合作伙伴应用程序，请打开 Exchange 命令行管理程序并运行与此 (类似的命令，假定 Exchange 已安装在驱动器 C： 上，并且它使用默认文件夹路径) ：
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

配置合作伙伴应用程序后，建议您停止并重新启动Internet Information Services (邮箱和客户端) IIS Exchange IIS 应用程序。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：
  
```powershell
iisreset atl-exchange-001
```

此命令可以从命令行管理程序Exchange运行，也可以从以管理员权限运行的其他命令窗口运行。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>将Exchange Server配置为合作伙伴应用程序Skype for Business Server

将 Skype for Business Server 配置为 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序后，必须将 Exchange Server 配置为 Skype for Business Server 的合作伙伴应用程序。 为此，可以使用命令行管理Skype for Business Server并指定身份验证元数据文档进行Exchange;这通常是自动发现服务的 URI，Exchange后缀 /metadata/json/1。 例如：
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

在Skype for Business Server中，合作伙伴应用程序是使用[New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet 配置的。 除了指定元数据 URI 之外，还应将应用程序信任级别设置为"完全";这将允许Exchange表示自身和领域中任何授权的用户。 例如：
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

或者，您可以通过复制和修改在服务器到服务器身份验证文档中Skype for Business Server脚本代码来创建合作伙伴应用程序。 有关详细信息[，请参阅管理 OAuth](../../manage/authentication/server-to-server-and-partner-applications.md) (身份验证) 合作伙伴应用程序Skype for Business Server文章。
  
如果已成功为 Skype for Business Server 和 Exchange Server 配置合作伙伴应用程序，则还成功配置了两个产品之间的服务器到服务器身份验证。 Skype for Business Server包括一个 Windows PowerShell cmdlet [Test-CsExStorageConnectivity，](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)它使您能够验证服务器到服务器身份验证是否正确配置，以及 Skype for Business Server 存储 服务能否连接到 Exchange Server。 此 cmdlet 通过连接到 Exchange Server 用户的邮箱、将项目写入该用户的对话历史记录文件夹，然后选择 (删除) 来完成此操作。
  
若要测试 Skype for Business Server 和 Exchange Server 的集成，请从命令行管理程序运行类似Skype for Business Server命令：
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

在上一个命令中，SipUri 表示拥有用户帐户的用户的 SIP Exchange Server;你的命令将失败，因为这不是一个有效的用户帐户。
  
> [!NOTE]
> 如果从此 cmdlet 收到 401 响应，可能是因为 Exchange 的默认配置不包括对接受 Oauth 令牌的支持。 有关在 Exchange 中使用[Oauth](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help)SharePoint和 Skype for Business Server。 
  
如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。