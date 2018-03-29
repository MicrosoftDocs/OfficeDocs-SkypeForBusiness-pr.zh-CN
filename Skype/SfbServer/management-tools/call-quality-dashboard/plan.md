---
title: 通话质量仪表板规划的 Skype 业务服务器 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/27/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 摘要： 了解调用质量仪表板规划时应考虑的问题。
ms.openlocfilehash: 25438b759e367d70df6ae09b7d4a5cc093dc1e7a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server-2015"></a>通话质量仪表板规划的 Skype 业务服务器 2015
 
**摘要：**了解如何调用质量仪表板规划时应考虑的问题。
  
## <a name="overview-of-the-skype-for-business-server-2015-call-quality-dashboard"></a>Skype 业务服务器 2015年通话质量仪表板的概述

Skype 的业务服务器 2015年呼叫质量仪表板 (CQD) 是报告质量的经验数据库在监视服务器中业务服务器 2015年和 Lync Server 2013 Skype 在顶层。 CQD 使用 Microsoft SQL Server Analysis Services 提供总使用量以及调用质量以及关于信息过滤和数据集上进行透视。 CQD 功能包括：
  
- **通过 QoE 档案组件的 CQD QoE 数据的归档存储。** QoE 档案组件可以监视服务器可以比更长持续时间为存储 QoE 数据。 这样的趋势分析和报告的多达七个月的数据，一次能够滑动背面至于告没有数据。
    
- **报告和分析使用的电源和 Microsoft SQL Server Analysis Services 的速度。** CQD 利用 Microsoft SQL Analysis Services 提供快速汇总、 筛选和旋转电源仪表板通过分析多维数据集的能力。 报告执行速度和深入分析数据的能力可以大大减少分析时间。
    
- **新的数据架构优化呼叫质量报告。** 多维数据集具有架构设计的语音质量报告和调查。 门户用户可以关注的报告任务，而不是搞清楚如何 QoE 指标数据库架构映射到所需的视图。 QoE 存档和多维数据集的组合提供了降低了报告和分析通过 CQD 的复杂性的一种抽象。 QoE 存档数据库架构还包含可以使用特定于部署的数据，以提高整体价值的数据填充的表。
    
- **内置的报表设计器和就地报告编辑。** 门户组件附带了几个内置报告仿效呼叫质量的方法。 门户用户可以修改报表并创建新的报表，通过门户网站的编辑功能。
    
- **Web API 访问报表结构和分析多维数据集数据。** 仪表板报告框架不是显示的多维数据集数据的唯一方法。 CQD 提供使用 HTML 和 JavaScript 从 CQD Web Api 检索数据并呈现自定义格式的数据的几个示例。 报告编辑器和 CQD Web Api 的组合允许报表和自定义报表布局的快速原型法。
    
## <a name="cqd-design-goals"></a>CQD 设计目标

CQD 允许 IT 专业人员使用聚合数据来识别其环境中遇到媒体质量问题的重点关注区域。它允许 IT 专业人员比较不同用户组的统计信息，并识别趋势和模式。它重点关注的不是单个通话问题，而是识别适用于给定环境中许多用户的问题和解决方案。 
  
## <a name="call-quality-dashboard-components"></a>呼叫质量仪表板组件

呼叫质量面板包含几个数据库、 Microsoft SQL 代理作业、 流程和 web 应用程序。 Microsoft SQL 代理作业定期将数据从 QoE 指标数据库复制到 QoE 存档数据库和进程 QoE 存档数据库中的数据与多维数据集。 知识库数据库中存储的报告定义门户的电源。 门户网站提供对多维数据集浏览器访问。 
  
CQD 组件，包括 QoE 存档、 多维数据集和存储库数据库中，可以监视服务器上安装、 安装在自己的服务器上或安装在多台服务器。 特殊的安装方法取决于 CQD，以及影响到同一个服务器上的其他进程的性能需求。 有关详细信息，请参阅本文内下文中的"组件和 CQD 的拓扑结构"部分。
  
### <a name="architectural-overview"></a>体系结构概述

总之，CQD 需要以下元素：
  
- 这两个数据库： 一个存档数据库和知识库数据库。
    
- 一个 SSA 多维数据集可视化聚合数据 
    
- IIS 承载 CQD Web 门户
    
![CQD 组件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
相同的 CQD 体系结构支持业务 Lync Server 2013 和 Skype。 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 和 Skype 的业务与 Lync 2013

 在商业环境中仅为 Skype，以下功能有：
  
- Wi-Fi 信号强度的报告
    
- Wi-Fi 报告芯片组驱动程序
    
- 我呼叫数据速率 
    
## <a name="information-available-through-cqd"></a>通过 CQD 可用信息

CQD 可以显示 Skype 业务服务器音频、 视频和应用程序共享流计数和计数的好与坏的调用以及调用坏到好的比率。 可以切片并由多个不同维度筛选视图。 CQD 从监视服务器中的 QoE 指标数据库中提取数据。 数据然后合并与任何客户提供的数据，例如网络子网与构建映射若要使报表，例如"呼叫质量每个大厦"成为可能。 
  
CQD 还抽象化许多内部的 QoE 数据特性如"调用方"和"被调用方"，使用户可以集中精力构建报表视图，在"服务器"和"客户端"。 以下调用的质量方法，CQD 都得到了优化可帮助识别差调用的口袋有共同点的条件 — 提高通话质量的原则之一。
  
## <a name="viewing-data-in-cqd"></a>在 CQD 中查看数据

可以查看通过 CQD 门户和通过 REST API 调用的 CQD 数据。
  
### <a name="cqd-portal"></a>CQD 门户

该门户是查看多维数据集中的数据的最快方法。 门户附带了几个内置的报告将立即可用。 内置报告链接以结构化的方式来指导用户调用数据的连续较小和较小的切片。 内置的报告还突出显示的数据可以显示展现的图表和表格与不同支枢、 过滤器和措施组合的各种不同方法。 访问门户网站的每个用户都可以有他或她自己的一套报告他/她可以修改和共享。 用法的 CQD Web 门户的更多信息，请参阅[使用呼叫质量为仪表板业务服务器 2015年的 Skype](use.md)。
  
受 CQD 门户所支持的操作系统： Windows 8.1、 Windows 8、 Windows Server 2012 R2 和 Windows Server 2012。
  
对于 CQD 门户支持的浏览器： Internet Explorer 11、 Internet Explorer 10 和 Internet Explorer 9。
  
### <a name="rest-apis"></a>REST Api

也可以通过 REST API 调用访问多维数据集数据。 通过 REST API 调用检索到的数据可以通过 HTML 页将呈现。 仍要创建自定义报表适合其业务需求的同时，用户可以利用查询速度和较高的层次架构 CQD。 API 和示例的详细信息，请参见[开发业务服务器 2015年的 Skype 的呼叫质量面板](develop.md)。 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>定义您的组织要求 CQD

CQD 提供呼叫质量数据的 QoE 数据存档和快速和深入分析。 以下指南可帮助您决定何时以及为何您将部署 CQD。
  
### <a name="when-to-deploy-cqd"></a>何时部署 CQD

 **可以部署 CQD 建立基准呼叫质量测量，即使组织不会遇到通话质量问题。** 建立基准呼叫质量测量很重要，因为每个组织都有各种不同的与有线和远程办公室的工作人员与 Wi-Fi。 当呼叫质量问题出现时，最新的呼叫质量测量可以比作前一个时间间隔。 CQD 的趋势分析功能允许呼叫质量随着时间的推移易于检测的变化。
  
 **可以部署 CQD 要主动地找出可能影响通话质量的问题区域。** 即使平均呼叫质量组织可能满足目标设置的组织，可能有大量隐藏在平均指标的呼叫质量问题。 CQD 允许呼叫质量测量数据的数据透视表类似细分通过对 QoEMetrics 数据库中的多个维度。 对等组中发现离群值是主动找到通话质量问题的快速方法。
  
 **应部署 CQD，如果调用质量问题中存在的组织，以减少解决问题所需的时间。** 通过提供快速报告性能和动态功能深化，CQD 可以简化现有呼叫质量调查。 CQD 专为许多类型的呼叫质量调查验证修复对环境中的工作流。
  
### <a name="why-deploy-cqd"></a>为什么要部署 CQD

 **如果 QoE 报告需要多 3 个月的数据，则应部署 CQD。** QoEMetrics 数据库和监控服务器报告旨在保留，并将报告一个小型数据集。 QoE 指标数据库非常适合快速插入操作，并可以因此在由大量的呼叫或同类报告访问数据库时阻碍报告性能。 CQD 的 QoE 存档数据库提供了更长的保留能力的 QoE 指标数据的另一个副本。 门户还可以显示多达 7 个月的数据一次而优化，QoE 存档中的所有数据根据需要可以都报告。
  
 **如果需要自定义 QoE 报表，应部署 CQD。** 门户已创建和原型设计报表的报表编辑器功能，快速而轻松地。 它还对多维数据集数据，以允许自定义演示文稿使用 HTML/JavaScript 或许多其他框架可用 REST Api，可用于以编程方式访问。 不再需要编写新的 SQL 查询来创建自定义数据视图的报告。
  
 **如果报告功能的现有 QoE 不符的速度和深度，所需的组织，则应部署 CQD。** CQD 附带了很多内置的报告。 报告，可立即并演示如何逐渐深入数据可以提供在每个级别的更多见解。 报表层次结构也帮助以逻辑方式管理大量的报告，并且促进了创建许多都轻松地访问和理解的详细报告。 CQD 并不只是提供了速度和灵活性，但也非常适合开发调用质量方法的工作流。
  
## <a name="components-and-topologies-for-cqd"></a>组件和 CQD 的拓扑

CQD 附带了几个组件，并有助于了解每个组件和它们的相互关系的要求，以获得该工具的最简单和最好地执行部署。 下表描述每个 CQD 组件依赖的组件。
  

|**组件名称**|**依赖组件**|
|:-----|:-----|
|QoE 存档  <br/> |Microsoft SQL Server  <br/> |
|多维数据集  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|门户网站  <br/> |Microsoft 的信息服务  <br/> |
|存储库服务 （门户安装的一部分）  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> 对于 QoE 存档和多维数据集，某些部署选项要求商业情报或企业版本的 Microsoft SQL Server。 请参阅[CQD 的基础结构要求](plan.md#Infrastructure_Req)以下部分的详细信息。
  
![CQD 组件](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>单服务器配置

所有的 CQD 组件和相关组件可以安装到一台计算机上。 单服务器配置是最简单的配置，并允许 CQD 是独立。 CQD 者只需要监视服务器上的 QoE 指标数据库访问。 CQD 服务器可以是独立计算机，虚拟机，或者它甚至可以监视服务器，这取决于主机和性能需求的可用资源。 
  
在安装、 用户执行安装只需要提供 Microsoft SQL Server 和被以前设置了在计算机安装 CQD 所在的 Microsoft SQL Server Analysis Services 实例。 请有关详细信息参阅[部署业务服务器 2015年的 Skype 的呼叫质量面板](deploy-0.md)。
  
### <a name="multiserver-configuration"></a>多服务器配置

在多服务器配置、 QoE 档案、 多维数据集和门户都可以在不同的计算机上。 有两种主要用途为多服务器配置：
  
- 在不同的服务器上托管 CQD Web 门户和 CQD 多维数据集。
    
- 主持的"开发"独立于"生产"门户的门户。 
    
 **在不同的计算机上承载 CQD Web 门户和 CQD 多维数据集。** 组织可能具有单独的 CQD 门户从 SQL Server 安装的要求或者，可能想要混合和匹配 SQL Server 版本的 SQL Server 实例和 SQL Server Analysis Services 实例可以选择安装 CQD 门户和在不同的机器上 CQD 多维数据集。 QoE 档案组件也可以是组织只是要有可持续方法 QoE 数据存档不达到监视服务器上的性能限制的情况下如果安装的唯一 CQD 组件。
  
![单服务器 CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **主持的"开发"独立于"生产"门户的门户。** 开发自己的自定义报表 （通过 REST Api) 的组织可能希望部署生产普通用户的呼叫质量监视或调查访问的门户旁边的其他 (CQD) 门户实例。 开发门户可以隔离从生产环境到门户的任何修改。 可以在不同的机器 （如下所示） 上部署或部署到不同的 web 目录 （未显示） 的同一计算机上其他 web 门户。 为后者，其他的 CQD web 门户必须复制到生产计算机手动因为 CQD 安装过程始终将 CQD Web 门户部署到默认的 web 站点使用预定义的 web 应用程序的名称。
  
![计划 CQD 多服务器](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>支持的拓扑

CQD 不合并来自多个 QoEMetrics 数据库，数据就是这样在有多个 Skype 的业务服务器的拓扑中，每个都有自己的监视服务器。 每个 CQD 实例都必须指向一个 QoEMetrics 数据库。 但是，CQD 将移动大量从监视服务器报告的工作，因为对于业务服务器拓扑部署 Skype 每个监视服务器所需的大型组织应考虑使用一台监视服务器用于所有拓扑结构。
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD 的基础结构要求
<a name="Infrastructure_Req"> </a>

CQD，包括其所有组件和相关组件，可以部署的虚拟机，一台计算机上或跨多台计算机。 下面列出了软件和硬件的最低要求。 数据可用性和查询性能因分钟到数小时，具体取决于活动的业务服务器硬件和配置中，Skype 数目因此某些性能测量如下所示。
  
|||
|:-----|:-----|
|支持的操作系统  <br/> |Windows Server 2008 R2，Windows Server 2012，Windows Server 2012 R2  <br/> |
|支持的 SQL Server  <br/> |SQL Server 2008 R2，SQL Server 2012，SQL Server 2014  <br/> |
   
因此，CQD 的最低硬件和软件要求基本上与那些依赖的组件相同，CQD 利用 Microsoft SQL Server，Microsoft SQL Server Analysis Services 和 Microsoft Internet Information Services。 但是，根据组织的要求，围绕数据新鲜度 （这将部分地取决 QoE 数据组织生成量） 和部署成本，额外的部署应考虑。
  
在 CQD 的数据处理被分为两个主要阶段： 
  
- QoE 存档过程
    
- CQD 多维数据集处理
    
 **QoE 存档处理。** QoE 存档处理任务将从监视服务器上的 QoE 指标数据库的数据复制到 QoE 存档数据库。 有两种情况下，任务的处理时间必须从根本上不同的性能特性。 第一种是 CQD 在初始安装后。 执行全新安装后第一次运行任务，QoE 存档处理任务会将复制到 QoE 存档数据库 QoE 指标数据库中的所有数据。 第二个是此初始轮之后的定期处理。 处理任务 QoE 存档将每 15 分钟运行一次并处理 QoE 指标数据库中的任何新 QoE 记录。 通常情况下，初始的处理时间不是问题因为它运行仅第一次，当安装 CQD。 但是，如果严重下调配 CQD 服务器，此任务可以需要几个小时。 请参阅例如初始 QoE 归档文件处理时间下表。
  
 **CQD 多维数据集处理。** 多维数据集处理任务到多维数据集聚合 QoE 存档数据库中的数据。 初始的多维数据集的处理时间和后续的多维数据集的处理时间由 CQD 多维数据集所使用的 SQL Server Analysis Services 版本确定。 如果使用标准版，则是没有区别的初始的多维数据集的处理时间和后续多维数据集处理时间，因为每次刷新多维数据集数据时，将始终是可用的所有数据的完全处理。 （这意味着该多维数据集处理时间随着数据库增加 QoE 存档中的数据量。商务智能版和企业版的 SQL Server 有分区支持，如果使用这两种版本，因为只是初始的运行将处理 QoE 存档数据库中的所有数据。 在后续的运行，每隔 15 分钟触发任务时任务只处理自上次运行任务添加到 QoE 存档数据库的新记录。 一天一次，也有完全处理包含当前月份的数据的分区上。
  
物理计算机特征会影响 CQD 性能，以及可以从 SQL Server 组件的软件功能。 QoE 存档组件将更多的磁盘密集型与其他组件，而更多的 CPU 和内存的占用量能多维数据集的组件。 所有这些因素共同构成 CQD 的总的数据处理时间，直接影响到数据新鲜度和可用性。 组织应决定上的硬件和软件基于个别组织的需要。 
  
### <a name="tested-hardware-configurations"></a>经测试的硬件配置

本节假设为单一的 QoEMetrics 数据库环境中。 
  
**计算机配置文件**

|**机器**|**CPU 内核**|**RAM**|**QoE 存档和同一个磁盘上的多维数据集**|**QoE 归档和 SQL Temp 数据库在同一磁盘上**|
|:-----|:-----|:-----|:-----|:-----|
|虚拟的 mmachine  <br/> |4  <br/> |7 GB  <br/> |是  <br/> |是  <br/> |
|4 Ccore  <br/> |4  <br/> |20 GB  <br/> |是  <br/> |否  <br/> |
|8 核心  <br/> |8  <br/> |32 GB  <br/> |是  <br/> |否  <br/> |
|16 核心  <br/> |16  <br/> |128GB  <br/> |否  <br/> |否  <br/> |
   
**性能测试结果**

|**机器**|**QoE 指标数据库大小**|**SQL 的分区**|**磁盘类型**|**流数**|**初始的存档过程**|**初始的多维数据集处理**|**后续的存档过程**|**随后的多维数据集处理**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|虚拟机  <br/> |有 900 MB  <br/> |一个  <br/> |VHD （可变大小）  <br/> |.5 米  <br/> |30 分钟  <br/> |2 米  <br/> |30 s  <br/> |1 米  <br/> |
|虚拟机  <br/> |9 GB  <br/> |一个  <br/> |VHD （可变大小）  <br/> |5 米  <br/> |4 h  <br/> |15 分钟  <br/> |1 米  <br/> |5 米  <br/> |
|虚拟机  <br/> |9 GB  <br/> |一个  <br/> |VHD （固定大小）  <br/> |5 米  <br/> |2 h  <br/> |5 米  <br/> |1 米  <br/> |5 米  <br/> |
|虚拟机  <br/> |30 + GB  <br/> |一个  <br/> |VHD （固定大小）  <br/> |10 米  <br/> |15 h  <br/> |20 米  <br/> |2 米  <br/> |45 米  <br/> |
|8 核心  <br/> |9 GB  <br/> |一个  <br/> |多个磁盘  <br/> |5 米  <br/> |2 h  <br/> |5 米  <br/> |25 s  <br/> |5 米  <br/> |
|8 核心  <br/> |9 GB  <br/> |多个  <br/> |多个磁盘  <br/> |5 米  <br/> |2 h  <br/> |15 分钟  <br/> |35 s  <br/> |2 米  <br/> |
|8 核心  <br/> |30 + GB  <br/> |一个  <br/> |多个磁盘  <br/> |20 米  <br/> |9h  <br/> |20 米  <br/> |1 米  <br/> |20 米  <br/> |
|8 核心  <br/> |30 + GB  <br/> |多个  <br/> |多个磁盘  <br/> |20 米  <br/> |9h  <br/> |30 分钟  <br/> |2 米  <br/> |2 米  <br/> |
|4 核心  <br/> |200 GB  <br/> |一个  <br/> |多个磁盘  <br/> |125 米  <br/> |6 + 天  <br/> |7 h  <br/> |2 米  <br/> |6 h  <br/> |
|16 核心  <br/> |500 GB  <br/> |多个  <br/> |多个心轴  <br/> |250 米  <br/> |8 天  <br/> |2 h  <br/> |2 米  <br/> |10 米  <br/> |
   
\*这些不会遇到在实际部署中因为 QoE 指标数据库者必须分别有 9 和 18 个月的数据，但他们出于完整性的考虑在此处提供。
  
### <a name="service-account-requirements"></a>服务帐户要求

您将需要 SQL 服务器上的代理 CQD 可用于数据导入到 QoEArchiveDB （与 QoEMetrics 对读取访问权限） 的帐户。
  
您可能还需要配置单独的帐户 SSA 作业取出数据从 QoEArchiveDB （这是一个可选的流程）。
  
IIS 通常为应用程序池标识，使用网络服务，但可以配置为服务帐户。
  
### <a name="portal-access-control"></a>门户访问控制

默认情况下，任何经过身份验证的用户都有访问权。 这可以通过使用 IIS 授权规则限制到特定的组更改。
  
### <a name="pre-install-requirements"></a>预安装要求

这些说明假定 QoE 指标数据库已安装并在 Skype 业务服务器拓扑中某个位置运行。
  
#### <a name="hardware-requirements"></a>硬件要求

因此 CQD 的最低硬件和软件要求基本上与那些依赖的组件相同，CQD 利用 Microsoft SQL Server、 Microsoft SQL 分析服务器和 Microsoft Internet 信息服务器。 但是，根据组织的要求，围绕数据新鲜度 （这将部分地取决 QoE 数据组织生成量） 和部署成本，额外的部署应考虑。
  
#### <a name="software-requirements"></a>软件要求

下列操作系统所需的 CQD:
  
- Windows Server 2008 R2 与 IIS 7.5
    
- Windows Server 2012 与 IIS 8.0
    
- 使用 IIS 8.5 Windows Server 2012 R2
    
以下 （按层次结构顺序） 是必需的 IIS 角色服务：
  
- Web 服务器
    
  - 常见的 HTTP 功能
    
  - 静态内容
    
  - 默认文档
    
  - 应用程序开发
    
  - ASP.NET
    
  - ISAPI 筛选器
    
  - 健康&amp;诊断程序
    
  - HTTP 日志记录
    
  - 安全性
    
  - URL 授权
    
  - Windows 身份验证
    
  - 管理工具
    
  - IIS 管理控制台
    
> [!NOTE]
>  请注意上述要求的以下： > 3.5 和 4.5 版本的.Net framework 都可用。 两者都是必需的 （更具体地说，3.5 SP1 是必需的）。 > 在某些系统中，如果 ASP.NET 安装程序之前安装 IIS，然后 ASP.NET 可能不能注册到 IIS。 问题清单通过相应的.Net 版本和还缺少应用程序池配置中的.NET CLR 版本的应用程序池不存在。 若要解决此类问题在 Windows Server 2008 R2，执行`%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`。 在 Windows Server 2012 和 Windows Server 2012 R2，执行`dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45`跟卸下从默认 Web 站点在 IIS 管理器的"ServiceModel"模块 > 管理工具是可选的但建议。
  
要安装使用 PowerShell 这些要求，请运行以下命令：
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

支持下面的 SQL Server 版本：
  
- SQL Server 2008 R2
    
- SQL Server 2012
    
- SQL Server 2014
    
商业智能或企业版建议由于性能的原因。 这些版本允许使用多个可并行，这是有益于处理数据跨越多个月或更长时间处理的分区文件。 
  
虽然不建议，也支持标准版。 将受到处理限制在单个分区 （这需要在安装过程中配置）。 
  
在所有情况下，必须安装"数据库引擎服务"和"Analysis Services"。 它建议但不是需要安装"管理工具-完成"功能，添加 SQL Server 管理 Studio Analysis Services 支持。 功能选择屏幕应该类似图。
  
![SQL Server 功能要求](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
在 ssa 上安装程序，配置在 Analysis Services 配置时，将设置"服务器模式"到"多维和数据挖掘模式"。 
  
在安装和配置 SQL Server 商务智能功能的更多帮助，请参阅[多维和数据挖掘模式中安装 Analysis Services](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx)。
  
#### <a name="account-requirements"></a>帐户的要求

三个域服务帐户的最小特权原则建议： 
  
- 一个已登录安全主体 QoE 指标数据库 （使用 db_datareader 权限） 并登录安全主体 QoE 存档 SQL Server 实例 （需要在安装过程中创建链接服务器对象） 中。 此帐户将用于运行的 SQL Server 代理程序作业的"QoE 存档数据"步骤。
    
- 一个用于运行的 SQL Server 代理程序作业步骤中"处理多维数据集"。 安装程序将创建一个登录到 QoE 存档数据库的安全主体 (与读取和写入权限) 而且还创建 QoE （具有完全控制权限） 多维数据集角色中的成员。
    
- 一个可用于 web 门户和 web Api 运行 IIS 工作进程。 安装程序将创建一个登录 （拥有读取权限） 的 QoE 存档数据库的安全主体，登录到存储库数据库安全主体 (与读取和写入权限)，并为该多维数据集 （具有完全控制权限） 的 QoERole 中的一个成员。 
    
    > [!NOTE]
    > 当 QoE 存档数据库和知识库数据库承载于同一 SQL Server 中时，创建一个登录安全主体与两个用户映射。 
  
前两个帐户可以逻辑上被视为"后端服务帐户"作为它的最后一个科目"前端服务帐户"。 尽管不建议这样做，就可以在所有情况下使用单个帐户。
  
> [!NOTE]
> 启动安装的用户帐户必须具有向 QoE 指标数据库的读取权限以及 （除了 QoE 存档数据库服务器必须执行安装上具有计算机管理员权限）。 
  
## <a name="capacity-planning"></a>容量规划
<a name="Infrastructure_Req"> </a>

CQD 专为在 QoEMetrics 上的影响降到最低： 代码已经过优化，以便不锁定数据，并且可调式导入作业。
  
硬件使用的类型取决于用于同步运行多快的速度要求。 磁盘大小调整情况如下：
  
- QoEArchive 最初是大于 QoEMetrics DB ~1.5x
    
- SSIS 多维数据集压缩的数据，几乎 10 x 媲美数据库
    
- 数据分区每月一次;可以删除分区
    

