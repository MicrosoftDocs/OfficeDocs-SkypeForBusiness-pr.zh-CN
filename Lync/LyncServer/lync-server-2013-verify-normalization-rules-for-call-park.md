---
title: Lync Server 2013：验证呼叫寄存的规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ab8e6038fd17daed7f10f11023793b702dd7d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>在 Lync Server 2013 中验证呼叫寄存的规范化规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-11_

呼叫寄存轨道式不得进行规范化。 检查您的拨号计划，以确保您的轨道编号不规范。 如果您必须创建一个额外的规范化规则来阻止对您的轨道式进行规范化，请按照在[Lync Server 2013 中创建拨号计划中](lync-server-2013-create-a-dial-plan.md)的过程来定义新的规范化规则，以便**匹配的模式**标识和**转换模式**为 **$1**。 例如，如果您的呼叫寄存通道范围是7000–7999，则**要匹配的模式**为 **^ （\\7{3}d） $** and**转换模式**为 **$1**。

<div>


> [!IMPORTANT]  
> 请确保您的拨号计划中的默认规范化规则不包含<STRONG>^ （\d *）</STRONG>。 否则，您的呼叫寄存规范化规则将永远不会运行。



</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

