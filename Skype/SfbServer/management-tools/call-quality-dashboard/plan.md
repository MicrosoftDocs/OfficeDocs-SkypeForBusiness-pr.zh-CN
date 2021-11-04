---
title: Skype for Business Server：规划通话质量仪表板
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 摘要：了解规划呼叫质量仪表板时要考虑的问题。
ms.openlocfilehash: 42b80c8e426f438a1608d3c71a41b20dd9d27a63
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777342"
---
# <a name="skype-for-business-server-plan-for-call-quality-dashboard"></a>Skype for Business Server：规划通话质量仪表板 
 
**摘要：** 了解规划呼叫质量仪表板时要考虑的问题。
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>呼叫质量Skype for Business Server概述

Skype for Business Server呼叫质量仪表板 (CQD) 是位于 Skype for Business Server 中监控服务器中用户体验质量数据库顶部的报告层。 CQD Microsoft SQL Server Analysis Services提供聚合使用情况和呼叫质量信息，以及筛选和透视数据集。 CQD 功能包括：
  
- **通过 CQD 的 QoE 存档组件对 QoE 数据进行存档存储。** QoE 存档组件可以存储 QoE 数据的持续时间比监控服务器长得多。 这允许一次最多对七个月的数据进行趋势和报告，并能够滑动报告窗口，只要数据多一点。
- **使用功能与速度报告和分析Microsoft SQL Server Analysis Services。** CQD 利用 Microsoft SQL Analysis Services提供快速摘要、筛选和透视功能，以通过分析多维数据集为仪表板提供电源。 报告执行速度和深入了解数据的能力可大大减少分析时间。
- **针对呼叫质量报告优化的新数据架构。** 多维数据集具有专为语音质量报告和调查设计的架构。 门户用户可以专注于报告任务，而不是找出 QoE 指标数据库架构如何映射到所需的视图。 QoE 存档和多维数据集的组合提供了一种抽象化，通过 CQD 降低了报告和分析的复杂性。 QoE 存档数据库架构还包含可以使用特定于部署的数据填充的表，以增强数据的总体值。
- **内置报表设计器和就地报表编辑。** 门户组件附带几个在呼叫质量方法之后建模的内置报告。 门户用户可以通过门户的编辑功能修改报告并创建新报告。
- **对报告结构和分析多维数据集数据的 Web API 访问。** 仪表板报告框架不是显示多维数据集数据的唯一方法。 CQD 提供了几个使用 HTML 和 JavaScript 从 CQD Web API 检索数据和以自定义格式呈现数据的示例。 通过结合使用报告编辑器和 CQD Web API，可以快速制作报告和自定义报表布局的原型。

> [!NOTE]
> 管理员现在可以使用[CQD](https://cqd.teams.microsoft.com) Skype for Business Server 3 管理 2019 (管理员凭据登录) 。 这需要混合实现并使用呼叫数据连接器与 () 。 请参阅 [规划呼叫数据连接器](../../../SfbHybrid/hybrid/plan-call-data-connector.md) ，了解有关启用省/市/县的详细信息。 有关 CQD 版本 3 的文档，请参阅打开并使用适用于 Microsoft Teams 和[Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)的呼叫质量仪表板，了解有关 CQD 版本 3 有关详细信息。

## <a name="cqd-design-goals"></a>CQD 设计目标

CQD 允许 IT 专业人员使用聚合数据来确定环境中遇到媒体质量问题的重点关注区域。 它使 IT Pro可以比较不同用户组的统计信息，并确定趋势和模式。 它并非专注于解决单个呼叫问题，而是侧重于确定适用于给定环境中许多用户的问题和解决方案。 
  
## <a name="call-quality-dashboard-components"></a>呼叫质量仪表板组件

呼叫质量仪表板由多个数据库、Microsoft SQL代理作业、进程和 Web 应用程序组成。 Microsoft SQL 代理作业定期将数据从 QoE 指标数据库复制到 QoE 存档数据库，并处理包含 QoE 存档数据库中的数据的多维数据集。 存储库数据库存储支持门户的报告定义。 门户提供对多维数据集数据的浏览器访问。 
  
CQD 组件（包括 QoE 存档、多维数据集和存储库数据库）可以安装在监控服务器上、安装在其自己的服务器上或安装在多台服务器上。 特定的安装方法取决于 CQD 的性能需求以及对同一服务器上其他进程的影响。 有关详细信息，请参阅本文稍后介绍的"CQD 的组件和拓扑"一节。
  
### <a name="architectural-overview"></a>体系结构概述

总之，CQD 需要以下元素：
  
- 两个数据库：存档数据库和存储库数据库。
    
- 一个 SSAS 多维数据集，用于可视化聚合数据 
    
- IIS 承载 CQD Web 门户
    
![CQD 组件。](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
相同的 CQD 体系结构支持 Lync Server 2013 和 Skype for Business。 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 和 Skype for Business 与 Lync 2013

 仅在Skype for Business环境中，以下功能可用：
  
- Wi-Fi信号强度报告
    
- Wi-Fi芯片集驱动程序的报告
    
- 评价我的呼叫数据 
    
## <a name="information-available-through-cqd"></a>通过 CQD 获取的信息

CQD 可以显示Skype for Business Server、视频和应用程序共享流计数、好通话与坏呼叫的计数，以及错误与良好呼叫的比率。 可以按许多不同的维度对视图进行切片和筛选。 CQD 从监控服务器中的 QoE 指标数据库绘制数据。 然后，将数据与客户提供的任何数据（如网络子网到建筑物的映射）合并，以生成"每个建筑物的呼叫质量"等报告。 
  
CQD 还将许多内部 QoE 数据 idiosyncies（如"呼叫方"和"被叫方"）抽象化，以便用户可以专注于围绕"服务器"和"客户端"生成报告视图。 按照呼叫质量方法，CQD 得到简化，以帮助确定许多质量欠佳的呼叫所共同的条件，这是改善呼叫质量的一项原则。
  
## <a name="viewing-data-in-cqd"></a>在 CQD 中查看数据

CQD 数据可通过 CQD 门户查看，可通过 REST API 调用访问。
  
### <a name="cqd-portal"></a>CQD 门户

门户是查看多维数据集中数据的最快方式。 门户附带多个可马上使用内置报告。 内置报告以结构化方式链接，以指导用户依次对呼叫数据进行较小和更小的切片。 内置报表还通过演示图表和表与不同透视表、筛选器和度量的组合来突出显示各种显示数据的方式。 访问门户的每个用户都可以拥有自己的一组报告，用户可以修改和共享这些报告。 有关 CQD Web 门户使用情况详细信息，请参阅使用呼叫[质量仪表板进行Skype for Business Server。](use.md)
  
CQD 门户支持的操作系统：Windows 8.1、Windows 8、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2016 (Skype for Business Server仅 2019 CQD) 。
  
CQD 门户支持的浏览器：Internet Explorer 11、Internet Explorer 10 和 Internet Explorer 9。
  
### <a name="rest-apis"></a>REST API

还可通过 REST API 调用访问多维数据集数据。 通过 REST API 调用检索到的数据可以通过 HTML 页面呈现。 用户可以利用查询速度和 CQD 的高级别架构，同时仍创建适合其业务需求的自定义报告。 有关 API 和示例详细信息，请参阅[开发通话质量仪表板Skype for Business Server。](develop.md) 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>定义组织的 CQD 要求

CQD 提供 QoE 数据存档，并快速而深入地分析呼叫质量数据。 以下指南可帮助你决定何时以及为什么部署 CQD。
  
### <a name="when-to-deploy-cqd"></a>何时部署 CQD

 **可以部署 CQD 以建立基线呼叫质量度量，即使组织没有遇到呼叫质量问题。** 建立基线呼叫质量度量非常重要，因为每个组织都有不同的组合，Wi-Fi有线和远程与办公室工作人员。 出现呼叫质量问题时，可以将最新的呼叫质量度量与之前的时间间隔进行比较。 通过 CQD 的趋势功能，可以轻松检测呼叫质量在一段时间的变化。
  
 **可以部署 CQD 以主动查找可能会影响呼叫质量的问题区域。** 即使组织的平均呼叫质量可能满足组织设定的目标，也可能有很多隐藏在平均指标后面的呼叫质量问题。 CQD 允许按 QoEMetrics 数据库中的多个维度细分呼叫质量指标，以类似数据透视表。 在对等组中排除异常是主动查找呼叫质量问题的一种快速方法。
  
 **如果组织中存在呼叫质量问题，应部署 CQD，以减少解决问题所需的时间。** CQD 通过提供快速的报告性能和动态向下钻取功能来简化现有通话质量调查。 CQD 设计用于多种工作流，这些工作流用于对环境的修复进行验证的呼叫质量调查。
  
### <a name="why-deploy-cqd"></a>为什么要部署 CQD

 **如果 QoE 报告需要发生超过 3 个月的数据，应部署 CQD。** QoEMetrics 数据库和监控服务器报告旨在保留和报告一小组数据。 QoE 指标数据库针对快速插入进行了优化，因此报告性能可能会受到大量呼叫或数据库的报告访问竞争的影响。 CQD 的 QoE 存档数据库提供了 QoE 指标数据的第二个副本，具有更长的保留功能。 门户还进行了优化，一次最多显示 7 个月的数据，并可以根据需要报告 QoE 存档中的所有数据。
  
 **如果需要自定义 QoE 报告，应部署 CQD。** 门户具有报告编辑器功能，可快速轻松地创建报表并制作报表原型。 它还使 REST API 可用于以编程方式访问多维数据集数据，从而允许使用 HTML/JavaScript 或许多其他框架进行自定义演示。 不再需要创作新的数据SQL来创建自定义数据视图用于报告。
  
 **如果现有 QoE 报告功能不符合组织所需的速度或深度，应部署 CQD。** CQD 附带许多内置报告。 报告将立即有用，并演示逐步钻取数据如何在每一级提供其他见解。 报告层次结构还有助于以逻辑方式管理大量报告，并有助于创建更易于访问和易于理解的更多报告。 CQD 不仅是提供速度和灵活性，而且还针对呼叫质量方法开发的工作流进行了优化。
  
## <a name="components-and-topologies-for-cqd"></a>CQD 的组件和拓扑

CQD 附带了若干个组件，它有助于了解每个组件的要求及其相互之间的关系，以获取最简单且性能最佳的工具部署。 下表介绍每个 CQD 组件的依赖组件。
  

|组件名称|从属组件|
|:-----|:-----|
|QoE 存档   |Microsoft SQL Server   |
|多维数据集   |Microsoft SQL ServerAnalysis Services   |
|门户   |Microsoft Information Services   |
|存储库服务 (门户安装服务的一)    |Microsoft SQL Server   |
   
> [!NOTE]
> 对于 QoE 存档和多维数据集，某些部署选项需要商业智能Enterprise或 Microsoft SQL Server。 有关更多详细信息，请参阅下面的 [CQD](plan.md#Infrastructure_Req) 基础结构要求部分。
  
![CQD 组件。](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>单服务器配置

所有 CQD 组件和依赖组件都可以安装到一台计算机中。 单盒配置是最简单的配置，允许 CQD 自我包含。 CQD 只需访问监控服务器上 QoE 指标数据库。 CQD 服务器可以是独立计算机、虚拟机，或者甚至可以是监控服务器，具体取决于主机的可用资源和性能要求。 
  
在安装过程中，执行安装的用户只需提供之前在要安装 CQD 的计算机上安装的 Microsoft SQL Server 和 Microsoft SQL Server Analysis Services 实例。 有关详细信息，请参阅[部署呼叫质量Skype for Business Server](deploy-0.md)了解详细信息。
  
### <a name="multiserver-configuration"></a>多服务器配置

在多服务器配置中，QoE 存档、多维数据集和门户可以全部位于不同的计算机上。 多服务器配置有两个主要用途：
  
- 在不同的服务器上承载 CQD Web 门户和 CQD 多维数据集。
    
- 托管独立于"生产"门户的"开发"门户。 
    
  **在不同的计算机上承载 CQD Web 门户和 CQD 多维数据集。** 组织可能要求将 CQD 门户与 SQL Server 安装分开，或者可能希望混合并匹配 SQL Server 实例和 SQL Server Analysis Services 实例的 SQL Server 版本，可以选择在不同的计算机上安装 CQD 门户和 CQD 多维数据集。 如果组织只是希望采用一种持续方法来存档 QoE 数据，而未达到监控服务器上的性能限制，则 QoE 存档组件还可以是安装的唯一 CQD 组件。
  
![单服务器 CQD。](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **托管独立于"生产"门户的"开发"门户。** 通过 REST API (开发自己的自定义报告的组织) 可能希望将其他 (CQD) 门户实例与常规用户访问用于通话质量监视或调查的生产门户一起部署。 开发门户可以将对门户所做的任何修改与生产环境隔离。 其他 Web 门户可以部署在不同的计算机上 (如下所示) 或部署到同一计算机上不同的 Web 目录 (未) 。 若要完成后者，其他 CQD Web 门户必须手动复制到生产计算机，因为 CQD 安装过程始终使用预定义的 Web 应用程序名称将 CQD Web 门户部署到默认网站。
  
![规划 CQD 多服务器。](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>受支持的拓扑

CQD 不合并来自多个 QoEMetrics 数据库的数据，就像存在多个 Skype for Business Server 拓扑的情况一样，每个拓扑都有自己的监控服务器。 每个 CQD 实例必须指向一个 QoEMetrics 数据库。 但是，由于 CQD 将迁移监控服务器中的大部分报告工作负载，因此需要按 Skype for Business Server 拓扑部署一台监控服务器的大型组织应考虑将一台监控服务器用于所有拓扑。
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD 的基础结构要求
<a name="Infrastructure_Req"> </a>

CQD（包括所有组件和依赖组件）可以部署在虚拟机、单台计算机或跨多台计算机。 下面列出了最低软件和硬件要求。 数据可用性和查询性能可能会因用户和硬件Skype for Business Server配置而因分钟而异，因此下面列出了一些性能度量。
  

|对于 CQD 2015 |&nbsp;  |
|:-----|:-----|
|支持的操作系统   |WindowsServer 2008 R2、Windows Server 2012、Windows Server 2012 R2   |
|支持SQL Server   |SQL Server 2012、SQL Server 2014、SQL Server 2016   |


|对于 CQD 2019  |&nbsp;  |
|:-----|:-----|
|支持的操作系统   |Windows Server 2016，Windows Server 2019   |
|支持SQL Server   |2017 SQL Server 2019 SQL Server 2019   |
   
CQD 利用 Microsoft SQL Server、Microsoft SQL Server Analysis Services 和 Microsoft Internet Information Services，因此 CQD 的最低硬件和软件要求基本上与这些相关组件相同。 但是，根据组织对数据新鲜度要求 (数据新鲜度要求部分取决于组织生成的 QoE 数据量) 和部署成本，应考虑其他部署注意事项。
  
CQD 中的数据处理分为两个主要阶段： 
  
- QoE 存档过程
    
- CQD 多维数据集处理
    
  **QoE 存档处理。** QoE 存档处理任务将数据从监控服务器的 QoE 指标数据库复制到 QoE 存档数据库。 在两种情况下，任务的处理时间将具有完全不同的性能特征。 第一个是在 CQD 初始安装之后。 全新安装后首次运行该任务时，QoE 存档处理任务将 QoE 指标数据库中的所有数据复制到 QoE 存档数据库中。 第二种是在此初始轮之后进行定期处理。 QoE 存档处理任务将每 15 分钟运行一次，并处理 QoE 指标数据库中的任何新 QoE 记录。 通常，初始处理时间不是问题，因为它仅在安装 CQD 时第一次运行。 但是，如果 CQD 服务器的设置严重不足，此任务可能需要几个小时。 请参阅下表，例如初始 QoE 存档处理时间。
  
  **CQD 多维数据集处理。** 多维数据集处理任务将数据从 QoE 存档数据库聚合到多维数据集中。 初始多维数据集处理时间和后续多维数据集处理时间由用于 CQD SQL Server Analysis Services的多维数据集版本决定。 如果使用 Standard 版本，则初始多维数据集处理时间和后续多维数据集处理时间之间没有区别，因为每次刷新多维数据集数据时，它始终会完全处理所有可用数据。  (这意味着多维数据集处理时间会随着 QoE 存档数据库中的数据量增加而增加。) 因为 SQL Server 的商业智能版本和 Enterprise Edition 具有分区支持，所以如果使用任一版本，则只有初始运行将处理 QoE 存档数据库中的所有数据。 在后续运行中，当每 15 分钟触发一次任务时，该任务将仅处理自上次运行该任务以来添加到 QoE 存档数据库的新记录。 一天一次，还将对包含当前月份数据的分区进行完全处理。
  
物理计算机特征可能会影响 CQD 性能以及可从物理计算机组件SQL Server功能。 与其他组件相比，QoE 存档组件将占用更多的磁盘，而多维数据集组件将占用更多的 CPU 和内存。 所有这些因素都会影响 CQD 的总数据处理时间，这直接影响数据新鲜性和可用性。 组织应基于组织的个人需求对硬件和软件做出决策。 
  
### <a name="tested-hardware-configurations"></a>测试的硬件配置

本节假定环境中只有一个 QoEMetrics DB。 
  
**计算机配置文件**

|计算机|CPU 内核|RAM|同一磁盘上的 QoE 存档和多维数据集|QoE 存档和SQL磁盘上的 Temp DB|
|:-----|:-----|:-----|:-----|:-----|
|虚拟机   |4    |7 GB   |是   |是   |
|4 核   |4    |20 GB   |是   |否   |
|8 核   |8    |32 GB   |是   |否   |
|16 核   |16   |128 GB   |否   |否   |
   
**性能结果**

|计算机|QoE 指标数据库大小|SQL分区|磁盘类型|流的数量|初始存档过程|初始多维数据集过程|后续存档过程|后续多维数据集进程|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|虚拟机   |900 MB   |单精度   |VHD (可变大小)    |.5 M   |30 m   |2 m   |30 s   |1 m   |
|虚拟机   |9 GB   |单精度   |VHD (可变大小)    |5 M   |4 h   |15 m   |1 m   |5 m   |
|虚拟机   |9 GB   |单精度   |VHD (固定大小)    |5 M   |2 h   |5 m   |1 m   |5 m   |
|虚拟机   |30+ GB   |单精度   |VHD (固定大小)    |10 M   |15 h   |20 m   |2 m   |45 m   |
|8 核   |9 GB   |单精度   |多个磁盘   |5 M   |2 h   |5 m   |25 s   |5 m   |
|8 核   |9 GB   |多个   |多个磁盘   |5 M   |2 h   |15 m   |35 s   |2 m   |
|8 核   |30+ GB   |单精度   |多个磁盘   |20 M   |9 h   |20 m   |1 m   |20 m   |
|8 核   |30+ GB   |多个   |多个磁盘   |20 M   |9 h   |30 m   |2 m   |2 m   |
|4 核   |200 GB   |单精度   |多个磁盘   |125 M   |6 天以上   |7 h   |2 m   |6 h   |
|16 核   |500 GB   |多个   |多个心轴   |250 M   |8 天   |2 h   |2 m   |10 m   |
   
\*预计实际部署中不会遇到这些错误，因为 QoE 指标数据库必须分别具有 9 个月和 18 个月的数据，但此处提供了它们，以用于实现完整性。
  
### <a name="service-account-requirements"></a>服务帐户要求

您需要具有 QoEMetrics (读访问权限的帐户) CQD Server 上的 SQL 代理可以使用该帐户将数据导入 QoEArchiveDB。
  
您可能还需要为 SSAS 作业配置单独的帐户，以从 QoEArchiveDB 拉取数据 (这是一个可选) 。
  
IIS 最常使用网络服务作为应用程序池标识，但可以配置为服务帐户。
  
### <a name="portal-access-control"></a>门户访问控制

默认情况下，任何经过身份验证的用户都有访问权限。 这可以通过使用 IIS 授权规则来限制为特定组进行更改。
  
### <a name="pre-install-requirements"></a>预安装要求

这些说明假定 QoE 指标数据库已安装，并且正在该拓扑中的Skype for Business Server运行。
  
#### <a name="hardware-requirements"></a>硬件要求

CQD 利用 Microsoft SQL Server、Microsoft SQL Analysis Server 和 Microsoft Internet Information Server，因此 CQD 的最低硬件和软件要求基本上与这些相关组件相同。 但是，根据组织对数据新鲜度要求 (数据新鲜度要求部分取决于组织生成的 QoE 数据量) 和部署成本，应考虑其他部署注意事项。
  
#### <a name="software-requirements"></a>软件要求

CQD 需要以下操作系统：
  
- Windows带 IIS 7.5 的服务器 2008 R2
    
- Windows Server 2012 IIS 8.0
    
- Windows Server 2012R2 与 IIS 8.5

- Windows Server 2016 2019 CQD (Skype for Business Server IIS 10.0) 

- WindowsServer 2019 (Skype for Business Server 2019 CQD 仅) 
    
以下是按层次结构顺序 (IIS 角色服务) ：
  
- Web 服务器
    
  - 常见的 HTTP 功能
    
  - 静态内容
    
  - 默认文档
    
  - 应用程序开发
    
  - ASP.NET
    
  - ISAPI 筛选器
    
  - 运行状况 &amp; 诊断
    
  - HTTP 日志记录
    
  - 安全性
    
  - URL 授权
    
  - Windows 身份验证
    
  - 管理工具
    
  - IIS 管理控制台
    
> [!NOTE]
>  请注意以下上述要求：> .Net 框架的 3.5 和 4.5 版本可用。 这两个 (更具体地说，3.5 SP1 是必需的) .> 在某些系统中，如果在 IIS 安装之前设置 ASP.NET，则 ASP.NET 可能不会在 IIS 中注册。 由于相应 .Net 版本没有应用程序池，并且应用程序池配置中也缺少 .NET CLR 版本，问题清单。 若要在 Windows Server 2008 R2 上更正此问题，请执行 `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` 。 在 Windows Server 2012 和 Windows Server 2012 R2 上，执行后从 IIS 管理器中的默认网站中删除"ServiceModel"模块。> 管理工具是可选的，但建议这样做 `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` 。
  
若要使用 PowerShell 安装这些要求，请运行以下代码：
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

支持以下版本的SQL Server支持：

- CQD 2015：SQL Server 2012、SQL Server 2014、SQL Server 2016
- CQD 2019：SQL Server 2017、SQL Server 2019 
    
出于性能Enterprise建议使用商业智能或商业智能版本。 这些版本允许使用多个可以并行处理的分区文件，这有利于处理跨越几个月或更长时间的数据。 
  
虽然不建议使用，但也支持标准版。 处理将限定于单个分区 (在安装程序期间需要配置) 。 
  
必须安装"数据库引擎服务"和"Analysis Services"。 建议安装"管理工具 - 完成"功能，但不要求安装此功能，该功能SQL Server Management Studio支持Analysis Services。 功能选择屏幕应如图所示。
  
![SQL Server功能要求。](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
配置 SSAS 安装程序时，在"Analysis Services配置"中，将"服务器模式"设置为"多维和数据挖掘模式"。 
  
有关安装和配置商业智能功能的其他SQL Server，请参阅在多维Analysis Services和数据挖掘模式下[安装数据库](/previous-versions/sql/sql-server-2012/ms143708(v=sql.110))。
  
#### <a name="account-requirements"></a>帐户要求

根据最小特权原则建议使用三个域服务帐户： 
  
- 具有 QoE 指标数据库 (的登录安全主体（具有 db_datareader 特权) ）和 QoE 存档 SQL Server 实例 (（在设置) 期间创建链接服务器对象所需的登录安全主体）的登录安全主体。 此帐户将用于运行管理代理作业的"QoE 存档SQL Server步骤。
    
    > [!NOTE]
    > 如果您在严格锁定的环境中工作，则需要检查此服务帐户是否确实被授予了"以批处理作业登录"和"允许在本地登录"用户对 QoE 指标监控数据库 SQL Server 和 QoE 存档 SQL Server 的权限。
    
- 用于运行代理作业的"进程多维数据集"SQL Server之一。 安装程序将创建具有读取和写入权限 (QoE 存档数据库 (的登录安全主体) 还将在 QoE 角色 (中为多维数据集创建具有完全控制权限) 的成员。
    
- 用于为 Web 门户和 Web API 运行 IIS 工作进程的进程。 安装程序将创建具有读取权限) 的 QoE 存档数据库 (的登录安全主体、具有读取和写入权限) 的存储库数据库 (的登录安全主体以及 QoERole (中具有多维数据集的完全控制权限) 的成员。 
    
    > [!NOTE]
    > 当 QoE 存档数据库和存储库数据库都承载在同一个SQL Server中时，只会创建一个具有两个用户映射的登录安全主体。 
  
在逻辑上，可以将前两个帐户视为"后端服务帐户"，最后一个帐户是"前端服务帐户"。 虽然不建议这样做，但可能在所有情况下都使用单个帐户。
  
> [!NOTE]
> 启动安装的用户帐户必须具有对 QoE 指标数据库以及 (的读取权限，此外，还必须对必须在其中执行安装的 QoE 存档 DB 服务器拥有计算机管理员) 。 
  
## <a name="capacity-planning"></a>容量规划
<a name="Infrastructure_Req"> </a>

CQD 旨在将对 QoEMetrics 的影响降至最低：代码已优化为不锁定数据，并且导入作业是可设计的。
  
使用的硬件类型取决于同步应运行速度的要求。 磁盘大小调整如下：
  
- QoEArchive 最初比 QoEMetrics DB 大约 1.5 倍
    
- 与 DB 相比，SSIS 多维数据集几乎压缩 10 倍的数据
    
- 数据每月分区一次;可删除分区
