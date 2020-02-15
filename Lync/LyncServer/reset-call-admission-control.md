---
title: 重置呼叫允许控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c51eed6e5164316c2785ff5d560291afe58015c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>重置呼叫允许控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-11_

如果 Lync Server 2010 前端池承载呼叫允许控制（CAC），则必须先将 CAC 托管到 Lync Server 2013 池，然后才能删除 Lync Server 2010 前端池。

<div>

## <a name="to-reset-cac"></a>重置 CAC

1.  打开拓扑生成器。

2.  右键单击站点节点，然后单击“编辑属性”****。

3.  在“呼叫允许控制设置”**** 下，确保选择“启用呼叫允许控制”****。

4.  在 "**前端池" 下运行呼叫允许控制（CAC）**，选择要承载 CAC 的 Lync Server 2013 池，然后单击 **"确定"**。

5.  发布拓扑。

</div>

</div>

<span> </span>

</div>

</div>

</div>

