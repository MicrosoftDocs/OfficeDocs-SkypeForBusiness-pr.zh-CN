---
title: 在 Skype for Business 服务器中规划监视
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 摘要：在规划 Skype for Business 服务器中的监视服务时查看本主题。
ms.openlocfilehash: ebe94d3088e319a0c210c9d169f35f1c783ad5f5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991777"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>在 Skype for Business 服务器中规划监视

**摘要：** 在规划 Skype for Business 服务器中的监视服务时查看此主题。

"Skype for Business" 服务器中的 "监视服务" 为管理员收集组织中发生的通信会话的使用情况和质量数据提供了一种方式，从而使其能够识别趋势和问题。 持续监视你的部署使你能够尽早发现问题，并让你的组织的用户满意。

Skype for business 服务器中的监视不需要单独的服务器角色（与早期 Lync 版本中的情况相同）;而是将监视服务内置于每个前端服务器。 默认情况下，Skype for Business 服务器中不启用监视。 本文将帮助你确定在初始 Skype for Business 服务器配置期间还是之后启用监视，以及需要哪些 SQL 资源支持监视活动。 如果你不是很确定哪些内容被监控或哪些内容不被监控，以及监控有什么帮助，请参阅[监控基础知识](monitoring.md#Basics)。 要开始执行规划过程，请参阅[定义监控需求](monitoring.md#requirements)。 有关监控的 SQL 要求的详细信息，请参阅[监控的 SQL 要求](monitoring.md#topologies)。

## <a name="basics-about-monitoring"></a>监控基础知识
<a name="Basics"> </a>

会话是用户与 a 的连接的一般术语：

- 会议

- 会议工具，如音频/视频或应用程序共享

- 通过点对点对话（如即时消息或音频呼叫）的其他用户

> [!NOTE]
> Skype for Business 服务器跟踪有关每个会话的信息：谁称为谁;会话中使用了哪些终结点;该会话持续多长时间;会话的感知质量是多少;依此类推。 Skype for business 服务器不会记录和存储实际呼叫本身。 包括即时消息会话：虽然 Skype for Business 服务器记录有关即时消息会话的信息，但它不保留会话期间发送的每条即时消息的记录。

Skype for Business Server 为每个会话收集的基本呼叫详细信息可用于：

- **投资回报率 (ROI)** 分析。 管理员可以将使用数据与为其以前的电话系统收集的类似数据进行比较，以便显示成本节约并帮助论证 Skype for business 服务器的部署。

- **设备库存管理**。资产管理信息可帮助管理员识别需要更换但仍在使用的旧设备，以及未使用或未充分利用的昂贵设备。

- **技术支持**。 数据故障排除有助于支持工程师确定用户调用失败的原因，而无需收集服务器或客户端日志。 对于不具备 Skype for business 客户端和 Skype for business 服务器的深厚技术知识的支持人员，可随时访问和理解此信息。

- **系统故障排除**。使管理员能够检测可能阻止最终用户执行基本任务（如加入会议、建立呼叫或发送即时消息）的重大问题。

监视还提供允许 SIP 终结点（如 Skype for Business）提供管理员无权访问的故障排除信息的机制：

- **影响质量的媒体指标**。这些指标处理呼叫本身的实际传输；它们提供了关于呼叫在网络中的传输过程的旅行日志。这些指标（包括数据包丢失、抖动和来回行程时间）提供了呼叫从离开某个人的终结点到呼叫到达其他人员的终结点期间所经历事情的相关信息。

- **报告给最终用户的问题**。 这些指标包括在以下情况下，Skype for Business 向最终用户提供的信号质量较差：在以下情况下，Skype for Business 会向最终用户提供太远的通知：声音太远、网络连接较差或质量较差，因为另一个程序在计算机占用可用资源。

- **环境信息**。这些指标详细说明了呼叫质量因素，如所使用的麦克风和扬声器的类型、用户是否通过 VPN 连接进行连接以及用户是否使用无线连接。

在每个呼叫结束时，符合 SIP 的终结点会将该信息传输到实现该呼叫的前端服务器。你不必执行任何操作就能让终结点传输该信息；该行为内置于 SIP 协议中。但是，如果要收集和存储该信息，则需要安装和启用监控。如果确实安装并启用了监控，则呼叫信息将由前端服务器上运行的代理收集，并被中继到一对 SQL Server 数据库。监控服务（采用“统一数据收集代理”的形式）并置到所有前端服务器中。

## <a name="define-your-requirements-for-monitoring"></a>定义监控要求
<a name="requirements"> </a>

在开始通过 Skype for Business 服务器安装和配置监视之前，还应解决几个关键问题：

 **想要何时安装监控？** 可以在安装和配置 Skype for business 服务器的同时安装和配置监视;Skype for Business 服务器部署向导将向你提供在安装期间将前端池与监视数据库相关联的机会。 或者，您也可以在安装 Skype for Business 服务器后安装监视;可通过使用拓扑生成器将前端池和服务器与监视数据库相关联，然后发布已修改的拓扑来执行此操作。

请记住，必须先安装并配置 SQL Server，然后再部署和配置监控。 但是，你只需部署 SQL Server 本身;当你发布 Skype for Business Server 拓扑时，将为你创建监视数据库。

 **您想要监视何种类型的数据？** Skype for Business 服务器使你能够监视两种常规类型的数据：调用详细记录（CDR）数据和体验质量（QoE）数据。 呼叫详细记录提供了一种跟踪 Skype for Business 服务器功能（如 IP 语音电话（VoIP）电话呼叫）的使用方式的方法。即时消息（IM）;文件传输;音频/视频（A/V）会议;和应用程序共享会话。 此信息可帮助你了解使用的是哪些 Skype for business 服务器功能（以及哪些功能不是），还会提供有关何时使用这些功能的信息。 体验数据质量允许您维护组织中发出的音频和视频通话质量的记录，包括网络数据包丢失、背景噪音和 "抖动" （数据包延迟的差异）的数量。

如果你选择在 Skype for Business 服务器中启用监视，你可以同时启用 CDR 监视和 QoE 监视，或者你可以选择启用一种类型的监视，同时禁用另一种类型。 例如，假设用户仅使用即时消息和文件传输，不进行音频或视频呼叫。 在这种情况下，可能没有理由启用 QoE 监控。 同样，Skype for business 服务器使您能够轻松地在部署监视后启用和禁用监控。 例如，您可能选择部署监控但最初禁用 QoE 监控。 如果用户开始遇到音频或视频呼叫问题，您可以启用 QoE 监控并使用该数据帮助排查和解决这些问题

安装 skype for business Server 和安装 Skype for business 服务器后安装监视功能时，没有特殊的优势（或缺点）。 需要谨记的一点是，在安装监控之前，必须选择一台计算机来承载后端监控存储，并且必须在该计算机上安装和配置支持的 SQL Server 版本，之后才能将该计算机用于监控。 如果你已在计算机上安装了 SQL Server，并且该计算机已准备好使用，则可以在安装 Skype for Business 服务器时安装监视。 如果你没有后端计算机准备就绪，你可以继续安装 Skype for business 服务器，然后在后端计算机准备好使用时安装监视。

 **需要多少个后端监控数据库？** 预计监视和存档的 collocated 数据库可能支持 240000 Skype for Business Server 用户）。 此外，一个监控数据库可以被多个前端池使用；如果组织中有三个前端池，则可以将全部三个池与同一后端存储关联。

对于许多组织来说，数据库容量并不是确定所需后端监控数据库数量的决定因素。相反，网络速度可能是更重要的考虑事项。假设你有三个前端池，但其中一个池位于慢速网络连接。在这种情况下，你可能想要使用两个监控数据库：一个数据库为网络连接良好的两个池提供服务，另一个数据库为网络连接较慢的池提供服务。

您还应考虑 Skype for Business 服务器是否支持使用镜像数据库。 “数据库镜像”提供了同时维护两个数据库副本，且每个数据库位于不同服务器上的方式。 每当将数据写入主数据库时，相同的数据也会写入镜像数据库。 如果主数据库出现故障或以其他方式变为不可用，则可以通过使用简单的 Skype for Business 服务器 PowerShell 命令，将故障转移到镜像数据库。 例如：

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

这对于规划来说很重要，仅仅因为镜像需要将所需数据库数量翻倍：除了各个主数据库，还需要第二个数据库作为镜像。

 **您的 Skype for Business 服务器网站是否需要自己的自定义监视配置？** 安装 Skype for Business 服务器时，还会安装 CDR 和 QoE 配置设置的全局集合;这些全局集合让你能够将相同的 CDR 和 QoE 设置应用到整个组织。 In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

但是，有时也可能需要对不同的网站应用不同的设置。 例如，您可能希望在 Redmond 网站中同时使用 CDR 和 QoE 监视，但仅在都柏林网站中使用 CDR 监控。 同样，您可能想要在雷德蒙站点中保留60天的监视数据，但只需要在都柏林网站中保留此类型的数据30天。 Skype for Business 服务器允许你在网站范围内创建单独的 CDR 和 QoE 配置设置集合;这使你能够以不同的方式管理每个网站。 （这包括启用和禁用监视功能，以及配置管理设置，例如保留数据的时间。）

请注意，您既可以在部署监控前也可以在部署监控后做出此决定。例如，您可以先部署监控，然后使用全局设置管理整个组织。如果以后改变主意，例如可以为 Redmond 站点创建单独的设置集合，然后使用这些设置管理 Redmond 的监控。（在站点作用域内应用的设置始终优先于在全局作用域内应用的设置。）如果您再次改变主意，只需删除应用于 Redmond 站点的配置设置。删除站点设置集合后，全局设置集合将自动应用于该站点。

## <a name="sql-requirements-for-monitoring"></a>监控的 SQL 要求
<a name="topologies"> </a>

当你启用监控时，会自动在每个前端服务器上安装并激活统一数据收集代理。 有关支持的 SQL Server 版本和其他详细信息，请参阅[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)

监控数据可以与其他类型的数据共享 SQL Server 实例。通常，呼叫详细信息记录数据库 (LcsCdr) 和体验质量数据库 (QoEMetrics) 共享相同的 SQL 实例；这两个监控数据库与存档数据库 (LcsLog) 位于相同的 SQL 实例中也是很常见的。对 SQL Server 实例的唯一真正要求是，SQL Server 的任何一个实例仅限于以下各项：

- Skype for Business Server 2015 后端数据库的一个实例。 （作为一般规则，建议不要将监视数据库 collocated 在同一 SQL 实例中，甚至可以在同一台计算机上，而不是后端数据库。 尽管技术上可以使用后端数据库所需的磁盘空间来运行监视数据库的风险。）

- 呼叫详细信息记录数据库的一个实例。

- 体验质量数据库的一个实例。

- 存档数据库的一个实例。

换句话说，你不能在同一个 SQL Server 实例中拥有两个 LcsCdr 数据库实例。如果你需要多个 LcsCdr 数据库实例，则需要配置多个 SQL Server 实例。

## <a name="see-also"></a>另请参阅


[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
