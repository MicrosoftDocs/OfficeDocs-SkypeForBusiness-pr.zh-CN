---
title: 在 Set-CsCertificate 中使用滚动分期 AV 和 OAuth 证书
TOCTitle: 在 Set-CsCertificate 中使用滚动分期 AV 和 OAuth 证书
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49888334
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Set-CsCertificate 中使用滚动分期 AV 和 OAuth 证书

 

_**上一次修改主题：** 2012-11-13_

音频/视频 (A/V) 通信是 Microsoft Lync Server 2013 的重要组成部分。诸如应用程序共享以及音频和视频会议之类的功能都依赖于分配给 A/V 边缘服务（具体说就是 A/V 身份验证服务）的证书。

> [!IMPORTANT]  
> <ol>
> <li><p>这一新功能设计用于 A/V 边缘服务和 <em>OAuthTokenIssuer</em> 证书。其他证书类型可与 A/V 边缘服务和 OAuth 证书类型一起设置，但不会从 A/V 边缘服务证书将具有的共存行为中获益。</p></li>
> <li><p>用于管理 Microsoft Lync Server 2013 证书的 Lync Server 命令行管理程序 PowerShell cmdlet 将 A/V 边缘服务证书称为 <em>AudioVideoAuthentication</em> 证书类型，将 OAuthServer 证书称为 <em>OAuthTokenIssuer</em> 类型。在本主题的其余部分，为了唯一地标识这些证书，将按同一标识符类型 <em>AudioVideoAuthentication</em> 和 <em>OAuthTokenIssuer</em> 引用这些证书。</p></li>
> </ol>

A/V 身份验证服务负责颁发供客户端和其他 A/V 使用者使用的令牌。这些令牌是根据证书上的属性生成的，当证书到期时，会断开连接并需要用新证书生成的新令牌重新连接。Lync Server 2013 中的一项新功能可缓解此问题，通过此功能，可以在旧证书到期之前暂存新证书并允许这两个证书在一段时间内继续发挥作用。此功能使用 Set-CsCertificate Lync Server 命令行管理程序 cmdlet 中更新的功能。新参数 –Roll 以及现有参数 –EffectiveDate 会将新 AudioVideoAuthentication 证书置于证书存储中。旧 AudioVideoAuthentication 证书仍将保留，以便根据该证书验证颁发的令牌。随着新 AudioVideoAuthentication 证书的就绪，将发生以下一系列事件：

> [!TIP]
> 通过使用 Lync Server 命令行管理程序 cmdlet 管理证书，您可以请求彼此独立、截然不同的证书，以满足边缘服务器上的各种需要。使用 Lync Server 部署向导中的证书向导可帮助您创建证书，但此类证书通常为<strong>默认</strong>类型，可将要在边缘服务器中使用的所有证书组合为一个证书。如果要使用滚动证书功能，建议的做法是将 AudioVideoAuthentication 证书与其他证书用途分离开。您可以设置和暂存默认类型的证书，但只有已合并证书的 AudioVideoAuthentication 部分将从暂存中受益。证书到期时参与即时消息会话等活动的用户将需要注销并重新登录，才能使用与访问边缘服务关联的新证书。对于使用 Web 会议边缘服务参与 Web 会议的用户，也会出现类似行为。OAuthTokenIssuer 证书是一种跨所有服务器共享的特定类型证书。您在一个位置创建和管理该证书后，它将存储在所有其他服务器的中央管理存储中。


需要更多详细信息才能充分了解您在使用 Set-CsCertificate cmdlet 并在当前证书到期之前将其用于暂存证书时的选择和要求。–Roll 参数很重要，但基本上只能满足一种用途。如果将其定义为参数，将会指示 Set-CsCertificate，您将在由 –Type（例如 AudioVideoAuthentication 和 OAuthTokenIssuer）定义并且将会受到影响的证书生效时，提供有关该证书的信息，证书生效时间将由 –EffectiveDate 定义。

**-Roll：**–Roll 参数是必需的，并且具有必须随其提供的依赖项。以下必需参数用于充分定义哪些证书将受影响以及将如何应用这些证书：

**-EffectiveDate：**–EffectiveDate 参数定义新证书何时与当前证书共同发挥作用。–EffectiveDate 可以接近当前证书的到期时间，也可以具有更长的时间段。建议的 AudioVideoAuthentication 证书的最短 –EffectiveDate 为 8 小时，这是使用 AudioVideoAuthentication 证书颁发的 AV 边缘服务令牌的默认令牌生命周期。

暂存 OAuthTokenIssuer 证书时，对于证书生效之前的提前期有不同的要求。OAuthTokenIssuer 证书的最短提前时间是当前证书到期前的 24 小时。为实现共存而延长提前期是因为存在依赖于 OAuthTokenIssuer 证书的其他服务器角色（例如 Exchange Server），该证书创建的身份验证和加密密钥材料具有更长的保留时间。

**-Thumbprint：**指纹是证书特有的属性。–Thumbprint 参数用于标识将受 Set-CsCertificate cmdlet 操作影响的证书。

**-Type：**–Type 参数可接受单个证书使用类型或证书使用类型的逗号分隔列表。证书类型用于向 cmdlet 和服务器确认证书的用途。例如，AudioVideoAuthentication 类型供 A/V 边缘服务和 AV 身份验证服务使用。如果您决定同时暂存和设置不同类型的证书，则必须针对这些证书的最短生效提前期，考虑其中所需的最长生效期。例如，您需要暂存 AudioVideoAuthentication 和 OAuthTokenIssuer 类型的证书。则最短 –EffectiveDate 必须是两个证书中的较大者，本例中为 OAuthTokenIssuer，其最短提前期为 24 小时。如果您不想用 24 小时提前期暂存 AudioVideoAuthentication 证书，请使用更符合您的要求的 EffectiveDate 单独暂存它。

## 使用 –Roll 和 -EffectiveDate 参数更新或续订 A/V 边缘服务证书

1.  以 Administrators 组成员的身份登录本地计算机。

2.  使用 A/V 边缘服务上现有证书的可导出私钥请求续订或新 OAuthTokenIssuer 证书。

3.  将新的 AudioVideoAuthentication 证书导入边缘服务器和您的池中的所有其他边缘服务器（如果您部署了一个池）。

4.  使用 Set-CsCertificate cmdlet 配置导入的证书并结合使用 –Roll 参数和 –EffectiveDate 参数。生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去令牌生命周期（默认为八小时）。这样就得出了必须将证书设置为活动状态的时间，即 –EffectiveDate \<字符串\> “7/22/2012 6:00:00 AM”。
    
    > [!IMPORTANT]
    > 对于边缘池，您必须依照部署的第一个证书的 –EffectiveDate 参数定义的日期和时间部署和设置所有 AudioVideoAuthentication 证书，以避免由于旧证书在使用新证书续订所有客户端和使用者令牌之前到期而可能出现的 A/V 通信中断。
    
    带 –Roll 和 –EffectiveTime 参数的 Set-CsCertificate 命令：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate 命令示例：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    > [!IMPORTANT]
    > 必须设置 EffectiveDate 的格式以匹配您的服务器的区域和语言设置。本例使用美国英语区域和语言设置


为进一步了解如何使用 Set-CsCertificate、-Roll 和 –EffectiveDate 暂存新证书，以便在仍使用现有证书验证使用者使用的 AudioVideoAuthentication 时颁发新 AudioVideoAuthentication 令牌，可通过直观的日程表充分了解此过程。

在下面的示例中，管理员确定 A/V 边缘服务证书将于 07/22/2012 2:00:00 PM 到期。他请求和接收新证书并将其导入池中的每个边缘服务器。在 07/22/2012 2 AM，他开始运行带 –Roll 的 Get-CsCertificate，使 -Thumbprint 等于新证书的指纹字符串，并将 –EffectiveTime 设置为 07/22/2012 6:00:00 AM。他在每个边缘服务器上运行此命令。

![使用 Roll 和 EffectiveDate 参数。](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "使用 Roll 和 EffectiveDate 参数。")

当到达生效时间 (7/22/2012 6:00:00 AM) 时，新证书将颁发所有新令牌。在验证令牌时，将首先根据新证书验证令牌。如果验证失败，将尝试旧证书。尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。旧证书到期后 (7/22/2012 2:00:00 PM)，将只根据新证书验证令牌。可以使用带 –Previous 参数的 Remove-CsCertificate cmdlet 安全地删除旧证书。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

## 使用 –Roll 和 -EffectiveDate 参数更新或续订 OAuthTokenIssuer 证书

1.  以 Administrators 组成员的身份登录本地计算机。

2.  使用 A/V 边缘服务上的现有证书的可导出私钥请求续订或新 OAuthTokenIssuer 证书

3.  将新的 OAuthTokenIssuer 证书导入池中的前端服务器（如果您部署了一个池）。将全局复制 OAuthTokenIssuer 证书且只需在部署中的任何服务器更新和续订这些证书。前端服务器只是用作示例。

4.  使用 Set-CsCertificate cmdlet 配置导入的证书并结合使用 –Roll 参数和 –EffectiveDate 参数。生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去至少 24 个小时。
    
    带 –Roll 和 –EffectiveTime 参数的 Set-CsCertificate 命令：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate 命令示例：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    > [!IMPORTANT]
    > 必须设置 EffectiveDate 的格式以匹配您的服务器的区域和语言设置。本例使用美国英语区域和语言设置


当到达生效时间 (7/21/2012 1:00:00 AM) 时，将由新证书颁发所有新令牌。在验证令牌时，将首先根据新证书验证令牌。如果验证失败，将尝试旧证书。尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。旧证书到期后 (7/22/2012 2:00:00 PM)，将只根据新证书验证令牌。可以使用带 –Previous 参数的 Remove-CsCertificate cmdlet 安全地删除旧证书。

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

## 另请参阅

#### 概念

[在 Lync Server 2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)  
[在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  

#### 其他资源

[为 Lync Server 2013 设置边缘证书](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  
[Remove-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCertificate)

