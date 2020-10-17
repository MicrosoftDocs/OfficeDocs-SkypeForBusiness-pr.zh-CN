---
title: Lync Server 2013：为用户启用 E9-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f03e3f0249897a17af8354cfca9f58a4d6508b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500909"
---
# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中为用户启用 E9-1-1

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-06_

在客户端注册过程中，Lync Server 使用位置策略为已启用企业语音的用户配置 E9-1-1 属性。 此策略包含定义 E9-1-1 实现方式的设置。 例如，位置策略包含紧急拨号字符串等信息，以及在位置信息服务不自动提供某个位置时是否需要用户手动输入位置。 有关位置策略的完整定义，请参阅 [定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)。

Lync Server 可以基于子网将位置策略分配给客户端，也可以基于全局、每站点或每用户策略将其分配给用户。 为帮助确定启用用户的方式，应首先回答以下问题。

  - **您计划启用所有用户还是限制为对企业的特定地理区域的支持？**  
    可以使用全局位置策略为企业中的所有用户分配位置。 但是，通过将位置策略分配给 Lync Server 网络站点，然后将子网添加到站点中，可以将 E9-1-1 支持限制到企业内的选定位置，并以每个站点为基础指定 E9-1 路由行为。

<!-- end list -->

  - **您是否计划通过用户策略启用单个用户？**  
    如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。

<!-- end list -->

  - **当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**  
    如果向用户分配了全局、站点或每用户位置策略，则当客户端不在已定义的子网中或位置信息服务未找到任何位置时，可以需要手动将该位置输入到客户端中。 有关详细信息，请参阅在 [Lync Server 2013 中定义用于手动获取位置的用户体验](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)。

</div>

<span> </span>

</div>

</div>

</div>

