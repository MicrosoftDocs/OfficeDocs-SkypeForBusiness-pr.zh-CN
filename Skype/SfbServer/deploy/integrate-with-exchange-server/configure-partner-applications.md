---
title: 在 Skype for Business Server 2015 和 Exchange Server 中配置合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：将服务器配置为 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器的服务器身份验证。
ms.openlocfilehash: 9512d271b23f26afcb1ef6385a1a6dd5d513c948
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797073"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>在 Skype for Business Server 和 Exchange Server 中配置合作伙伴应用程序
 
**摘要：** 将服务器配置为 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器的服务器身份验证。
  
服务器到服务器身份验证通常要有两台需要相互通信的服务器以及一台第三方安全令牌服务器。 如果服务器 A 和服务器 B 需要进行通信，则这两个服务器通常都通过联系令牌服务器并获取相互信任的安全令牌开始。 之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。
  
但是，这是一个一般规则。 Skype for business 服务器、Exchange Server 2016、Exchange Server 2013 和 SharePoint Server 2013 在彼此通信时不需要使用第三方令牌服务器;这是因为这些服务器产品可以创建彼此不需要单独的令牌服务器即可接受的安全令牌。 （此功能仅在 Skype for Business Server、Exchange Server 2016、Exchange Server 2013 和 SharePoint Server 2013 中可用。 如果需要与其他服务器（包括其他 Microsoft 服务器产品）设置服务器到服务器的身份验证，则需要使用第三方令牌服务器执行此操作。
  
若要在 Skype for Business 服务器和 Exchange Server 之间设置服务器到服务器身份验证，你必须执行两项操作：1）必须为每台服务器分配相应的证书;和2），您必须将每台服务器配置为另一台服务器的合作伙伴应用程序：这意味着您必须将 Skype for business 服务器配置为 Exchange Server 的合作伙伴应用程序，并且您必须将 Exchange Server 配置为适用于 Skype 的合作伙伴应用程序适用于企业服务器。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>将 Skype for business 服务器配置为 Exchange Server 的合作伙伴应用程序

将 Skype for business 服务器配置为具有 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序的最简单方法是运行 Configure-EnterprisePartnerApplication 脚本，该脚本是随 Exchange Server 一起提供的 Windows PowerShell 脚本。 若要运行此脚本，必须提供 Skype for Business Server 身份验证元数据文档的 URL;这通常是 Skype for Business 服务器池的完全限定的域名，后跟后缀/metadata/json/1。 例如：
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

若要将 Skype for Business 服务器配置为合作伙伴应用程序，请打开 Exchange 命令行管理程序并运行与此类似的命令（假设 Exchange 已安装在驱动器 C：上，并且它使用默认文件夹路径）：
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

配置合作伙伴应用程序后，建议您在 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet 信息服务（IIS）。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：
  
```powershell
iisreset atl-exchange-001
```

此命令可以从 Exchange 命令行管理程序中运行，也可以从任何其他命令窗口中通过管理员权限运行。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>将 Exchange Server 配置为 Skype for Business 服务器的合作伙伴应用程序

将 Skype for business 服务器配置为 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序后，必须随后将 Exchange Server 配置为适用于 Skype for business 服务器的合作伙伴应用程序。 这可以通过使用 Skype for Business 服务器管理外壳程序和指定 Exchange 的身份验证元数据文档来完成;这通常是 Exchange 自动发现服务的 URI，后跟后缀/metadata/json/1。 例如：
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

在 Skype for Business 服务器中，通过使用[CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet 配置合作伙伴应用程序。 除了指定元数据 URI 之外，还应将应用程序信任级别设置为 "完全";这将允许 Exchange 同时代表领域中的自身和任何授权用户。 例如：
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

或者，你可以通过复制和修改 Skype for Business Server 服务器到服务器身份验证文档中找到的脚本代码来创建合作伙伴应用程序。 有关详细信息，请参阅[Skype For Business server 文章中的 "管理服务器到服务器的身份验证（OAuth）和合作伙伴应用程序](../../manage/authentication/server-to-server-and-partner-applications.md)"。
  
如果你已成功配置 Skype for business Server 和 Exchange Server 的合作伙伴应用程序，则你还成功配置了这两个产品之间的服务器到服务器身份验证。 Skype for Business 服务器包括 Windows PowerShell cmdlet、 [CsExStorageConnectivity 测试](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)版，可用于验证服务器到服务器身份验证是否已正确配置以及 Skype For Business Server 存储服务是否可以连接到 Exchange 服务器。 该 cmdlet 通过以下方式执行此操作：连接到 Exchange Server 用户的邮箱，向该用户的 "对话历史记录" 文件夹中写入项目，然后（可选）删除该项目。
  
若要测试 Skype for business 服务器和 Exchange Server 的集成，请从 Skype for business 服务器管理外壳程序运行类似以下内容的命令：
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

在前面的命令中，SipUri 表示具有 Exchange Server 帐户的用户的 SIP 地址;您的命令将失败，这不是有效的用户帐户。
  
> [!NOTE]
> 如果你收到来自此 cmdlet 的401响应，这可能是因为 Exchange 的默认配置不包括对接受 Oauth 令牌的支持。 有关在 Exchange 中使用 Oauth 的详细信息，请参阅[使用 SharePoint 2013 和 Skype For Business 服务器配置 oauth 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=513103)。 
  
如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。
