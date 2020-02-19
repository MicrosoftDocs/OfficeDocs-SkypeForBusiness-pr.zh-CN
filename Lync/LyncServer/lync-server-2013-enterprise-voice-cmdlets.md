---
title: Lync Server 2013：企业语音 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice cmdlets
ms:assetid: 7d7c6d94-3ead-4d99-95f7-c31b448ab9e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415658(v=OCS.15)
ms:contentKeyID: 48184613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c32a3647b27ed2cc7a22162c959f00be4c3324
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的企业语音 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-03-19_

企业语音是 Microsoft 的 IP 语音 (VoIP) 实现。 在 Microsoft Lync Server 2013 中可用于管理企业语音的 cmdlet 将允许您创建和修改拨号计划（以前称为位置配置文件）、语音策略、路由和规范化规则。

<div>

## <a name="enterprise-voice-cmdlets"></a>企业语音 Cmdlet

适用于企业语音的大多数管理任务可以从 Lync Server 控制面板中执行。 可以使用 Lync Server 命令行管理程序中的 cmdlet 或在脚本中执行这些相同的任务，从而使您能够自动执行某些任务。 下面列出了直接与管理企业语音相关的 cmdlet：

**[Lync Server 2013 中的企业语音 cmdlet 疑难解答](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**

  - <span></span>  
    [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - <span></span>  
    [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - <span></span>  
    [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - <span></span>  
    [新 CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - <span></span>  
    [CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - <span></span>  
    [CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - <span></span>  
    [Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-Grant-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

**[Lync Server 2013 中的语音规范化规则 cmdlet](lync-server-2013-voice-normalization-rules-cmdlets.md)**

  - <span></span>  
    [CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - <span></span>  
    [新 CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - <span></span>  
    [CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - <span></span>  
    [CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - <span></span>  
    [Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新 CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

**[Lync Server 2013 中的语音策略 cmdlet](lync-server-2013-voice-policy-cmdlets.md)**

  - <span></span>  
    [Grant-csdialplan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - <span></span>  
    [Grant-Grant-csdialplan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - <span></span>  
    [新 Grant-csdialplan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - <span></span>  
    [Grant-csdialplan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - <span></span>  
    [Grant-csdialplan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))

  - <span></span>  
    [Test-Grant-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - <span></span>  
    [CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - <span></span>  
    [Grant-Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - <span></span>  
    [新 Set-csvoicepolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - <span></span>  
    [Test-Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

**[Lync Server 2013 中的语音路由 cmdlet](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - <span></span>  
    [新 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - <span></span>  
    [CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - <span></span>  
    [CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - <span></span>  
    [新 CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - <span></span>  
    [CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - <span></span>  
    [CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - <span></span>  
    [Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的高级企业语音 cmdlet](lync-server-2013-advanced-enterprise-voice-cmdlets.md)  
[Lync Server 2013 中的语音应用程序 cmdlet](lync-server-2013-voice-application-cmdlets.md)  


[Lync Server PowerShell 博客](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

