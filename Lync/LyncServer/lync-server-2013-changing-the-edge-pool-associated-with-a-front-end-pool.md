---
title: Lync Server 2013：更改与前端池关联的边缘池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>在 Lync Server 2013 中更改与前端池关联的边缘池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

如果边缘池已关闭, 但同一网站上的前端池仍在运行, 则需要将前端池设置为在其他网站上使用边缘池, 直到还原失败的边缘池。

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>更改与前端池关联的边缘池

1.  在拓扑生成器中, 导航到需要更改的前端池的名称。

2.  右键单击该池, 然后单击 "**编辑属性**"。

3.  在 "**关联**" 部分中的 "**关联 Edge 池 (对于媒体组件)**" 下, 使用下拉框选择要与之关联的 "前端" 池的边缘池。

4.  单击“**确定**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

