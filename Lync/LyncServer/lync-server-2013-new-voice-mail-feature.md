---
title: Lync Server 2013：新的语音邮件功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691374b2287029c21be88e25ab7a56ecce96a675
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a>Lync Server 2013 中新的语音邮件功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

Lync Server 2013 引入了语音邮件转义，这是用于管理语音邮件的增强功能。 此新功能可检测到呼叫路由到语音邮件的情况，防止在用户无机会应答呼叫的情况下直接将呼叫路由到用户的移动电话语音邮件。 此情况在用户对其移动电话启用了同时响铃以及用户的移动电话关机、没电或不在服务区时发生。 Voicemail Escape 检测到用户的移动电话语音邮件立即应答了呼叫，并且断开了发往移动电话语音邮件的呼叫。 呼叫继续在用户的其他终结点上响铃，以便为用户提供应答呼叫的机会。 如果用户未应答呼叫，则呼叫将路由到企业语音邮件中。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置语音邮件转义](lync-server-2013-configuring-voice-mail-escape.md)  


[Lync Server 2013 中新的企业语音功能](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

