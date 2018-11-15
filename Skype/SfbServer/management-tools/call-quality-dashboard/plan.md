---
title: 规划呼叫质量仪表板的 Skype 业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 摘要： 了解有关呼叫质量仪表板规划时应考虑的事项。
ms.openlocfilehash: 6df705b4d3b39bdd9f75d328277d9aa1c5fc23d1
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531231"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>规划呼叫质量仪表板的 Skype 业务服务器 
 
**摘要：** 了解有关呼叫质量仪表板规划时应考虑的事项。
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>业务服务器呼叫质量仪表板的 Skype 的概述

Skype 的业务服务器呼叫质量仪表板 (CQD) 是在质量的体验中的数据库中的业务服务器 Skype 的监控服务器报告层。 CQD 使用 Microsoft SQL Server Analysis Services 提供聚合的用法和呼叫质量的信息以及与筛选和数据集上透视。 CQD 功能包括：
  
- **通过 CQD 的 QoE 存档组件的 QoE 数据的存档存储。** QoE 存档组件可为更长时间工期超过监控服务器可以存储 QoE 数据。 这样，趋势和报告的最多七个月的数据时，能够幻灯片背面至于报告窗口没有数据。
    
- **报告和分析使用的电源和 Microsoft SQL Server Analysis Services 的速度。** CQD 利用 Microsoft SQL Analysis Services，以提供快速摘要、 筛选和透视功能 power 通过分析多维数据集仪表板。 报告执行速度和能够向下钻取数据可以显著减少分析时间。
    
- **为呼叫质量报告进行了优化的新数据架构。** 多维数据集具有设计用于语音质量报告和调查的架构。 门户网站用户可以关注的报告的任务，而不是找出如何 QoE 指标数据库架构映射到所需的视图。 QoE 存档和多维数据集的组合提供降低了报告和分析通过 CQD 的复杂性抽象。 QoE 存档数据库架构还包含可填入部署特定的数据来增强的数据的总体值的表。
    
- **内置报表设计器和报表的就地编辑。** 门户组件附带仿效了呼叫质量方法的多个内置报表。 门户网站用户可以修改报告和创建新的报表，通过门户的编辑功能。
    
- **Web API 访问报告结构和分析多维数据集数据。** 仪表板报告框架不是显示来自多维数据集的数据的唯一方式。 CQD 提供了几个示例使用 HTML 和 JavaScript 检索 CQD Web Api 中的数据和呈现自定义格式中的数据。 报告编辑器和 CQD Web Api 的组合允许快速原型的报表和自定义报表布局。
    
## <a name="cqd-design-goals"></a>CQD 设计目标

CQD 允许 IT 专业人员使用聚合数据来识别其环境中遇到媒体质量问题的重点关注区域。它允许 IT 专业人员比较不同用户组的统计信息，并识别趋势和模式。它重点关注的不是单个通话问题，而是识别适用于给定环境中许多用户的问题和解决方案。 
  
## <a name="call-quality-dashboard-components"></a>呼叫质量仪表板组件

呼叫质量仪表板包含多个数据库、 Microsoft SQL 代理作业、 流程和 web 应用程序。 Microsoft SQL 代理作业定期将数据从的 QoE 指标数据库复制到 QoE 存档数据库和流程与 QoE 存档数据库中的数据多维数据集。 存储库数据库存储的报告定义门户的电源。 门户提供对多维数据集数据的浏览器访问。 
  
CQD 组件，包括 QoE 存档、 多维数据集和存储库数据库，可以监控服务器上安装，安装在其自己的服务器上或跨多台服务器安装。 特定安装方法取决于 CQD 以及影响到相同的服务器上的其他进程的性能需求。 有关详细信息，请参阅本文后面的"的组件和拓扑 CQD"部分。
  
### <a name="architectural-overview"></a>体系结构概述

总之，CQD 需要以下元素：
  
- 两个数据库： 存档数据库和存储库数据库。
    
- 一个 SSAS 多维数据集可视化聚合数据 
    
- IIS 承载 CQD Web 门户
    
![CQD 组件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
相同的 CQD 体系结构支持 Lync Server 2013 和 Skype 业务。 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 和业务与 Lync 2013 的 Skype

 在仅业务环境 Skype，以下功能有：
  
- Wi-fi 报告信号
    
- Wi-fi 报告芯片集驱动程序
    
- 评价我的呼叫数据 
    
## <a name="information-available-through-cqd"></a>可通过 CQD 信息

CQD 可以显示 Skype 业务服务器音频、 视频和应用程序共享流计数和良好与错误的呼叫数以及错误到良好的呼叫的比率。 可以切片并由许多不同的维度筛选视图。 CQD 从中监控服务器的 QoE 指标数据库绘制数据。 与任何客户提供的数据，如网络子网为构建映射进行报告，例如"呼叫质量每 Building"可能然后合并数据。 
  
CQD 还抽象化许多内部的 QoE 数据特性，例如"呼叫者"和"被叫方"以便用户可以专注于构建围绕"服务器"和"客户端"报表视图。 以下呼叫的质量方法，CQD 将得到改进可帮助确定质量欠佳的呼叫的多种孤立共有的条件 — 用于改进呼叫质量的原则之一。
  
## <a name="viewing-data-in-cqd"></a>查看 CQD 中的数据

可以通过 CQD 门户查看和访问通过 REST API 调用 CQD 数据。
  
### <a name="cqd-portal"></a>CQD 门户

门户是最快捷的方式查看中多维数据集的数据。 门户附带了可供立即多个内置报表。 内置报告结构化方式指导用户到连续较小和最小切片呼叫数据的链接。 内置报告还突出显示的数据可以显示由演示图表和表具有不同的数据透视表、 筛选器和度量值的组合的各种不同方式。 每个访问门户的用户可以有其自己的报告，他/她可以修改和共享的组。 有关使用率 CQD Web 门户的详细信息，请参阅[使用呼叫质量仪表板 Skype 业务服务器](use.md)。
  
支持为 CQD 门户的操作系统： Windows 8.1、 Windows 8、 Windows Server 2012 R2 和 Windows Server 2012。
  
支持的浏览器 CQD 门户： Internet Explorer 11、internet、 Internet Explorer 10 和 Internet Explorer 9。
  
### <a name="rest-apis"></a>REST Api

也可以通过 REST API 调用访问多维数据集数据。 可以通过 HTML 页呈现通过 REST API 调用检索到的数据。 在仍创建自定义报告适合其业务需求，用户可以利用查询速度和高级别 CQD 架构。 有关 API 和示例的详细信息，请参阅[开发呼叫质量仪表板 Skype 业务服务器](develop.md)。 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>定义的 CQD 贵组织的要求

CQD 提供呼叫质量数据的 QoE 数据存档和快速和深入分析。 以下指南可帮助您决定何时和为什么您将部署 CQD。
  
### <a name="when-to-deploy-cqd"></a>何时部署 CQD

 **可以部署 CQD 建立基准呼叫质量度量单位，即使组织不会遇到呼叫质量问题。** 建立基准呼叫质量度量很重要，因为每个组织具有与有线和远程与 office 工作者 Wi-fi 的不同组合。 当呼叫质量问题出现时，最新呼叫质量度量可以进行比较到以前的时间间隔。 CQD 的趋势功能允许随着时间的推移呼叫质量中轻松检测的更改。
  
 **可以部署 CQD 主动查找问题可能会影响呼叫质量的区域。** 即使平均呼叫质量的组织可能满足目标设置的组织，可能有大量隐藏在平均指标的呼叫质量问题。 CQD 允许通过 QoEMetrics 数据库中的多个维度的呼叫质量指标的数据透视表类似细分。 在对等方组探索离群值是一种主动查找呼叫质量问题的快捷方式。
  
 **应部署 CQD，如果呼叫质量问题中有组织以减少解决问题所需的时间。** CQD 可以通过提供 fast 报告性能和动态深化功能来简化现有呼叫质量调查。 CQD 专为多种类型的呼叫质量调查验证修复到环境中的工作流。
  
### <a name="why-deploy-cqd"></a>为什么部署 CQD

 **应部署 CQD，如果 QoE 报告需要发生超过 3 个月内的数据。** QoEMetrics 数据库和监控服务器报告旨在保留和报告小型的一组数据。 针对 fast 插入优化的 QoE 指标数据库并因此报告性能也可以通过大量呼叫或竞争报告访问数据库时阻碍。 CQD 的 QoE 存档数据库提供具有多更长时间保留功能的 QoE 指标数据的第二个副本。 门户还优化显示达 7 个月的数据一次，并根据需要在 QoE 存档中的所有数据可以报告。
  
 **应部署 CQD，如果所需自定义 QoE 报告。** 门户具有创建和设计原型报告报告编辑器功能，快速、 方便地。 它还向多维数据集数据，以允许使用 HTML/JavaScript 或许多其他框架的自定义演示文稿进行程序访问的可用 REST Api。 不再需要编写新的 SQL 查询，以创建自定义数据视图进行报告。
  
 **应部署 CQD，如果现有的 QoE 报告功能不满足速度或由组织所需的深度。** CQD 附带了许多内置报表。 立即有用的报告，并演示如何逐渐钻取数据可以提供每个级别的其他见解。 报告层次结构还有助于以逻辑方式管理大量报告并促进创建多个详细的报告的轻松访问和理解。 CQD 不只提供速度和灵活性，但也优化的工作流开发的呼叫质量方法。
  
## <a name="components-and-topologies-for-cqd"></a>CQD 的组件和拓扑

CQD 附带了几个组件，并帮助了解获取该工具的最简单和最佳执行部署的每个组件及其关系，以及与每个其他要求。 下表介绍对于每个 CQD 组件依赖的组件。
  

|**组件名称**|**依赖的组件**|
|:-----|:-----|
|QoE 存档  <br/> |Microsoft SQL Server  <br/> |
|多维数据集  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|门户  <br/> |Microsoft 信息服务  <br/> |
|存储库服务 （门户安装的一部分）  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> QoE 存档和多维数据集，某些部署选项需要 Microsoft SQL Server 的商业智能或企业版。 请参阅[CQD 的基础结构要求](plan.md#Infrastructure_Req)部分下方的详细信息。
  
![CQD 组件](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>单服务器配置

可以拖放到一台计算机上安装所有 CQD 组件和相关组件。 单服务器配置是最简单的配置，并允许 CQD 是独立。 CQD 只需要对监控服务器上的 QoE 指标数据库的访问。 CQD 服务器可以是独立计算机，虚拟机，也可以甚至是监控服务器，具体取决于主机和性能要求的可用资源。 
  
在过程中安装、 用户执行安装只需要提供 Microsoft SQL Server 和已以前设置的计算机安装 CQD 所在的 Microsoft SQL Server Analysis Services 实例。 请参阅[部署呼叫质量仪表板 Skype 业务服务器](deploy-0.md)的详细信息。
  
### <a name="multiserver-configuration"></a>多服务器配置

在多服务器配置、 QoE 存档、 多维数据集，和门户中所有可在不同的计算机上。 有两种主要用途为多服务器配置：
  
- 不同服务器上承载 CQD Web 门户和 CQD 多维数据集。
    
- 承载"开发"门户"生产"门户分开。 
    
  **不同的计算机上承载 CQD Web 门户和 CQD 多维数据集。** 组织可能具有要求分隔 CQD 门户从 SQL Server 安装的或，可能需要混合和与 SQL Server 版本匹配的 SQL Server 实例和 SQL Server Analysis Services 实例可以选择安装 CQD 门户和不同的计算机上 CQD 多维数据集。 QoE 存档组件也可能是如果组织只想要不达到监控服务器上的性能限制存档的 QoE 数据的可持续方法安装的唯一 CQD 组件。
  
![单服务器 CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **承载"开发"门户"生产"门户分开。** 开发自己的自定义报告 （通过 REST Api 中) 的组织可能更愿意部署生产常规用户访问用于呼叫的质量监控或调查的门户旁的其他 (CQD) 门户实例。 开发门户可以隔离到门户网站从生产环境的任何修改。 可以部署在不同的计算机 （如下所示） 或部署到不同的 web 目录 （不显示） 的相同计算机上的其他 web 门户。 若要完成后者，其他 CQD web 门户必须将复制到生产计算机手动因为 CQD 安装过程始终将 CQD Web 门户部署到默认网站使用预定义的 web 应用程序名称。
  
![计划 CQD 多服务器](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>支持的拓扑

就像 CQD 不合并来自多个 QoEMetrics 数据库，其中有多个 Skype 的企业服务器拓扑，每个都有其自己的监控服务器。 每个 CQD 实例必须指向一个 QoEMetrics 数据库。 但是，因为 CQD 将移动何种移开监控服务器报告的工作负荷，企业服务器拓扑中部署每 Skype 的一台监控服务器所需的大型组织应考虑的所有拓扑使用一台监控服务器。
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD 的基础结构要求
<a name="Infrastructure_Req"> </a>

虚拟机，一台计算机上或跨多台计算机，则可以部署 CQD，包括其所有组件和相关组件。 下面列出的最低软硬件要求。 数据可用性和性能因分钟到数小时，具体取决于业务 Server 用户和硬件和配置，活动 Skype 数的查询，以便一些性能度量如下所示。
  
|||
|:-----|:-----|
|支持的操作系统  <br/> |Windows Server 2008 R2、 Windows Server 2012、 Windows Server 2012 R2  <br/> |
|支持的 SQL Server  <br/> |SQL Server 2008 R2，SQL Server 2012，SQL Server 2014  <br/> |
   
CQD 利用 Microsoft SQL Server、 Microsoft SQL Server Analysis Services 和 Microsoft Internet 信息服务，因此 CQD 的最低硬件和软件要求基本上与这些依赖的组件相同。 但是，根据组织的要求围绕数据刷新 （这将取决于部分的组织将生成的 QoE 数据量） 和部署成本，其他部署注意事项应将。
  
CQD 中的数据处理被分为两个主要阶段： 
  
- QoE 存档进程
    
- CQD 多维数据集处理
    
  **QoE 处理存档。** QoE 存档处理任务将数据从监控服务器上的 QoE 指标数据库复制到 QoE 存档数据库。 有两种情况下的任务的处理时间必须发生根本性不同的性能特征。 首先是 CQD 在初始安装后。 任务在首次运行全新安装后，QoE 存档处理任务会将复制到 QoE 存档数据库的 QoE 指标数据库中的所有数据。 第二个是此初始舍入后的定期处理。 处理任务 QoE 存档将每 15 分钟运行和处理的 QoE 指标数据库中的任何新的 QoE 记录。 通常的初始的处理时间是不担心，因为它运行只在首次，当安装 CQD。 但是，如果 CQD 服务器是严重下设置，该任务中可能需要数小时。 请参阅下例如初始 QoE 存档处理时间表。
  
  **CQD 多维数据集处理。** 多维数据集处理任务将数据从 QoE 存档数据库聚合到多维数据集。 由用于 CQD 多维数据集的 SQL Server Analysis Services 版本确定的初始多维数据集处理时间和后续多维数据集处理时间。 如果使用标准版，则没有任何差别之间的初始多维数据集处理时间和后续多维数据集处理时间，因为每次刷新多维数据集数据，将始终是所有可用的数据的完整处理。 （这意味着的多维数据集处理时间随着 QoE 存档数据库增加中的数据量。）由于的业务智能 Edition 和 Enterprise Edition 的 SQL Server 具有分区支持，如果使用两种版本中，仅初始运行将处理 QoE 存档数据库中的所有数据。 在后续运行时触发任务每隔 15 分钟，任务将仅处理最后一次运行任务添加到 QoE 存档数据库的新记录。 每天一次，也有包含当前月份的数据分区上完全处理。
  
物理计算机特征会影响 CQD 性能，以及可从 SQL Server 组件的软件功能。 QoE 存档组件将更多磁盘密集型与其他组件，而多维数据集组件将更多的 CPU 和内存占用大量。 所有这些因素参与到 CQD 的总数据处理时间，直接影响数据刷新和可用性。 组织应做出上的硬件和软件基于组织的个别需求的决策。 
  
### <a name="tested-hardware-configurations"></a>测试的硬件配置

本节假设在环境中存在单个的 QoEMetrics DB。 
  
**计算机配置文件**

|**计算机**|**CPU 内核**|**RAM**|**QoE 存档和同一磁盘上的多维数据集**|**QoE 存档和同一磁盘上的 SQL 临时 DB**|
|:-----|:-----|:-----|:-----|:-----|
|虚拟机  <br/> |4  <br/> |7 GB  <br/> |是  <br/> |是  <br/> |
|四核  <br/> |4  <br/> |20 GB  <br/> |是  <br/> |否  <br/> |
|8 核心  <br/> |8  <br/> |32 GB  <br/> |是  <br/> |否  <br/> |
|16 核心  <br/> |16  <br/> |128 GB  <br/> |否  <br/> |否  <br/> |
   
**性能结果**

|**计算机**|**数据库大小的 QoE 指标**|**SQL 分区**|**磁盘类型**|**流的数量**|**初始存档过程**|**初始多维数据集过程**|**后续存档进程**|**后续的多维数据集过程**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|虚拟机  <br/> |900 MB  <br/> |单个  <br/> |VHD （变量大小）  <br/> |.5 M  <br/> |30 分钟  <br/> |2m  <br/> |30 s  <br/> |1m  <br/> |
|虚拟机  <br/> |9 GB  <br/> |单个  <br/> |VHD （变量大小）  <br/> |5 分钟  <br/> |4 h  <br/> |15 分钟  <br/> |1m  <br/> |5 分钟  <br/> |
|虚拟机  <br/> |9 GB  <br/> |单个  <br/> |VHD （固定大小）  <br/> |5 分钟  <br/> |2 h  <br/> |5 分钟  <br/> |1m  <br/> |5 分钟  <br/> |
|虚拟机  <br/> |30 + GB  <br/> |单个  <br/> |VHD （固定大小）  <br/> |10M  <br/> |15 h  <br/> |20 m  <br/> |2m  <br/> |45 m  <br/> |
|8 核心  <br/> |9 GB  <br/> |单个  <br/> |多个磁盘  <br/> |5 分钟  <br/> |2 h  <br/> |5 分钟  <br/> |25 s  <br/> |5 分钟  <br/> |
|8 核心  <br/> |9 GB  <br/> |多个  <br/> |多个磁盘  <br/> |5 分钟  <br/> |2 h  <br/> |15 分钟  <br/> |35 s  <br/> |2m  <br/> |
|8 核心  <br/> |30 + GB  <br/> |单个  <br/> |多个磁盘  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1m  <br/> |20 m  <br/> |
|8 核心  <br/> |30 + GB  <br/> |多个  <br/> |多个磁盘  <br/> |20 M  <br/> |9 h  <br/> |30 分钟  <br/> |2m  <br/> |2m  <br/> |
|四核  <br/> |200 GB  <br/> |单个  <br/> |多个磁盘  <br/> |125 M  <br/> |6 + 天  <br/> |7 h  <br/> |2m  <br/> |6 h  <br/> |
|16 核心  <br/> |500 GB  <br/> |多个  <br/> |多轴  <br/> |250 M  <br/> |8 天  <br/> |2 h  <br/> |2m  <br/> |10m  <br/> |
   
\*这些不会因为的 QoE 指标数据库者必须分别有 9 和 18 个月的数据，但它们为了完整性，此处提供在实际部署中遇到。
  
### <a name="service-account-requirements"></a>服务帐户要求

您将需要 CQD 服务器上的 SQL 代理可用于将数据导入到 QoEArchiveDB （具有读取权限 QoEMetrics） 的帐户。
  
您可能还需要将单独的帐户 SSAS 作业配置为提取数据，从 QoEArchiveDB （这是一个可选的过程）。
  
IIS 最常使用网络服务作为应用程序池标识，但可配置为服务帐户。
  
### <a name="portal-access-control"></a>门户访问控制

默认情况下，任何身份验证的用户具有访问权限。 这可以通过使用 IIS 授权规则将限制为特定组更改。
  
### <a name="pre-install-requirements"></a>预安装要求

这些说明假定的 QoE 指标数据库已安装和某个位置中的企业服务器拓扑 Skype 运行。
  
#### <a name="hardware-requirements"></a>硬件要求

CQD 利用 Microsoft SQL Server、 Microsoft SQL Analysis Server 和 Microsoft Internet Information Server，因此 CQD 的最低硬件和软件要求基本上与这些依赖的组件相同。 但是，根据组织的要求围绕数据刷新 （这将取决于部分的组织将生成的 QoE 数据量） 和部署成本，其他部署注意事项应将。
  
#### <a name="software-requirements"></a>软件要求

在以下操作系统所需的 CQD:
  
- 使用 IIS 7.5 的 Windows Server 2008 R2
    
- Windows Server 2012 with IIS 8.0
    
- 使用 IIS 8.5 的 Windows Server 2012 R2

- Windows Server 2016 IIS
    
以下是 （层次结构顺序） 中所需的 IIS 角色服务：
  
- Web 服务器
    
  - 常见的 HTTP 功能
    
  - 静态内容
    
  - 默认文档
    
  - 应用程序开发
    
  - ASP.NET
    
  - ISAPI 筛选器
    
  - 运行状况&amp;诊断
    
  - HTTP 日志记录
    
  - 安全性
    
  - URL 授权
    
  - Windows 身份验证
    
  - 管理工具
    
  - IIS 管理控制台
    
> [!NOTE]
>  请注意以下上述要求： 有 > 3.5 和.Net framework 4.5 版。 两者均需 （具体而言，3.5 SP1，则需要）。 > 中有些系统，如果 ASP.NET 为安装程序之前安装 IIS，然后 ASP.NET 可能未注册在 IIS 中。 通过不存在相应的.Net 版本和还缺少应用程序池配置中的.NET CLR 版本的应用程序池会出现该问题。 若要纠正此类问题 Windows Server 2008 R2 上的，执行`%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`。 在 Windows Server 2012 和 Windows Server 2012 R2 上，执行`dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45`跟删除从默认网站在的"ServiceModel"模块 > 管理工具是可选的但建议。 IIS 管理器。
  
若要安装使用 PowerShell 这些要求，运行以下命令：
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

SQL Server 的以下版本支持：
  
- SQL Server 2008 R2
    
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016
    
出于性能原因，建议您使用商业智能或 Enterprise edition。 这些版本允许使用的多个分区文件可以并行，这是有益于处理数据跨越多个月份或更长时间处理。 
  
时不推荐; 以及支持标准版。 处理将受到限制在单个分区 （它需要安装过程中配置）。 
  
在所有情况下，必须安装"数据库引擎服务"和"Analysis Services"。 它是建议，但不是要求也安装了"管理工具-完成"功能，添加对 Analysis Services 的 SQL Server Management Studio 支持。 功能选择屏幕应类似于图。
  
![SQL Server 功能要求](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
配置时 SSAS 安装程序，在 Analysis Services 配置，设置为"多维和数据挖掘模式"的"服务器模式"。 
  
在安装和配置 SQL Server 商业智能功能的更多帮助，请参阅[多维和数据挖掘模式下安装 Analysis Services](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx)。
  
#### <a name="account-requirements"></a>帐户要求

三个域服务帐户被建议的最小特权原则： 
  
- 一个已经登录安全主体的 QoE 指标数据库 （与 db_datareader 权限） 和登录安全主体 （需要安装过程中创建链接服务器对象） 的 QoE 存档 SQL Server 实例中。 此帐户将用于运行 SQL Server 代理作业的"QoE 存档数据"步骤。
    
- 一个用于运行 SQL Server 代理作业的"进程多维数据集"步骤。 安装程序将创建一个登录到 QoE 存档数据库的安全主体 (具有读取和写入权限) 和还创建多维数据集 （具有完全控制权限） 的 QoE 角色中的成员。
    
- 一个用于运行程序的 web 门户和 web Api 的 IIS 工作进程。 安装程序将创建登录名 （具有读取权限） 的 QoE 存档数据库的安全主体，登录到存储库数据库安全主体 (与读取和写入权限)，并中的多维数据集 QoERole （具有完全控制权限） 的成员。 
    
    > [!NOTE]
    > 当 QoE 存档数据库和存储库数据库位于同一 SQL Server 中时，将创建只有一个登录安全主体具有两个用户之间的映射。 
  
前两个帐户可以逻辑视为"后端服务帐户"和最后一个帐户为"前端服务帐户"。 虽然不建议，就可以在所有情况下使用一个帐户。
  
> [!NOTE]
> 启动安装的用户帐户必须具有对 QoE 指标 DB 的读取权限以及 （除了具有对必须执行安装 QoE 存档数据库服务器计算机管理员权限）。 
  
## <a name="capacity-planning"></a>容量规划
<a name="Infrastructure_Req"> </a>

CQD 专为对 QoEMetrics 影响最少： 优化了代码不锁定数据，并且可调导入作业。
  
若要使用的硬件的类型取决于同步应运行速度的要求。 磁盘大小调整为，如下所示：
  
- QoEArchive 最初是 ~1.5x 大于 QoEMetrics DB
    
- SSIS 多维数据集压缩的数据，几乎 10 x 到数据库比较
    
- 数据分区每月;可以删除分区
    

