---
title: Lync Server 2013：定义组织的监控要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 102735e7a8149edcb858b30644197553f5392c1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中定义组织的监控要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-05_

优化 Microsoft Lync Server 2013 中的监视部署和安装还可以简化定义组织的监视要求所涉及的过程。 但是，在开始安装和配置 Lync Server 2013 之前，仍需要解决几个关键问题：

**您想要监视何种类型的数据？** Lync Server 2013 使你能够监视两种不同类型的数据：调用详细记录（CDR）数据和体验质量（QoE）数据。 呼叫详细记录提供了一种跟踪 Lync Server 功能（如 IP 语音电话（VoIP）电话呼叫）的使用方式的方式。即时消息（IM）;文件传输;音频/视频（A/V）会议;和应用程序共享会话。 此信息可帮助你了解正在使用哪些 Lync Server 功能（以及哪些功能不是），还会提供有关这些功能的使用时间的信息。 体验数据质量允许您维护组织中发出的音频和视频通话质量的记录，包括网络数据包丢失、背景噪音和 "抖动" （数据包延迟的差异）的数量。

如果你选择在 Lync Server 2013 中启用监视，你可以同时启用 CDR 监视和 QoE 监视，或者你可以选择启用一种类型的监视，同时使其他类型处于禁用状态。 例如，假设用户仅使用即时消息和文件传输，不进行音频或视频呼叫。 在这种情况下，可能没有理由启用 QoE 监控。 同样，Lync Server 使你可以在部署监视后轻松启用和禁用监视。 例如，您可能选择部署监控但最初禁用 QoE 监控。 如果用户开始遇到音频或视频呼叫问题，您可以启用 QoE 监控并使用该数据帮助排查和解决这些问题

在安装 lync Server 和安装 Lync Server 后安装 "监视" 时，没有特殊的优势（或缺点），无法安装。 需要谨记的一点是，在安装监控之前，必须选择一台计算机来承载后端监控存储，并且必须在该计算机上安装和配置支持的 SQL Server 版本，之后才能将该计算机用于监控。 如果你已在计算机上安装了 SQL Server，并且该计算机已准备好使用，则可以在安装 Lync Server 的同时安装监视。 如果你没有后端计算机准备就绪，你可以继续自行安装 Lync Server，然后在后端计算机准备好使用时安装监视。

**想要何时安装监控？** 在安装和配置 Lync Server 2013 时，可以同时安装和配置监视;Lync Server 部署向导将向你提供在安装期间将前端池与监视数据库相关联的机会。 或者，也可以在安装 Lync Server 本身后安装监视;可通过使用拓扑生成器将前端池和服务器与监视数据库相关联，然后发布已修改的拓扑来执行此操作。

**需要多少个后端监控数据库？** 单个监视数据库可以支持数十个用户（对于 Microsoft Lync Server 2010，估计，collocated 数据库用于监视和存档可支持240000用户）。 此外，一个监控数据库可以被多个前端池使用；如果组织中有三个前端池，则可以将全部三个池与同一后端存储关联。

这只是意味着对于许多组织而言，数据库容量在确定所需的后端监视数据库数量时不是决定因素。 相反，网络速度可能是更重要的考虑事项。 假设你有三个前端池，但其中一个池位于慢速网络连接。 在这种情况下，你可能想要使用两个监控数据库：一个数据库为网络连接良好的两个池提供服务，另一个数据库为网络连接较慢的池提供服务。

规划你的监视基础结构时，你还应考虑 Lync Server 2013 是否支持使用镜像数据库。 “数据库镜像”提供了同时维护两个数据库副本，且每个数据库位于不同服务器上的方式。 每当将数据写入主数据库时，相同的数据也会写入镜像数据库。 如果主数据库出现故障或以其他方式变为不可用，则可以通过使用简单的 Lync Server PowerShell 命令，将故障转移到镜像数据库。 例如：

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

这对于规划来说很重要，仅仅因为镜像需要将所需数据库数量翻倍：除了各个主数据库，还需要第二个数据库作为镜像。

**您的 Lync 服务器网站是否需要自己的自定义监视配置？** 安装 Lync Server 2013 时，还会安装 CDR 和 QoE 配置设置的全局集合;这些全局集合让你能够将相同的 CDR 和 QoE 设置应用到整个组织。 In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

但是，有时也可能需要对不同的网站应用不同的设置。 例如，您可能希望在 Redmond 网站中同时使用 CDR 和 QoE 监视，但仅在都柏林网站中使用 CDR 监控。 同样，您可能想要在雷德蒙站点中保留60天的监视数据，但只需要在都柏林网站中保留此类型的数据30天。 Lync Server 2013 允许你在网站范围内创建单独的 CDR 和 QoE 配置设置集合;这使你能够以不同的方式管理每个网站。 （这包括启用和禁用监视功能，以及配置管理设置，例如保留数据的时间。）

请注意，您既可以在部署监控前也可以在部署监控后做出此决定。例如，您可以先部署监控，然后使用全局设置管理整个组织。如果以后改变主意，例如可以为 Redmond 站点创建单独的设置集合，然后使用这些设置管理 Redmond 的监控。（在站点作用域内应用的设置始终优先于在全局作用域内应用的设置。）如果您再次改变主意，只需删除应用于 Redmond 站点的配置设置。删除站点设置集合后，全局设置集合将自动应用于该站点。

</div>

<span> </span>

</div>

</div>

</div>

