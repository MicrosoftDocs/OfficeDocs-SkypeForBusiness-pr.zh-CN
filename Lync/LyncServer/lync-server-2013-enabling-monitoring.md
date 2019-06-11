---
title: 'Lync Server 2013: 启用监视'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中启用监视

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-17_

虽然统一的数据收集代理会在每个前端服务器上自动安装和激活, 但这并不意味着你在完成安装 Microsoft Lync Server 2013 后将自动开始收集监视数据。 你必须执行两项操作: 必须将前端服务器/前端池与监视数据库相关联, 并且必须在全局范围和/或网站范围内启用呼叫详细记录 (CDR) 和/或体验质量 (QoE) 监视。

有关将前端服务器或前端池与监视数据库关联的分步说明, 请参阅部署指南中的主题将[监视存储与 Lync Server 2013 中的前端池相关联](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md)。 在创建这些关联后, 在新的 Lync Server 拓扑发布后, 你仍然无法收集监视数据。 这是因为, 默认情况下, 在安装 Lync Server 2013 时, 将禁用 CDR 和 QoE 数据收集。

若要开始数据收集，您将需要启用 CDR 和/或 QoE 监控。 (请注意, 你无需同时启用 CDR 和 QoE 监视; 如果你愿意, 可以启用一种类型的监视, 同时禁用另一种类型。)若要在全局范围内启用 CDR 监视, 请从 Lync Server 命令行管理程序内运行以下命令:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

或者, 您可以从 Lync Server 2013 控制面板中启用 CDR 监视。 在 Lync Server "控制面板" 中, 完成以下过程:

1.  单击“**监控**”。

2.  在“**呼叫详细记录**”选项卡上，双击“**全局**”设置。

3.  在“**编辑呼叫详细记录(CDR)设置**”窗格中，选择“**启用 CDR 监控**”，然后单击“**提交**”。

若要在全局范围内启用 QoE 监视, 请从 Lync Server Management Shell 中运行此命令:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

如果您愿意, 也可以从 Lync Server 控制面板中启用 QoE 监控。 从控制面板中，完成以下过程：

1.  单击“**监控**”。

2.  在“**用户体验质量数据**”选项卡上，双击“**全局**”设置。

3.  在“**编辑体验质量(QoE)设置**”窗格中，选择“**启用 QoE 数据监控**”，然后单击“**提交**”。

您已看到，上面的示例在全局范围启用监控；即，它们在贵组织内启用 CDR 和 QoE 监控。 您也可以在站点范围创建单独的 CDR 和 QoE 配置设置，然后有选择地为每个站点启用或禁用监控。 例如，可以为您的 Redmond 站点启用 CDR 监控，而为您的 Dublin 站点禁用 CDR 监控。 有关管理监视配置设置的详细信息, 请参阅部署指南主题[配置 Lync Server 2013 中的 "呼叫详细记录" 和 "体验质量" 设置](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)。

</div>

<span> </span>

</div>

</div>

</div>

