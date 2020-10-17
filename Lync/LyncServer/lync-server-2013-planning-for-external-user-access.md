---
title: Lync Server 2013：规划外部用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3068cae2545c0d3f1df3f04935914d21d032ffc2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522179"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中规划外部用户访问

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-19_

大部分组织中的通信涉及内部网络外的服务和用户。这些服务和用户包括临时或永久位于组织外的员工、客户或伙伴组织的员工、使用公共即时消息 (IM) 服务的人员以及受邀参加会议和发布会的潜在客户、合作伙伴或匿名用户。在本文档中，这些人员统称为*外部用户*。

在 Microsoft Lync Server 2013 中，组织中的用户可以使用 IM 和状态与外部用户进行通信，并且他们可以参与音频/视频 (A/V) 会议和使用您的非现场员工和其他类型的外部用户的 web 会议。 还可以支持从移动设备和通过企业语音进行外部访问。 不是组织成员的外部用户可以参与 Lync Server 2013 会议，从而允许匿名与会者。

若要支持整个组织的防火墙中的通信，请在外围网络中部署 Lync Server 2013 边缘服务器 (也称为 DMZ、隔离区域和屏蔽子网) 。 边缘服务器可控制防火墙外的用户如何连接到内部 Lync Server 2013 部署。 还控制从防火墙内发出的与外部用户的通信。

根据您的要求，您可在一个或多个位置部署一台或多台边缘服务器。 本节介绍了 Lync Server 2013 中的外部用户访问方案，并说明了如何规划边缘和反向代理拓扑。

<div>


> [!NOTE]  
> 虽然您需要一台边缘服务器来支持企业语音和外部用户访问，但本节重点介绍了对 IM、状态、A/V 会议、联合、web 会议和 Lync Mobile 的支持。 有关企业语音支持的详细信息，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013 中规划企业语音</A> 。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中影响边缘服务器规划的更改](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Lync Server 2013 的外部用户访问组件的系统要求](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 中的外部用户访问概述](lync-server-2013-overview-of-external-user-access.md)

  - [了解 Lync Server 2013 中的自动发现](lync-server-2013-understanding-autodiscover.md)

  - [在 Lync Server 2013 中选择拓扑](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013 中的数据收集](lync-server-2013-data-collection.md)

  - [确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)

  - [确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [在 Lync Server 2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

