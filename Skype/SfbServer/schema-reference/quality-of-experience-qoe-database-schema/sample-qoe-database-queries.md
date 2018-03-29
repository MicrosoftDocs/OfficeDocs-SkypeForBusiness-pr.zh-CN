---
title: 示例 QoE 数据库查询
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: 本节包含示例体验质量 (QoE) 数据库的查询。
ms.openlocfilehash: 20ca6bc8aea6035ebe27fc5f77d512464cd82dcc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="d2fab-103">示例 QoE 数据库查询</span><span class="sxs-lookup"><span data-stu-id="d2fab-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="d2fab-104">本节包含示例体验质量 (QoE) 数据库的查询。</span><span class="sxs-lookup"><span data-stu-id="d2fab-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="d2fab-105">使用下面的示例获取抖动和包丢失的所有音频流的平均。</span><span class="sxs-lookup"><span data-stu-id="d2fab-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="d2fab-106">使用下面的示例查找使用会议控制台的会议的总数字。</span><span class="sxs-lookup"><span data-stu-id="d2fab-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync

```

<span data-ttu-id="d2fab-107">使用下面的示例获取每个捕获设备的 ConversstionalMOS、 SendingMOS 和 ListendingMOS。</span><span class="sxs-lookup"><span data-stu-id="d2fab-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```
select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
from
(
   select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

   union

   select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

)as t
group by t.DeviceName
order by SampleNum desc

```


