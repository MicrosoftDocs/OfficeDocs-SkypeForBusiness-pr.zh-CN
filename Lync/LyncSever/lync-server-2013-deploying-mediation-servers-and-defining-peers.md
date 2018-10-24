---
title: Lync Server 2013：部署中介服务器和定义对等方
TOCTitle: 部署中介服务器和定义对等方
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412780(v=OCS.15)
ms:contentKeyID: 49313852
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中部署中介服务器和定义对等方

 

_**上一次修改主题：** 2012-09-21_

前端池提供了 企业语音工作负荷、拨入式会议和高级 企业语音应用程序（ 响应组应用程序、 呼叫寄存应用程序、呼叫允许控制 (CAC) 等）。随着 Lync Server 2013 的推出， 中介服务器的功能内置在 前端服务器中。单个独立的 中介服务器不再是必需的。 前端池可以直接与支持的网关（公用电话交换网 (PSTN) 网关或 IP-PBX）进行通信，从而不再需要 中介服务器来充当中介。

唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。要将 企业语音基础结构连接到您的 SIP 中继提供商，必须部署单独的 中介服务器。

Lync Server（ 前端池上的 中介服务器组件或独立的 中介服务器）与网关之间的连接定义为称为 *中继* 的逻辑关联。本节中的主题介绍如何定义中继，以及在连接到 SIP 中继的情况下，如何部署独立的中介服务器。

## 本部分内容

  - [在 Lync Server 2013 拓扑生成器中定义中介服务器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [在 Lync Server 2013 拓扑生成器中定义网关](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [在 Lync Server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)

  - [在 Lync Server 2013 拓扑生成器中定义其他中继](lync-server-2013-define-additional-trunks-in-topology-builder.md)

## 相关部分

[在 Lync Server 2013 中配置拨入式会议](lync-server-2013-configuring-dial-in-conferencing.md)

