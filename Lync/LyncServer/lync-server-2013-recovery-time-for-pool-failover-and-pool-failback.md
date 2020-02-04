---
title: Lync Server 2013 池故障转移和池故障回复的恢复时间
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
ms.openlocfilehash: 3fff6f74b5d486c05d01bcd3a911ae674b4f0708
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Lync Server 2013 中的池故障转移和池故障回复的恢复时间

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-10_

对于池故障转移和池故障回复，针对恢复时间目标（RTO）的工程目标是30分钟。 这是发生故障转移所需的时间，在管理员确定存在灾难并启动故障转移过程之后。 此时间不包括管理员评估情况并作出决策所需的时间，也不包括用户在故障转移完成后再次登录所需的时间。

对于池故障转移和池故障回复，针对恢复点目标（RPO）的工程目标是30分钟。 这表示测量可能因灾难、因备份服务的复制延迟丢失的数据的时间。 例如，如果池在 10:00 A.M. 停止，RPO 为30分钟，则在 9:30 A.M. 之间写入到池中的数据将被写入。 和10:00 （可能尚未复制到备份池），将丢失。

本文档中的所有 RTO 和 RPO 数字均假定两个数据中心位于同一在两个网站间具有高速度、低延迟传输的世界区域中。 这些数字是针对具有 40,000 个同时活动的用户和 200,000 个已启用有关预定义的用户模型（在该模型中，数据复制没有备份日志）的 Lync 的用户的池测量而来的。 这些数字可能根据测试和验证性能发生改变。

</div>

<span> </span>

</div>

</div>

</div>

