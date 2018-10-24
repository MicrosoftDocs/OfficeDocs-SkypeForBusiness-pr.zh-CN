---
title: 在 Lync Server 2013 中启用监控
TOCTitle: 在 Lync Server 2013 中启用监控
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49888336
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中启用监控

 

_**上一次修改主题：** 2012-10-17_

尽管会在每台前端服务器上自动安装和激活统一数据集合代理，但这并不意味着您将在安装完 Microsoft Lync Server 2013 时自动开始收集监控数据。相反，您必须执行两项任务：必须将您的前端服务器/前端池与监控数据库关联，并且必须在全局范围和/或站点范围启用呼叫详细记录 (CDR) 和/或体验质量 (QoE) 监控。

有关将前端服务器或前端池与监控数据库关联的分步说明，请参阅部署指南中的[将监控存储与前端池关联](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md)主题。在完成这些关联且发布新的 Lync Server 拓扑后，您仍无法收集监控数据。这是因为默认情况下，在您安装 Lync Server 2013 时将禁用 CDR 和 QoE 数据收集。

若要开始数据收集，您将需要启用 CDR 和/或 QoE 监控。（请注意，您无需同时启用 CDR 和 QoE 监控；如果愿意，您可以启用一种监控类型同时禁用另一种类型。）若要在全局范围启用 CDR 监控，请从 Lync Server 命令行管理程序中运行以下命令：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

或者，也可以从 Lync Server 2013 控制面板中启用 CDR 监控。从 Lync Server 控制面板中，完成以下过程。

1.  单击“监控”。

2.  在“呼叫详细记录”选项卡上，双击“全局”设置。

3.  在“编辑呼叫详细记录(CDR)设置”窗格中，选择“启用 CDR 监控”，然后单击“提交”。

若要在全局范围启用 QoE 监控，请从 Lync Server 命令行管理程序中运行此命令：

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

如果愿意，您还可以从 Lync Server 控制面板中启用 QoE 监控。从控制面板中，完成以下过程：

1.  单击“监控”。

2.  在“用户体验质量数据”选项卡上，双击“全局”设置。

3.  在“编辑体验质量(QoE)设置”窗格中，选择“启用 QoE 数据监控”，然后单击“提交”。

您已看到，上面的示例在全局范围启用监控；即，它们在贵组织内启用 CDR 和 QoE 监控。您也可以在站点范围创建单独的 CDR 和 QoE 配置设置，然后有选择地为每个站点启用或禁用监控。例如，可以为您的 Redmond 站点启用 CDR 监控，而为您的 Dublin 站点禁用 CDR 监控。有关管理监控配置设置的详细信息，请参阅部署指南主题[配置呼叫详细信息记录和启用体验质量设置](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)。

