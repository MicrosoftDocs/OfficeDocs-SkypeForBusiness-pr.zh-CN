---
title: 在 CsCertificate 中使用-滚在 Skype for Business 服务器中暂存 AV 和 OAuth 证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 摘要：暂存 Skype for business 服务器的 AV 和 OAuth 证书。
ms.openlocfilehash: 530e8f603d2c5be368df37354c3974e2b5abeb5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818724"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>在 CsCertificate 中使用-滚在 Skype for Business 服务器中暂存 AV 和 OAuth 证书
 
**摘要：** 暂存 Skype for business 服务器的 AV 和 OAuth 证书。
  
音频/视频（A/V）通信是 Skype for Business 服务器的一个关键组件。 应用程序共享和音频和视频会议等功能依赖于分配给 A/V 边缘服务的证书，特别是 A/V 身份验证服务。
  
> [!IMPORTANT]
> 此新功能旨在适用于 A/V 边缘服务和 OAuthTokenIssuer 证书。 其他证书类型可以与 A/V 边缘服务和 OAuth 证书类型一起设置，但不会受益于 A/V 边缘服务证书将使用的共存行为。
  
用于管理 Skype for business Server 证书的 Skype for Business Server Management Shell PowerShell cmdlet 是将 A/V 边缘服务证书作为 AudioVideoAuthentication 证书类型，将 OAuthServer 证书称为 typeOAuthTokenIssuer。 对于本主题的其余部分和唯一标识证书，它们将被同一标识符类型（AudioVideoAuthentication andOAuthTokenIssuer）引用。
  
A/V 身份验证服务负责颁发供客户端和其他 A/V 使用者使用的令牌。 这些令牌是根据证书上的属性生成的，当证书到期时，会断开连接并需要用新证书生成的新令牌重新连接。 Skype for Business 服务器中的新功能将缓解此问题，即在旧证书即将过期并允许两个证书在一段时间内继续运行的功能。 此功能使用 CsCertificate Skype for business Server Management Shell cmdlet 中的更新功能。 新的参数 EffectiveDate （现有参数为）会将新的 AudioVideoAuthentication 证书放置在证书存储中。 旧 AudioVideoAuthentication 证书仍将保留，以便根据该证书验证颁发的令牌。 随着新 AudioVideoAuthentication 证书的就绪，将发生以下一系列事件：
  
> [!TIP]
> 使用 Skype for Business Server Management Shell cmdlet 管理证书，你可以为边缘服务器上的每个用途请求单独和不同的证书。 使用 Skype for Business 服务器部署向导中的 "证书" 向导可帮助你创建证书，但通常是**默认**类型，它会将边缘服务器的所有证书使用集中到单个证书。 如果要使用滚动证书功能，建议的做法是将 AudioVideoAuthentication 证书与其他证书用途分离开。 您可以设置和暂存默认类型的证书，但只有已合并证书的 AudioVideoAuthentication 部分将从暂存中受益。 当证书过期时，参与即时消息对话的用户需要注销，然后重新登录以使用与访问边缘服务关联的新证书。 对于使用 Web 会议边缘服务的 Web 会议中涉及的用户，将出现类似行为。 OAuthTokenIssuer 证书是一种跨所有服务器共享的特定类型证书。 您在一个位置创建和管理证书，并且证书存储在所有其他服务器的中央管理存储中。
  
需要更多详细信息才能充分了解您在使用 Set-CsCertificate cmdlet 并在当前证书到期之前将其用于暂存证书时的选择和要求。 -滚参数很重要，但实质上是单用途。 如果你将其定义为参数，你将告诉 CsCertificate，你将在证书将变为时提供有关受类型（例如 AudioVideoAuthentication 和 OAuthTokenIssuer）定义的证书的信息有效的 EffectiveDate 定义。
  
 **-滚**：-滚参数是必需的，并且具有必须随其一起提供的依赖项。 以下必需参数用于充分定义哪些证书将受影响以及将如何应用这些证书：
  
 **-EffectiveDate**： EffectiveDate 定义新证书与当前证书之间的活动状态。 -EffectiveDate 可以接近当前证书的到期时间，也可能需要较长的一段时间。 对于 AudioVideoAuthentication 证书，建议的最小 EffectiveDate 为8小时，这是使用 AudioVideoAuthentication 证书颁发的 AV 边缘服务令牌的默认令牌有效期。
  
暂存 OAuthTokenIssuer 证书时，对于证书生效之前的提前期有不同的要求。OAuthTokenIssuer 证书的最短提前时间是当前证书到期前的 24 小时。为实现共存而延长提前期是因为存在依赖于 OAuthTokenIssuer 证书的其他服务器角色（例如 Exchange Server），该证书创建的身份验证和加密密钥材料具有更长的保留时间。
  
 **-Thumbprint**：指纹是证书特有的属性。 -Thumbprint 参数用于标识将受 CsCertificate cmdlet 的操作影响的证书。
  
 **-Type**：-type 参数可以接受单个证书使用类型或证书使用类型的逗号分隔列表。 证书类型用于向 cmdlet 和服务器确认证书的用途。 例如，键入 AudioVideoAuthentication 供 A/V 边缘服务和 AV 身份验证服务使用。 如果你决定同时暂存和设置不同类型的证书，则必须针对这些证书的最短生效提前期，考虑其中所需的最长生效期。 例如，你需要暂存 AudioVideoAuthentication 和 OAuthTokenIssuer 类型的证书。 您的最低 EffectiveDate 必须是两个证书中的较大值，在本例中为 OAuthTokenIssuer，其最短提前期为24小时。 如果你不想用 24 小时提前期暂存 AudioVideoAuthentication 证书，请使用更符合你的要求的 EffectiveDate 单独暂存它。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>使用-滚和-EffectiveDate 参数更新或续订 A/V 边缘服务证书

1. 以 Administrators 组成员的身份登录本地计算机。
    
2. 向 A/V 边缘服务上的现有证书的可导出私钥请求续订或新的 AudioVideoAuthentication 证书。
    
3. 将新的 AudioVideoAuthentication 证书导入到边缘服务器以及你的池中的所有其他边缘服务器（如果已部署池）。
    
4. 使用 CsCertificate cmdlet 配置导入的证书，并将-滚参数与-EffectiveDate 参数一起使用。 生效日期应定义为当前证书到期时间（14:00:00 或下午 2:00:00）减去令牌生命周期（默认为八小时）。 这为我们提供了一个证书必须设置为活动的时间，并且是-EffectiveDate \<字符串\>： "7/22/2015 6:00:00 AM"。 
    
    > [!IMPORTANT]
    > 对于边缘池，你必须使用部署的第一个证书的-EffectiveDate 参数定义的日期和时间部署和预配所有 AudioVideoAuthentication 证书，以避免可能的 A/V 通信中断，因为较旧的证书在使用新证书续订所有客户端和消费者令牌之前即将过期。 
  
    带有-滚和-EffectiveTime 参数的 CsCertificate 命令：
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Set-CsCertificate 命令示例：
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate 必须设置格式以匹配服务器的区域和语言设置。 本例使用美国英语区域和语言设置 
  
若要进一步了解设置 CsCertificate、EffectiveDate 和-的过程，以便在发出新的 AudioVideoAuthentication 令牌的同时仍使用现有证书验证正在使用的 AudioVideoAuthentication 的新证书通过使用者，视觉日程表是了解流程的有效方法。 在以下示例中，管理员确定 A/V 边缘服务证书的到期日期为 2:00:00 PM 的07/22/2015。 他请求并接收新证书，并将其导入到池中的每个边缘服务器。 在 07/22/2015 AM，他开始运行 CsCertificate with，-Thumbprint 等于新证书的指纹字符串，而-EffectiveTime 设置为 07/22/2015 6:00:00 AM。 他在每台边缘服务器上运行此命令。
  
![使用 Roll 和 EffectiveDate 参数。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**标注**|**阶段**|
|:-----|:-----|
|1  <br/> |开始时间：2015 年 7 月 22 日上午 12:00:00  <br/> 当前 AudioVideoAuthentication 证书在 2015 年 7 月 22 日下午 2:00:00 到期。这由证书上的过期时间戳决定。规划证书替换和滚动，计入现有证书达到过期时间前的 8 小时重叠期（默认令牌生命周期）。上午 2:00:00 提前时间在本例中用来给管理员留出足够的时间，在上午 6:00:00 生效时间前放置和设置新证书。  <br/> |
|ppls-2  <br/> |2015 年 7 月 22 日上午 2:00:00 - 2015 年 7 月 22 日上午 5:59:59  <br/> 在\<边缘服务器上设置具有 6:00:00 AM 有效时间的证书（4小时的提前期是针对此示例，但可以更长）使用 CsCertificate 类型证书使用类型\> -新证书\<的有效时间的\>新证书 EffectiveDate \<日期时间字符串的指纹指纹\>  <br/> |
|3  <br/> |2015 年 7 月 22 日上午 6:00 - 2015 年 7 月 22 日下午 2:00  <br/> 若要验证令牌，首先尝试新证书，如果新证书无法验证令牌，则会尝试旧证书。 此过程用于8小时（默认令牌生存期）重叠期间的所有令牌。  <br/> |
|4  <br/> |结束： 7/22/2015 2:00:01 PM  <br/> 旧证书已过期，新证书已被占用。 可以使用删除 CsCertificate 类型\<证书使用类型\>安全地删除旧证书-上一个  <br/> |
   
当达到有效时间（7/22/2015 6:00:00 AM）时，所有新令牌均由新证书发出。 验证令牌时，将首先对照新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新的和回退到旧证书的过程将继续，直到旧证书的到期时间。 一旦旧证书已过期（7/22/2015 2:00:00 PM），令牌将仅由新证书验证。 可以使用带有-Previous 参数的 CsCertificate cmdlet 安全地删除旧证书。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>使用-滚和-EffectiveDate 参数更新或续订 OAuthTokenIssuer 证书

1. 以 Administrators 组成员的身份登录本地计算机。
    
2. 使用前端服务器上现有证书的可导出私钥请求续订或新的 OAuthTokenIssuer 证书。
    
3. 将新的 OAuthTokenIssuer 证书导入到你的池中的前端服务器（如果已部署池）。 OAuthTokenIssuer 证书是全局复制的，并且仅需要在部署中的任何服务器上更新和续订。 前端服务器用作示例。
    
4. 使用 CsCertificate cmdlet 配置导入的证书，并将-滚参数与-EffectiveDate 参数一起使用。 有效日期应定义为当前证书过期时间（14:00:00，即 2:00:00 PM）减去至少24小时。 
    
    带有-滚和-EffectiveTime 参数的 CsCertificate 命令：
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Set-CsCertificate 命令示例：
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate 必须设置格式以匹配服务器的区域和语言设置。 本例使用美国英语区域和语言设置 
  
当达到有效时间（7/21/2015 1:00:00 AM）时，所有新令牌均由新证书发出。 验证令牌时，将首先对照新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新的和回退到旧证书的过程将继续，直到旧证书的到期时间。 一旦旧证书已过期（7/22/2015 2:00:00 PM），令牌将仅由新证书验证。 可以使用带有-Previous 参数的 CsCertificate cmdlet 安全地删除旧证书。
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中管理服务器到服务器的身份验证（OAuth）和合作伙伴应用程序](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
