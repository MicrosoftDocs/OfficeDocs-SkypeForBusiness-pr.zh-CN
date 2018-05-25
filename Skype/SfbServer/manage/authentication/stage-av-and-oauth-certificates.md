---
title: 在 Set-CsCertificate 中使用 -Roll 在 Skype for Business Server 2015 中暂存 AV 和 OAuth 证书
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 摘要： 用于业务服务器 2015年的 Skype 阶段 AV 和 OAuth 证书。
ms.openlocfilehash: 7c5abf07c5b30e4e015936fcf0987e989f1d8117
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-2015-using--roll-in-set-cscertificate"></a>在 Set-CsCertificate 中使用 -Roll 在 Skype for Business Server 2015 中暂存 AV 和 OAuth 证书
 
**摘要：** 为业务服务器 2015 Skype 的阶段 AV 和 OAuth 证书。
  
音频/视频 (A / V) 通信是业务服务器 2015年的 Skype 的关键组成部分。 等应用程序共享和音频和视频会议功能依赖于证书分配给 A / V 边缘服务，特别是 A / V 身份验证服务。
  
> [!IMPORTANT]
> 这一新功能旨在配合使用的 a / V 边缘服务和 OAuthTokenIssuer 证书。 其他证书类型可设置以及 A / V 边缘服务和 OAuth 证书类型，但不是将受益的共存行为的 A / V 边缘服务证书将。
  
业务服务器管理命令行管理程序 PowerShell cmdlet 用于管理业务服务器 2015年证书的 Skype Skype 指的是 A / V 边缘服务作为 AudioVideoAuthentication 证书类型的证书和为 OAuthServer 证书typeOAuthTokenIssuer。 对于其余的本主题和来唯一地标识证书，它们将按相同的标识符类型 AudioVideoAuthentication andOAuthTokenIssuer 身份引用。
  
A/V 身份验证服务负责颁发供客户端和其他 A/V 使用者使用的令牌。 这些令牌是根据证书上的属性生成的，当证书到期时，会断开连接并需要用新证书生成的新令牌重新连接。 中的业务服务器 2015 Skype 的新功能将缓解这一问题-阶段日过期，并允许两个证书，即可继续运行的一段时间，旧的一个新的证书的能力。 此功能使用已更新的功能在 Set-cscertificate Skype 业务 Server Management Shell cmdlet。 新参数-滚动，与现有的参数的-EffectiveDate，将新的 AudioVideoAuthentication 证书的证书存储中。 旧 AudioVideoAuthentication 证书仍将保留，以便根据该证书验证颁发的令牌。 随着新 AudioVideoAuthentication 证书的就绪，将发生以下一系列事件：
  
> [!TIP]
> 使用 Skype 业务 Server Management Shell cmdlet 用于管理证书，您可以为每个边缘服务器上请求单独和不同的证书。 使用 for Business Server 部署向导的 Skype 中的证书向导帮助您创建的证书，但通常为**默认**类型的将到单个证书的边缘服务器使用的所有证书。 如果要使用滚动证书功能，建议的做法是将 AudioVideoAuthentication 证书与其他证书用途分离开。 您可以设置和暂存默认类型的证书，但只有已合并证书的 AudioVideoAuthentication 部分将从暂存中受益。 用户 （例如） 参与即时消息对话，证书过期时将需要注销然后重新登录以使与访问边缘服务关联的新证书的使用。 使用 Web 会议边缘服务为 Web 会议中所涉及的用户，则会发生类似的行为。 OAuthTokenIssuer 证书是一种跨所有服务器共享的特定类型证书。 创建和管理一个位置中的证书和证书存储中中央管理存储的所有其他服务器。
  
需要更多详细信息才能充分了解您在使用 Set-CsCertificate cmdlet 并在当前证书到期之前将其用于暂存证书时的选择和要求。 在-回滚参数很重要，但实际上单一用途。 如果您定义它作为参数，您在告诉您将提供有关由-定义将受影响的证书的信息的 Set-cscertificate 类型 （例如 AudioVideoAuthentication 和 OAuthTokenIssuer） 时将成为证书定义-EffectiveDate 有效。
  
 **-滚动**： 参数是必需的具有依赖项必须提供以及其在-回滚。 以下必需参数用于充分定义哪些证书将受影响以及将如何应用这些证书：
  
 **-EffectiveDate**: 参数-EffectiveDate 定义时，新证书将成为 co-active 与当前证书。 -EffectiveDate 可以是接近当前证书的到期时间也很长的时间段。 建议最小-EffectiveDate AudioVideoAuthentication 证书将为 8 小时，这是默认令牌生存期 AV 边缘服务令牌颁发使用 AudioVideoAuthentication 证书。
  
暂存 OAuthTokenIssuer 证书时，对于证书生效之前的提前期有不同的要求。OAuthTokenIssuer 证书的最短提前时间是当前证书到期前的 24 小时。为实现共存而延长提前期是因为存在依赖于 OAuthTokenIssuer 证书的其他服务器角色（例如 Exchange Server），该证书创建的身份验证和加密密钥材料具有更长的保留时间。
  
 **-Thumbprint**：指纹是证书特有的属性。 -指纹参数用于标识将受影响的证书的 Set-cscertificate cmdlet 的操作。
  
 **-类型**:-类型参数可以接受单个证书使用类型或证书使用类型以逗号分隔列表。 证书类型用于向 cmdlet 和服务器确认证书的用途。 例如，类型 AudioVideoAuthentication 是用于通过 A / V 边缘服务和 AV 身份验证服务。 如果你决定同时暂存和设置不同类型的证书，则必须针对这些证书的最短生效提前期，考虑其中所需的最长生效期。 例如，你需要暂存 AudioVideoAuthentication 和 OAuthTokenIssuer 类型的证书。 您最小 EffectiveDate 必须更大容量的两个证书，在此情况下 OAuthTokenIssuer，上面有最小负责人时间为 24 小时。 如果你不想用 24 小时提前期暂存 AudioVideoAuthentication 证书，请使用更符合你的要求的 EffectiveDate 单独暂存它。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>更新或续订 A / V 边缘服务证书使用-Roll 和-EffectiveDate 参数

1. 以 Administrators 组成员的身份登录本地计算机。
    
2. A 上的现有证书的可导出私钥请求续订或新的 AudioVideoAuthentication 证书 / V 边缘服务。
    
3. （如果您部署了一个池），新的 AudioVideoAuthentication 证书导入边缘服务器和池中的所有其他边缘服务器。
    
4. 使用 Set-cscertificate cmdlet 配置导入的证书和使用-Roll 参数和-EffectiveDate 参数。 生效日期应定义为当前证书到期时间（14:00:00 或下午 2:00:00）减去令牌生命周期（默认为八小时）。 这让我们证书必须设置为活动，一次，-EffectiveDate\<字符串\>:"7/22/2015年 6:00:00"。 
    
    > [!IMPORTANT]
    > 对于边缘池，您必须具有所有 AudioVideoAuthentication 证书部署并设置过的日期和时间的第一个证书部署以避免可能 A-EffectiveDate 参数定义 / 由于较旧的 V communications 中断证书过期之前已使用新的证书续订客户端和使用者的所有令牌。 
  
    Set-cscertificate 命令与-Roll 和-EffectiveTime 参数：
    
  ```
  Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
  ```

    Set-CsCertificate 命令示例：
    
  ```
  Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
  ```

    > [!IMPORTANT]
    > EffectiveDate 必须要设置格式，以匹配您的服务器的区域和语言设置。 本例使用美国英语区域和语言设置 
  
若要进一步了解过程，该 Set-cscertificate，-Roll 和-EffectiveDate 用于阶段颁发同时仍使用现有证书来验证 AudioVideoAuthentication 正在使用的新 AudioVideoAuthentication 令牌的新证书通过使用者，可视日程表是了解过程有效方法。 在以下示例中，管理员确定的 A / V 边缘服务证书将在 2:00:00 07/22/2015年过期。 他请求和接收新证书并在其池将其导入每台边缘服务器。 上午 2 上 07/22/2015年，他开始运行 Get-cscertificate-滚动，-指纹等于的新证书的指纹字符串和-EffectiveTime 设置为 07/22/2015年 6:00:00。 他在每台边缘服务器上运行此命令。
  
![使用 Roll 和 EffectiveDate 参数。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**标注**|**阶段**|
|:-----|:-----|
|1  <br/> |开始时间：2015 年 7 月 22 日上午 12:00:00  <br/> 当前 AudioVideoAuthentication 证书在 2015 年 7 月 22 日下午 2:00:00 到期。这由证书上的过期时间戳决定。规划证书替换和滚动，计入现有证书达到过期时间前的 8 小时重叠期（默认令牌生命周期）。上午 2:00:00 提前时间在本例中用来给管理员留出足够的时间，在上午 6:00:00 生效时间前放置和设置新证书。  <br/> |
|2  <br/> |2015 年 7 月 22 日上午 2:00:00 - 2015 年 7 月 22 日上午 5:59:59  <br/> 有效时间 6:00:00 （4 小时提前期对于此示例，但可更长时间） 边缘服务器上设置证书使用 Set-cscertificate-类型\<证书使用类型\>-指纹\<新证书的指纹\>-滚动-EffectiveDate\<的新证书的有效时间的 datetime 字符串\>  <br/> |
|3  <br/> |2015 年 7 月 22 日上午 6:00 - 2015 年 7 月 22 日下午 2:00  <br/> 为了验证令牌，首先尝试新证书，如果新证书未能验证令牌，则尝试旧证书。在 8 小时（默认令牌生命周期）重叠期内，此过程用于所有令牌。  <br/> |
|4  <br/> |结束时间：2015 年 7 月 22 日下午 2:00:01  <br/> 旧证书过期，新证书接替旧证书。 可以使用删除 CsCertificate 安全删除旧证书-类型\<证书使用类型\>-以前  <br/> |
   
当达到生效时间（2015 年 7 月 22 日上午 6:00:00）时，新证书将颁发所有新令牌。 在验证令牌时，将首先根据新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。 旧证书到期后（2015 年 7 月 22 日下午 2:00:00），将只根据新证书验证令牌。 旧证书可安全删除使用删除 cmdlet 与-以前的参数。

```
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>更新或续订 OAuthTokenIssuer 证书使用-Roll 和-EffectiveDate 参数

1. 以 Administrators 组成员的身份登录本地计算机。
    
2. 前端服务器上的现有证书的可导出私钥请求续订或新 OAuthTokenIssuer 证书。
    
3. （如果您部署了一个池），新 OAuthTokenIssuer 证书导入前端池中服务器。 将全局复制 OAuthTokenIssuer 证书且只需在部署中的任何服务器更新和续订这些证书。 前端服务器用作示例。
    
4. 使用 Set-cscertificate cmdlet 配置导入的证书和使用-Roll 参数和-EffectiveDate 参数。 生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去至少 24 个小时。 
    
    Set-cscertificate 命令与-Roll 和-EffectiveTime 参数：
    
  ```
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
  ```

Set-CsCertificate 命令示例：
    
  ```
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate 必须要设置格式，以匹配您的服务器的区域和语言设置。 本例使用美国英语区域和语言设置 
  
当到达生效时间（2015 年 7 月 21 日上午 1:00:00）时，新证书将颁发所有新令牌。 在验证令牌时，将首先根据新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。 旧证书到期后（2015 年 7 月 22 日下午 2:00:00），将只根据新证书验证令牌。 旧证书可安全删除使用删除 cmdlet 与-以前的参数。
```
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>另请参阅

#### 

[管理服务器到服务器身份验证 (OAuth) 和 Skype 中的业务服务器 2015年的合作伙伴应用程序](server-to-server-and-partner-applications.md)

[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[删除 CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)

