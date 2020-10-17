---
title: Lync Server 2013：包括安全服务台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52133ebc1e842b1f2ee3f885e038cf521fb18f3d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526619"
---
# <a name="including-the-security-desk-in-lync-server-2013"></a>在 Lync Server 2013 中包括安全桌面

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

公司可能要求安全服务台参与紧急呼叫。为帮助确定如何将安全服务台集成到 E9-1-1 部署，应回答以下问题。

  - **发出紧急呼叫时，是否希望通知安全服务台？**  
    您可以配置位置策略，以便 Lync Server 向一个或多个安全人员的 Lync SIP 地址发送即时消息 (IM) 警报。 这些警报包含拨打紧急呼叫的人员的姓名、号码和位置，并可在紧急情况下实现安全性。

<!-- end list -->

  - **是否要在发出每个紧急呼叫时通知安全服务台？**  
    如果紧急服务服务提供商支持，可以将位置策略配置为在每个紧急呼叫中包含回拨号码。提供商随后使用此号码通知组织的安全人员参加有关紧急呼叫的会议。可在位置策略中将此会议配置为单向（仅侦听）或双向（双向）。

<div>


> [!NOTE]  
> 如果需要，可针对每个位置策略配置不同的紧急服务人员。这允许您为公司内的不同区域自定义响应，或为来自与网络外部相对的网络内部的紧急呼叫创建不同的行为。您可使用通讯组指定要通知的人员。



</div>

</div>

<span> </span>

</div>

</div>

</div>

