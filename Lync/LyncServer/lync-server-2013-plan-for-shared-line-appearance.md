---
title: Lync Server 2013：规划共享线路外观
description: Lync Server 2013：规划共享线路外观。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c34a4792d6df9b37b138c08881699dfcdf684d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554378"
---
# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>在 Lync Server 2013 中规划共享线路外观

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-03-21_

阅读本主题，了解如何在 Lync Server 2013 中规划共享线路外观 (SLA) ，累积更新4月2016。

共享线路外观是 Lync Server 2013 中的一项功能，累积更新4月2016，用于处理对特定号码（称为共享号码）的多个呼叫。 SLA 可以将任何已启用企业语音的 Lync 用户配置为具有多个线路的共享号码，以响应多个呼叫。 实际上不会在共享号码上接收呼叫，而是将其转发给充当共享号码的代理人的用户。 任何一个代理都可以接听呼叫，而代理的其余部分会在他们的电话上收到通知，告知他们接听呼叫的人以及哪些线路因结果而变得占线。 可以为 SLA 中的共享号码配置行数和代理人。 此外，高级选项（例如 BusyOption (在所有线路忙) 和 (MissedCallOption 中时，如果没有任何代理挑选呼叫) 的情况下，也可以为共享号码进行配置。

仅在以下电话设备上支持 SLA (计算机、移动电话或其他设备上的 Lync 客户端不支持) ：

  - 带有固件更新5.4.1 的 Polycom VVX300

  - 带有固件更新5.4.1 的 Polycom VVX400

  - 带有固件更新5.4.1 的 Polycom VVX500

  - 带有固件更新5.4.1 的 Polycom VVX600

SLA 是 Lync Server 2013 中的一项新功能，累积更新4月2016。

有关部署 SLA 的信息，请参阅 [在 Lync Server 2013 中部署共享线路外观](lync-server-2013-deploy-shared-line-appearance.md)。

<div>

## <a name="feature-list"></a>功能列表

设置 SLA 组可实现以下功能：

  - 组中的所有代理都可以将入站呼叫应答为相同的共享号码。 呼叫可以是基于 PSTN 的，也可以是基于 SIP 的。

  - 代理人可以保留和接听呼叫。

  - 代理可以将呼叫转移到 SLA 组之外的号码。

  - 代理可以查看共享号码上当前有多少呼叫，并查看每个呼叫的状态。

  - 您可以为共享号码配置最大并发呼叫数。 您还可以设置在达到此最大值后您希望如何处理其他呼叫。 多余的呼叫可以通过占线信号被拒绝，将其转发到备用号码，或转发到语音邮件。

  - 您可以配置在特定时间) 处理时，您希望未选取的未接来电 (呼叫的方式。 如果为组标识启用语音邮件，则未接来电将自动转到语音邮件。 如果您没有为组标识启用 (共享号码) 的语音邮件，则可以选择使用占线信号拒绝的未接来电，并将其转接至备用号码或断开连接。

</div>

</div>

<span> </span>

</div>

</div>

</div>

