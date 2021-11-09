---
title: 使用 -Roll 在 Skype for Business Server中将 AV 和 OAuth 证书Set-CsCertificate
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 摘要：为用户阶段 AV 和 OAuth Skype for Business Server。
ms.openlocfilehash: 7eeac29ba322d40d8ab8f70712ecfca5ead5c97d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832106"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>使用 -Roll 在 Skype for Business Server中将 AV 和 OAuth 证书Set-CsCertificate
 
**摘要：** 为用户阶段 AV 和 OAuth Skype for Business Server。
  
音频/视频 (A/V) 通信是音频/视频Skype for Business Server。 应用程序共享以及音频和视频会议等功能依赖于分配给 A/V 边缘服务（特别是 A/V 身份验证服务）的证书。
  
> [!IMPORTANT]
> 此新功能设计用于 A/V 边缘服务和 OAuthTokenIssuer 证书。 其他证书类型可以与 A/V 边缘服务和 OAuth 证书类型一起设置，但无法从 A/V 边缘服务证书的共存行为中获益。
  
用于Skype for Business Server Skype for Business Server 证书的命令行管理程序 PowerShell cmdlet 将 A/V 边缘服务证书引用为 AudioVideoAuthentication 证书类型，将 OAuthServer 证书作为类型OAuthTokenIssuer。 对于本主题的其余部分和唯一标识证书，它们将被相同的标识符类型 AudioVideoAuthentication 和OAuthTokenIssuer 引用。
  
A/V 身份验证服务负责颁发供客户端和其他 A/V 使用者使用的令牌。 这些令牌是根据证书上的属性生成的，当证书到期时，会断开连接并需要用新证书生成的新令牌重新连接。 Skype for Business Server中的一项新功能将缓解这一问题 ，即能够在旧证书过期之前阶段新证书并允许这两个证书继续运行一段时间。 此功能使用命令行管理程序 cmdlet 中的Set-CsCertificate Skype for Business Server功能。 新参数 -Roll 以及现有参数 -EffectiveDate 将新的 AudioVideoAuthentication 证书放在证书存储中。 旧 AudioVideoAuthentication 证书仍将保留，以便根据该证书验证颁发的令牌。 随着新 AudioVideoAuthentication 证书的就绪，将发生以下一系列事件：
  
> [!TIP]
> 使用 Skype for Business Server命令行管理程序 cmdlet 管理证书，可以针对边缘服务器上每个用途请求单独且不同的证书。 使用 Skype for Business Server 部署向导中的证书向导可帮助你创建证书，但通常是默认类型，用于边缘服务器的所有证书都结合到一个证书上。 如果要使用滚动证书功能，建议的做法是将 AudioVideoAuthentication 证书与其他证书用途分离开。 您可以设置和暂存默认类型的证书，但只有已合并证书的 AudioVideoAuthentication 部分将从暂存中受益。 例如， (中涉及的用户) 证书过期时进行即时消息对话将需要注销并重新登录，才能使用与访问边缘服务关联的新证书。 对于使用 Web 会议边缘服务参与 Web 会议的用户，也会发生类似行为。 OAuthTokenIssuer 证书是一种跨所有服务器共享的特定类型证书。 您可以在一处创建和管理证书，证书将存储在所有其他服务器的中央管理存储中。
  
需要更多详细信息才能充分了解您在使用 Set-CsCertificate cmdlet 并在当前证书到期之前将其用于暂存证书时的选择和要求。 -Roll 参数很重要，但基本上只有一个用途。 如果您将参数定义为参数，则告知 Set-CsCertificate您将提供有关将在 -Type (（例如 AudioVideoAuthentication 和 OAuthTokenIssuer) ）定义（例如 AudioVideoAuthentication 和 OAuthTokenIssuer) ）定义的证书生效时，该证书将受到影响的信息。
  
 **-Roll**：-Roll 参数是必需的，并且具有必须随其一起提供的依赖项。 以下必需参数用于充分定义哪些证书将受影响以及将如何应用这些证书：
  
 **-EffectiveDate**：参数 -EffectiveDate 定义新证书何时与当前证书共同使用。 -EffectiveDate 可以接近当前证书的到期时间，也可以长一段时间。 AudioVideoAuthentication 证书的建议最低 -EffectiveDate 为 8 小时，这是使用 AudioVideoAuthentication 证书颁发的 AV 边缘服务令牌的默认令牌生存期。
  
暂存 OAuthTokenIssuer 证书时，对于证书生效之前的提前期有不同的要求。OAuthTokenIssuer 证书的最短提前时间是当前证书到期前的 24 小时。为实现共存而延长提前期是因为存在依赖于 OAuthTokenIssuer 证书的其他服务器角色（例如 Exchange Server），该证书创建的身份验证和加密密钥材料具有更长的保留时间。
  
 **-Thumbprint**：指纹是证书特有的属性。 -Thumbprint 参数用于标识受 Set-CsCertificate cmdlet 操作影响的证书。
  
 **-Type**：-Type 参数可以接受单个证书使用类型或证书使用类型的逗号分隔列表。 证书类型用于向 cmdlet 和服务器确认证书的用途。 例如，类型 AudioVideoAuthentication 供 A/V 边缘服务和 AV 身份验证服务使用。 如果您决定同时暂存和设置不同类型的证书，则必须针对这些证书的最短生效提前期，考虑其中所需的最长生效期。 例如，您需要暂存 AudioVideoAuthentication 和 OAuthTokenIssuer 类型的证书。 最小 -EffectiveDate 必须为两个证书中的较大值，在这种情况下为 OAuthTokenIssuer，其最短前向时间为 24 小时。 如果您不想用 24 小时提前期暂存 AudioVideoAuthentication 证书，请使用更符合您的要求的 EffectiveDate 单独暂存它。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 -Roll 和 -EffectiveDate 参数更新或续订 A/V 边缘服务证书

1. 以以下组的成员登录到本地管理员组。
    
2. 为 A/V 边缘服务上的现有证书请求续订或新的 AudioVideoAuthentication 证书以及可导出的私钥。
    
3. 将新的 AudioVideoAuthentication 证书导入到池中的边缘服务器和所有其他边缘 (如果已部署池) 。
    
4. 使用 Set-CsCertificate cmdlet 配置导入的证书，并使用 -Roll 参数和 -EffectiveDate 参数。 生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去令牌生命周期（默认为八小时）。 这为我们提供了必须将证书设置为活动状态的时间，并且为 -EffectiveDate \<string\> ： "7/22/2015 6：00：00 AM"。 
    
    > [!IMPORTANT]
    > 对于边缘池，必须按照部署的第一个证书的 -EffectiveDate 参数定义的日期和时间部署和设置所有 AudioVideoAuthentication 证书，以避免由于旧证书在使用新证书续订所有客户端和使用者令牌之前过期而可能出现的 A/V 通信中断。 
  
    The Set-CsCertificate command with the -Roll and -EffectiveTime parameter：
    
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
    > 必须设置 EffectiveDate 的格式，以匹配服务器的区域设置和语言设置。 本例使用美国英语区域和语言设置 
  
为了进一步理解 Set-CsCertificate、-Roll 和 -EffectiveDate 用于阶段新证书以颁发新的 AudioVideoAuthentication 令牌，同时仍使用现有证书验证使用者使用的 AudioVideoAuthentication 的过程，可视化时间线是了解该过程的有效方式。 在下面的示例中，管理员确定 A/V 边缘服务证书将于 2015 年 7 月 22 日下午 2：00：00 过期。 他请求并接收新证书，并导入到池中的每台边缘服务器。 2015 年 7 月 22 日上午 2 点，他开始运行 Get-CsCertificate，其中 -Roll、-Thumbprint 等于新证书的指纹字符串，-EffectiveTime 设置为 07/22/2015 6：00：00 AM。 他在每个边缘服务器上运行此命令。
  
![使用 Roll 和 EffectiveDate 参数。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Stage**|
|:-----|:-----|
|1  <br/> |开始时间：2015 年 7 月 22 日上午 12：00：00  <br/> 当前的 AudioVideoAuthentication 证书将于 2015 年 7 月 22 日下午 2：00：00 过期。 这由证书上的过期时间戳决定。 Plan your certificate replacement and rollover to account for an 8 hour overlap (default token lifetime) before the existing certificate reaches the expire time. 此示例使用 2：00：00 AM 提前时间，以便管理员在 6：00：00 AM 生效时间之前留出足够的时间来放置和设置新证书。  <br/> |
|2  <br/> |2015/7/22 2：00：00 AM - 7/22/2015 5：59：59 AM  <br/> 对于此示例，在有效时间为上午 6：00：00 (4 小时的边缘服务器上设置证书适用于此示例，但使用 Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate) 可以更长 \<datetime string of the effective time for new certificate\>  <br/> |
|3  <br/> |7/22/2015 6：00 AM - 7/22/2015 2：00 PM  <br/> 若要验证令牌，首先尝试新证书，如果新证书无法验证令牌，则尝试旧证书。 此过程在 8 小时（默认令牌生存期 (重叠期间）) 令牌。  <br/> |
|4  <br/> |结束时间：2015/7/22 2：00：01 PM  <br/> 旧证书已过期，新证书已接管。 使用 -Type -Previous 可以安全地Remove-CsCertificate旧 \<certificate usage type\> 证书  <br/> |
   
在 2015 年 7 (6：00：00 AM) 到达生效时间时，所有新令牌都由新证书颁发。 在验证令牌时，将首先根据新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。 旧证书在 (2015 年 7 月 22 日下午 2：00：00) 过期后，令牌将仅通过新证书进行验证。 可以使用带 -Previous 参数的 Remove-CsCertificate cmdlet 安全地删除旧证书。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 -Roll 和 -EffectiveDate 参数更新或续订 OAuthTokenIssuer 证书

1. 以以下组的成员登录到本地管理员组。
    
2. 使用前端服务器上现有证书的可导出私钥请求续订或新 OAuthTokenIssuer 证书。
    
3. 如果您已经部署了池，则将新的 OAuthTokenIssuer 证书导入池 (前端) 。 将全局复制 OAuthTokenIssuer 证书且只需在部署中的任何服务器更新和续订这些证书。 前端服务器用作示例。
    
4. 使用 Set-CsCertificate cmdlet 配置导入的证书，并使用 -Roll 参数和 -EffectiveDate 参数。 生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去至少 24 个小时。 
    
    The Set-CsCertificate command with the -Roll and -EffectiveTime parameter：
    
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
> 必须设置 EffectiveDate 的格式，以匹配服务器的区域设置和语言设置。 本例使用美国英语区域和语言设置 
  
在 2015 年 7 月 21 (上午 1：00：00) 到达生效时间时，所有新令牌都由新证书颁发。 在验证令牌时，将首先根据新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。 旧证书在 (2015 年 7 月 22 日下午 2：00：00) 过期后，令牌将仅通过新证书进行验证。 可以使用带 -Previous 参数的 Remove-CsCertificate cmdlet 安全地删除旧证书。
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>另请参阅

[管理 OAuth 服务器到服务器 (OAuth) 和合作伙伴应用程序Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate?view=skype-ps)