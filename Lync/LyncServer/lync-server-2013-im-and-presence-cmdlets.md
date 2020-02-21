---
title: Lync Server 2013： IM 和状态 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a39f195bf6424f76a98e2b5c25dc4bf21942911
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的 IM 和状态 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-26_

即时消息（IM）和状态 cmdlet 允许您通过 Windows PowerShell 管理这些客户端功能。 可以在 global、site 或每用户作用域设置应用于用户的状态策略。 还可以配置各种隐私和 IM 功能。

<div>

## <a name="im-and-presence-cmdlets"></a>IM 和状态 Cmdlet

要配置 IM 和状态，请使用以下 cmdlet：

  - <span></span>  
    [CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - <span></span>  
    [Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - <span></span>  
    [新 CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - <span></span>  
    [CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - <span></span>  
    [CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [新 CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - <span></span>  
    [新 CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - <span></span>  
    [CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - <span></span>  
    [CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - <span></span>  
    [新 CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - <span></span>  
    [CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - <span></span>  
    [CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - <span></span>  
    [新 CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - <span></span>  
    [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - <span></span>  
    [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - <span></span>  
    [新 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - <span></span>  
    [CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - <span></span>  
    [CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的客户端管理 cmdlet](lync-server-2013-client-management-cmdlets.md)  


[Lync Server PowerShell 博客](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

