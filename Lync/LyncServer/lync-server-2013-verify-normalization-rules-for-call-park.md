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
ms.openlocfilehash: 627832870de3a8306912d07134bb92caeee3076e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518619"
---
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>在 Lync Server 2013 中验证呼叫寄存的规范化规则

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-11_

呼叫寄存轨道式不得进行规范化。 检查您的拨号计划，以确保您的轨道编号不规范。 如果您必须创建一个额外的规范化规则来阻止对您的轨道式进行规范化，请按照在 [Lync Server 2013 中创建拨号计划中](lync-server-2013-create-a-dial-plan.md) 的过程来定义新的规范化规则，以便 **匹配的模式** 标识和 **转换模式** 为 **$1**。 例如，如果您的呼叫寄存通道范围是7000–7999，则 **要匹配的模式** 为 **^ (7 \\ d {3}) $** and **转换模式** 为 **$1**。

<div>


> [!IMPORTANT]  
> 请确保您的拨号计划中的默认规范化规则不包含 <STRONG>^ ( \d * ) </STRONG>。 否则，您的呼叫寄存规范化规则将永远不会运行。



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

