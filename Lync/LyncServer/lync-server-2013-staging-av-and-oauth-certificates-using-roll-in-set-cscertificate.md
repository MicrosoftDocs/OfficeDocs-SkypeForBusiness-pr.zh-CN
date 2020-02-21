---
title: 在 Set-cscertificate 中使用-中间暂存 AV 和 OAuth 证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee572bbf115d1e83476194b0e5c92859886da42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>使用-Set-cscertificate 中的 Lync Server 2013 暂存 AV 和 OAuth 证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-13_

音频/视频（A/V）通信是 Microsoft Lync Server 2013 的关键组件。 应用程序共享和音频和视频会议等功能依赖于为 A/V 边缘服务分配的证书，特别是 A/V 身份验证服务。

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>此新功能旨在适用于 A/V 边缘服务和<EM>OAuthTokenIssuer</EM>证书。 其他证书类型可以与 A/V 边缘服务和 OAuth 证书类型一起设置，但不会从 A/V 边缘服务证书将受益的共存行为中受益。</P>
> <LI>
> <P>用于管理 Microsoft Lync Server 2013 证书的 Lync Server 命令行管理程序 PowerShell cmdlet 是指 A/V 边缘服务证书作为<EM>AudioVideoAuthentication</EM>证书类型，将 OAuthServer 证书称为类型<EM>OAuthTokenIssuer</EM>。 在本主题的其余部分中，若要唯一标识证书，它们将通过相同的标识符类型<EM>AudioVideoAuthentication</EM>和<EM>OAuthTokenIssuer</EM>引用。</P></LI></OL>



</div>

A/V 身份验证服务负责颁发供客户端和其他 A/V 使用者使用的令牌。 这些令牌是根据证书上的属性生成的，当证书到期时，会断开连接并需要用新证书生成的新令牌重新连接。 Lync Server 2013 中的一项新功能将缓解此问题–在旧证书即将过期并允许证书在一段时间内继续运行的功能。 此功能使用 Set-cscertificate Lync Server 命令行管理程序 cmdlet 中的更新功能。 新参数 –Roll 以及现有参数 –EffectiveDate 会将新 AudioVideoAuthentication 证书置于证书存储中。 旧 AudioVideoAuthentication 证书仍将保留，以便根据该证书验证颁发的令牌。 随着新 AudioVideoAuthentication 证书的就绪，将发生以下一系列事件：

<div>


> [!TIP]
> 使用 Lync Server 命令行管理程序 cmdlet 管理证书，可以为边缘服务器上的每个用途请求单独和不同的证书。 使用 Lync Server 部署向导中的 "证书向导" 可帮助您创建证书，但通常会将边缘服务器的所有证书使用的<STRONG>默认</STRONG>类型集中到一个证书上。 如果要使用滚动证书功能，建议的做法是将 AudioVideoAuthentication 证书与其他证书用途分离开。 您可以设置和暂存默认类型的证书，但只有已合并证书的 AudioVideoAuthentication 部分将从暂存中受益。 在证书过期时，参与（例如）即时消息对话的用户需要注销，然后重新登录以使用与访问边缘服务关联的新证书。 对于使用 Web 会议边缘服务的 Web 会议中涉及的用户，将发生类似的行为。 OAuthTokenIssuer 证书是一种跨所有服务器共享的特定类型证书。 您可以在一个位置创建和管理证书，并将证书存储在所有其他服务器的中央管理存储中。



</div>

需要更多详细信息才能充分了解您在使用 Set-CsCertificate cmdlet 并在当前证书到期之前将其用于暂存证书时的选择和要求。 –Roll 参数很重要，但基本上只能满足一种用途。 如果将其定义为参数，则表明您要向 Set-cscertificate 提供有关受– Type （例如 AudioVideoAuthentication 和 OAuthTokenIssuer）定义的证书的信息，当证书将变为时。有效的-EffectiveDate 定义。

**-滚动：**–汇总参数是必需的，并且具有必须与它一起提供的依赖项。 以下必需参数用于充分定义哪些证书将受影响以及将如何应用这些证书：

**-EffectiveDate：** 参数– EffectiveDate 定义新证书何时与当前证书共同生效。 –EffectiveDate 可以接近当前证书的到期时间，也可以具有更长的时间段。 建议的 AudioVideoAuthentication 证书的最短 –EffectiveDate 为 8 小时，这是使用 AudioVideoAuthentication 证书颁发的 AV 边缘服务令牌的默认令牌生命周期。

暂存 OAuthTokenIssuer 证书时，对于证书生效之前的提前期有不同的要求。OAuthTokenIssuer 证书的最短提前时间是当前证书到期前的 24 小时。为实现共存而延长提前期是因为存在依赖于 OAuthTokenIssuer 证书的其他服务器角色（例如 Exchange Server），该证书创建的身份验证和加密密钥材料具有更长的保留时间。

**-指纹：** 指纹是证书上唯一的证书属性。 –Thumbprint 参数用于标识将受 Set-CsCertificate cmdlet 操作影响的证书。

**-类型：**– Type 参数可以接受单个证书使用类型或以逗号分隔的证书使用类型列表。 证书类型用于向 cmdlet 和服务器确认证书的用途。 例如，键入 AudioVideoAuthentication 可供 A/V 边缘服务和 AV 身份验证服务使用。 如果您决定同时暂存和设置不同类型的证书，则必须针对这些证书的最短生效提前期，考虑其中所需的最长生效期。 例如，您需要暂存 AudioVideoAuthentication 和 OAuthTokenIssuer 类型的证书。 则最短 –EffectiveDate 必须是两个证书中的较大者，本例中为 OAuthTokenIssuer，其最短提前期为 24 小时。 如果您不想用 24 小时提前期暂存 AudioVideoAuthentication 证书，请使用更符合您的要求的 EffectiveDate 单独暂存它。

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>使用-滚和-EffectiveDate 参数更新或续订 A/V 边缘服务证书

1.  以 Administrators 组成员的身份登录到本地计算机。

2.  使用 A/V 边缘服务上的现有证书的可导出私钥请求续订或新 AudioVideoAuthentication 证书。

3.  将新的 AudioVideoAuthentication 证书导入到边缘服务器和池中的所有其他边缘服务器（如果部署了池）。

4.  使用 Set-CsCertificate cmdlet 配置导入的证书并结合使用 –Roll 参数和 –EffectiveDate 参数。 生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去令牌生命周期（默认为八小时）。 这为我们提供了一段时间，即证书必须设置为 "活动"，并且\<是\>– EffectiveDate 字符串： "7/22/2012 6:00:00 AM"。
    
    <div>
    

    > [!IMPORTANT]
    > 对于边缘池，必须使用部署的首个证书的– EffectiveDate 参数定义的日期和时间部署和预配所有 AudioVideoAuthentication 证书，以避免由于旧证书即将到期而使用新证书续订所有客户端和消费者令牌而导致的可能的 A/V 通信中断。

    
    </div>
    
    带 –Roll 和 –EffectiveTime 参数的 Set-CsCertificate 命令：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate 命令示例：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > 必须设置 EffectiveDate 的格式以匹配您的服务器的区域和语言设置。本例使用美国英语区域和语言设置

    
    </div>

为进一步了解如何使用 Set-CsCertificate、-Roll 和 –EffectiveDate 暂存新证书，以便在仍使用现有证书验证使用者使用的 AudioVideoAuthentication 时颁发新 AudioVideoAuthentication 令牌，可通过直观的日程表充分了解此过程。

在下面的示例中，管理员确定 A/V 边缘服务证书是在07/22/2012 时的 2:00:00 PM 到期。 他请求并接收新证书，并将其导入到池中的每台边缘服务器。 在 07/22/2012 2 AM，他开始运行带 –Roll 的 Get-CsCertificate，使 -Thumbprint 等于新证书的指纹字符串，并将 –EffectiveTime 设置为 07/22/2012 6:00:00 AM。 他在每台边缘服务器上运行此命令。

![使用滚动和 EffectiveDate 参数。](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "使用滚动和 EffectiveDate 参数。")

当到达生效时间 (7/22/2012 6:00:00 AM) 时，新证书将颁发所有新令牌。在验证令牌时，将首先根据新证书验证令牌。如果验证失败，将尝试旧证书。尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。旧证书到期后 (7/22/2012 2:00:00 PM)，将只根据新证书验证令牌。可以使用带 –Previous 参数的 Remove-CsCertificate cmdlet 安全地删除旧证书。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>使用 –Roll 和 -EffectiveDate 参数更新或续订 OAuthTokenIssuer 证书

1.  以 Administrators 组成员的身份登录到本地计算机。

2.  使用 A/V 边缘服务上的现有证书的可导出私钥请求续订或新 OAuthTokenIssuer 证书。

3.  将新的 OAuthTokenIssuer 证书导入到池中的前端服务器（如果已部署池）。 将全局复制 OAuthTokenIssuer 证书且只需在部署中的任何服务器更新和续订这些证书。 前端服务器可用作示例。

4.  使用 Set-CsCertificate cmdlet 配置导入的证书并结合使用 –Roll 参数和 –EffectiveDate 参数。生效日期应定义为当前证书到期时间（14:00:00 或 2:00:00 PM）减去至少 24 个小时。
    
    带 –Roll 和 –EffectiveTime 参数的 Set-CsCertificate 命令：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate 命令示例：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > 必须设置 EffectiveDate 的格式以匹配您的服务器的区域和语言设置。本例使用美国英语区域和语言设置

    
    </div>

当到达生效时间 (7/21/2012 1:00:00 AM) 时，将由新证书颁发所有新令牌。在验证令牌时，将首先根据新证书验证令牌。如果验证失败，将尝试旧证书。尝试新证书并回到旧证书的过程将一直继续下去，直到到达旧证书的到期时间。旧证书到期后 (7/22/2012 2:00:00 PM)，将只根据新证书验证令牌。可以使用带 –Previous 参数的 Remove-CsCertificate cmdlet 安全地删除旧证书。

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)  
[在 Lync Server 2013 中管理服务器到服务器的身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[为 Lync Server 2013 设置边缘证书](lync-server-2013-set-up-edge-certificates.md)  
[Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[Set-cscertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

