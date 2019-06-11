---
title: 'Lync Server 2013: 验证呼叫寄存的规范化规则'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114c7e035d96217f8cf41e88a87ccfd490fe5754
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>在 Lync Server 2013 中验证呼叫寄存的规范化规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-11_

调用寄存轨道式不得正常化。 检查拨号计划以确保未对通道号码进行规范化。 如果必须创建另一种规范化规则来防止你的轨道式被正常化, 请按照在[Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)中的过程定义新的规范化规则, 以便**匹配的模式**标识轨道范围和**翻译模式**为 **$1**。 例如, 如果您的呼叫公园轨道范围为 7000-7999, 则**要匹配的模式**为 **^ (\\7{3}d) $** 和**转换模式**为 **$1**。

<div>


> [!IMPORTANT]  
> 请确保拨号计划中的默认规范化规则不包含 <STRONG>^(\d*)</STRONG>。 否则, 您的通话寄存规范化规则将永远不会运行。



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

