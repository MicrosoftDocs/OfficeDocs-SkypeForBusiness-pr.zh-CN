---
title: 为 Skype for Business Server 规划通话质量仪表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 摘要：了解在为通话质量仪表板规划时应考虑的事项。
ms.openlocfilehash: 25342998332a596abce9ecd02e63e153be6e6d94
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029413"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>为 Skype for Business Server 规划通话质量仪表板 
 
**摘要：** 了解在为通话质量仪表板规划时应考虑的事项。
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Skype for Business Server 呼叫质量仪表板概述

Skype for Business Server 呼叫质量仪表板（CQD）是 Skype for business Server 中的监视服务器上的 "体验质量" 数据库顶部的报告层。 CQD 使用 Microsoft SQL Server Analysis Services 提供聚合使用率和呼叫质量信息，以及对数据集进行筛选和透视。 CQD 功能包括：
  
- **QoE 数据的存档存储（通过 CQD 的 QoE 存档组件）。** QoE 存档组件可以存储 QoE 数据的持续时间比监视服务器可以长得多。 这允许一次对最多七个月的数据进行趋势分析和报告，并能够将报告窗口滑回原来的数据。
- **使用 Microsoft SQL Server Analysis Services 的电源和速度进行报告和分析。** CQD 利用 Microsoft SQL Analysis Services 提供快速的摘要、筛选和透视功能，以便通过分析多维数据集为仪表板提供动力。 报告执行速度和向下钻取数据的能力可以显著减少分析时间。
- **为呼叫质量报告优化的新数据架构。** 多维数据集具有旨在实现语音质量报告和调查的架构。 门户用户可以将精力集中在报告任务上，而不是了解 QoE 指标数据库架构如何映射到所需的视图。 QoE 存档和多维数据集的组合提供了一个抽象，可通过 CQD 降低报告和分析的复杂性。 QoE 存档数据库架构还包含可使用特定于部署的数据填充的表，以增强数据的总体价值。
- **内置报表设计器和就地报表编辑。** 门户组件附带了多个内置报告，这些报告在通话质量方法之后建模。 门户用户可以修改报告，并通过门户的编辑功能创建新报告。
- **对报表结构和分析多维数据集数据的 Web API 访问。** 仪表板报告框架并不是显示多维数据集中的数据的唯一方法。 CQD 提供了使用 HTML 和 JavaScript 从 CQD Web Api 检索数据并以自定义格式呈现数据的几个示例。 报告编辑器和 CQD Web Api 的组合允许对报告和自定义报告布局进行快速原型设计。

> [!NOTE]
> 管理员现在可以使用[CQD 版本 3](https://cqd.teams.microsoft.com)管理 Skype For business Server 2019 （使用管理员凭据登录）。 这需要混合实施和使用呼叫数据连接器（CDC）。 有关启用 CDC 的详细信息，请参阅[Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) 。 有关 CQD 版本3的文档，请参阅[打开和使用呼叫质量仪表板 For Microsoft 团队和 Skype For Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) ，了解有关 CQD 版本3的详细信息。

## <a name="cqd-design-goals"></a>CQD 设计目标

CQD 使 IT 专业人员可以使用聚合数据来识别其环境中遇到媒体质量问题的焦点区域。 它允许 IT 专业人员比较不同用户组的统计信息，并确定趋势和模式。 它不侧重于解决单个呼叫问题，但在确定将适用于给定环境中的多个用户的问题和解决方案时。 
  
## <a name="call-quality-dashboard-components"></a>呼叫质量仪表板组件

呼叫质量仪表板由多个数据库、Microsoft SQL 代理作业、进程和 web 应用程序组成。 Microsoft SQL 代理作业定期将数据从 QoE 指标数据库复制到 QoE 存档数据库，并使用 QoE 存档数据库中的数据处理多维数据集。 存储库数据库存储了为门户供电的报告定义。 门户提供了对多维数据集数据的浏览器访问。 
  
CQD 组件（包括 QoE 存档、多维数据集和存储库数据库）可以安装在监视服务器上，也可以安装在自己的服务器上，也可以跨多台服务器安装。 特定安装方法取决于 CQD 的性能需求，以及对相同服务器上的其他进程的影响。 有关详细信息，请参阅本文后面的 "CQD 的组件和拓扑" 一节。
  
### <a name="architectural-overview"></a>体系结构概述

总而言之，CQD 需要以下元素：
  
- 两个数据库：一个存档数据库和一个存储库数据库。
    
- 一个 SSAS 多维数据集可视化聚合数据 
    
- IIS 主机 CQD Web 门户
    
![CQD 组件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
相同的 CQD 体系结构支持 Lync Server 2013 和 Skype for Business。 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 和 Skype for Business 与 Lync 2013

 仅在 Skype for business 环境中，可以使用以下功能：
  
- 信号强度的 wi-fi 报告
    
- 基于芯片组驱动程序的 wi-fi 报告
    
- 评价我的呼叫数据 
    
## <a name="information-available-through-cqd"></a>通过 CQD 提供的信息

CQD 可以显示 Skype for business Server 音频、视频和应用程序共享流计数，以及良好呼叫的良好与差呼叫计数以及坏的比率与正常呼叫的比率。 可以按多种不同的尺寸对视图进行切片和筛选。 CQD 从监控服务器中的 QoE 指标数据库中绘制数据。 然后，将数据与任何客户提供的数据（如网络子网之间的映射）合并，以使报告（如 "每个建筑物的呼叫质量"）成为可能。 
  
CQD 还会提取许多内部 QoE 数据特性（如 "调用方" 和 "被叫方"），以便用户可以专注于围绕 "server" 和 "client" 生成报告视图。 按照呼叫质量方法，CQD 简化了少的条件，以帮助确定较差的呼叫的常见条件，这是提高通话质量的原则之一。
  
## <a name="viewing-data-in-cqd"></a>查看 CQD 中的数据

可以通过 CQD 门户查看 CQD 数据，并通过 REST API 调用访问这些数据。
  
### <a name="cqd-portal"></a>CQD 门户

门户是查看多维数据集中的数据的最快方法。 门户附带有几个可立即使用的内置报告。 内置报告以结构化方式进行链接，以指导用户连续缩小和较小的呼叫数据切片。 内置报告还突出显示了使用不同透视、筛选器和度量值的图表和表的组合来显示数据的各种不同方法。 访问门户的每个用户都可以拥有他或她自己可以修改和共享的自己的报告集。 有关 CQD Web 门户用法的详细信息，请参阅[使用呼叫质量仪表板获取 Skype For Business Server](use.md)。
  
CQD 门户支持的操作系统： Windows 8.1、Windows 8、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2016 （仅适用于 Skype for Business Server 2019 CQD）。
  
支持的 CQD 门户浏览器： Internet Explorer 11、Internet Explorer 10 和 Internet Explorer 9。
  
### <a name="rest-apis"></a>REST API

也可以通过 REST API 调用访问多维数据集数据。 通过 REST API 调用检索的数据可以通过 HTML 页面呈现。 用户可以利用 CQD 的查询速度和高级别架构，同时仍创建适合其业务需求的自定义报告。 有关 API 和示例的详细信息，请参阅[开发适用于 Skype For Business Server 的呼叫质量仪表板](develop.md)。 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>定义组织对 CQD 的要求

CQD 提供了 QoE 数据存档和对呼叫质量数据的快速和深入分析。 以下指南可帮助您确定部署 CQD 的时间和原因。
  
### <a name="when-to-deploy-cqd"></a>何时部署 CQD

 **可以部署 CQD 以建立基准呼叫质量度量，即使组织不会遇到呼叫质量问题也是如此。** 建立基准呼叫质量度量非常重要，因为每个组织都有不同的 Wi-fi 与有线和远程与 office 工作人员的组合。 当出现通话质量问题时，可以将最近的呼叫质量测量值与之前的时间间隔进行比较。 CQD 的趋势功能允许在一段时间内轻松检测呼叫质量变化。
  
 **可以部署 CQD 以主动查找可能会影响呼叫质量的问题区域。** 即使组织的平均呼叫质量可能会满足组织设置的目标，也可能会有少的通话质量问题，这些问题在平均指标的标准之下。 CQD 允许 QoEMetrics 数据库中的多个维度以透视表的形式分解呼叫质量指标。 对等组中的 Spotting 离群离群是一种提前查找呼叫质量问题的快速方法。
  
 **如果组织中存在通话质量问题，则应部署 CQD，以减少解决问题所需的时间。** CQD 可以通过提供快速报告性能和动态深入查看功能来简化现有呼叫质量调查。 CQD 设计用于在通话质量调查中对环境进行修复验证的多种类型的工作流。
  
### <a name="why-deploy-cqd"></a>为什么要部署 CQD

 **如果需要对3个月以上的数据执行 QoE 报告，应部署 CQD。** QoEMetrics 数据库和监控服务器报表旨在保留和报告一小部分数据集。 QoE 指标数据库针对快速插入进行了优化，因此可以通过大量的呼叫或对数据库的竞争性报告访问来抑制报告性能。 CQD 的 QoE 存档数据库提供了 QoE 指标数据的第二个副本，保留能力较长。 门户还经过优化，可一次显示最长7个月的数据，并根据需要报告 QoE 存档中的所有数据。
  
 **如果需要自定义 QoE 报告，应部署 CQD。** 门户提供了一个报告编辑器功能，用于快速轻松地创建和原型报告。 此外，它还为编程访问多维数据集数据提供了可用的 REST Api，允许使用 HTML/JavaScript 或其他许多框架进行自定义演示文稿。 不再需要创作新的 SQL 查询，目的是为了创建用于报告的自定义数据视图。
  
 **如果现有 QoE 报告功能不符合组织所需的速度或深度，则应部署 CQD。** CQD 附带了许多内置报告。 这些报告可立即发挥作用，并演示如何以渐进方式深入查看数据，从而在每个级别提供其他见解。 报告层次结构还有助于以逻辑方式管理大量报告，并促使创建更易于访问且易于理解的更多报告。 CQD 不仅提供速度和灵活性，而且还针对由呼叫质量方法开发的工作流进行了优化。
  
## <a name="components-and-topologies-for-cqd"></a>CQD 的组件和拓扑

CQD 提供了多个组件，并有助于了解每个组件的要求以及它们彼此之间的关系，以获得最简单和最佳的工具部署。 下表描述了每个 CQD 组件的依赖组件。
  

|**组件名称**|**相关组件**|
|:-----|:-----|
|QoE 存档  <br/> |Microsoft SQL Server  <br/> |
|集  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|门户  <br/> |Microsoft 信息服务  <br/> |
|存储库服务（门户安装的一部分）  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> 对于 QoE 存档和多维数据集，某些部署选项需要 Microsoft SQL Server 的商业智能或企业版。 有关更多详细信息，请参阅下面的 CQD 部分的[基础结构要求](plan.md#Infrastructure_Req)。
  
![CQD 组件](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>单服务器配置

所有 CQD 组件和相关组件都可以安装到一台计算机上。 单框配置是最简单的配置，允许 CQD 自包含。 CQD 只需要访问监控服务器上的 QoE 指标数据库。 CQD 服务器可以是独立计算机，也可以是虚拟机，也可以是监视服务器，具体取决于主机的可用资源和性能要求。 
  
在安装过程中，执行安装的用户只需提供 Microsoft SQL Server 和 Microsoft SQL Server Analysis Services 实例（之前已在要安装 CQD 的计算机上设置）。 有关详细信息，请参阅[部署适用于 Skype For Business Server 的呼叫质量仪表板](deploy-0.md)。
  
### <a name="multiserver-configuration"></a>多服务器配置

在多服务器配置中，QoE 存档、多维数据集和门户都可以位于不同的计算机上。 多服务器配置主要有以下两种用途：
  
- 在不同的服务器上托管 CQD Web 门户和 CQD 多维数据集。
    
- 承载独立于 "生产" 门户的 "开发" 门户。 
    
  **在不同的计算机上托管 CQD Web 门户和 CQD 多维数据集。** 可能需要将 CQD 门户与 SQL Server 安装分开或可能需要混合和匹配 sql server 实例和 SQL Server Analysis Services 实例的 SQL Server 版本的组织可以选择安装 CQD 门户和不同计算机上的 CQD 多维数据集。 QoE 存档组件也可以是唯一的 CQD 组件，如果组织只想使用可持续方法来存档 QoE 数据，而不会在监视服务器上达到性能限制，则会安装该组件。
  
![单个服务器 CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **承载独立于 "生产" 门户的 "开发" 门户。** 开发自己的自定义报告（通过 REST Api）的组织可能更愿意在生产门户旁部署其他（CQD）门户实例，以便定期用户访问呼叫质量监控或调查。 开发门户可将对门户所做的任何修改从生产环境中分离出来。 可以在不同的计算机上部署其他 web 门户（如下所示），或将其部署到同一台计算机上的不同 web 目录（未显示）。 若要完成后者，必须手动将额外的 CQD web 门户复制到生产计算机，因为 CQD 安装过程总是使用预定义的 web 应用程序名称将 CQD Web 门户部署到默认网站。
  
![规划 CQD 多服务器](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>受支持的拓扑

CQD 不会合并多个 QoEMetrics 数据库中的数据，这是因为有多个 Skype for Business Server 拓扑，每个拓扑都有其自己的监控服务器。 每个 CQD 实例都必须指向一个 QoEMetrics 数据库。 但是，由于 CQD 将很多报告工作负载从监视服务器中移出，因此每个 Skype for Business Server 拓扑需要部署一个监视服务器的大型组织应考虑为所有拓扑使用一个监视服务器。
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD 的基础结构要求
<a name="Infrastructure_Req"> </a>

可以在虚拟机、单个计算机或多台计算机上部署 CQD，包括其所有组件和相关组件。 下面列出了最低软件和硬件要求。 数据可用性和查询性能可能会从几分钟到几小时，具体取决于活动 Skype for Business Server 用户和硬件和配置的数量，因此下面给出了一些性能指标。
  
|||
|:-----|:-----|
|对于 CQD 2015 <br/> |  <br/> |
|支持的操作系统  <br/> |Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2  <br/> |
|支持的 SQL Server  <br/> |SQL server 2012 sql Server 2014 sql Server 2016  <br/> |

|||
|:-----|:-----|
|对于 CQD 2019 <br/> |  <br/> |
|支持的操作系统  <br/> |Windows Server 2016、Windows Server 2019  <br/> |
|支持的 SQL Server  <br/> |SQL Server 2017 SQL Server 2019  <br/> |
   
CQD 利用 Microsoft SQL Server、Microsoft SQL Server Analysis Services 和 Microsoft Internet Information Services，因此 CQD 的最低硬件和软件要求基本上与这些依赖组件相同。 但是，根据组织对数据新鲜度的要求（取决于组织生成的 QoE 数据量的一部分）和部署成本，应执行其他部署注意事项。
  
CQD 中的数据处理分为两个主要阶段： 
  
- QoE 存档过程
    
- CQD 多维数据集处理
    
  **QoE 存档处理。** QoE 存档处理任务将数据从监视服务器上的 QoE 指标数据库复制到 QoE 存档数据库。 在以下两种情况下，任务的处理时间将具有基本不同的性能特征。 第一个是在 CQD 的初始安装之后。 当任务在进行全新安装后第一次运行时，QoE 存档处理任务会将 QoE 指标数据库中的所有数据复制到 QoE 存档数据库中。 第二个是此初始循环之后的定期处理。 QoE 存档处理任务将每15分钟运行一次，并处理 QoE 指标数据库中的任何新 QoE 记录。 通常情况下，初始处理时间不是一个问题，因为它仅在第一次安装 CQD 时运行。 但是，如果 CQD 服务器受到严格的预配，则此任务可能需要几个小时。 有关初始 QoE 存档处理时间的示例，请参阅下表。
  
  **CQD 多维数据集处理。** 多维数据集处理任务将 QoE 存档数据库中的数据聚合到多维数据集。 最初的多维数据集处理时间和后续的多维数据集处理时间由用于 CQD 多维数据集的 SQL Server Analysis Services 版本决定。 如果使用 Standard edition，则最初的多维数据集处理时间和后续多维数据集处理时间之间没有任何差异，因为每次刷新多维数据集数据时，它将始终是所有可用数据的完全处理。 （这意味着，随着 QoE 存档数据库中的数据量的增加，多维数据集的处理时间也会增加。由于 SQL Server 的商业智能版本和 Enterprise Edition 具有分区支持，如果使用任一版本，则只有初始运行将处理 QoE 存档数据库中的所有数据。 在后续运行中，每15分钟触发一次任务时，任务将仅处理自上次运行任务以来添加到 QoE 存档数据库中的新记录。 一天，还将对包含当前月份数据的分区进行完全处理。
  
物理计算机特征可能会影响 CQD 性能以及 SQL Server 组件中提供的软件功能。 与其他组件相比，QoE 存档组件会占用更多磁盘空间，而多维数据集组件则占用更多的 CPU 和内存。 所有这些因素都涉及 CQD 的总数据处理时间，这将直接影响数据新鲜度和可用性。 组织应根据组织的各个需求对硬件和软件做出决策。 
  
### <a name="tested-hardware-configurations"></a>测试的硬件配置

本部分假设环境中存在一个 QoEMetrics DB。 
  
**计算机配置文件**

|**计算机**|**CPU 内核**|**RAM**|**在同一磁盘上 QoE 存档和多维数据集**|**在同一磁盘上 QoE 存档和 SQL 临时数据库**|
|:-----|:-----|:-----|:-----|:-----|
|虚拟机  <br/> |4   <br/> |7 GB  <br/> |是  <br/> |是  <br/> |
|4核心  <br/> |4   <br/> |20 GB  <br/> |是  <br/> |否  <br/> |
|8核  <br/> |8   <br/> |32 GB  <br/> |是  <br/> |否  <br/> |
|16核  <br/> |16   <br/> |128 GB  <br/> |否  <br/> |否  <br/> |
   
**性能结果**

|**计算机**|**QoE 指标数据库大小**|**SQL 分区**|**磁盘类型**|**流的数量**|**初始存档过程**|**初始多维数据集进程**|**后续存档过程**|**后续多维数据集进程**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|虚拟机  <br/> |900 MB  <br/> |单精度  <br/> |VHD （可变大小）  <br/> |.5 M  <br/> |30米  <br/> |2米  <br/> |30秒  <br/> |1米  <br/> |
|虚拟机  <br/> |9 GB  <br/> |单精度  <br/> |VHD （可变大小）  <br/> |5米  <br/> |4 h  <br/> |15米  <br/> |1米  <br/> |5米  <br/> |
|虚拟机  <br/> |9 GB  <br/> |单精度  <br/> |VHD （固定大小）  <br/> |5米  <br/> |2 h  <br/> |5米  <br/> |1米  <br/> |5米  <br/> |
|虚拟机  <br/> |30 + GB  <br/> |单精度  <br/> |VHD （固定大小）  <br/> |10米  <br/> |15 h  <br/> |20米  <br/> |2米  <br/> |45米  <br/> |
|8核  <br/> |9 GB  <br/> |单精度  <br/> |多个磁盘  <br/> |5米  <br/> |2 h  <br/> |5米  <br/> |25 s  <br/> |5米  <br/> |
|8核  <br/> |9 GB  <br/> |多个  <br/> |多个磁盘  <br/> |5米  <br/> |2 h  <br/> |15米  <br/> |35 s  <br/> |2米  <br/> |
|8核  <br/> |30 + GB  <br/> |单精度  <br/> |多个磁盘  <br/> |20米  <br/> |9 h  <br/> |20米  <br/> |1米  <br/> |20米  <br/> |
|8核  <br/> |30 + GB  <br/> |多个  <br/> |多个磁盘  <br/> |20米  <br/> |9 h  <br/> |30米  <br/> |2米  <br/> |2米  <br/> |
|4核心  <br/> |200 GB  <br/> |单精度  <br/> |多个磁盘  <br/> |125米  <br/> |6 + 天  <br/> |7 h  <br/> |2米  <br/> |6 h  <br/> |
|16核  <br/> |500 GB  <br/> |多个  <br/> |多个心轴  <br/> |250米  <br/> |8天  <br/> |2 h  <br/> |2米  <br/> |10米  <br/> |
   
\*由于 QoE 指标数据库必须分别包含9和18个月的数据，因此不应在实际部署中遇到这些数据，但此处提供了这些数据是为了实现完整性。
  
### <a name="service-account-requirements"></a>服务帐户要求

你将需要 CQD 服务器上的 SQL 代理可用于将数据导入到 QoEArchiveDB 的帐户（具有对 QoEMetrics 的读取访问权限）。
  
您可能还需要为 SSAS 作业配置一个单独的帐户，以从 QoEArchiveDB 中提取数据（这是一个可选的过程）。
  
IIS 最常使用网络服务作为应用程序池标识，但可以配置为服务帐户。
  
### <a name="portal-access-control"></a>门户访问控制

默认情况下，任何已通过身份验证的用户都可以访问。 可以使用 IIS 授权规则对其进行更改以限制到特定的组。
  
### <a name="pre-install-requirements"></a>预安装要求

这些说明假定已安装 QoE 指标数据库并在 Skype for Business Server 拓扑中的某个位置运行。
  
#### <a name="hardware-requirements"></a>硬件要求

CQD 利用 Microsoft SQL Server、Microsoft SQL 分析服务器和 Microsoft Internet Information Server，因此 CQD 的最低硬件和软件要求基本上与那些依赖组件相同。 但是，根据组织对数据新鲜度的要求（取决于组织生成的 QoE 数据量的一部分）和部署成本，应执行其他部署注意事项。
  
#### <a name="software-requirements"></a>软件要求

CQD 需要以下操作系统：
  
- Windows Server 2008 R2 （包含 IIS 7.5）
    
- Windows Server 2012 with IIS 8。0
    
- Windows Server 2012 R2 （包含 IIS 8.5）

- Windows Server 2016 with IIS 10.0 （Skype for Business Server 2019 CQD）

- Windows Server 2019 （仅适用于 Skype for Business Server 2019 CQD）
    
以下是必需的 IIS 角色服务（按层次结构顺序）：
  
- Web 服务器
    
  - 常见的 HTTP 功能
    
  - 静态内容
    
  - 默认文档
    
  - 应用程序开发
    
  - ASP.NET
    
  - ISAPI 筛选器
    
  - 运行&amp;状况诊断
    
  - HTTP 日志记录
    
  - 安全性
    
  - URL 授权
    
  - Windows 身份验证
    
  - 管理工具
    
  - IIS 管理控制台
    
> [!NOTE]
>  请注意以下针对上述要求的以下内容： .Net framework > 3.5 和4.5 版本可用。 两者都是必需的（更具体地说，是必需的 3.5 SP1）。在某些系统中 >，如果 ASP.NET 是在安装 IIS 之前设置的，则 ASP.NET 可能不会在 IIS 中注册。 通过缺少对应 .Net 版本的应用程序池，并在应用程序池配置中也缺少 .NET CLR 版本的问题清单。 若要解决 Windows Server 2008 R2 上的此问题， `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`请执行。 在 Windows Server 2012 和 Windows Server 2012 R2 上， `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45`执行后再从 IIS Manager 中的默认网站删除 "未使用" 模块。 > 管理工具是可选的，但建议这样做。
  
若要使用 PowerShell 安装这些要求，请运行以下命令：
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

支持以下版本的 SQL Server：
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 （仅适用于 Skype for Business Server 2019 CQD）
    
出于性能方面的考虑，建议使用商业智能或企业版。 这些版本允许使用可并行处理的多个分区文件，这对于处理跨越多个月或更长时间的数据非常有用。 
  
尽管不建议这样做，但也支持标准版。 处理将被限制为单个分区（需要在安装过程中进行配置）。 
  
在所有情况下，必须安装 "数据库引擎服务" 和 "Analysis Services"。 建议但不需要安装 "管理工具-完成" 功能，这将为 Analysis Services 添加 SQL Server Management Studio 支持。 功能选择屏幕应如下图所示。
  
![SQL Server 功能要求](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
配置 SSAS 安装程序时，在 Analysis Services 配置中，将 "服务器模式" 设置为 "多维和数据挖掘模式"。 
  
有关安装和配置 SQL Server 商业智能功能的详细信息，请参阅[Install Analysis Services In 多维和数据挖掘模式](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx)。
  
#### <a name="account-requirements"></a>帐户要求

建议在最小特权原则上使用三个域服务帐户： 
  
- 一个已在 QoE 存档 SQL Server 实例中具有 QoE 指标数据库的登录安全主体（具有 db_datareader 特权）和登录安全主体（在安装过程中创建链接服务器对象）。 此帐户将用于运行 SQL Server 代理作业的 "QoE 存档数据" 步骤。
    
- 一个将用于运行 SQL Server 代理作业的 "处理多维数据集" 步骤。 安装程序将创建登录安全主体以 QoE 存档数据库（具有读取和写入权限），同时在多维数据集的 QoE 角色中创建一个成员（具有 "完全控制" 权限）。
    
- 一个将用于为 web 门户和 web Api 运行 IIS 工作进程。 安装程序将创建一个登录安全主体，以 QoE 存档数据库（具有读取权限）、存储库数据库的登录安全主体（具有读取和写入权限）以及对多维数据集的 QoERole （具有完全控制权限）中的成员。 
    
    > [!NOTE]
    > 当 QoE 存档数据库和存储库数据库都托管在同一 SQL Server 中时，只会创建一个具有两个用户映射的登录安全主体。 
  
前两个帐户可被逻辑视为 "后端服务帐户"，最后一个帐户是 "前端服务帐户"。 尽管不建议这样做，但在所有情况下都可以使用单个帐户。
  
> [!NOTE]
> 启动安装的用户帐户必须具有 QoE 指标 DB （除了必须在其上进行安装的 QoE 存档数据库服务器上的计算机管理员权限）的读取访问权限。 
  
## <a name="capacity-planning"></a>容量规划
<a name="Infrastructure_Req"> </a>

CQD 旨在实现对 QoEMetrics 的最小影响：代码已优化为不锁定数据，并且导入作业是可优化的。
  
要使用的硬件类型取决于您对同步运行速度的要求。 磁盘大小调整如下所示：
  
- QoEArchive ~ 1.5 x 大于 QoEMetrics DB 初始
    
- SSIS 多维数据集与数据库相比几乎10倍地压缩数据
    
- 按月对数据进行分区;可以删除分区
    

