---
title: 在 Skype 为业务服务器 2015年和 Exchange Server 配置合作伙伴应用程序
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 摘要： 配置服务器到服务器的身份验证的 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年。
ms.openlocfilehash: d7b3d93126c5b2db06e5f7343f5636b3c305d7c8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-partner-applications-in-skype-for-business-server-2015-and-exchange-server"></a>在 Skype 为业务服务器 2015年和 Exchange Server 配置合作伙伴应用程序
 
**摘要：**配置服务器到服务器的身份验证的 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年。
  
服务器到服务器身份验证通常要有两台需要相互通信的服务器以及一台第三方安全令牌服务器。 如果服务器 A 和服务器 B 需要进行通信，然后这些服务器的两个通常首先与令牌服务器联系并获得相互信任安全令牌。 之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。
  
但是，这是一般规则。 Skype 业务服务器 2015年、 Exchange Server 2016年、 Exchange Server 2013，和 SharePoint Server 2013 不需要与另一个; 通信时使用第三方的令牌服务器这是因为这些服务器产品可以创建无需单独的令牌服务器通过另一个被接受的安全令牌。 （此功能才可用在 Skype 业务服务器 2015年、 Exchange Server 2016年、 Exchange Server 2013，和 SharePoint Server 2013。 如果您需要设置服务器到服务器与其他服务器的身份验证，包括其他的 Microsoft 服务器产品，则您将需要使用第三方的令牌服务器进行操作。）
  
Skype 业务服务器和 Exchange Server 之间的服务器到服务器身份验证设置，您必须做两件事： 1) 必须将适当的证书分配给每个服务器;并且，2） 您必须配置为其他服务器的合作伙伴应用程序的每台服务器： 这意味着您必须配置为 Exchange Server 的合作伙伴应用程序的业务服务器 2015年的 Skype，您必须配置 Exchange Server 是一个合作伙伴应用程序业务服务器 2015 的 Skype。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Skype 将 Exchange Server 的合作伙伴应用程序的业务服务器的配置

配置为与 Exchange Server 2016年或 Exchange Server 2013年的合作伙伴应用程序的业务服务器 2015年的 Skype 的最简单方法就是运行配置 EnterprisePartnerApplication.ps1 脚本，随 Exchange Server 的 Windows PowerShell 脚本. 若要运行此脚本，您必须提供的 URL Skype 业务服务器身份验证元数据文档;通常，这将完全限定的域名的 Skype 跟后缀 /metadata/json/1 业务服务器 2015年池。 例如：
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

要配置 Skype 业务合作伙伴应用程序的服务器，打开 Exchange 管理外壳程序并运行与以下类似的命令 （假定驱动器 c： 上安装了 Exchange 和它使用默认的文件夹路径）：
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

合作伙伴应用程序配置后建议您停止并重新启动 Exchange 邮箱存储和客户端访问服务器上的 Internet Information Services (IIS)。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：
  
```
iisreset atl-exchange-001
```

在 Exchange 管理外壳程序中或从管理员权限下运行的任何其他命令窗口，可以从运行此命令。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>配置 Exchange Server 将 Skype 业务服务器合作伙伴应用程序

在配置 Exchange Server 2016年或 Exchange Server 2013年合作伙伴应用程序的业务服务器 2015年的 Skype 之后，然后必须配置 Exchange Server 将 Skype 业务服务器的合作伙伴应用程序。 这可以通过使用 Skype 业务服务器管理外壳和指定身份验证元数据文档交换;这通常是跟后缀 /metadata/json/1 Exchange 自动发现服务的 URI。 例如：
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

在 Skype 业务服务器，通过使用[New CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet 配置合作伙伴应用程序。 除了指定元数据 URI 应当还应用程序信任级别设置为完全;这将允许 Exchange 表示本身和任何领域中的授权的用户。 例如：
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

或者，您可以创建合作伙伴应用程序复制并修改 Skype 业务服务器 2015年服务器到服务器的身份验证文档中的脚本代码。 请参阅[管理服务器的身份验证 (OAuth) 和合作伙伴应用程序中的业务服务器 2015 Skype](../../manage/authentication/server-to-server-and-partner-applications.md)文章的详细信息。
  
如果您已成功配置为两种 Skype 业务服务器和 Exchange Server 的合作伙伴应用程序，还成功配置了两个产品之间的服务器到服务器进行身份验证。 Skype 的业务服务器 2015年包括 Windows PowerShell cmdlet，使您可以验证是否已正确配置该服务器的身份验证和[测试 CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) Skype 业务服务器存储服务可以连接到 Exchange Server。 该 cmdlet 会通过连接到邮箱的 Exchange Server 用户、 为用户编写到对话历史记录文件夹中的项，然后 （可选） 删除该项目。
  
若要测试的 Skype 业务服务器 2015年和 Exchange Server 的集成，业务服务器管理外壳程序运行从 Skype 与以下类似的命令：
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

在上述命令中，SipUri 表示 SIP 地址的用户的帐户在 Exchange Server;您的命令将在失败这不是一个有效的用户帐户。
  
> [!NOTE]
> 如果您收到来自此 cmdlet 的 401 响应，可能是因为 Exchange 的默认配置不包括对接受 Oauth 标记的支持。 有关在 Exchange 使用 Oauth 的详细信息，请参阅[使用 SharePoint 2013 和 Skype 的业务服务器 2015年配置 OAuth 进行身份验证](https://go.microsoft.com/fwlink/p/?LinkId=513103)。 
  
如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。
  

