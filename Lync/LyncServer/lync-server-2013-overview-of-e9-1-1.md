---
title: Lync Server 2013： E9-1-1 概述
description: Lync Server 2013： E9-1-1 概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa13d8bfd1c273e8cbbb1d70f1fb3d733ac6167
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571898"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 中的 E9-1-1 概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

Microsoft Lync Server 2013 支持增强 9-1-1 (E9-1-1) 从 Lync 客户端和 Lync Phone Edition 设备调用。 为 E9-1-1 配置 Lync Server 时，来自 Lync 2013 或 Lync Phone Edition 的紧急呼叫包括来自位置信息服务数据库的紧急响应位置 (ERL) 信息。 ERL 包含市政（即街道）地址，以及有助于确定在办公楼和其他多租户设施中的更精确位置的其他信息。 当用户发出紧急呼叫时，Lync Server 通过中介服务器将呼叫音频以及位置和回拨信息路由到 E9-1-1 服务提供商。 E9-1-1 服务提供商会使用呼叫者的市政地址，将呼叫路由到为呼叫者的位置提供服务的公共安全应答点 (PSAP)，并沿着 PSAP 用来查找呼叫者的 ERL 的紧急服务查询键 (ESQK) 进行发送。

Lync Server 支持将紧急呼叫路由到 E9-1-1 服务提供商的两种方法：

  - 到合格的 E9-1-1 服务提供商的会话初始协议 (SIP) 中继连接

  - 到基于公用电话交换网 (PSTN) 的 E9-1-1 服务提供商的紧急位置标识号 (ELIN) 网关

在使用 SIP 中继 E9-1-1 服务提供程序时，将 Erl 添加到位置信息服务数据库，然后根据主街道地址指南 (MSAG) （由 E9-1-1 服务提供商维护）验证位置。 如果 E9-1-1 服务提供商收到一个没有位置信息的呼叫，或者有一个尚未针对 MSAG 验证的位置，E9-1-1 服务提供商将呼叫路由到国家/地区紧急呼叫响应中心 (ECRC) ，它由专门训练有素的人员组成，可以获取呼叫者的位置（如有可能），并手动将呼叫路由到相应的 PSAP。  (某些 SIP 中继 E9-1-1 服务提供商还向客户提供 PSTN direct 向内拨号 (是否向 ECRC 提供了) 号码，如果 SIP 中继因任何原因而失败，则会提供路由9-1-1 呼叫的备用方法。 ) 

与时间分段多路复用 (TDM) 和基于 IP 的专用分支 exchange (PBX) 电话（它具有固定位置），Lync 终结点可以成为非常移动的。 部署 E9-1-1 功能时，Lync Server 有助于确保无论呼叫者位于何处，紧急呼叫都可以路由到充当呼叫者位置的 PSAP。 例如，如果用户的总部位于华盛顿州的雷德蒙德，而用户从位于堪萨斯州的威奇托的分支机构的计算机发出紧急呼叫，则基于 SIP 中继或 PSTN 的 E9-1-1 服务提供商会将该呼叫路由至威奇托的 PSAP，而不是雷德蒙德的 PSAP。

使用 ELIN 网关时，还会将 Erl 添加到位置信息服务数据库中，但每个位置也包含一个 ELIN 号码。 ELIN 号码会在紧急呼叫过程中变为紧急呼叫号码。 然后，您必须确保 PSTN 运营商将 ELIN 上载到自动位置标识 (ALI) 数据库。

<div>


> [!NOTE]  
> 连接 Lync 的模拟设备无法从位置信息服务接收位置信息，或将位置信息发送到 E9-1-1 服务提供商。 如果您使用 SIP 中继 E9-1-1 服务提供商选项并需要通过模拟电话支持 E9-1-1，则有以下两个选项： 
> <UL>
> <LI>
> <P><STRONG>传统 PS-阿里选项</STRONG> &nbsp; &nbsp; &nbsp;如果在每个站点上都有本地 PSTN 网关，并且每个模拟电话有一个，则可以使用专用交换机/自动位置标识 (PS-阿里) 服务提供商，直接预配模拟设备的位置。 在这种情况下，您可配置精心制作的 Lync 语音策略并将其分配给模拟设备联系人对象，以便从这些电话发出的 E9-1-1 呼叫可直接通过本地网关路由至为该站点服务的 PSTN 提供商（而不是将该呼叫路由至 E9-1-1 服务提供商 SIP 中继）。 发出紧急呼叫后，与 PSTN 中继关联的 PS-ALI 提供商的数据库会将每个模拟电话的 DID 映射到一个物理位置并将此位置提供给 PSAP。 每当将电话移至不同的 ERL 时，必须通过 PS-ALI 服务提供商更新这些记录。</P>
> <LI>
> <P><STRONG>E9-1-1 服务提供商选项</STRONG> &nbsp; &nbsp; &nbsp;您可以使用 E9-1-1 服务提供商注册模拟电话 Did 及其对应的 Erl （如果 E9-1-1 服务提供商支持）。 如果提供程序从 Lync Server 收到不包含 PIDF-LO 数据的呼叫，则该提供程序可以查看呼叫方的已完成号码是否与数据库匹配。 通过使用从数据库检索到的 ERL，提供商可自动将紧急呼叫路由至正确的 PSAP，该 PSAP 将收到模拟设备的 DID 和允许调度程序查找呼叫者位置的 ESQK 记录。</P></LI></UL>如果您使用 ELIN 网关选项并需要通过模拟电话支持 E9-1-1，则可以直接向 PS-ALI 服务提供商提供模拟设备的位置，如上面第一个选项中所述。</div>

从 Lync Server 的角度来看，E9-1-1 过程可分为两个阶段：

  - 阶段 1：获取位置

  - 阶段 2：将紧急呼叫路由至 E9-1-1 服务提供商

本节介绍这些阶段的工作原理。

如果您计划将基础结构配置为自动检测客户端位置，则首先需要确定将使用哪些网络元素将呼叫者映射到不同位置。 有关可能的选项的详细信息，请参阅 [定义用于确定 Lync Server 2013 中的位置的网络元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中获取位置](lync-server-2013-acquiring-a-location.md)

  - [在 Lync Server 2013 中使用 SIP 中继路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [在 Lync Server 2013 中使用 ELIN 网关路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

