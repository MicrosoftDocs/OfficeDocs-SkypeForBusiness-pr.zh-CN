---
title: 'Lync Server 2013: 为 E9 启用用户-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中启用 E9-1 的用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-06_

在客户端注册期间, Lync Server 使用一个位置策略来配置适用于企业语音的用户的 E9 属性。 此策略包含定义 E9-1-1 实现方式的设置。 例如, 位置策略包含 "紧急拨号" 字符串之类的信息, 以及是否需要用户手动输入一个位置 (如果位置信息服务不会自动提供)。 有关位置策略的完整定义, 请参阅[定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)。

Lync Server 可以基于子网将位置策略分配给客户, 或者根据全局、每网站或每用户策略向用户分配位置策略。 为帮助确定启用用户的方式，应首先回答以下问题。

  - **你计划启用所有用户还是限制为对企业的特定地理区域的支持？**  
    可以使用全局位置策略为企业中的所有用户分配位置。 但是, 通过将位置策略分配给 Lync 服务器网络网站, 然后将子网添加到该网站, 你可以将 E9 支持限制到企业内选定的位置, 并以每个站点为基础指定 E9 路由行为。

<!-- end list -->

  - **你是否计划通过用户策略启用单个用户？**  
    如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。

<!-- end list -->

  - **当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**  
    如果为用户分配了全局、网站或每用户位置策略, 则可以在客户端不在定义的子网中或未找到位置信息服务的位置时, 将其手动输入到客户端的位置。 有关详细信息, 请参阅[定义在 Lync Server 2013 中手动获取位置的用户体验](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)。

</div>

<span> </span>

</div>

</div>

</div>

