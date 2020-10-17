---
title: Lync Server 2013：称为 ID 演示文稿
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
ms.openlocfilehash: dddb1902422cb3efc52f4f0b3271976ab9b9950e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508219"
---
# <a name="called-id-presentation-in-lync-server-2013"></a>Lync Server 2013 中名为 ID 的演示文稿

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

在 Lync Server 2010 中，被叫方的电话号码 (也就是说，呼叫) 的电话号码可以从 e.164 格式转换为中继 (对等方所需的本地拨号格式，即关联网关、专用分支 exchange (PBX) 或 SIP 中继) 。 为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

<div>


> [!IMPORTANT]  
> 将一个或多个转换规则与企业语音中继配置进行关联的功能可用作在中继对等方上配置转换规则的<EM></EM>备选方法。如果已在中继对等方上配置转换规则，则不要将任何转换规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。



</div>

可以使用以下任一方法创建或修改转换规则：

  - 使用 " **生成转换规则** " 工具指定要删除的起始数字、长度、要删除的数字和要添加的数字的值，然后让 Lync Server 控制面板为您生成相应的匹配模式和转换规则。

  - 手动编写正则表达式以定义匹配模式和转换规则。

<div>


> [!NOTE]  
> 有关如何编写正则表达式的信息，请参阅处的 ".NET Framework 正则表达式" <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> 。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [使用 Lync Server 2013 中的 "构建转换规则" 工具创建或修改转换规则](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [在 Lync Server 2013 中手动创建或修改转换规则](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的呼叫者 ID 演示](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

