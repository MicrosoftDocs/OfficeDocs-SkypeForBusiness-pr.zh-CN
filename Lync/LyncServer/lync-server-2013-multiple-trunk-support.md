---
title: Lync Server 2013：多中继支持
TOCTitle: 多中继支持
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205127(v=OCS.15)
ms:contentKeyID: 49313797
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的多中继支持

 

_**上一次修改主题：** 2012-11-01_

Lync Server 2013 功能支持网关和 中介服务器之间的多个关联。这些关联通过定义一个中继（ 中介服务器池和公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联）实现。使用 拓扑生成器可将网关与中介服务器（即中继）关联。

  - 若要在 Lync Server 2013 中分配或删除中继，必须先在 拓扑生成器中定义中继。中继包含以下关联： 中介服务器完全限定域名 (FQDN)、 中介服务器侦听端口、网关 FQDN 和网关侦听端口。

  - 若要配置多个中继，可以在相同的网关和 中介服务器之间创建多个关联。这就为 企业语音基础结构提供了更大弹性，这在专用交换机 (PBX) 互操作方案中特别有用。

定义中继，必须将其与路由关联。若要将中继与路由关联，可以在 拓扑生成器中为中继定义一个简单名称。此简单名称将用作 Lync Server 控制面板（在其中可将中继与路由关联）中的中继名称。简单中继名称将用作 Lync Server 命令行管理程序中的网关名称。

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

管理员必须选择与中介服务器关联的默认中继。从拓扑生成器中，右键单击关联的中介服务器，然后单击“属性”。指定中介服务器的默认网关。

下图演示了为每个 中介服务器和网关定义的多个中继。

**M-N 中继路由**

![多个中继分配。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多个中继分配。")

