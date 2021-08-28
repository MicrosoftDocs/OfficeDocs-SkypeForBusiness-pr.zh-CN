---
title: 规划监控Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 摘要：在规划 Skype for Business Server 中的监控服务时，请查看Skype for Business Server。
ms.openlocfilehash: 561bff18f7c5c9a358513ab73c2ff272546f93c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620938"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>规划监控Skype for Business Server

**摘要：** 在规划 Skype for Business Server 中的监控服务时，请查看Skype for Business Server。

Skype for Business Server中的监控服务为管理员提供了一种收集其组织中发生通信会话的使用情况和质量数据的方法，从而允许管理员识别趋势和问题。 通过持续监视部署，可以尽早发现问题并保持组织用户的满意。

在 Skype for Business Server 中监控不需要单独的服务器角色 (与早期 Lync 版本部署中的情况) ;相反，监控服务内置在每个前端服务器中。 默认情况下，不启用监控Skype for Business Server。 本文将帮助您确定在初始部署配置期间还是之后启用Skype for Business Server，以及支持SQL活动所需的资源。 如果您不确定监视的是什么或不监控，以及监视功能如何有用，请转到有关监控 [的基础知识](monitoring.md#Basics)。 若要开始规划过程，请转到定义 [监控要求](monitoring.md#requirements)。 有关监控要求的详细信息SQL，请转到监视SQL[要求](monitoring.md#topologies)。

## <a name="basics-about-monitoring"></a>监控基础知识
<a name="Basics"> </a>

会话是用户与：

- 会议

- 会议工具，例如音频/视频或应用程序共享

- 通过点对点对话（如即时消息或音频呼叫）的其他用户

> [!NOTE]
> Skype for Business Server跟踪有关每个会话的信息：谁致电谁;会话中使用了哪些终结点;会话持续多久;会话的感知质量是什么;等。 Skype for Business Server不会记录和存储实际调用本身。 这包括即时消息会话：尽管Skype for Business Server有关即时消息会话的信息，但它不会维护会话期间发送的每个即时消息的记录。

每个会话的呼叫Skype for Business Server的详细信息可用于：

- **投资回报率 (ROI)** 分析。 管理员可以将使用情况数据与为其以前的电话系统收集的类似数据进行比较，以显示节约的成本并帮助证明部署 Skype for Business Server。

- **设备库存管理**。 资产管理信息可帮助管理员识别仍在使用中需要替换的旧设备，并确定未使用或未使用不足的昂贵设备。

- **技术支持**。 数据疑难解答可帮助支持工程师确定用户的呼叫失败的原因，而无需收集服务器或客户端日志。 如果支持人员对 Skype for Business 和 Skype for Business Server 没有深入的技术知识，就可以轻松访问和理解Skype for Business Server。

- **系统故障排除**。使管理员能够检测可能阻止最终用户执行基本任务（如加入会议、建立呼叫或发送即时消息）的重大问题。

监控还提供了一种机制，允许 SIP 终结点 (（如 Skype for Business) ）提供管理员将无法访问的疑难解答信息：

- **影响质量的媒体指标**。 这些指标处理呼叫本身的实际传输;它们提供一种作为整个网络的呼叫旅程的 travelogue。 这些 (包括数据包丢失、抖动和往返时间) 等指标提供有关从呼叫离开一个人终结点到呼叫到达另一个人终结点时呼叫发生的情况的信息。

- **报告给最终用户的问题**。 这些指标包括最终用户Skype for Business麦克风过远、说话声音过小、网络连接不佳或由于计算机上其他程序消耗可用资源而遇到质量不佳的情况，向最终用户显示的质量欠佳通知。

- **环境信息**。这些指标详细说明了呼叫质量因素，如所使用的麦克风和扬声器的类型、用户是否通过 VPN 连接进行连接以及用户是否使用无线连接。

在每个呼叫结束时，符合 SIP 的终结点将此信息传输到实现呼叫的前端服务器。 您不必执行任何操作就能让终结点传输该信息；该行为内置于 SIP 协议中。 但是，如果要收集和存储该信息，则需要安装和启用监控。 如果执行了安装并启用了监控，则呼叫信息将由前端服务器上运行的代理收集，并被中继到一对 SQL Server 数据库。 监控服务 ("统一数据收集代理"的形式) 并并到所有前端服务器。

## <a name="define-your-requirements-for-monitoring"></a>定义监视要求
<a name="requirements"> </a>

在开始安装和配置监控之前，仍有一些关键问题需要Skype for Business Server：

 **想要何时安装监控？** 可以在安装和配置监控功能的同时安装和配置Skype for Business Server;Skype for Business Server向导将提供在安装期间将前端池与监控数据库关联的机会。 或者，您可以在安装监控程序Skype for Business Server安装监控;为此，可以使用拓扑生成器将前端池和服务器与监控数据库关联，然后发布修改后的拓扑。

请记住，在SQL Server和配置监控之前，必须安装和配置此配置。 但是，你只需部署SQL Server本身;当您发布您的监控拓扑时，将Skype for Business Server数据库。

 **要监视哪种类型的数据？** Skype for Business Server监控两种常规类型的数据：呼叫详细记录 (CDR) 数据和用户体验质量 (QoE) 数据。 呼叫详细信息记录提供了一种跟踪呼叫功能（如 IP 语音Skype for Business Server VoIP (VoIP) 呼叫）的使用情况的方法;即时消息传输 (IM) ;文件传输;音频/视频 (A/V) 会议;和应用程序共享会话。 此信息可帮助你了解Skype for Business Server哪些功能 (以及哪些功能) 并提供有关这些功能何时使用的信息。 用户体验质量数据允许您维护组织中音频和视频呼叫的质量记录，包括丢失的网络数据包数量、背景噪音和"抖动"量 (数据包延迟差异) 。

如果选择在呼叫中启用监控Skype for Business Server可以同时启用 CDR 监控和 QoE 监控，也可以选择启用一种类型的监控，同时禁用另一种类型。 例如，假设用户仅使用即时消息和文件传输，不进行音频或视频呼叫。 在这种情况下，可能没有理由启用 QoE 监控。 同样，Skype for Business Server部署监控后，可以轻松启用和禁用监控。 例如，您可能选择部署监控但最初禁用 QoE 监控。 如果用户开始遇到音频或视频呼叫问题，您可以启用 QoE 监控并使用该数据帮助排查和解决这些问题

安装监控 (安装) 安装监控与安装监控Skype for Business Server安装监控相比，没有Skype for Business Server优势。 需要谨记的一点是，在安装监控之前，必须选择一台计算机来承载后端监控存储，并且必须在该计算机上安装和配置支持的 SQL Server 版本，之后才能将该计算机用于监控。 如果已在计算机上安装SQL Server，并且该计算机可供使用，可以在安装监控程序的同时安装Skype for Business Server。 如果没有准备好后端计算机，可以继续自行安装Skype for Business Server，然后在后端计算机可供使用时安装监控。

 **需要多少个后端监控数据库？** 估计用于监控和存档的并Skype for Business Server可支持 240，000) 。 此外，一个监控数据库可以被多个前端池使用；如果组织中有三个前端池，则可以将全部三个池与同一后端存储关联。

对于许多组织来说，在确定所需的后端监控数据库数量时，数据库容量不是决定因素。 相反，网络速度可能是更重要的考虑事项。 假设您有三个前端池，但其中一个池位于慢速网络连接。 在这种情况下，您可能想要使用两个监控数据库：一个数据库为网络连接良好的两个池提供服务，另一个数据库为网络连接较慢的池提供服务。

您还应考虑到，Skype for Business Server镜像数据库的使用。 “数据库镜像”提供了同时维护两个数据库副本，且每个数据库位于不同服务器上的方式。 任何时候将数据写入主数据库，相同的数据也会写入镜像数据库。 如果主数据库出现故障或不可用，可以使用简单的 PowerShell 命令"故障转移"到Skype for Business Server数据库。 例如：

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

这对于规划来说很重要，仅仅因为镜像需要将所需数据库数量翻倍：除了各个主数据库，还需要第二个数据库作为镜像。

 **您的网站Skype for Business Server自己的自定义监视配置吗？** 安装后Skype for Business Server还要安装 CDR 和 QoE 配置设置的全局集合;这些全局集合让你能够将相同的 CDR 和 QoE 设置应用到整个组织。 这在许多情况下将足够：比如通常您会想要为所有用户启用 CDR 监控。

但是，有时可能还需要将不同的设置应用到不同的网站。 例如，您可能想要在 Redmond 站点中同时使用 CDR 和 QoE 监控，但仅在 Dublin 站点中使用 CDR 监控。 同样，您可能希望在 Redmond 站点中将监控数据保留 60 天，但只需在 Dublin 站点中将此类数据保留 30 天。 Skype for Business Server允许您在站点范围创建单独的 CDR 和 QoE 配置设置集合;这使您能够以不同方式管理每个网站。  (包括启用和禁用监控以及配置管理设置（如数据保留时间）。) 

请注意，您既可以在部署监控前也可以在部署监控后做出此决定。例如，您可以先部署监控，然后使用全局设置管理整个组织。如果以后改变主意，例如可以为 Redmond 站点创建单独的设置集合，然后使用这些设置管理 Redmond 的监控。（在站点作用域内应用的设置始终优先于在全局作用域内应用的设置。）如果您再次改变主意，只需删除应用于 Redmond 站点的配置设置。删除站点设置集合后，全局设置集合将自动应用于该站点。

## <a name="sql-requirements-for-monitoring"></a>SQL要求
<a name="topologies"> </a>

启用监控时，会自动在每个前端服务器上安装并激活统一数据收集代理。 有关支持的版本SQL Server的详细信息，请参阅 Server requirements for [Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)

监控数据可以与SQL Server数据共享一个数据库实例。 通常，呼叫详细信息记录数据库 (LcsCdr) 用户体验质量数据库 (QoEMetrics) 共享同一SQL实例;这两个监控数据库通常位于与 LcsLog SQL存档数据库相同的 (实例) 。 关于这些实例SQL Server一个实际要求是，SQL Server实例仅限于以下项：

- 2015 Skype for Business Server数据库的一个实例。  (一般而言，不建议将监控数据库与后端数据库并在同一 SQL 实例中，甚至不要与后端数据库并位于同一计算机上。 尽管从技术上来说可能，但存在监控数据库占用后端数据库所需的磁盘空间的风险) 

- 呼叫详细信息记录数据库的一个实例。

- 用户体验质量数据库的一个实例。

- 存档数据库的一个实例。

换句话说，不能在同一个服务器实例中拥有两个 LcsCdr 数据库SQL Server。 如果需要 LcsCdr 数据库的多个实例，则需要配置多个 SQL Server。

## <a name="see-also"></a>另请参阅


[部署监控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)