---
title: 在 Skype for Business Server 2015 和 Exchange Server 中配置合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 摘要： 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 的业务服务器的服务器到服务器身份验证。
ms.openlocfilehash: 70433d0a6f3b6d9c30e510e116003a4efb5ba9b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894335"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>在 Skype for Business Server 和 Exchange Server 中配置合作伙伴应用程序
 
**摘要：** 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 业务服务器的服务器到服务器身份验证。
  
服务器到服务器身份验证通常要有两台需要相互通信的服务器以及一台第三方安全令牌服务器。 如果服务器 A 和服务器 B 需要进行通信，然后两台这些服务器通常首先联系令牌的服务器和获取相互受信任安全令牌。 之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。
  
但是，这是一个常规的规则。 为 Business Server、 Exchange Server 2016、 Exchange Server 2013 和 SharePoint Server 2013 的 Skype 不需要时相互; 通信使用第三方令牌服务器这是因为这些服务器产品可以创建可由另一接受无需单独的令牌服务器的安全令牌。 （此功能才 Skype Business Server、 Exchange Server 2016、 Exchange Server 2013 和 SharePoint Server 2013 中可用。 如果您需要设置与其他服务器的服务器到服务器身份验证，包括其他 Microsoft 服务器产品，则您将需要使用第三方令牌服务器完成此操作。）
  
若要设置 Skype 业务 server 和 Exchange 服务器之间的服务器到服务器身份验证，您必须执行两个操作： 1) 必须将适当的证书分配给每个服务器;以及 2） 必须配置每台服务器的其他服务器合作伙伴应用程序： 这意味着您必须配置 Skype 业务服务器进行 Exchange server 合作伙伴应用程序，您必须配置 Exchange Server 的 Skype 合作伙伴应用程序对于业务服务器。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>配置 Exchange server 合作伙伴应用程序的业务服务器的 Skype

配置业务合作伙伴应用程序与 Exchange Server 2016 或 Exchange Server 2013 服务器的 Skype 的最简单方式是运行 Configure-EnterprisePartnerApplication.ps1 脚本随 Exchange Server 的 Windows PowerShell 脚本。 若要运行此脚本，必须提供的 URL 的业务服务器身份验证元数据文档; Skype通常，这将业务服务器池跟后缀 /metadata/json/1 Skype 的完全限定名称。 例如：
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

若要配置 Skype 业务合作伙伴应用程序的服务器，打开 Exchange Management Shell 并运行类似如下的命令 （假定 c： 驱动器上安装了 Exchange，并使其使用的默认文件夹路径）：
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

配置合作伙伴应用程序后建议您停止并在您的 Exchange 邮箱和客户端访问服务器上重新启动 Internet 信息服务 (IIS)。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：
  
```
iisreset atl-exchange-001
```

在 Exchange 命令行管理程序中或从管理员权限下运行的任何其他命令窗口，可以从运行此命令。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>配置 Exchange Server 的企业服务器的 Skype 合作伙伴应用程序

配置 Skype 业务服务器进行 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序后，您必须然后配置 Exchange Server 的企业服务器的 Skype 合作伙伴应用程序。 这可以通过使用 Skype 业务 Server 命令行管理程序和 exchange; 指定身份验证元数据文档这通常是跟后缀 /metadata/json/1 Exchange 自动发现服务的 URI。 例如：
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

在业务服务器 Skype，通过[New-cspartnerapplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet 配置合作伙伴应用程序。 除了指定 URI 的元数据应当还应用程序信任级别设置为 Full;这将使 Exchange 以表示本身和领域中的任何授权的用户。 例如：
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

或者，您可以通过复制并修改脚本代码中的业务服务器到服务器身份验证文档 Skype 找到创建合作伙伴应用程序。 请参阅[管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序中的业务服务器 Skype](../../manage/authentication/server-to-server-and-partner-applications.md)文章的详细信息。
  
如果您已成功配置这两个 Skype 的业务 Server 和 Exchange Server 合作伙伴应用程序，您还成功已配置的两个产品之间的服务器到服务器身份验证。 Skype 业务服务器包括 Windows PowerShell cmdlet、 [Test-csexstorageconnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)可以验证已正确配置服务器到服务器身份验证和业务 Server 存储服务 Skype 可以连接到 Exchange 服务器。 此 cmdlet 来连接到 Exchange Server 用户的邮箱，为该用户，写入到对话历史记录文件夹的项目，然后 （可选） 删除该项目达到此目的。
  
若要测试业务 Server 和 Exchange Server 的集成的 Skype，运行 Business Server 命令行管理程序从 Skype 类似于以下命令：
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

在上述命令中，SipUri 表示的用户的 Exchange 服务器; 上的帐户的 SIP 地址您的命令将失败这不是有效的用户帐户。
  
> [!NOTE]
> 如果您收到 401 响应来自此 cmdlet 时，可能是因为 Exchange 的默认配置不包括对接受 Oauth 令牌的支持。 有关在 Exchange 中使用 Oauth 的详细信息，请参阅[使用 SharePoint 2013 和 Skype 业务服务器配置 OAuth 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=513103)。 
  
如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。
