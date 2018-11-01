---
title: Lync Server 2013：使用 SIP 中继路由 E9-1-1 呼叫
TOCTitle: 使用 SIP 中继路由 E9-1-1 呼叫
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204701(v=OCS.15)
ms:contentKeyID: 49312100
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中使用 SIP 中继路由 E9-1-1 呼叫

 

_**上一次修改主题：** 2012-09-29_

使用 SIP 中继连接至限定的 E9-1-1 服务提供商是可用于部署 E9-1-1 的一种方式。有关使用 ELIN 网关连接至基于公用电话交换网 (PSTN) 的 E9-1-1 服务提供商的详细信息，请参阅 [在 Lync Server 2013 中使用 ELIN 网关路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。

下图显示在使用 SIP 中继和限定的 E9-1-1 服务提供商时如何将紧急呼叫从 Lync Server 路由到公共安全应答点 (PSAP)。

**通过 SIP 中继路由 E9-1-1 呼叫**

![从 Lync Server 路由到 PSAP 的紧急呼叫](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "从 Lync Server 路由到 PSAP 的紧急呼叫")

从兼容的 Lync Server 客户端发出紧急呼叫时：

1.  包含位置、呼叫者的回拨号码和（可选）通知 URL 以及会议回拨号码的 SIP INVITE 将路由至 Lync Server。

2.  Lync Server 匹配紧急号码并将呼叫（根据在适用的位置策略中定义的“PSTN 用法”值）路由至中介服务器，在此通过 SIP 中继路由到 E9-1-1 服务提供商。

3.  E9-1-1 服务提供商根据呼叫提供的位置将紧急呼叫路由至正确的 PSAP。如果客户端随紧急呼叫提供了已验证的紧急响应位置 (ERL)，则提供商会自动将呼叫路由至相应的 PSAP。如果位置是由用户手动输入的，则在将紧急呼叫路由至 PSAP 之前，紧急呼叫响应中心 (ECRC) 将首先口头与呼叫者核实位置的准确性。

4.  如果您配置了用于通知的位置策略，则会向贵组织的一位或多位安全主管发送特殊的 Lync 紧急通知即时消息。此消息始终会在安全主管的屏幕上弹出，并包含呼叫者的姓名、电话号码、时间和位置，使安全人员可以使用即时消息或声音快速应答紧急呼叫者。

5.  如果您配置了用于会议的位置策略并且 E9-1-1 服务提供商支持该策略，则国际安全服务台会通过单向音频或双向音频作为与会者加入呼叫。

6.  如果过早中断呼叫，则 PSAP 使用回拨号码直接与呼叫者联系。

