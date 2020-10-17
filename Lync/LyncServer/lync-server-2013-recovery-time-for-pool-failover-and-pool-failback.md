---
title: Lync Server 2013 池故障转移和池故障回复的恢复时间
description: Lync Server 2013 池故障转移和池故障回复的恢复时间。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bb09c32ac4d062358a511464dc21aa7346ee034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559168"
---
# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Lync Server 2013 中池故障转移和池故障回复的恢复时间

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-10_

对于池故障转移和池故障回复，恢复时间目标 (RTO) 的工程目标为 30 分钟。这是管理员确定存在灾难并启动故障转移过程之后，故障转移发生所需的时间。此时间不包括管理员评估情况并作出决策所需的时间，也不包括用户在故障转移完成后再次登录所需的时间。

对于池故障转移和池故障回复，恢复点目标 (RPO) 的工程目标为 30 分钟。 这表示测量可能因灾难、因备份服务的复制延迟丢失的数据的时间。 例如，如果池在 10:00 A.M. 停止，RPO 为30分钟，则在 9:30 A.M. 之间写入到池的数据 而10:00 可能尚未复制到备份池，并且将丢失。

本文档中的所有 RTO 和 RPO 数字均假定两个数据中心位于同一在两个网站间具有高速度、低延迟传输的世界区域中。 对于在数据复制中没有积压工作的预定义用户模型，为40000并发活动用户和200000用户启用了与 Lync 相关的池的度量值。 这些数字可能根据测试和验证性能发生改变。

</div>

<span> </span>

</div>

</div>

</div>

