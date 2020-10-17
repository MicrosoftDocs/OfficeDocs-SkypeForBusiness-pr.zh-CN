---
title: Lync Server 2013：定义您的监控要求
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
ms.openlocfilehash: 6f116fec331c252934c42e624c36813218d8f9ca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504319"
---
# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>定义在 Lync Server 2013 中进行监视的要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-05_

简化了在 Microsoft Lync Server 2013 中进行监视的部署和安装还简化了定义组织的监控要求时所涉及的过程。 然而，在开始安装和配置 Lync Server 2013 之前，还应解决几个关键问题：

**您要监视哪种类型的数据？** Lync Server 2013 使您能够监视两种不同类型的数据：呼叫详细记录 (CDR) 数据和 (QoE) 数据的体验质量。 呼叫详细信息记录提供了一种跟踪 Lync Server 功能（如 IP 语音 (VoIP) 电话呼叫）的使用方式的方法。即时消息 (IM) ;文件传输;音频/视频 (A/V) 会议;和应用程序共享会话。 此信息可帮助您了解 (使用哪些 Lync Server 功能，哪些功能未) ，还会提供有关这些功能的使用时间的信息。 使用经验丰富的数据，可以维护组织中发出的音频和视频呼叫质量的记录，包括网络数据包丢失次数、背景噪音和 "抖动" (数据包延迟中的差异) 的情况。

如果选择在 Lync Server 2013 中启用监控，则可以同时启用 CDR 监控和 QoE 监控，也可以选择启用一种监控类型，同时使其他类型保持禁用状态。 例如，假设用户仅使用即时消息和文件传输，不进行音频或视频呼叫。 在这种情况下，可能没有理由启用 QoE 监控。 同样，Lync Server 还便于在部署监控后启用和禁用监控。 例如，您可能选择部署监控但最初禁用 QoE 监控。 如果用户开始遇到音频或视频呼叫问题，您可以启用 QoE 监控并使用该数据帮助排查和解决这些问题

在安装 Lync server 和安装 Lync Server 后安装监视时，没有特别优势 (或缺点) 安装 Lync Server。 需要谨记的一点是，在安装监控之前，必须选择一台计算机来承载后端监控存储，并且必须在该计算机上安装和配置支持的 SQL Server 版本，之后才能将该计算机用于监控。 如果已在计算机上安装了 SQL Server，并且该计算机已准备好使用，则可以在安装 Lync Server 的同时安装监视。 如果没有后端计算机准备就绪，则可以继续安装 Lync Server，然后在后端计算机准备好使用时安装监视。

**想要何时安装监控？** 可以在安装和配置 Lync Server 2013 时安装和配置监控;Lync Server 部署向导将向您提供在安装过程中将前端池与监控数据库相关联的机会。 或者，也可以在安装 Lync Server 本身后安装监视;可以通过使用拓扑生成器将前端池和服务器与监控数据库关联，然后发布修订后的拓扑来完成此操作。

**需要多少个后端监控数据库？** 单个监视数据库可以支持成千上万个用户 (为 Microsoft Lync Server 2010，据此估计，并置数据库的监视和存档可支持240000用户) 。 此外，一个监控数据库可以被多个前端池使用；如果组织中有三个前端池，则可以将全部三个池与同一后端存储关联。

这就意味着，对于许多组织来说，数据库容量并不是确定所需后端监控数据库数量时的决定因素。相反，网络速度可能是更重要的考虑事项。假设您有三个前端池，但其中一个池位于慢速网络连接。在这种情况下，您可能想要使用两个监控数据库：一个数据库为网络连接良好的两个池提供服务，另一个数据库为网络连接较慢的池提供服务。

在规划您的监控基础结构时，还应考虑 Lync Server 2013 支持使用镜像数据库。 “数据库镜像”提供了同时维护两个数据库副本，且每个数据库位于不同服务器上的方式。 任何时候将数据写入主数据库，相同的数据也会写入镜像数据库。 如果主数据库应失败或因其他原因而变得不可用，可以使用简单的 Lync Server PowerShell 命令 "故障转移" 到镜像数据库。 例如：

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

这对于规划来说很重要，仅仅因为镜像需要将所需数据库数量翻倍：除了各个主数据库，还需要第二个数据库作为镜像。

**你的 Lync Server 网站是否需要自己的自定义监视配置？** 安装 Lync Server 2013 时，还会安装 CDR 和 QoE 配置设置的全局集合;这些全局集合使您能够将相同的 CDR 和 QoE 设置应用于整个组织。 这在许多情况下将足够：比如通常您会想要为所有用户启用 CDR 监控。

但是，有时也可能需要对不同的网站应用不同的设置。 例如，您可能希望在 Redmond 网站中同时使用 CDR 和 QoE 监控，但仅在都柏林网站中使用 CDR 监控。 同样，您可能希望在 Redmond 网站中保留60天的监控数据，但只需在都柏林网站中维护此类型的数据30天。 Lync Server 2013 允许您在网站范围创建单独的 CDR 和 QoE 配置设置集合;这使您能够以不同的方式管理每个网站。  (这包括启用和禁用监控，以及配置管理设置，如保留数据的时间。 ) 

请注意，您既可以在部署监控前也可以在部署监控后做出此决定。例如，您可以先部署监控，然后使用全局设置管理整个组织。如果以后改变主意，例如可以为 Redmond 站点创建单独的设置集合，然后使用这些设置管理 Redmond 的监控。（在站点作用域内应用的设置始终优先于在全局作用域内应用的设置。）如果您再次改变主意，只需删除应用于 Redmond 站点的配置设置。删除站点设置集合后，全局设置集合将自动应用于该站点。

</div>

<span> </span>

</div>

</div>

</div>

