---
title: 重置呼叫允许控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>重置呼叫允许控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-11_

如果 Lync Server 2010 前端池托管呼叫许可控制 (CAC), 则必须先将 CAC 托管托管到 Lync Server 2013 池, 然后才能删除 Lync Server 2010 前端池。

<div>

## <a name="to-reset-cac"></a>重置 CAC

1.  打开拓扑生成器。

2.  右键单击 "网站" 节点, 然后单击 "**编辑属性**"。

3.  在 "**呼叫许可控制" 设置**下, 请确保已选中 "**启用呼叫许可控制**"。

4.  在 "**前端池" 下运行呼叫许可控制 (CAC)**, 选择要托管 CAC 的 Lync Server 2013 池, 然后单击 **"确定"**。

5.  发布拓扑。

</div>

</div>

<span> </span>

</div>

</div>

</div>

