---
title: Lync Server 2013：定义规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 712e4cec9be89894b391ba940f054bc121e4acea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>在 Lync Server 2013 中定义规范化规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-22_

Lync Server 2013 规范化规则使用 .NET Framework 正则表达式将拨打的电话号码转换为. 164 格式;换言之，规范化规则采用用户拨打的电话号码，并将该号码转换为 Lync Server 在内部使用的格式。 必须将每个拨号计划分配给一个或多个规范化规则。

有关规范化规则的详细信息，请参阅规划文档中的[Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)。

有关如何编写正则表达式的详细信息，请参阅中[https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)的 ".Net Framework 正则表达式"。

可以使用以下任一方法定义或编辑规范化规则：

  - 使用 "**生成规范化规则**" 工具指定要删除的起始数字、长度、要删除的数字和要添加的数字的值，然后让 Lync Server 控制面板为您生成相应的匹配模式和转换规则。

  - 手动编写正则表达式以定义匹配模式和转换规则。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中使用 Build a 规范化规则创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [在 Lync Server 2013 中手动创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

