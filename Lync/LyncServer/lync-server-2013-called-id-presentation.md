---
title: Lync Server 2013：名为 "ID 演示文稿"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dc22438a688239618fc7a73cf3aa30ec614568d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Lync Server 2013 中名为 "ID 演示文稿"

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

使用 Lync Server 2010，被呼叫方的电话号码（称为电话号码）可以从格式转换为中继对等（即关联网关、专用分支 exchange （PBX）或 SIP 主干）所需的本地拨号格式。 为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

<div>


> [!IMPORTANT]  
> 将一个或多个翻译规则与企业语音中继配置相关联的功能旨在用作在中继对等上配置翻译规则的<EM>替代方法</EM>。 如果你已在中继对等上配置了转换规则，请不要将翻译规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。



</div>

你可以使用以下任一方法来创建或修改翻译规则：

  - 使用 "**生成翻译规则**" 工具来指定起始数字、长度、要删除的数字和要添加的数字的值，然后让 Lync Server "控制面板" 为你生成相应的匹配模式和转换规则。

  - 手动编写正则表达式以定义匹配的模式和转换规则。

<div>


> [!NOTE]  
> 有关如何编写正则表达式的信息，请参阅的<A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>".Net Framework 正则表达式"。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [使用 Lync Server 2013 中的 "生成翻译规则" 工具创建或修改翻译规则](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [在 Lync Server 2013 中手动创建或修改翻译规则](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的呼叫者 ID 演示文稿](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

