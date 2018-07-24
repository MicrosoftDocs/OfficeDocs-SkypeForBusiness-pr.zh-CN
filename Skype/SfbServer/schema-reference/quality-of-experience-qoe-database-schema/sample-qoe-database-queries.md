---
title: 示例 QoE 数据库查询
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: 此部分包含的用户体验质量 (QoE) 数据库的示例查询。
ms.openlocfilehash: c66d0fdc51ee3382034f5fba1e98f93a8799f312
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020595"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="88545-103">示例 QoE 数据库查询</span><span class="sxs-lookup"><span data-stu-id="88545-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="88545-104">此部分包含的用户体验质量 (QoE) 数据库的示例查询。</span><span class="sxs-lookup"><span data-stu-id="88545-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="88545-105">下面的示例用于获取所有音频流的抖动和丢包平均。</span><span class="sxs-lookup"><span data-stu-id="88545-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="88545-106">下面的示例用于查找使用 Meeting Console 的会议的总号码。</span><span class="sxs-lookup"><span data-stu-id="88545-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
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

<span data-ttu-id="88545-107">下面的示例用于获取每个捕获设备的 ConversstionalMOS、 SendingMOS 和 ListendingMOS。</span><span class="sxs-lookup"><span data-stu-id="88545-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
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