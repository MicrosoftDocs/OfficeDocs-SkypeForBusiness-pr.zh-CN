---
title: Lync Server 2013 会议用户模型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f16ebf97a23bad014fde7fa9ebfbe005c4b95a8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517669"
---
# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Lync Server 2013 中的会议用户模型

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

Lync Server 会议用户模型的关键部分是会议大小。 从多个数据点收集数据（如上一节中所述）之后，我们确定了以下内容：

  - 大多数会议实际上都是平均有四到六位参与者的小型协作会议

  - 大约 80% 的会议的参与者不到 20 人。

  - 99.98% 的会议的参与者不到 100 人。

除了会议规模以外，会议用户模型还考虑到各种因素，如：

  - **并发会议**    在会议中，需要有多少个用户同时参与？

  - **媒体组合**    哪些类型的媒体可用并预期由会议中的用户使用？

  - **用户类型**    用户是用户内部用户、远程用户、联合用户还是匿名用户？

  - **会议提升时间**    会议的所有用户加入会议需要多长时间？

有关用户模型的详细信息，请参阅 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。

为了确定要用于测试的会议数和用户数，我们执行了以下操作：

  - 将组织中的用户总数（例如，80,000 位用户）乘以会议并发率（例如，所有用户的 5%），以确定预计同时参加会议的用户总数（在此示例中，为 4000 位用户）。

  - 将用户总数除以部署中的 Lync Server 2013、前端服务器数 (例如，8台服务器) ，以确定每个前端服务器的估计会议参与者数 (在此示例中，每个前端服务器) 500 个用户。

  - 将每个前端服务器的用户数除以平均会议大小 (例如，4个用户) 以确定每个前端服务器的估计平均会议数 (在此示例中，每个前端服务器) 125 个会议。

  - 若要在每台前端服务器上获取每个媒体负载，我们估计媒体组合。 例如，假设75% 的会议要求的不只是音频支持，而这些会议的50% 需要应用程序共享，则平均47会议和188用户同时连接到每个前端服务器以进行应用程序共享。

  - 对各种会议规模进行测试（基于共享池中多达 250 位用户的用户模型），以确保服务器可伸缩性。

</div>

<span> </span>

</div>

</div>

</div>

