---
title: 在Skype for Business Server中使用 -Roll Set-CsCertificate 暂存 AV 和 OAuth 证书
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 摘要：用于Skype for Business Server的阶段 AV 和 OAuth 证书。
ms.openlocfilehash: fda09cb53b664419d9652a0b663c83adc770c5cf
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674604"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>在Skype for Business Server中使用 -Roll Set-CsCertificate 暂存 AV 和 OAuth 证书

**总结：** 用于Skype for Business Server的阶段 AV 和 OAuth 证书。

音频/视频 (A/V) 通信是Skype for Business Server的关键组成部分。 应用程序共享、音频和视频会议等功能依赖于分配给 A/V Edge 服务的证书，特别是 A/V 身份验证服务。

> [!IMPORTANT]
> 此新功能旨在适用于 A/V Edge 服务和 OAuthTokenIssuer 证书。 可以将其他证书类型与 A/V Edge 服务和 OAuth 证书类型一起预配，但不会从 A/V Edge 服务证书的共存行为中获益。

用于管理Skype for Business Server证书的 Skype for Business Server Management Shell PowerShell cmdlet 将 A/V Edge 服务证书称为 AudioVideoAuthentication 证书类型，OAuthServer 证书称为 typeOAuthTokenIssuer。 对于本主题的其余部分，若要唯一标识证书，它们将被同一标识符类型、AudioVideoAuthentication 和OAuthTokenIssuer 引用。

A/V 身份验证服务负责颁发供客户端和其他 A/V 使用者使用的令牌。 这些令牌是根据证书上的属性生成的，当证书到期时，会断开连接并需要用新证书生成的新令牌重新连接。 Skype for Business Server中的新功能将缓解此问题 - 能够在旧证书过期之前暂存新证书，并允许两个证书在一段时间内继续运行。 此功能在 Set-CsCertificate Skype for Business Server Management Shell cmdlet 中使用更新的功能。 具有现有参数 -EffectiveDate 的新参数 -Roll 会将新的 AudioVideoAuthentication 证书放置在证书存储中。 旧 AudioVideoAuthentication 证书仍将保留，以便根据该证书验证颁发的令牌。 随着新 AudioVideoAuthentication 证书的就绪，将发生以下一系列事件：

> [!TIP]
> 使用 Skype for Business Server Management Shell cmdlet 管理证书，可以在 Edge Server 上针对每个用途请求单独和不同的证书。 在Skype for Business Server部署向导中使用证书向导有助于创建证书，但通常是 **默认** 类型，将所有证书用于边缘服务器的证书都与单个证书结合使用。 如果要使用滚动证书功能，建议的做法是将 AudioVideoAuthentication 证书与其他证书用途分离开。 您可以设置和暂存默认类型的证书，但只有已合并证书的 AudioVideoAuthentication 部分将从暂存中受益。 参与 (的用户，例如，在证书过期时) 即时消息会话，需要注销并重新登录，以使用与 Access Edge 服务关联的新证书。 对于使用 Web 会议 Edge 服务参与 Web 会议的用户，也会发生类似的行为。 OAuthTokenIssuer 证书是一种跨所有服务器共享的特定类型证书。 可以在一个位置创建和管理证书，并且证书存储在所有其他服务器的中央管理存储中。

需要更多详细信息才能充分了解您在使用 Set-CsCertificate cmdlet 并在当前证书到期之前将其用于暂存证书时的选择和要求。 -Roll 参数很重要，但实质上是单个用途。 如果将其定义为参数，则告知Set-CsCertificate，当证书将由 -EffectiveDate 有效定义时，你将提供有关将受 -Type (（例如 AudioVideoAuthentication 和 OAuthTokenIssuer) ）定义的证书的信息。

 **-Roll**：-Roll 参数是必需的，并且具有必须随其一起提供的依赖项。 以下必需参数用于充分定义哪些证书将受影响以及将如何应用这些证书：

 **-EffectiveDate**：参数 -EffectiveDate 定义新证书何时与当前证书共用。 -EffectiveDate 可以接近当前证书的过期时间，也可以是较长的时间段。 AudioVideoAuthentication 证书的建议最小 -EffectiveDate 为 8 小时，这是使用 AudioVideoAuthentication 证书颁发的 AV Edge 服务令牌的默认令牌生存期。

暂存 OAuthTokenIssuer 证书时，对于证书生效之前的提前期有不同的要求。OAuthTokenIssuer 证书的最短提前时间是当前证书到期前的 24 小时。为实现共存而延长提前期是因为存在依赖于 OAuthTokenIssuer 证书的其他服务器角色（例如 Exchange Server），该证书创建的身份验证和加密密钥材料具有更长的保留时间。

 **-Thumbprint**：指纹是证书特有的属性。 -Thumbprint 参数用于标识受 Set-CsCertificate cmdlet 操作影响的证书。

 **-Type**：-Type 参数可以接受单个证书使用类型或证书使用类型的逗号分隔列表。 证书类型用于向 cmdlet 和服务器确认证书的用途。 例如，类型 AudioVideoAuthentication 可供 A/V Edge 服务和 AV 身份验证服务使用。 如果您决定同时暂存和设置不同类型的证书，则必须针对这些证书的最短生效提前期，考虑其中所需的最长生效期。 例如，您需要暂存 AudioVideoAuthentication 和 OAuthTokenIssuer 类型的证书。 最小 -EffectiveDate 必须是两个证书中较大的一个，在这种情况下，OAuthTokenIssuer 的最小提前时间为 24 小时。 如果您不想用 24 小时提前期暂存 AudioVideoAuthentication 证书，请使用更符合您的要求的 EffectiveDate 单独暂存它。

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 -Roll 和 -EffectiveDate 参数更新或续订 A/V Edge 服务证书

1. 以管理员组成员身份登录到本地计算机。

2. 请求续订或使用 A/V Edge 服务上现有证书的可导出私钥的新 AudioVideoAuthentication 证书。

3. 如果已部署池) ，请将新的 AudioVideoAuthentication 证书导入到边缘服务器和池中所有其他边缘服务器 (。

4. 使用 Set-CsCertificate cmdlet 配置导入的证书，并将 -Roll 参数与 -EffectiveDate 参数配合使用。 生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去令牌生命周期（默认为八小时）。 这给我们一个时间，证书必须设置为活动，是 -EffectiveDate \<string\>：“7/22/2015 6：00：00 AM”。

   > [!IMPORTANT]
   > 对于 Edge 池，必须在部署第一个证书的 -EffectiveDate 参数定义的日期和时间之前部署和预配所有 AudioVideoAuthentication 证书，以避免由于旧证书过期而导致的 A/V 通信中断，然后才使用新证书续订所有客户端和使用者令牌。

   具有 -Roll 和 -EffectiveTime 参数的Set-CsCertificate命令：

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
   ```

   Set-CsCertificate 命令示例：

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015 6:00:00 AM"
   ```

    > [!IMPORTANT]
    > 必须设置 EffectiveDate 格式才能匹配服务器的区域和语言设置。 本例使用美国英语区域和语言设置

为了进一步了解 Set-CsCertificate、-Roll 和 -EffectiveDate 用于暂存新证书以颁发新的 AudioVideoAuthentication 令牌，同时仍然使用现有证书来验证使用者正在使用的 AudioVideoAuthentication 的过程，可视化时间线是了解该过程的有效方法。 在以下示例中，管理员确定 A/V Edge 服务证书将于 2015 年 7 月 22 日下午 2：00：00 过期。 他请求并接收新证书，并将其导入到池中的每个 Edge Server。 2015 年 7 月 22 日凌晨 2 点，他开始运行Get-CsCertificate-Roll，-Thumbprint 等于新证书的指纹字符串，-EffectiveTime 设置为 2015 年 7 月 22 日上午 6：00：00。 他在每个 Edge Server 上运行此命令。

![使用 Roll 和 EffectiveDate 参数。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)

|标注|阶段|
|:-----|:-----|
|1|"开始"菜单：2015/7/22 上午 12：00：00  <br/> 当前 AudioVideoAuthentication 证书将于 2015 年 7 月 22 日下午 2：00：00 过期。 这由证书上的过期时间戳决定。 在现有证书到达过期时间之前， (默认令牌生存期) 计划证书替换和滚动更新，以考虑 8 小时重叠。 本示例使用凌晨 2：00：00 的提前时间，以便管理员有足够的时间在早上 6：00：00 生效时间之前放置和预配新证书。|
|2|7/22/2015 2：00：00 AM - 7/22/2015 5：59：59 AM  <br/> 在边缘服务器上设置证书的有效时间为上午 6：00：00 (4 小时的提前时间适用于本示例，但使用 Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate 可以更长) \<datetime string of the effective time for new certificate\>|
|3|2015/7/22 上午 6：00 - 7/22/2015 下午 2：00  <br/> 若要验证令牌，首先尝试新证书，如果新证书无法验证令牌，则会尝试使用旧证书。 此过程用于 8 小时 (默认令牌生存期) 重叠期间的所有令牌。|
|4|结束：2015/7/22 下午 2：00：01  <br/> 旧证书已过期，新证书已接管。 可使用 Remove-CsCertificate -Type \<certificate usage type\> -Previous 安全删除旧证书|

当有效时间 (2015/7/22 6：00：00 AM) 时，所有新令牌均由新证书颁发。 在验证令牌时，将首先根据新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。 旧证书 (2015/7/22 下午 2：00：00) 过期后，令牌将仅由新证书验证。 可以使用包含 -Previous 参数的Remove-CsCertificate cmdlet 安全删除旧证书。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 -Roll 和 -EffectiveDate 参数更新或续订 OAuthTokenIssuer 证书

1. 以管理员组成员身份登录到本地计算机。

2. 为前端服务器上的现有证书请求具有可导出私钥的续订或新的 OAuthTokenIssuer 证书。

3. 将新的 OAuthTokenIssuer 证书导入池中的前端服务器 (如果已部署池) 。 将全局复制 OAuthTokenIssuer 证书且只需在部署中的任何服务器更新和续订这些证书。 前端服务器用作示例。

4. 使用 Set-CsCertificate cmdlet 配置导入的证书，并将 -Roll 参数与 -EffectiveDate 参数配合使用。 生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去至少 24 个小时。

    具有 -Roll 和 -EffectiveTime 参数的Set-CsCertificate命令：

   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumbprint of new certificate> -Roll -EffectiveDate <date and time for certificate to become active> -identity Global
   ```

Set-CsCertificate 命令示例：

  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015 1:00:00 PM"
  ```

> [!IMPORTANT]
> 必须设置 EffectiveDate 格式才能匹配服务器的区域和语言设置。 本例使用美国英语区域和语言设置

当有效时间 (2015/7/21 凌晨 1：00：00) 时，所有新令牌均由新证书颁发。 在验证令牌时，将首先根据新证书验证令牌。 如果验证失败，将尝试旧证书。 尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。 旧证书 (2015/7/22 下午 2：00：00) 过期后，令牌将仅由新证书验证。 可以使用包含 -Previous 参数的Remove-CsCertificate cmdlet 安全删除旧证书。

```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous
```

## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中管理服务器到服务器的身份验证 (OAuth) 和合作伙伴应用程序](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate)

[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate)
