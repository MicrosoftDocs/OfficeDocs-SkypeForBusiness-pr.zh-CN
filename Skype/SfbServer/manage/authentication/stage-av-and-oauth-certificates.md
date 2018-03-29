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
description: 摘要： 舞台 AV 和 OAuth 的证书业务服务器 2015年的 Skype。
ms.openlocfilehash: 4117707e7a86833ebb235100c26e27d16e1df9db
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-2015-using--roll-in-set-cscertificate"></a>在 Set-CsCertificate 中使用 -Roll 在 Skype for Business Server 2015 中暂存 AV 和 OAuth 证书
 
**摘要：**Skype 的业务服务器 2015年的舞台 AV 和 OAuth 证书。
  
音频/视频 (A / V) 通信是业务服务器 2015年的 Skype 的关键组成部分。 应用程序共享和音频和视频会议等功能依赖于证书分配到 A / V 边缘服务，特别是 A / V 认证服务。
  
> [!IMPORTANT]
> 这种新功能旨在适用于 A / V 边缘服务和 OAuthTokenIssuer 证书。 其他证书类型可以调配以及 A / V 边缘服务和 OAuth 证书类型，但将不会受益的共存行为的 A / V 边缘服务证书将。
  
用于管理业务服务器 2015年证书 Skype 业务服务器管理外壳 PowerShell cmdlet 的 Skype 指 A / V 边缘服务证书作为 AudioVideoAuthentication 证书类型和形式的 OAuthServer 证书typeOAuthTokenIssuer。 有关此主题的并唯一地标识证书的其余部分，它们将被相同的标识符类型，AudioVideoAuthentication andOAuthTokenIssuer。
  
A/V 身份验证服务负责颁发供客户端和其他 A/V 使用者使用的令牌。 这些令牌是根据证书上的属性生成的，当证书到期时，会断开连接并需要用新证书生成的新令牌重新连接。 Skype 的业务服务器 2015年中的新功能将缓解这一问题的阶段之前过期，并允许这两个证书，以继续工作一段时间内的旧一个新证书的能力。 此功能用于更新的功能在集 CsCertificate Skype 业务服务器管理外壳 cmdlet。 新参数-掷，使用现有的参数-EffectiveDate，会将新 AudioVideoAuthentication 证书的证书存储中。 旧 AudioVideoAuthentication 证书仍将保留，以便根据该证书验证颁发的令牌。 随着新 AudioVideoAuthentication 证书的就绪，将发生以下一系列事件：
  
> [!TIP]
> 使用 Skype 业务服务器管理外壳程序用于管理证书的 cmdlet，您可以为边缘服务器上的每个目标请求独立且不同的证书。 在 Skype 业务服务器部署向导使用证书向导帮助您创建的证书，但通常的情侣对边缘服务器到一个证书中使用的所有证书的**默认**类型。 如果要使用滚动证书功能，建议的做法是将 AudioVideoAuthentication 证书与其他证书用途分离开。 您可以设置和暂存默认类型的证书，但只有已合并证书的 AudioVideoAuthentication 部分将从暂存中受益。 用户 （例如） 中涉及到即时消息对话在证书过期时将需要注销然后重新登录以使用新的证书与访问边缘服务相关联。 类似的行为将发生在 Web 会议中使用的 Web 会议边缘服务所涉及的用户。 OAuthTokenIssuer 证书是一种跨所有服务器共享的特定类型证书。 创建和管理在一个位置的证书和证书存储在中央管理存储的所有其他服务器。
  
需要更多详细信息才能充分了解您在使用 Set-CsCertificate cmdlet 并在当前证书到期之前将其用于暂存证书时的选择和要求。 参数是重要的但实质上是单用途-辊。 如果作为参数中定义它，告诉您将提供会影响为-定义证书的有关信息的一组 CsCertificate 类型 （例如 AudioVideoAuthentication 和 OAuthTokenIssuer），证书将成为时-EffectiveDate 所定义的有效性。
  
 **-滚动**:-辊参数是必需的必须与它提供的依赖项。 以下必需参数用于充分定义哪些证书将受影响以及将如何应用这些证书：
  
 **-EffectiveDate**： 参数-EffectiveDate 定义当新证书将成为 co-active 的当前证书。 -EffectiveDate 可以接近当前的证书的到期时间或更长一段时间。 建议使用最小的 EffectiveDate AudioVideoAuthentication 证书是 8 小时，即 AV 边缘服务令牌颁发使用 AudioVideoAuthentication 证书的默认令牌生存期。
  
暂存 OAuthTokenIssuer 证书时，对于证书生效之前的提前期有不同的要求。OAuthTokenIssuer 证书的最短提前时间是当前证书到期前的 24 小时。为实现共存而延长提前期是因为存在依赖于 OAuthTokenIssuer 证书的其他服务器角色（例如 Exchange Server），该证书创建的身份验证和加密密钥材料具有更长的保留时间。
  
 **-Thumbprint**：指纹是证书特有的属性。 参数用于标识的证书将会受到影响，通过设置 CsCertificate cmdlet 的操作-指纹。
  
 **-类型**:-类型参数可以接受一个证书使用类型或逗号分隔的列表的证书用法类型。 证书类型用于向 cmdlet 和服务器确认证书的用途。 例如，类型 AudioVideoAuthentication 是用于通过 A / V 边缘服务和 AV 身份验证服务。 如果你决定同时暂存和设置不同类型的证书，则必须针对这些证书的最短生效提前期，考虑其中所需的最长生效期。 例如，你需要暂存 AudioVideoAuthentication 和 OAuthTokenIssuer 类型的证书。 您最小 EffectiveDate 必须是较大的两个证书，在此情况下 OAuthTokenIssuer，它具有最短提前期的 24 小时。 如果你不想用 24 小时提前期暂存 AudioVideoAuthentication 证书，请使用更符合你的要求的 EffectiveDate 单独暂存它。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>更新或续订一个 A / V 边缘服务证书的横滚和-EffectiveDate 参数

1. 以 Administrators 组成员的身份登录本地计算机。
    
2. 用可导出私钥上一个现有的证书申请更新或新的 AudioVideoAuthentication 证书 / V 边缘服务。
    
3. （如果您已部署的池） 新 AudioVideoAuthentication 证书导入到边缘服务器并在池中的所有其他边缘服务器。
    
4. 配置集 CsCertificate cmdlet 导入的证书，并使用-辊参数用-EffectiveDate 参数。 生效日期应定义为当前证书到期时间（14:00:00 或下午 2:00:00）减去令牌生命周期（默认为八小时）。 这为我们提供了一次，则必须将证书设置为活动状态，并且是-EffectiveDate\<字符串\>:"7/22/2015 6:00:00"。 
    
    > [!IMPORTANT]
    > 对于边缘池，您必须部署和调配的日期和时间的第一个证书部署以避免可能的 A-EffectiveDate 参数定义的所有 AudioVideoAuthentication 证书 / V 由于较早的通信中断证书过期之前已使用新证书续订所有客户和使用者的标记。 
  
    设置 CsCertificate 命令与-横滚和-EffectiveTime 参数：
    
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
    > 必须采用 EffectiveDate 格式以匹配您的服务器的区域设置和语言设置。 本例使用美国英语区域和语言设置 
  
要进一步了解过程，该集 CsCertificate，-辊和-EffectiveDate 使用暂存时仍在使用现有的证书来验证 AudioVideoAuthentication 正在使用的新 AudioVideoAuthentication 令牌颁发一个新证书由使用者，可视时间线是理解过程的有效手段。 在下面的示例中，管理员决定将 A / V 边缘服务证书将在下午 2:00:00 07/22/2015年上过期。 他请求并接收一个新的证书并在他池中将它导入每个边缘服务器。 在凌晨两点 07/22/2015年上，他开始与辊运行 Get CsCertificate，-指纹的新证书的指纹字符串相等和-EffectiveTime 设置为 07/22/2015年 6:00:00 AM。 他每个边缘服务器上运行此命令。
  
![使用 Roll 和 EffectiveDate 参数。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**标注**|**舞台**|
|:-----|:-----|
|1  <br/> |开始时间：2015 年 7 月 22 日上午 12:00:00  <br/> 当前 AudioVideoAuthentication 证书在 2015 年 7 月 22 日下午 2:00:00 到期。这由证书上的过期时间戳决定。规划证书替换和滚动，计入现有证书达到过期时间前的 8 小时重叠期（默认令牌生命周期）。上午 2:00:00 提前时间在本例中用来给管理员留出足够的时间，在上午 6:00:00 生效时间前放置和设置新证书。  <br/> |
|2  <br/> |2015 年 7 月 22 日上午 2:00:00 - 2015 年 7 月 22 日上午 5:59:59  <br/> 在边缘服务器上的证书设置有效时间 6:00:00 AM （4 小时前置重叠时间是对于此示例，但时间要长） 的使用设置 CsCertificate-类型\<证书使用类型\>-指纹\<新证书的指纹\>-回滚-EffectiveDate\<的新证书的有效时间的日期时间字符串\>  <br/> |
|3  <br/> |2015 年 7 月 22 日上午 6:00 - 2015 年 7 月 22 日下午 2:00  <br/> 为了验证令牌，首先尝试新证书，如果新证书未能验证令牌，则尝试旧证书。在 8 小时（默认令牌生命周期）重叠期内，此过程用于所有令牌。  <br/> |
|4  <br/> |结束时间：2015 年 7 月 22 日下午 2:00:01  <br/> 旧证书过期，新证书接替旧证书。 可以使用删除 CsCertificate 安全地删除旧证书-类型\<证书使用类型\>-前面  <br/> |
   
当达到生效时间（2015 年 7 月 22 日上午 6:00:00）时，新证书将颁发所有新令牌。 在验证令牌时，将首先根据新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。 旧证书到期后（2015 年 7 月 22 日下午 2:00:00），将只根据新证书验证令牌。 旧的证书可以被安全地删除使用删除 CsCertificate cmdlet 使用的上一个参数。

```
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>若要更新或续订 OAuthTokenIssuer-横滚和-EffectiveDate 参数与证书

1. 以 Administrators 组成员的身份登录本地计算机。
    
2. 使用前端服务器上的现有证书导出私钥请求续订或新 OAuthTokenIssuer 证书。
    
3. 将证书导入新 OAuthTokenIssuer 在池中前端服务器 （如果已部署的池）。 将全局复制 OAuthTokenIssuer 证书且只需在部署中的任何服务器更新和续订这些证书。 前端服务器用作示例。
    
4. 配置集 CsCertificate cmdlet 导入的证书，并使用-辊参数用-EffectiveDate 参数。 生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去至少 24 个小时。 
    
    设置 CsCertificate 命令与-横滚和-EffectiveTime 参数：
    
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
> 必须采用 EffectiveDate 格式以匹配您的服务器的区域设置和语言设置。 本例使用美国英语区域和语言设置 
  
当到达生效时间（2015 年 7 月 21 日上午 1:00:00）时，新证书将颁发所有新令牌。 在验证令牌时，将首先根据新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。 旧证书到期后（2015 年 7 月 22 日下午 2:00:00），将只根据新证书验证令牌。 旧的证书可以被安全地删除使用删除 CsCertificate cmdlet 使用的上一个参数。
```
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>另请参阅

#### 

[管理服务器的身份验证 (OAuth) 和在 Skype 的业务服务器 2015年的合作伙伴应用程序](server-to-server-and-partner-applications.md)
#### 

[一组 CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[删除 CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)

