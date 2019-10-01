---
title: 为 Skype for business 服务器计划通话质量仪表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 摘要：在为 "呼叫质量" 仪表板进行规划时，了解要考虑的事项。
ms.openlocfilehash: c98828f8fed3567a892e20dcab8040bb731c91f2
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328434"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>为 Skype for business 服务器计划通话质量仪表板 
 
**摘要：** 了解在针对 "呼叫质量" 仪表板进行规划时要考虑的事项。
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Skype for Business Server 通话质量仪表板概述

Skype for Business Server 通话质量仪表板（CQD）是 "Skype for business" 服务器的 "监视服务器" 中的 "体验质量" 数据库顶部的报告层。 CQD 使用 Microsoft SQL Server Analysis Services 提供聚合用法以及调用质量信息，以及在数据集上筛选和旋转。 CQD 功能包括：
  
- **QoE 数据的归档存储通过 CQD 的 QoE 存档组件进行存储。** QoE 存档组件可以存储 QoE 数据，其持续时间比监视服务器可以长得多。 这允许一次为多达7个月的数据进行趋势分析和报告，并且能够将报告窗口滑回最远的数据。
- **使用 Microsoft SQL Server Analysis Services 的电源和速度进行报告和分析。** CQD 利用 Microsoft SQL Analysis Services 提供快速摘要、筛选和透视功能，以便通过分析多维数据集为仪表板供电。 报告执行速度和向下钻取到数据的功能可显著减少分析时间。
- **为通话质量报告优化的新数据架构。** 多维数据集具有设计用于语音质量报告和调查的架构。 门户用户可以专注于报告任务，而不是了解 QoE 指标数据库架构如何映射到所需的视图。 QoE 存档和多维数据集的组合提供了一个抽象，可通过 CQD 减少报告和分析的复杂性。 QoE 存档数据库架构还包含可填充特定于部署的数据的表，以增强数据的总体价值。
- **内置报表设计器和就地报表编辑。** 门户组件附带了几个内置的报表，这些内置报表在通话质量方法后建模。 门户用户可以修改报表，并通过门户的编辑功能创建新报表。
- **对报表结构和分析多维数据集数据的 Web API 访问。** 仪表板报表框架不是显示多维数据集中的数据的唯一方式。 CQD 提供了使用 HTML 和 JavaScript 从 CQD Web Api 检索数据并以自定义格式呈现数据的一些示例。 报表编辑器和 CQD Web Api 的组合允许快速原型制作报表和自定义报表布局。

> [!NOTE]
> 管理员现在可以使用[CQD 版本 3](https://cqd.teams.microsoft.com) （使用管理员凭据登录）管理 Skype For business Server 2019。 这需要混合实现和使用 "调用数据连接器（CDC）"。 有关启用 CDC 的详细信息，请参阅[计划通话数据连接器](/SkypeForBusiness/hybrid/plan-call-data-connector)。 有关 CQD 版本3的文档，请参阅[打开和使用 Microsoft 团队和 Skype for Business Online 的呼叫质量仪表板](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)，了解有关 CQD 版本3的详细信息。

## <a name="cqd-design-goals"></a>CQD 设计目标

CQD 允许 IT 专业人员使用聚合数据来识别其环境中遇到媒体质量问题的重点关注区域。它允许 IT 专业人员比较不同用户组的统计信息，并识别趋势和模式。它重点关注的不是单个通话问题，而是识别适用于给定环境中许多用户的问题和解决方案。 
  
## <a name="call-quality-dashboard-components"></a>通话质量仪表板组件

通话质量仪表板由多个数据库、Microsoft SQL 代理作业、进程和 web 应用程序组成。 Microsoft SQL 代理作业会定期将 QoE 指标数据库中的数据复制到 QoE 存档数据库中，并将该多维数据集与 QoE 存档数据库中的数据一起处理。 存储库数据库存储了为门户供电的报表定义。 门户提供对多维数据集数据的浏览器访问。 
  
CQD 组件（包括 QoE 存档、多维数据集和存储库数据库）可安装在监视服务器上、安装在其自己的服务器上，或跨多台服务器安装。 特定安装方法取决于 CQD 的性能需求以及对同一服务器上的其他进程的影响。 有关详细信息，请参阅本文后面的 "CQD 的组件和拓扑" 部分。
  
### <a name="architectural-overview"></a>体系结构概述

总而言之，CQD 需要以下元素：
  
- 两个数据库：一个存档数据库和一个知识库数据库。
    
- 一个 SSAS 多维数据集可视化聚合数据 
    
- IIS 主机 CQD Web 门户
    
![CQD 组件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
相同的 CQD 体系结构支持 Lync Server 2013 和 Skype for business。 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 和 Skype for business 与 Lync 2013

 仅在 Skype for business 环境中，可以使用以下功能：
  
- 信号强度的 wi-fi 报告
    
- 芯片组驱动程序的 wi-fi 报告
    
- 评价我的通话数据 
    
## <a name="information-available-through-cqd"></a>通过 CQD 提供的信息

CQD 可以显示 Skype for business 服务器音频、视频和应用程序共享流计数以及良好的通话计数和不良通话的比率以及不正确通话的比率。 可按多种不同的尺寸对视图进行切片和筛选。 CQD 从监视服务器中的 QoE 指标数据库中绘制数据。 然后，将数据与客户提供的任何数据（如网络子网间的映射）合并，以使报表（如 "每个建筑物的通话质量"）成为可能。 
  
CQD 还提取许多内部 QoE 数据特性（如 "调用方" 和 "被调用方"），以便用户可以专注于围绕 "服务器" 和 "客户端" 构建报告视图。 按照通话质量方法，CQD 简化了 pockets 的通话的条件，这是提高通话质量的原则之一。
  
## <a name="viewing-data-in-cqd"></a>查看 CQD 中的数据

CQD 数据可以通过 CQD 门户查看，并通过 REST API 调用访问。
  
### <a name="cqd-portal"></a>CQD 门户

门户是查看多维数据集中的数据的最快方式。 门户附带有多个内置报表，可立即使用。 内置报表以结构化方式进行链接，以指导用户连续减少和缩小调用数据的扇区。 内置报表还通过演示具有不同的透视表、筛选器和度量值的图表和表的组合来突出显示数据显示的各种不同方式。 访问门户的每个用户都可以拥有他/她可以修改和共享的自己的一组报告。 有关 CQD Web 门户用法的详细信息，请参阅[使用 Skype for Business 服务器的呼叫质量仪表板](use.md)。
  
CQD Portal 支持的操作系统： Windows 8.1、Windows 8、Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2016 （仅限 Skype for Business Server 2019 CQD）。
  
CQD 门户支持的浏览器： Internet Explorer 11、Internet Explorer 10 和 Internet Explorer 9。
  
### <a name="rest-apis"></a>REST Api

也可以通过 REST API 调用访问多维数据集数据。 通过 REST API 调用检索的数据可以通过 HTML 页面呈现。 用户可以利用查询速度和高级模式的 CQD，同时还可以创建适合其业务需求的自定义报表。 有关 API 和示例的详细信息，请参阅[开发 Skype for Business 服务器的呼叫质量仪表板](develop.md)。 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>定义组织对 CQD 的要求

CQD 提供 QoE 数据存档和快速和深入的通话质量数据分析。 以下指南可帮助你确定部署 CQD 的时间和原因。
  
### <a name="when-to-deploy-cqd"></a>何时部署 CQD

 **CQD 可以部署，以建立基准通话质量测量，即使组织不会遇到通话质量问题。** 建立基准通话质量测量非常重要，因为每个组织都有不同的 Wi-fi 与有线和远程与 office 工作人员混合。 当出现通话质量问题时，最新的通话质量测量值可以与之前的时间间隔进行比较。 CQD 的趋势功能允许在一段时间内轻松地检测通话质量的变化。
  
 **可以部署 CQD 来主动找到可能会影响通话质量的问题区域。** 即使组织的平均通话质量可能满足组织设置的目标，也可能会有 pockets 的通话质量问题，这些问题在平均指标的下方隐藏。 CQD 使数据透视表类似于 QoEMetrics 数据库中的多个维度的通话质量指标细目。 对等组中的 Spotting 离群离群是一种提前查找通话质量问题的快速方法。
  
 **如果组织中存在通话质量问题，则应部署 CQD，以减少解决问题所需的时间。** CQD 可以通过提供快速的报表性能和动态的向下功能来简化现有的通话质量调查。 CQD 适用于在通话质量调查中对环境的修复进行验证的许多类型的工作流。
  
### <a name="why-deploy-cqd"></a>为什么要部署 CQD

 **如果需要针对超过3个月的数据执行 QoE 报告，应部署 CQD。** QoEMetrics 数据库和监视服务器报表旨在保留和报告少量数据集。 QoE 指标数据库已针对快速插入进行了优化，因此可通过大量的调用或对数据库具有竞争性报告访问权限来 impeded 报告性能。 CQD 的 QoE 存档数据库提供了 QoE 指标数据的第二个副本，保留功能更长。 门户还经过优化，可一次显示多达7个月的数据，并根据需要报告 QoE 存档中的所有数据。
  
 **如果需要自定义 QoE 报表，应部署 CQD。** 门户具有一个报表编辑器功能，用于快速轻松地创建报表和创建报表原型。 它还使可用的 REST Api 能够以编程方式访问多维数据集数据，从而允许使用 HTML/JavaScript 或其他许多框架的自定义演示文稿。 不再需要创作新的 SQL 查询，目的是创建用于报告的自定义数据视图。
  
 **如果现有 QoE 报告功能不符合组织所需的速度或深度，则应部署 CQD。** CQD 附带了许多内置的报表。 报告将立即有用，并演示如何以渐进方式向数据中钻取，从而可以在每个级别提供其他见解。 报表层次结构还有助于以合乎逻辑的方式管理大量报表，并促进创建更易于访问且易于理解的更多报表。 CQD 不仅提供速度和灵活性，还针对由通话质量方法开发的工作流进行了优化。
  
## <a name="components-and-topologies-for-cqd"></a>CQD 的组件和拓扑

CQD 提供了多个组件，并且有助于了解每个组件的要求以及它们之间的关系，以获取该工具的最简单且性能最佳的部署。 下表介绍了每个 CQD 组件的依赖组件。
  

|**组件名称**|**依赖组件**|
|:-----|:-----|
|QoE 存档  <br/> |Microsoft SQL Server  <br/> |
|立方体  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|站点  <br/> |Microsoft 信息服务  <br/> |
|存储库服务（门户安装的一部分）  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> 对于 QoE 存档和多维数据集，某些部署选项需要 Microsoft SQL Server 的商业智能或企业版。 有关详细信息，请参阅以下 CQD 部分的[基础结构要求](plan.md#Infrastructure_Req)。
  
![CQD 组件](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>单服务器配置

所有 CQD 组件和依赖组件都可以安装在一台计算机上。 单框配置是最简单的配置，并且允许 CQD 自包含。 CQD 只需访问监视服务器上的 QoE 指标数据库。 CQD 服务器可以是独立计算机、虚拟机或虚拟机，也可以是监视服务器，具体取决于主机的可用资源和性能要求。 
  
在安装过程中，执行安装的用户只需提供以前在要安装 CQD 的计算机上设置的 Microsoft SQL Server 和 Microsoft SQL Server Analysis Services 实例。 有关详细信息，请参阅[部署 Skype for Business 服务器的通话质量仪表板](deploy-0.md)。
  
### <a name="multiserver-configuration"></a>多服务器配置

在多服务器配置中，QoE 存档、多维数据集和门户都可以位于不同的计算机上。 多服务器配置主要有两种用途：
  
- 在不同服务器上托管 CQD Web 门户和 CQD 多维数据集。
    
- 托管独立于 "生产" 门户的 "开发" 门户。 
    
  **在不同计算机上托管 CQD Web 门户和 CQD 多维数据集。** 可能需要将 CQD 门户与 SQL Server 安装分开或可能希望混合和匹配 sql server 实例和 SQL Server Analysis Services 实例的 SQL Server 版本的组织可选择安装 CQD 门户和不同计算机上的 CQD 多维数据集。 QoE 存档组件也可以是安装的唯一 CQD 组件（如果组织只希望使用可持续方法来存档 QoE 数据，而不会在监视服务器上达到性能限制）。
  
![单服务器 CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **托管独立于 "生产" 门户的 "开发" 门户。** 开发自己的自定义报表（通过 REST Api）的组织可能希望在生产门户旁边部署其他（CQD）门户实例，以便常规用户在呼叫质量监视或调查中访问。 开发门户可将对门户的任何修改与生产环境隔离开来。 其他 web 门户可以部署在不同的计算机上（如下所示），或部署到同一台计算机上的不同 web 目录（未显示）。 若要实现后者，必须手动将其他 CQD web 门户复制到生产计算机，因为 CQD 安装过程始终将 CQD Web 门户部署到具有预定义 web 应用程序名称的默认网站。
  
![计划 CQD 多服务器](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>支持的拓扑

CQD 不会合并多个 QoEMetrics 数据库中的数据，因为存在多个 Skype for business 服务器拓扑的情况，每个拓扑都有自己的监视服务器。 每个 CQD 实例都必须指向一个 QoEMetrics 数据库。 但是，由于 CQD 将从监视服务器移动大量报告工作负荷，因此每个 Skype for Business 服务器拓扑需要部署一个监视服务器的大型组织应考虑为所有拓扑使用一个监视服务器。
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD 的基础结构要求
<a name="Infrastructure_Req"> </a>

CQD （包括其所有组件和依赖组件）可以部署在虚拟机、单个计算机上或跨多台计算机。 下面列出了最低软件和硬件要求。 数据可用性和查询性能可能因分钟而异，具体取决于活动 Skype for business 服务器用户和硬件和配置的数量，因此下面给出了一些性能测量结果。
  
|||
|:-----|:-----|
|对于 CQD 2015 <br/> |  <br/> |
|支持的操作系统  <br/> |Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2  <br/> |
|支持的 SQL Server  <br/> |SQL Server 2012、SQL Server 2014、SQL Server 2016  <br/> |

|||
|:-----|:-----|
|对于 CQD 2019 <br/> |  <br/> |
|支持的操作系统  <br/> |Windows Server 2016、Windows Server 2019  <br/> |
|支持的 SQL Server  <br/> |SQL Server 2017 sql Server 2019  <br/> |
   
CQD 利用 Microsoft SQL Server、Microsoft SQL Server Analysis Services 和 Microsoft Internet 信息服务，因此 CQD 的硬件和软件要求的最低程度与这些依赖组件基本相同。 但是，根据组织对数据新鲜度的要求（这将依赖于组织生成的 QoE 数据量）和部署开销，应执行其他部署注意事项。
  
CQD 中的数据处理分为两个主要阶段： 
  
- QoE 存档过程
    
- CQD 多维数据集处理
    
  **QoE 存档处理。** QoE 存档处理任务将监视服务器上 QoE 指标数据库中的数据复制到 QoE 存档数据库。 在两种情况下，任务的处理时间将具有基本不同的性能特征。 第一个是 CQD 的初始安装。 如果在执行全新安装后首次运行任务，QoE 存档处理任务会将 QoE 指标数据库中的所有数据复制到 QoE 存档数据库中。 第二个是此初始循环之后的定期处理。 QoE 存档处理任务将每隔15分钟运行，并处理 QoE 指标数据库中的任何新 QoE 记录。 通常，初始处理时间不是一个问题，因为它仅在安装 CQD 时首次运行。 但是，如果 CQD 服务器受到严格的预配，此任务可能需要几个小时。 有关初始 QoE 存档处理时间的示例，请参阅下表。
  
  **CQD 多维数据集处理。** 多维数据集处理任务将 QoE 存档数据库中的数据聚合到多维数据集中。 初始多维数据集处理时间和后续多维数据集处理时间由用于 CQD 多维数据集的 SQL Server Analysis Services 版本确定。 如果使用标准版，则初始多维数据集处理时间和后续多维数据集处理时间之间没有任何差异，因为每次刷新多维数据集数据时，它将始终完全处理所有可用数据。 （这意味着，当 QoE 存档数据库中的数据量增加时，多维数据集处理时间会增加。）由于 SQL Server 的商业智能版本和企业版具有分区支持，因此如果使用其中一个版本，则只有初始运行才会处理 QoE 存档数据库中的所有数据。 在后续运行中，当每15分钟触发一次任务时，任务将仅处理自上次运行任务以来添加到 QoE 存档数据库的新记录。 每天一次，包含当前月份数据的分区上还会有完整的处理。
  
物理计算机特征可能会影响 CQD 性能以及 SQL Server 组件中提供的软件功能。 与其他组件相比，QoE 存档组件更占用磁盘空间，而多维数据集组件会占用更多的 CPU 和内存。 所有这些因素都将影响 CQD 的总数据处理时间，这会直接影响数据的新鲜度和可用性。 组织应根据组织的个人需求来制定硬件和软件决策。 
  
### <a name="tested-hardware-configurations"></a>经测试的硬件配置

本部分假设环境中存在单个 QoEMetrics DB。 
  
**计算机配置文件**

|**机**|**CPU 内核**|**RAM**|**在同一磁盘上 QoE 存档和多维数据集**|**在同一磁盘上 QoE 存档和 SQL 临时数据库**|
|:-----|:-----|:-----|:-----|:-----|
|虚拟机  <br/> |4  <br/> |7 GB  <br/> |是  <br/> |是  <br/> |
|4核  <br/> |4  <br/> |20 GB  <br/> |是  <br/> |否  <br/> |
|8核  <br/> |个  <br/> |32 GB  <br/> |是  <br/> |否  <br/> |
|16核  <br/> |utf-16  <br/> |128 GB  <br/> |否  <br/> |否  <br/> |
   
**性能结果**

|**机**|**QoE 指标数据库大小**|**SQL 分区**|**磁盘类型**|**流的数量**|**初始存档过程**|**初始多维数据集流程**|**后续存档过程**|**后续多维数据集进程**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|虚拟机  <br/> |900 MB  <br/> |单个  <br/> |VHD （可变大小）  <br/> |。 5 M  <br/> |30米  <br/> |2 m  <br/> |30秒  <br/> |1 m  <br/> |
|虚拟机  <br/> |9 GB  <br/> |单个  <br/> |VHD （可变大小）  <br/> |5 M  <br/> |4 h  <br/> |15米  <br/> |1 m  <br/> |5 m  <br/> |
|虚拟机  <br/> |9 GB  <br/> |单个  <br/> |VHD （固定大小）  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|虚拟机  <br/> |30 + GB  <br/> |单个  <br/> |VHD （固定大小）  <br/> |10米  <br/> |15 h  <br/> |20米  <br/> |2 m  <br/> |45 m  <br/> |
|8核  <br/> |9 GB  <br/> |单个  <br/> |多个磁盘  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8核  <br/> |9 GB  <br/> |名  <br/> |多个磁盘  <br/> |5 M  <br/> |2 h  <br/> |15米  <br/> |35 s  <br/> |2 m  <br/> |
|8核  <br/> |30 + GB  <br/> |单个  <br/> |多个磁盘  <br/> |20米  <br/> |9 h  <br/> |20米  <br/> |1 m  <br/> |20米  <br/> |
|8核  <br/> |30 + GB  <br/> |名  <br/> |多个磁盘  <br/> |20米  <br/> |9 h  <br/> |30米  <br/> |2 m  <br/> |2 m  <br/> |
|4核  <br/> |200 GB  <br/> |单个  <br/> |多个磁盘  <br/> |125 M  <br/> |6天以上  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16核  <br/> |500 GB  <br/> |名  <br/> |多个心轴  <br/> |250 M  <br/> |8天  <br/> |2 h  <br/> |2 m  <br/> |10米  <br/> |
   
\*由于 QoE 指标数据库必须分别有9个和18个月的数据，因此在实际部署中不会遇到这些错误，但此处提供它们是为了实现完整性。
  
### <a name="service-account-requirements"></a>服务帐户要求

你将需要一个帐户（具有对 QoEMetrics 的读取访问权限），CQD 服务器上的 SQL 代理可以使用该帐户将数据导入到 QoEArchiveDB。
  
你可能还需要为 SSA 作业配置单独的帐户，以便从 QoEArchiveDB 提取数据（这是一个可选的过程）。
  
IIS 最常使用网络服务作为应用池标识，但可以配置为服务帐户。
  
### <a name="portal-access-control"></a>门户访问控制

默认情况下，任何经过身份验证的用户都具有访问权限。 这可以通过使用 IIS 授权规则限制到特定组来进行更改。
  
### <a name="pre-install-requirements"></a>预安装要求

这些说明假定 QoE 指标数据库已安装，并且在 Skype for Business Server 拓扑中的某个位置运行。
  
#### <a name="hardware-requirements"></a>硬件要求

CQD 利用 Microsoft SQL Server、Microsoft SQL 分析服务器和 Microsoft Internet Information Server，因此 CQD 的硬件和软件要求的最低程度与这些依赖组件基本相同。 但是，根据组织对数据新鲜度的要求（这将依赖于组织生成的 QoE 数据量）和部署开销，应执行其他部署注意事项。
  
#### <a name="software-requirements"></a>软件要求

CQD 需要以下操作系统：
  
- Windows Server 2008 R2 与 IIS 7。5
    
- Windows Server 2012 和 IIS 8。0
    
- Windows Server 2012 R2 与 IIS 8。5

- Windows Server 2016 与 IIS 10.0 （Skype for Business 服务器 2019 CQD）

- Windows Server 2019 （仅适用于 Skype for Business Server 2019 CQD）
    
以下是所需的 IIS 角色服务（按层次结构顺序）：
  
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
>  注意上述要求的以下内容： > 3.5 和4.5 版本的 .Net framework 可用。 两者都是必需的（更具体地说，需要 3.5 SP1）。在某些系统中 >，如果 ASP.NET 是在安装 IIS 之前设置的，则 ASP.NET 可能未在 IIS 中注册。 通过在应用池配置中缺少对应 .Net 版本的应用程序池以及缺少 .NET CLR 版本的问题清单。 若要更正 Windows Server 2008 R2 上的此类问题`%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`，请执行。 在 Windows Server 2012 和 Windows Server 2012 R2 上， `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45`执行后，从 IIS 管理器中的默认网站删除 "未加" 模块。 > 管理工具是可选的，但建议使用。
  
若要使用 PowerShell 安装这些要求，请运行以下操作：
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

支持以下版本的 SQL Server：
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 （仅适用于 Skype for Business Server 2019 CQD）
    
出于性能原因，建议使用商业智能或企业版。 这些版本允许使用可并行处理的多个分区文件，这对于处理跨越多个月或更长时间的数据非常有用。 
  
虽然不建议使用标准版本，但也支持标准版本。 处理将被限制为单个分区（需要在安装期间配置）。 
  
在所有情况下，必须安装 "数据库引擎服务" 和 "Analysis Services"。 建议但不需要同时安装 "管理工具-完成" 功能，这将为 Analysis Services 添加 SQL Server Management Studio 支持。 功能选择屏幕应如下图所示。
  
![SQL Server 功能要求](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
配置 SSAS 设置时，在 Analysis Services 配置中，将 "服务器模式" 设置为 "多维和数据挖掘模式"。 
  
有关安装和配置 SQL Server 商业智能功能的其他帮助，请参阅[在多维和数据挖掘模式下安装 Analysis Services](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx)。
  
#### <a name="account-requirements"></a>帐户要求

建议在最低权限原则上使用三个域服务帐户： 
  
- 一个已具有 QoE 指标数据库（具有 db_datareader 权限）的登录安全主体的用户和 QoE 存档 SQL Server 实例中的登录安全主体（在设置过程中创建链接服务器对象所需）。 此帐户将用于运行 SQL Server 代理作业的 "QoE 存档数据" 步骤。
    
- 将用于运行 SQL Server 代理作业的 "流程多维数据集" 步骤。 安装程序将创建一个登录安全主体来 QoE 存档数据库（具有 "读取" 和 "写入" 权限），还可在多维数据集的 QoE 角色（具有 "完全控制" 权限）中创建成员。
    
- 将用于针对 web 门户和 web Api 运行 IIS 辅助进程的一个。 安装程序将创建一个登录安全主体，以 QoE 存档数据库（具有读取权限）、对存储库数据库的登录安全主体（具有读取和写入权限），以及针对多维数据集的 QoERole 中的成员（具有 "完全控制" 权限）。 
    
    > [!NOTE]
    > 当 QoE 存档数据库和知识库数据库都托管在同一 SQL Server 中时，只会创建一个具有两个用户映射的登录安全主体。 
  
前两个帐户可以被逻辑视为 "后端服务帐户"，最后一个帐户是 "前端服务帐户"。 虽然不建议使用，但在所有情况下都可以使用单个帐户。
  
> [!NOTE]
> 启动安装的用户帐户必须具有 QoE 指标 DB 的读取访问权限（除了必须在其中进行安装的 QoE 存档数据库服务器上具有计算机管理员权限）。 
  
## <a name="capacity-planning"></a>容量规划
<a name="Infrastructure_Req"> </a>

CQD 适用于 QoEMetrics 的最小影响：代码已优化为不锁定数据，导入作业是可调的。
  
要使用的硬件类型取决于您对同步运行速度的要求。 磁盘大小调整如下所示：
  
- QoEArchive 比 QoEMetrics DB 的初始速度高 ~ 1.5 x
    
- SSIS 多维数据集将数据与数据库相比几乎10倍地压缩。
    
- 按月对数据进行分区;可以删除分区
    

