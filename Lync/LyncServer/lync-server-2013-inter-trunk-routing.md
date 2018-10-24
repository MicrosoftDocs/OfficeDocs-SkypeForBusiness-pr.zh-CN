---
title: Lync Server 2013：中继间路由
TOCTitle: 中继间路由
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49888690
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的中继间路由

 

_**上一次修改主题：** 2012-10-08_

Lync Server 2013 通过支持中继间路由提供基本会话管理。此新功能可使 Lync Server 向下游电话系统提供呼叫控制功能。中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。同样，Lync Server 可互联两个或更多 IP-PBX 系统，以便可布置呼叫并从不同 IP-PBX 系统的 PBX 电话间接收呼叫。

下图显示 Lync Server 2013 在 PSTN 网关和 IP-PBX 间提供互联性。

![Lync Server - 连接 PSTN 网关/IP-PBX 图示](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server - 连接 PSTN 网关/IP-PBX 图示")

下一个图显示连接两个 IP-PBX 系统的 Lync Server 2013。

![Lync Server - 将 IP-PAX 系统相互连接的图示](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server - 将 IP-PAX 系统相互连接的图示")

