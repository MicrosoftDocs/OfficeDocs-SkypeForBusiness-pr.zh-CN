---
title: Lync Server 2013：中继间路由
TOCTitle: 中继间路由
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205272(v=OCS.15)
ms:contentKeyID: 49314357
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的中继间路由

 

_**上一次修改主题：** 2012-10-20_

Lync Server 2013 可将 IP-PBX 和公用电话交换网 (PSTN) 网关相互连接起来，以便能将来自 PBX 电话的呼叫路由到 PSTN，并能将传入 PSTN 呼叫路由到专用交换机 (PBX) 电话。同样， Lync Server 2013 可将两个或两个以上的 IP-PBX 系统相互连接起来，以便能在不同的 PBX 系统中的各个 IP-PBX 电话之间发出和接收呼叫。

可将 Lync Server 命令行管理程序 cmdlet **Set-CsTrunkConfiguration** 与新参数 PstnUsages 结合使用来配置此中继间路由功能。此参数指定一组要使用的 PSTN 用法记录。中继使用此 PSTN 用法来确定路由并相应地路由所有传入呼叫。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

下图说明了提供 PSTN 网关和 IP-PBX 之间的互连性的 Lync Server 2013。

**网关与 IP PBX 之间的中继间路由**

![Lync Server - 连接 PSTN 网关/IP-PBX 图示](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server - 连接 PSTN 网关/IP-PBX 图示")

下图说明了将两个 IP-PBX 系统相互连接的 Lync Server 2013。

**两个 IP PBX 之间的中继间路由**

![Lync Server - 将 IP-PAX 系统相互连接的图示](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server - 将 IP-PAX 系统相互连接的图示")

