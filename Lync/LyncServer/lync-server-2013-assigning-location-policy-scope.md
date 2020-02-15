---
title: Lync Server 2013：分配位置策略作用域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69218c3f5399b62fc67fe0d538a98f1bdadd3cf4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>在 Lync Server 2013 中分配位置策略作用域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-06_

与其他 Lync Server 策略一样，可在多个作用域级别分配位置策略：全局、站点和用户。 但是，用户级位置策略的作用与其他 Lync Server 策略的行为略有不同。 每用户位置策略不仅可应用于终结点对象（如用户和公用区域电话联系对象），还可以应用于 Lync Server 网络站点。 网络站点是与地理位置关联的客户端子网的分组（但是不一定全部都为整个中央站点或分支站点中的子网）。 任何连接到网络站点子网的客户端都自动拾取分配给该网络站点的位置策略。 在将用户级别的位置策略分配给用户和网络站点的情况下，基于网络站点的位置策略将覆盖任何每用户策略设置。

每个网络站点都有为其分配的位置策略，而且每个策略都有为其分配的不同 PSTN 用途、通知 URI 和会议 URI 值。

<div>


> [!NOTE]  
> 这种特殊策略作用域行为的原因是，当某个用户驻留在某个 office 网站上的某个池访问另一个网站并需要进行紧急呼叫时，无论是哪个池或站点是什么池或站点，都将应用与该网络站点相对应的 E9-1 呼叫路由设置将 ser 分配给。



</div>

</div>

<span> </span>

</div>

</div>

</div>

