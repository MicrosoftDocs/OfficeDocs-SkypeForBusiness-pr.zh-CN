---
title: Lync Server 2013：中继配置 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trunking configuration cmdlets
ms:assetid: 2c36b03a-b80f-4321-a448-6ba26b9357f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416489(v=OCS.15)
ms:contentKeyID: 48183703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b3bb328b3567cb9a8826412838d7aad0ada386
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="trunking-configuration-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的中继配置 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-08_

中继配置 cmdlet 用于定义中继对等实体（如公共交换电话网络（PSTN）网关、IP-公共分支 exchange （PBX）或会话边界控制器（SBC）在服务提供商处的设置。 这些设置配置如下内容：是否在此中继上启用媒体旁路，是否在特定条件下发送实时传输控制协议 (RTCP) 数据包，以及是否需要安全实时协议 (SRTP) 加密。

<div>

## <a name="trunking-configuration-cmdlets"></a>中继配置 Cmdlet

对中继配置使用以下 cmdlet。

**中继配置**

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))

  - [New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))

  - [Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))

  - <span></span>  
    [新-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))

  - <span></span>  
    [Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))

  - <span></span>  
    [Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))

  - <span></span>  
    [新-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))

  - <span></span>  
    [Remove-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Set-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))

  - <span></span>  
    [Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))

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

