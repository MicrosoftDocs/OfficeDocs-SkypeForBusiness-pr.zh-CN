---
title: Lync Server 2013：静态路由 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a5c5dcefa5c4650c6bbfabf940840f22fc5df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的静态路由 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-20_

使用静态路由，管理员可以预先确定 SIP 消息所占用的网络路由。 当服务器收到邮件时，服务器会检查邮件地址，然后将该邮件转发到由管理员预配置的下一个跃点服务器。 如果配置正确，静态路由将有助于确保及时、准确地传送消息，并在服务器上消耗最少的开销。

<div>

## <a name="static-routing-cmdlets"></a>静态路由 Cmdlet

除非 Microsoft 支持人员另有说明，否则应使用[CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15)) cmdlet 创建为 Microsoft Lync Server 2013 配置的静态路由。 创建路由后，你可以使用 CsStaticRoutingConfiguration cmdlet 将该路由添加到静态路由集合。

**静态路由**

  - <span></span>  
    [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))

  - <span></span>  
    [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))

  - <span></span>  
    [新-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))

  - <span></span>  
    [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))

  - <span></span>  
    [Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

