---
title: 在 CsCertificate 中使用-滚将 AV 和 OAuth 证书暂存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4acdf759181dee3df872c7803ec595c63fb07016
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>在 CsCertificate 中使用-滚在 Lync Server 2013 中暂存 AV 和 OAuth 证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-13_

音频/视频 (A/V) 通信是 Microsoft Lync Server 2013 的关键组件。 应用程序共享和音频和视频会议等功能依赖于分配给 A/V 边缘服务的证书, 特别是 A/V 身份验证服务。

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>此新功能旨在适用于 A/V 边缘服务和<EM>OAuthTokenIssuer</EM>证书。 其他证书类型可以与 A/V 边缘服务和 OAuth 证书类型一起设置, 但不会受益于 A/V 边缘服务证书将使用的共存行为。</P>
> <LI>
> <P>用于管理 Microsoft Lync Server 2013 证书的 Lync Server Management Shell PowerShell cmdlet 将 A/V 边缘服务证书引用为<EM>AudioVideoAuthentication</EM>证书类型, 将 OAuthServer 证书用作类型<EM>OAuthTokenIssuer</EM>。 在本主题的其余部分，为了唯一地标识这些证书，将按同样的标识符类型 <EM>AudioVideoAuthentication</EM> 和 <EM>OAuthTokenIssuer</EM> 引用这些证书。</P></LI></OL>



</div>

A/V 身份验证服务负责颁发供客户端和其他 A/V 使用者使用的令牌。 这些令牌是根据证书上的属性生成的，当证书到期时，会断开连接并需要用新证书生成的新令牌重新连接。 Lync Server 2013 中的一项新功能将缓解此问题, 即在旧证书即将过期并允许两个证书在一段时间内继续运行的功能。 此功能使用 CsCertificate Lync Server Management Shell cmdlet 中的更新功能。 新参数 –Roll 以及现有参数 –EffectiveDate 会将新 AudioVideoAuthentication 证书置于证书存储中。 旧 AudioVideoAuthentication 证书仍将保留，以便根据该证书验证颁发的令牌。 随着新 AudioVideoAuthentication 证书的就绪，将发生以下一系列事件：

<div>


> [!TIP]
> 使用 Lync Server Management Shell cmdlet 管理证书, 你可以为边缘服务器上的每个用途请求单独和不同的证书。 在 Lync Server 部署向导中使用 "证书" 向导可帮助你创建证书, 但通常是<STRONG>默认</STRONG>类型, 它会将边缘服务器的所有证书使用集中到单个证书。 如果要使用滚动证书功能，建议的做法是将 AudioVideoAuthentication 证书与其他证书用途分离开。 您可以设置和暂存默认类型的证书，但只有已合并证书的 AudioVideoAuthentication 部分将从暂存中受益。 当证书过期时, 参与即时消息对话的用户需要注销, 然后重新登录以使用与访问边缘服务关联的新证书。 对于使用 Web 会议边缘服务的 Web 会议中涉及的用户, 将出现类似行为。 OAuthTokenIssuer 证书是一种跨所有服务器共享的特定类型证书。 您在一个位置创建和管理证书, 并且证书存储在所有其他服务器的中央管理存储中。



</div>

需要更多详细信息才能充分了解您在使用 Set-CsCertificate cmdlet 并在当前证书到期之前将其用于暂存证书时的选择和要求。–Roll 参数很重要，但基本上只能满足一种用途。如果将其定义为参数，将会指示 Set-CsCertificate，您将在由 –Type（例如 AudioVideoAuthentication 和 OAuthTokenIssuer）定义并且将会受到影响的证书生效时，提供有关该证书的信息，证书生效时间将由 –EffectiveDate 定义。

**-滚动:**-滚参数是必需的, 并且具有必须随其一起提供的依赖项。 以下必需参数用于充分定义哪些证书将受影响以及将如何应用这些证书：

**-EffectiveDate:** 参数-EffectiveDate 定义新证书与当前证书之间的活动状态。 -EffectiveDate 可以接近当前证书的到期时间，也可以具有更长的时间段。 建议的 AudioVideoAuthentication 证书的最短 –EffectiveDate 为 8 小时，这是使用 AudioVideoAuthentication 证书颁发的 AV 边缘服务令牌的默认令牌生命周期。

暂存 OAuthTokenIssuer 证书时，对于证书生效之前的提前期有不同的要求。OAuthTokenIssuer 证书的最短提前时间是当前证书到期前的 24 小时。为实现共存而延长提前期是因为存在依赖于 OAuthTokenIssuer 证书的其他服务器角色（例如 Exchange Server），该证书创建的身份验证和加密密钥材料具有更长的保留时间。

**-指纹:** 指纹是证书上的唯一证书的属性。 -Thumbprint 参数用于标识将受 Set-CsCertificate cmdlet 操作影响的证书。

**-类型:**– Type 参数可以接受单个证书使用类型或证书使用类型的逗号分隔列表。 证书类型用于向 cmdlet 和服务器确认证书的用途。 例如, 键入 AudioVideoAuthentication 供 A/V 边缘服务和 AV 身份验证服务使用。 如果你决定同时暂存和设置不同类型的证书，则必须针对这些证书的最短生效提前期，考虑其中所需的最长生效期。 例如，你需要暂存 AudioVideoAuthentication 和 OAuthTokenIssuer 类型的证书。 则最短 -EffectiveDate 必须是两个证书中的较大者，本例中为 OAuthTokenIssuer，其最短提前期为 24 小时。 如果你不想用 24 小时提前期暂存 AudioVideoAuthentication 证书，请使用更符合你的要求的 EffectiveDate 单独暂存它。

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>使用-滚和-EffectiveDate 参数更新或续订 A/V 边缘服务证书

1.  以 Administrators 组成员的身份登录本地计算机。

2.  向 A/V 边缘服务上的现有证书的可导出私钥请求续订或新的 AudioVideoAuthentication 证书。

3.  将新的 AudioVideoAuthentication 证书导入到边缘服务器以及你的池中的所有其他边缘服务器 (如果已部署池)。

4.  使用 Set-CsCertificate cmdlet 配置导入的证书并结合使用 -Roll 参数和 -EffectiveDate 参数。 生效日期应定义为当前证书到期时间（14:00:00 或下午 2:00:00）减去令牌生命周期（默认为八小时）。 这为我们提供了一个证书必须设置为活动的时间, 并且是– EffectiveDate \<字符串\>: "7/22/2012 6:00:00 AM"。
    
    <div>
    

    > [!IMPORTANT]
    > 对于边缘池, 你必须使用部署的第一个证书的-EffectiveDate 参数定义的日期和时间部署和预配所有 AudioVideoAuthentication 证书, 以避免可能的 A/V 通信中断 (由于较旧)在使用新证书续订所有客户端和消费者令牌之前, 证书即将到期。

    
    </div>
    
    带 -Roll 和 -EffectiveTime 参数的 Set-CsCertificate 命令：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate 命令示例：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > 必须设置 EffectiveDate 的格式以匹配您的服务器的区域和语言设置。本例使用美国英语区域和语言设置

    
    </div>

为进一步了解如何使用 Set-CsCertificate、-Roll 和 -EffectiveDate 暂存新证书，以便在仍使用现有证书验证使用者使用的 AudioVideoAuthentication 时颁发新 AudioVideoAuthentication 令牌，可通过直观的日程表充分了解此过程。

在以下示例中, 管理员确定 A/V 边缘服务证书的到期日期为 2:00:00 PM 的07/22/2012。 他请求并接收新证书, 并将其导入到池中的每个边缘服务器。 在 07/22/2012 AM, 他开始运行带 CsCertificate 的 EffectiveTime,-Thumbprint 等于新证书的指纹字符串, 并且-设置为 07/22/2012 6:00:00 AM。 他在每台边缘服务器上运行此命令。

![使用滚和 EffectiveDate 参数。](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "使用滚和 EffectiveDate 参数。")

当达到有效时间 (7/22/2012 6:00:00 AM) 时, 所有新令牌均由新证书发出。 验证令牌时, 将首先对照新证书验证令牌。 如果验证失败, 将尝试旧证书。 尝试新的和回退到旧证书的过程将继续, 直到旧证书的到期时间。 一旦旧证书已过期 (7/22/2012 2:00:00 PM), 令牌将仅由新证书验证。 使用 CsCertificate cmdlet 和-Previous 参数, 可以安全地删除旧证书。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>使用-滚和-EffectiveDate 参数更新或续订 OAuthTokenIssuer 证书

1.  以 Administrators 组成员的身份登录本地计算机。

2.  向 A/V 边缘服务上的现有证书的可导出私钥请求续订或新的 OAuthTokenIssuer 证书。

3.  将新的 OAuthTokenIssuer 证书导入到你的池中的前端服务器 (如果已部署池)。 OAuthTokenIssuer 证书是全局复制的, 并且仅需要在部署中的任何服务器上更新和续订。 前端服务器用作示例。

4.  使用 Set-CsCertificate cmdlet 配置导入的证书并结合使用 -Roll 参数和 -EffectiveDate 参数。 有效日期应定义为当前证书过期时间 (14:00:00, 即 2:00:00 PM) 减去至少24小时。
    
    带 -Roll 和 -EffectiveTime 参数的 Set-CsCertificate 命令：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate 命令示例：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > 必须设置 EffectiveDate 的格式以匹配您的服务器的区域和语言设置。本例使用美国英语区域和语言设置

    
    </div>

当达到有效时间 (7/21/2012 1:00:00 AM) 时, 所有新令牌均由新证书发出。 验证令牌时, 将首先对照新证书验证令牌。 如果验证失败, 将尝试旧证书。 尝试新的和回退到旧证书的过程将继续, 直到旧证书的到期时间。 一旦旧证书已过期 (7/22/2012 2:00:00 PM), 令牌将仅由新证书验证。 使用 CsCertificate cmdlet 和-Previous 参数, 可以安全地删除旧证书。

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)  
[在 Lync Server 2013 中管理服务器到服务器的身份验证 (OAuth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[为 Lync Server 2013 设置边缘证书](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

