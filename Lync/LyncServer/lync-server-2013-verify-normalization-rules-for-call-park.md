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
ms.openlocfilehash: 2041b807ad16f1e91a83da39739d0ea058a5fba5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>在 Lync Server 2013 中验证呼叫寄存的规范化规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-11_

调用寄存轨道式不得正常化。 检查拨号计划以确保未对通道号码进行规范化。 如果必须创建另一个规范化规则来防止你的轨道式被正常化，请按照在[Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)中的过程定义新的规范化规则，以便**匹配**"轨道范围" 和 "翻译 **$1****模式**"。 例如，如果您的呼叫公园轨道范围为 7000-7999，则**要匹配的模式**为 **^ （\\7{3}d） $** 和**转换模式**为 **$1**。

<div>


> [!IMPORTANT]  
> 请确保拨号计划中的默认规范化规则不包含 <STRONG>^(\d*)</STRONG>。 否则，您的通话寄存规范化规则将永远不会运行。



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

