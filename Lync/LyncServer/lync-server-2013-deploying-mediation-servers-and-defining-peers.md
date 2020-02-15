---
title: Lync Server 2013：部署中介服务器和定义对等方
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e9ca9fa29d2646a38a9cbf94d79ba9766b21d62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>在 Lync Server 2013 中部署中介服务器和定义对等方

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

在前端池中，企业语音工作负载、电话拨入式会议和高级企业语音应用程序（响应组应用程序、呼叫寄存应用程序、呼叫允许控制（CAC）等）均可用。 在 Lync Server 2013 中，中介服务器的功能内置于前端服务器中。 不再需要单独的独立中介服务器。 前端池可以直接与受支持的网关（公用电话交换网（PSTN）网关或 ip-pbx）进行通信，从而消除了中介服务器作为中介的需求。

唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。 若要将企业语音基础结构连接到 SIP 中继提供程序，必须部署单独的中介服务器。

Lync Server （前端池或独立中介服务器上的中介服务器组件）和网关之间的连接定义为称为*中继*的逻辑关联。 本节中的主题介绍如何定义中继，以及在连接到 SIP 中继的情况下，如何部署独立的中介服务器。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 的拓扑生成器中定义中介服务器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [在 Lync Server 2013 的拓扑生成器中定义网关](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [在 Lync Server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)

  - [在 Lync Server 2013 的拓扑生成器中定义其他中继](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>相关部分

[在 Lync Server 2013 中配置电话拨入式会议](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

