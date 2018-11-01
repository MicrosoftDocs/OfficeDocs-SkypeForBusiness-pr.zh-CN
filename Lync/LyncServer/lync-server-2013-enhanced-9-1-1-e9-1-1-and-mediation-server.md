---
title: Lync Server 2013：增强型 9-1-1 (E9-1-1) 和中介服务器
TOCTitle: 增强型 9-1-1 (E9-1-1) 和中介服务器
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398903(v=OCS.15)
ms:contentKeyID: 49314325
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的增强型 9-1-1 (E9-1-1) 和中介服务器

 

_**上一次修改主题：** 2012-09-29_

中介服务器扩展了某些功能，从而可以正确地与增强型 9-1-1 (E9-1-1) 服务提供商进行交互。中介服务器上不需要任何特殊的配置，默认情况下，E9-1-1 交互所需的 SIP 扩展包含在中介服务器用于与对等网关（Internet 电话服务提供商（包括 E9-1-1 服务提供商）的 PSTN 网关、IP-PBX 或 SBC）进行交互的 SIP 协议中。

到 E9-1-1 服务提供商的 SIP 中继是可以在现有中介服务器池上终止，还是需要独立的中介服务器将取决于 E9-1-1 SBC 能否与中介服务器池进行交互。有关详细信息，请参阅 [Lync Server 2013 中的 M:N 中继](lync-server-2013-m-n-trunk.md)。

