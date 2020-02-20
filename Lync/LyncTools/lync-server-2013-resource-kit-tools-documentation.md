---
title: Lync Server 2013 资源工具包工具文档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 046e29fcec697a1ac073833e6b73c7bfe15fb8ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Lync Server 2013 资源工具包工具文档

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-01-09_

本主题介绍属于 Lync Server 2013 资源工具包的工具，其中包括每个工具的用途及其使用示例。Lync Server 2013 的资源工具包工具可帮助部署和管理 Lync Server 2013 的 IT 管理员更轻松地执行日常任务。 例如，可以使用**Web 会议数据**工具轻松地控制用户在联机会议期间上载的数据。 **SEFAUtil**工具可用于为用户设置代理呼叫转发和应答。 我们鼓励 IT 管理员使用这些工具更有效地管理 Lync Server 2013。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>资源工具包工具的安装

若要安装 Lync Server 2013、资源工具包工具，请下载**ocsreskit.msi**。 您可以从下载中心下载资源工具包工具安装程序[https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429)。

运行**ocsreskit.msi**以执行简单安装。 .Msi 在以下路径中安装所有工具： **% Program Files%\\Microsoft Lync Server 2013\\\reskit**。 包含自包含可执行文件的工具位于此文件夹中。 还包含文件的工具位于自己的子文件夹中。

</div>

<div>

## <a name="supported-environments"></a>支持的环境

为了获得最佳性能，Lync Server 2013，资源工具包工具应安装在相同的环境中，并且具有与 Lync Server 2013 所需的相同规范。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>资源工具包工具概述

以下列表介绍了 Lync Server 2013 资源工具包中提供的工具。 下一节中介绍了每个工具的说明，包括要求和示例用法。

  - ABSConfig

  - 带宽策略服务监视器

  - 带宽利用率分析器

  - 调用寄存时间记录器

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - 网络配置查看器

  - 响应组代理实时

  - SEFAUtil

  - SYSPrep. ps1

  - 未分配号码通知迁移

  - Web 会议数据

</div>

<div>

## <a name="absconfig"></a>ABSConfig

通讯簿服务配置工具（ABSConfig）是一种管理工具，可帮助管理员在 Lync Server 2013 中自定义通讯簿服务配置。 此工具还使 Lync Server 2013 管理员能够还原默认通讯簿服务设置。

<div>

## <a name="description"></a>说明

ABSConfig 是一个图形用户界面应用程序，使管理员能够配置与通讯簿服务相关的 Active Directory 域服务属性。

该工具的主要方案如下所示：

  - 使管理员能够将 Active Directory 域服务中的属性映射到 Lync Server 2013 的属性。

  - 使管理员能够指定要在通讯簿服务文件中包含或排除的 Active Directory 域服务属性。

  - 使管理员能够还原默认通讯簿服务设置。

可以使用 absConfig 文件启动 ABSConfig 工具。 该工具将打开 "**配置属性**" 选项卡。此表中的选项可用于将 Active Directory 域服务属性映射到 Lync Server 2013 的属性字段，并指定哪些用户在通讯簿服务文件中根据特定的属性筛选器包含或排除。 它还具有自定义要在通讯簿文件中包含的电话号码的值的选项。 "**还原默认**值" 选项使管理员能够将通讯簿服务设置还原为默认值。

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>来自 Lync Server 2010 的更改

在 Lync Server 2013 ABS 配置工具中，可以通过取消选中属性的 "启用" 复选框来删除属性（行）。 这与删除 Lync Server 2010 中的行的效果相同。

<div>


> [!NOTE]  
> "启用" 复选框位于最右侧的列中;您可能需要向右滚动才能看到列



</div>

</div>

<div>

## <a name="output"></a>Output

ABSConfig 将通讯簿服务配置存储在数据库中。

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>用途

ABSConfig 提供了一种快速、简便的方法来自定义 Lync Server 2013 通讯簿服务。

</div>

<div>

## <a name="requirements"></a>Requirements

<div>

## <a name="computer"></a>计算机

只能从安装了 Lync Server 2013 的加入域的计算机运行 ABSConfig。 在 Lync Server 2013 （Enterprise Edition）的情况下，可以在安装过程中启用了通讯簿服务的任何前端服务器上运行此工具。

</div>

<div>

## <a name="network"></a>网络

计算机应能够连接到前端池和后端数据库。

</div>

<div>

## <a name="software"></a>软件

在运行 ABSConfig 工具之前，必须安装以下软件组件：

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>用户

拥有更新 Lync Server 2013 部署所需权限的管理员。

</div>

</div>

<div>

## <a name="examples"></a>示例

可以通过在命令提示符处键入**ABSConfig**来启动 ABSConfig。 下面显示的是 ABSConfig 工具用户界面。

![ABSConfig 工具。](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig 工具。")

</div>

<div>

## <a name="summary"></a>总结

ABSConfig 工具为管理员提供了一个快速且易于使用的工具，可用于自定义 Lync Server 2013 通讯簿服务。

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>带宽策略服务监视器

带宽策略服务监视器工具旨在允许管理员查看以下项的列表：

1.  拓扑中所有已配置的 Lync Server 2013 带宽策略服务（身份验证和核心）

2.  每个服务对其他带宽策略服务和边缘服务器所做的连接

3.  在网络配置文档中配置的所有链接，以及每个带宽策略服务报告的实时带宽使用率

<div>

## <a name="description"></a>说明

带宽策略服务监视器工具以基于 GUI 的应用程序的形式实现。 管理员通过运行 PDPMonUI 启动该工具。

当工具启动时，它将尝试发现拓扑中的带宽策略服务列表。 完成初始更新后，窗口左侧的窗格将使用由其所属群集分组的服务列表进行填充。

当管理员选择特定的带宽策略服务时，右侧窗格将显示有关该特定服务的信息。 该窗格还包含两个显示信息的主选项卡。

<div>

## <a name="machine-info-tab"></a>计算机信息选项卡

"**计算机信息**" 选项卡显示已选择的带宽策略服务的详细信息，以及由选定带宽策略服务对其他服务所做的所有连接的列表和状态。

</div>

<div>

## <a name="topology-info-tab"></a>拓扑信息选项卡

"**拓扑信息**" 选项卡显示在网络配置设置中配置的所有链接的列表。 对于每个链接，都会显示音频和视频带宽容量。 此外，当前使用的带宽以 Kbps 和容量百分比的形式显示。 该工具使用颜色编码突出显示具有接近容量的使用率的链接，这使管理员能够快速隔离此类链接。

<div>


> [!NOTE]  
> 如果带宽策略服务监视器工具在连接到任何已配置的带宽策略服务时遇到故障，则不会填充<STRONG>计算机信息</STRONG>和<STRONG>拓扑信息</STRONG>选项卡中的信息。 但是，该工具可能会在最初连接但随后失去与该服务的连接。 在这种情况下，管理员可能会看到过时的信息。 每个选项卡上都有<STRONG>最后更新</STRONG>的时间戳，这些选项卡可允许管理员查看特定带宽策略服务的上次更新数据的时间。



</div>

</div>

</div>

<div>

## <a name="output"></a>Output

没有命令行输出;程序输出包含在主图形用户界面（GUI）中。

</div>

<div>

## <a name="purpose"></a>用途

带宽策略服务监视器工具旨在使管理员能够查看拓扑中定义的每个带宽策略服务的状态。 此外，管理员可以查看网络配置文档中定义的所有链接的实时带宽使用率。

</div>

<div>

## <a name="requirements"></a>Requirements

带宽策略服务监视器工具需要在作为 Lync Server 拓扑的一部分的计算机上运行。

</div>

<div>

## <a name="summary"></a>总结

带宽策略服务监视器工具对于管理员来说是一项宝贵的资源，这样他们就可以检查拓扑中所有带宽策略服务的状态—更重要的是，它们可以获取链接的实时带宽利用率，在网络配置设置中定义。

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>带宽利用率分析器

带宽利用率分析器是一种工具，该工具通过企业网络中的多个 WAN 链接的 UC 终结点创建有关带宽消耗的各种视图的报告。 这些报告可用于了解当前带宽消耗模式，并可帮助进行带宽容量规划。

<div>

## <a name="description"></a>说明

带宽利用率分析器是作为基于 GUI 的应用程序实现的。 此工具专门针对网络中的音频利用率生成报告，并帮助进行容量规划。 它还会对分配给各个链路的带宽容量进行迭代。

</div>

<div>

## <a name="output"></a>Output

带宽利用率分析器为系统中配置的所有 WAN 链路提供了图形 al 的带宽容量和使用情况的视频。

</div>

<div>

## <a name="purpose"></a>用途

在任何语音和视频部署中，监视和理解整个企业网络中媒体流量的带宽利用率趋势非常关键。 利用带宽利用率分析器工具，管理员即可实现这一点。 此工具执行以下操作：

  - 为整个网络中的音频利用率生成特定报告

  - 有助于在分配给各个链路的带宽容量中进行更有效的容量规划和迭代

带宽利用率分析器可生成带宽容量和使用率报告的图形化绘图;它们如下所示：

  - 企业网络中的所有 WAN 链路

  - 通过选定的已选择的 WAN 链接进行筛选

  - 通过已超出链接容量的 WAN 链路进行筛选

  - 通过已在使用预配带宽的 WAN 链接进行筛选

  - 按已达到关键级别的 WAN 链路进行筛选（WAN 链路带宽使用率大于90% 的带宽使用率）

  - 按 WAN 链接类型（网络站点链接、区域间链接和站点内的链接）进行筛选

  - 按网络区域筛选

<div>

## <a name="applications"></a>应用程序

带宽使用率分析器包含以下两个应用程序（工具）：

  - **Wanlinklogcollector.exe**   此工具使其用户能够输入所需的信息。

  - **Bandwidthutilizationanalyzer.xlsm xlsm**  Microsoft Excel 电子表格软件报告由 wanlinklogcollector.exe 自动启动。 此应用程序允许用户将筛选器应用于报表，如本文后面所示。

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>使用带宽使用率分析器的各个阶段

使用带宽使用率分析器时有两个阶段：

  - 收集使用 Wanlinklogcollector.exe 执行的日志

  - 自定义报表，通过使用 Bandwidthutilizationanalyzer.xlsm 执行。 xlsm

<div>


> [!IMPORTANT]  
> 强烈建议最终用户手动启动 xlsm Bandwidthutilizationanalyzer.xlsm。



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>启动带宽使用率分析器

在命令提示符处或使用 Windows 资源管理器启动 Wanlinklogcollector.exe。

**使用 Wanlinklogcollector.exe**

使用 Wanlinklogcollector.exe 有三个步骤：

1.  **日志时间线**   提供需要生成报告的时间线

2.  **指定文件目录**   提供文件位置信息

3.  **收集日志并启动报告查看器**  执行命令以生成报告

<div>

## <a name="step-1---log-the-timeline"></a>步骤 1-记录日程表

记录日程表时，工具用户可以按下图所示指定以下各项。

1.  **开始日期**这是要为其生成报告的时间线的开始日期;例如，2010年8月1日。

2.  **结束日期**这是要为其生成报告的时间线的结束日期;例如，2010年9月30日。
    
    ![带宽利用率中的开始和结束日期](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "带宽利用率中的开始和结束日期")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>步骤 2-指定文件目录

用户可以按如下所示指定文件目录。

  - **服务器日志文件位置**存储带宽策略服务器日志的文件夹位置。 这通常是在\<\\AppServerFiles\>\\\<\>\\PDP 的登录选择中。

  - **临时文件存储位置**生成报告时存储中间文件的临时文件位置。

![带宽利用率用量中的文件目录](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "带宽利用率用量中的文件目录")

<div>


> [!NOTE]  
> 确保向工具用户提供了对服务器日志和临时文件存储文件夹的足够文件访问权限。



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>步骤 3-收集日志并启动报告查看器

若要收集日志并启动报告查看器，请单击 "**执行**"，如下所示。 此步骤将收集所需的数据。

![在带宽利用率用量中收集数据](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "在带宽利用率用量中收集数据")

输入验证成功后，将显示下面显示的消息。

![在带宽 Utili 中记录收集的通知](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "在带宽 Utili 中记录收集的通知")

单击“确定”。 Bandwidthutilizationanalyzer.xlsm 将自动启动。 按照消息框中的说明进行操作。 有关详细信息，请参阅下一节中的**Using bandwidthutilizationanalyzer.xlsm. xlsm** 。

</div>

<div>


**使用 Bandwidthutilizationanalyzer.xlsm。 xlsm**

1.  如果 xlsm 自动启动，请单击 "**刷新**"，如下所示。
    
    ![Bandwidthutilizationanalyzer.xlsm。 xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "Bandwidthutilizationanalyzer.xlsm。 xlsm")

2.  打开文件文件夹后，从消息框中指定的位置选择 "合并" .csv，如下所示。 它还将位置显示为**C：\\Temp**。
    
    ![打开 Bandwidthutilizationanalyzer.xlsm 中的文件夹。](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "打开 Bandwidthutilizationanalyzer.xlsm 中的文件夹。")

3.  单击“导入”****。

4.  图形绘图将自动生成。 它在后台工作指针消失时可用。
    
    ![在报告视图中应用筛选器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在报告视图中应用筛选器。")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>将筛选器应用于报告视图

可应用于报告视图的筛选器如下所示：

![在报告视图中应用筛选器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在报告视图中应用筛选器。")

1.  **名称**按 WAN 链接筛选（筛选器位于图形右侧）。前缀表示以下链接类型;请参阅垂直（蓝色）框：
    
      - **S 网站**从网络站点到网络区域的 WAN 链接
    
      - **是站点间**两个网络站点之间的 WAN 链路
    
      - **R 区域间**两个网络区域之间的 WAN 链路

2.  **超出限制**按带宽利用率大于带宽容量的 WAN 链路进行筛选

3.  **关键级别**按带宽利用率达到90% 或大于带宽容量的 WAN 链路进行筛选

4.  未**充分利用**按 WAN 链路进行筛选，其带宽使用率已少于带宽容量的25%

5.  **链接类型**按以下 WAN 链接类型进行筛选：
    
      - **网络站点**类型
    
      - **站点间**类型
    
      - **区域间链接**类型

6.  **区域**按网络区域筛选

下图显示了前面介绍的筛选器。

按**名称**筛选。 选择需要在图形中显示的链接的列表。

![按名称在 Bandwidthutilizationanalyzer.xlsm 中进行筛选。](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "按名称在 Bandwidthutilizationanalyzer.xlsm 中进行筛选。")

按**超出限制**进行筛选。 选择 " **True** " 以强制执行筛选器。

![按超出限制进行筛选。](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "按超出限制进行筛选。")

按**临界级别**进行筛选。 选择 " **True** " 以强制执行筛选器。

![按关键级别进行筛选。](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "按关键级别进行筛选。")

按**使用**情况筛选。 选择 " **True** " 以强制执行筛选器。

![按使用情况进行筛选。](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "按使用情况进行筛选。")

按**链接类型**筛选。 选择需要显示的一个或一种类型。

![按链接类型筛选。](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "按链接类型筛选。")

按**区域**筛选。 选择需要显示其链接的区域列表。

![按区域筛选。](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "按区域筛选。")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>Requirements

  - .NET Framework 3。5

  - Microsoft Excel 2010 或 Excel 2007

</div>

<div>

## <a name="summary"></a>总结

带宽利用率分析器用于绘制网络中 UC 流量的音频带宽使用率。 此工具还可用于报告网络上的视频带宽使用率。

</div>

</div>

<div>

## <a name="call-parkometer"></a>调用寄存时间记录器

调用寄存时间记录器是一个命令行应用程序，可提供对呼叫寄存轨道数据库的轻松访问。

<div>

## <a name="description"></a>说明

呼叫寄存时间记录器是一种跟踪当前寄存的呼叫的工具。 它还收集有关轨道式和呼叫寄存服务器（CPS）使用情况的统计信息。 此命令行工具提供对来自本地或远程连接的计算机上的 CPS 轨道 SQL Server 数据库的读写访问权限。

所有选项都是相互排斥的。 命令行语法如下所示：

  - **– o**参数-列出为此池配置的所有轨道范围。

  - **– n**参数—列出此池中当前使用的所有轨道。 显示的信息如下所示：
    
      - Parkee 和 parker 的 SIP 统一资源标识符（URI）。
    
      - 寄存呼叫的 CPS 的主机名。
    
      - 寄存呼叫时的时间戳。

  - **– f**参数-列出池中当前可用的轨道的数目。

  - **– r \<n\> **参数—列出\<n\>个最近寄存的呼叫。 显示的信息如下所示：
    
      - Parkee SIP URI。
    
      - Parker SIP URI。
    
      - 寄存呼叫的 CPS 的主机名。
    
      - 检索或丢弃呼叫时的时间戳。

  - **-t\<n\> **参数-测试在数据库中保留一种轨道，以显示分配的轨道编号的随机性。

</div>

<div>

## <a name="output"></a>Output

根据在命令提示符处指定的输入参数，调用寄存时间记录器显示以下输出：

  - 为此池配置的所有轨道范围

  - 当前寄存的呼叫

  - 空闲（可用）轨道式的数目

  - 最近寄存的呼叫

  - 用于测试统一和随机轨道值的保留轨道

</div>

<div>

## <a name="purpose"></a>用途

CPS 工具的目的是提供对 CPS 数据库的命令行访问。 管理员可以查看 CPS 使用情况，并确定分配给池的轨道式的数目。

</div>

<div>

## <a name="requirements"></a>Requirements

如果在运行 CPS 的同一台计算机上运行此工具，则没有任何要求。 如果此工具在远程计算机上运行，则必须将 Lync Server 2013 使用的 SQL Server 数据库配置为允许远程访问。 必须使用 SQL Server 数据库连接字符串配置调用寄存时间记录器以连接到池的 SQL Server。 此 SQL Server 数据库连接字符串是在配置文件**寄存时间记录器**中定义的。它必须放在寄存时间记录器所在的同一目录中。 下面的 XML 文件是一个寄存时间记录器的示例。必须配置的参数为用户名（例如，mydomain\\管理员）、密码（例如，mypassword）以及主机名称（例如，myserver）。

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a>示例

已部署的轨道范围：– o 参数列出为此池配置的所有轨道范围，如图所示

![呼叫寄存时间记录器中的轨道范围。](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "呼叫寄存时间记录器中的轨道范围。")

当前寄存的呼叫：– n 参数列出此池中当前使用的所有轨道，如下所示

![呼叫寄存时间记录器中当前寄存的呼叫。](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "呼叫寄存时间记录器中当前寄存的呼叫。")

自由轨道式的数目：– f 参数列出了池中当前可用的轨道式的数目，如图所示

![调用寄存时间记录器中的自由轨道式。](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "调用寄存时间记录器中的自由轨道式。")

最近寄存的呼叫：– r \<n\>参数列出 n \<\>个最近寄存的呼叫，如下所示

![呼叫寄存时间记录器中最近寄存的呼叫。](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "呼叫寄存时间记录器中最近寄存的呼叫。")

测试轨道保留：– t \<n\>参数测试在数据库中保留一个轨道，如下所示

![在呼叫寄存时间记录器中测试轨道保留。](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "在呼叫寄存时间记录器中测试轨道保留。")

</div>

<div>

## <a name="summary"></a>总结

呼叫寄存时间记录器是一个命令行工具，提供有关呼叫寄存服务器的详细信息。

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

CleanupStorageServiceData 资源工具包工具允许从 Lync Server Storage Service （LYSS）使用的数据库中删除孤立的数据。 存储服务的一个功能是在 Lync Server 和不同的后端数据存储终结点（如 SQL Server 和 Exchange）之间缓冲通信。

<div>

## <a name="description"></a>说明

为了支持高可用性，LYSS 在池中临时接收并保存多个前端服务器上的数据副本，并在将数据传递到其最终长期存储位置后将其删除。 在某些情况下，如果服务器可能崩溃或遇到处理问题，并且某些数据可能无法正确清理，则在其他正常操作过程中可能会发生异常情况。 此数据是无害的，但它会占用有限的处理资源。 大部分正常的必要数据维护都是自动进行的，但是此工具允许在无法进行自动删除时对此类孤立数据进行安全标识和删除。 当出现运行状况监视 System Center Operations Manager （SCOM）警报时，将提示管理员从池中的本地 LYSS 数据库中删除不需要的数据时，将显示此工具的使用情况。 在触发警报的前端上的事件日志中将会有相应的事件。 事件详细信息将包含前端上包含的孤立数据量的相关信息，并在该数据超过某些预确定阈值时引发。

</div>

<div>

## <a name="requirements"></a>Requirements

安装 Lync Server 2013 （资源工具包工具）。 该工具在安装了 Lync Server 和 Lync Server 2013 命令行管理程序的加入域的计算机上运行。 该工具使用命令行管理程序中的 cmdlet 来标识池中的所有前端服务器。 其次，该工具必须从安装了**RtcLocal**数据库的池中的计算机执行。 CleanupStorageServiceData 工具使用此数据库来获取与 Lync Server 路由服务通信所需的连接详细信息。最后，调用该工具的帐户或凭据必须具有对要向其写入输出日志的文件共享的读/写权限。此外，此工具依赖于池处于稳定状态。 实际上，这意味着每台前端服务器都应正常运行，SQL Server LYNCLOCAL 实例和 LYSS 数据库必须能够连接到，并且每个路由组必须具有一套完整的1个主前端服务器和2个辅助前端 servers.

</div>

<div>

## <a name="examples"></a>示例

C：\\Program Files\\Microsoft Lync Server 2013\\\reskit\\StorageService\> ImportStorageServiceData

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a>DBAnalyze

<div>

## <a name="description"></a>说明

DBAnalyze 是一个命令行工具，可帮助管理员收集有关 Lync Server 2013 数据库的分析报告。 DBAnalyze 具有以下模式：诊断、用户数据、会议、Mcu 和磁盘碎片：

  - **诊断模式**   创建一个报表，其中包含有关表的信息（记录数、碎片、数据大小和索引大小、数据和日志文件大小、最近的备份时间、在运行 Microsoft Office 通信服务器的服务器之间的联系人分布、平均权限数、联系人、容器、订阅、发布、每个用户的终结点、任何不正确的托管用户、无法路由的用户、计划的平均会议数会议、活动会议和数据库版本。
    
    <div>
    

    > [!NOTE]  
    > 运行诊断模式可能会影响服务器性能。

    
    </div>

  - **用户数据模式**  报告指定用户或其联系人和权限列表中具有该用户的用户的联系人、容器、订阅、发布、权限和联系人组数据。 此模式还报告用户组织或受邀的会议的摘要数据。

  - **会议模式**   报告特定会议的详细数据，包括会议的所有计划时间详细信息、被邀请者列表、会议允许的媒体类型列表、活动 mcu （multipoint 控制单位）、活动参与者列表和每个参与者的信号状态。

  - **解码会议 id**  解码由 **/pstnid**开关指定的公用电话交换网（PSTN）会议 ID，但不连接到后端以了解详细信息。

  - **解析会议**   解码由 **/pstnid**开关指定的 PSTN 会议 ID，并显示由 ID 指示的会议的相关信息。

  - **Mcu 模式**  报告池中每个 MCU 的 ID、媒体类型、URL、检测信号状态、会议负载和参与者负载。

  - **磁盘碎片模式**  显示所有磁盘的碎片状态。

此工具可用于诊断各种问题或帮助管理员进行容量规划。 例如，如果驻留在服务器上的大多数用户都选择用户驻留在服务器 B 上作为其联系人，则管理员可以将服务器 A 上的用户移动到服务器 B 以减少跨服务器流量。

</div>

<div>

## <a name="output"></a>Output

此工具输出有关 Lync Server 2013 数据库的预定义报告。 **路径：** % ProgramFiles%\\Microsoft Lync Server 2013\\\reskit

</div>

<div>

## <a name="purpose"></a>用途

若要安装 Dbanalyze，请将其复制到本地文件夹，然后运行该工具。 若要使用此工具，请从命令行运行以下命令。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 下面显示了有关命令行选项的说明。

![Dbanalyze 的命令行选项。](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze 的命令行选项。")

</div>

<div>

## <a name="requirements"></a>Requirements

**计算机**只能从安装了 Lync Server 2013 的加入域的计算机运行 DBAnalyze。

**网络**计算机应能够连接到后端数据库。

**软件**在运行 DBAnalyze 之前，必须安装 Lync Server 2013 软件组件。

**用户**下表显示了具有访问 Lync Server 2013 数据库所需的权限的管理员。

![Dbanalyze 的权限表。](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze 的权限表。")

<div>


> [!NOTE]  
> <STRONG>/Report：磁盘</STRONG>模式需要本地管理员帐户。



</div>

</div>

<div>

## <a name="examples"></a>示例

以下是有效 Dbanalyze 命令的示例：

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>总结

DBAnalyzer 为管理员提供了快速而轻松地分析 Lync Server 2013 数据库的情况。

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

ImportStorageServiceData 资源工具包工具允许将在存储服务（LYSS）上刷新的队列和终结点数据重新导入到存储服务中。

<div>

## <a name="description"></a>说明

从存储服务中刷新的数据可能已基于队列项目状态或数据库大小自动（定期）。 由于手动调用池故障转移 cmdlet 或 StorageServiceFullFlush cmdlet （池故障转移 cmdlet 调用），可能会发生此问题。 请注意，如果前端上的任何存储服务（LYSS）数据库大小高于正常级别，则不应重新导入数据，因为这样做可能只会导致更多数据被导出回来。此外，应首先解决导致存储服务队列增长的错误可能会导致出现的任何问题（例如 Exchange 终结点错误、网络问题或其他问题）。

**方案1：** 在池故障转移过程中，可能会从每个前端的存储服务中刷新文件。 故障转移完成后，应运行该工具以重新导入数据。

**方案2：** 每日自动刷新数据或响应超过特定大小阈值的 Storage Service 数据库（例如，60%、80%、90% 已满）。 此自动刷新的数据应由管理员定期重新导入。 在上述情况下，如果未部署监控 SCOM 包，则会出现与从存储服务刷新的数据相关的 Lync Server Storage Service 的事件。 事件 Id 为32075（已启动完全刷新操作）、32076（已完成完全刷新）、32082（维护级别刷新已启动）、32083（维护级别刷新完成）、32089（因填充数据库而发生刷新）。 注意，这些事件 Id 对应于 RTM 版本。 当管理员看到这些事件时，意味着已清除的文件。应使用此工具定期导入此数据，例如每周一次。

对于在线服务版本，如果部署了 Lync Server 的运行状况监视 SCOM 包，则可能会引发新警报，要求管理员将刷新后的数据重新导入存储服务。 在触发警报的前端服务器上的事件日志中将会有相应的事件。 该事件将提供刷新数据文件所在的父路径的说明，以及有多少个文件符合警报条件。 警报条件是特定父路径下的 X 或更多文件，这些文件至少为 Y 天旧（其中 X 和 Y 是在 StorageService 中预设的，但可以通过更改 APPCONFIG 文件进行重写。）下面显示了可以触发运行状况警报的事件的两个示例，区别在于它们的父路径。 有一种可能的情况是 Web 服务文件共享，而另一个可能的是每个前端的本地应用程序数据目录。 （例如，c：\\ProgramData\\Microsoft\\Lync Server\\StorageService）。 然后，管理员将运行此 \reskit 工具。

此工具会在其运行的前端上增加 CPU 和 IO 负载，以及其他前端，在数据不是在其上执行该工具的前端所拥有的情况下。 我们建议在前端不低于 CPU 和 IO 负载（例如在高峰时段之外）时 runng 此工具。 其次，此工具可以2至3分钟导入一个数据文件。 在估计工具的运行时间时，请记住这一点。默认情况下，该工具生成的详细日志文件将显示在文件存储上。 如果没有报告错误，则将其删除，因为日志文件可能是数十 MB 或更多。

![示例存储服务器事件日志事件。](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "示例存储服务器事件日志事件。")

</div>

<div>

## <a name="requirements"></a>Requirements

安装 Lync Server 2013 （资源工具包工具）。 该工具在安装了 Lync Server 和 Lync Server 命令行管理程序的加入域的计算机上运行。 该工具使用命令行管理程序中的 cmdlet 来标识池中的所有前端服务器。 其次，该工具必须从安装了**RtcLocal**数据库的池中的计算机执行。 工具使用此数据库检索池的 WEBSERVICE 文件共享的位置。此外，在使用此工具之前，每台前端服务器必须首先在每台前端服务器上使用**enable-psremoting**启用 Windows PowerShell 远程，以及执行该工具的计算机。 否则，此工具的远程 Windows PowerShell 命令将失败。 完成后，可以在池中的所有前端服务器上关闭 Windows PowerShell 远程处理。 最后，调用该工具的帐户或凭据必须具有对要在其上执行此工具的池的 webservice 文件共享的读/写权限。 否则，该工具将因 IO 权限错误而失败。

<div>


> [!NOTE]  
> 在 Windows Server 2012 中，Windows PowerShell 远程处理在默认情况下处于启用状态，而不是在 Windows Server 2008 操作系统上启用。



</div>

</div>

<div>

## <a name="examples"></a>示例

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a>LCSSync

LCSSync 工具可帮助在多林环境中部署 Lync Server 2013 通信软件。 此工具用于将不同用户林的用户和组作为 Active Directory 域服务联系人对象同步到安装了 Lync Server 2013 的中央林。

<div>

## <a name="description"></a>说明

LCSSync 使用中央林中的同步 Active Directory 域服务联系人对象为用户启用 Lync Server。 若要提供单一登录，必须将主用户帐户映射到适用于 Lync Server 2013 的中央林中的 Active Directory 域服务联系人对象。 此工具可帮助执行该映射。 此工具提供用于在 Microsoft Identity Integration Server 中创建管理代理的模板。

</div>

<div>

## <a name="summary"></a>总结

LCSSync 工具可帮助在多林环境中部署 Lync Server。

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

LookupUserConsole 工具显示有关特定用户的内部 Lync Server 路由信息。 此信息可能对 Microsoft 支持个人在诊断部署和路由问题方面有用。

<div>

## <a name="description"></a>说明

执行 LookupUserConsole 将打开一个命令提示符，该命令提示符接受 SIP 地址，并尝试显示与它们相关的内部 Lync Server 路由信息。 键入**exit**退出 LookupUserConsole 工具。

</div>

<div>

## <a name="requirements"></a>Requirements

安装 Lync Server 2013 （资源工具包工具）。 该工具在安装了 Lync Server 的加入域的计算机上运行

</div>

<div>

## <a name="examples"></a>示例

C：\\程序文件\\Microsoft Lync Server 2013\\\reskit\>LookupUserConsole

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a>MsTurnPing

MSTurnPing 工具允许 Microsoft Lync Server 2013 通信软件的管理员检查运行 "音频/视频边缘" 和 "音频/视频身份验证服务" 的服务器的状态，以及在拓扑中运行带宽策略服务的服务器的状态。

<div>

## <a name="description"></a>说明

MSTurnPing 工具允许 Lync Server 2013 通信软件的管理员检查运行 "音频/视频边缘" 和 "音频/视频身份验证服务" 的服务器的状态，以及在拓扑中运行带宽策略服务的服务器的状态。

此工具允许管理员执行以下测试：

1.  A/V 边缘服务器测试：该工具通过执行以下操作，对拓扑中的所有 A/V 边缘服务器执行测试：
    
      - 验证 Lync Server 音频/视频身份验证服务是否已启动，并可颁发正确的凭据。
    
      - 验证 Lync Server 音频/视频边缘服务是否已启动，并可以成功地在外部边缘上分配资源。

2.  带宽策略服务测试：该工具通过执行以下操作，对运行此拓扑中的带宽策略服务的所有服务器执行测试：
    
      - 验证 Lync Server 带宽策略服务（身份验证）是否已启动，并可颁发正确的凭据。
    
      - 验证 Lync Server 带宽策略服务（Core）是否已启动并可以成功执行带宽检查。

必须从作为拓扑一部分的计算机运行此工具，并安装本地存储。

</div>

<div>

## <a name="output"></a>Output

该工具将输出每个操作的结果。

  - 如果执行了**AudioVideoEdgeServer**测试，则工具输出如下所示：
    
      - 在拓扑中提供 Lync Server 音频/视频身份验证服务的计算机的测试结果
    
      - 在拓扑中提供 Lync Server 音频/视频边缘服务的计算机的测试结果

  - 如果执行了**BandwidthPolicyServer**测试，则工具输出如下所示：
    
      - 在拓扑中提供 Lync Server 带宽策略服务（身份验证）的计算机的测试结果
    
      - 在拓扑中提供 Lync Server 带宽策略服务（核心）的计算机的测试结果

</div>

<div>

## <a name="requirements"></a>Requirements

  - 此工具必须从拓扑中的计算机运行，且具有本地存储。

  - 该工具必须以具有本地存储访问权限的管理员身份运行。

</div>

<div>

## <a name="examples"></a>示例

以下是工具输入的一个示例。

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>总结

对于要检查运行音频/视频和带宽策略服务的服务器的状态的 Lync Server 2013 管理员，此工具可能是一种有用的资源。

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>网络配置查看器

Microsoft Lync Server 2013 通信软件管理员可使用网络配置查看器查看已预配的企业的呼叫允许控制（CAC）网络拓扑，以允许实时通信会话（如语音或基于指定带宽容量的视频呼叫。 Lync Server 2013 管理员定义 CAC 策略，这些策略由随 Lync Server 2013 一起安装的带宽策略服务强制实施。

<div>

## <a name="description"></a>说明

网络配置查看器（NetworkConfigurationViewer）允许管理员执行以下任务：

  - 以图形格式从 Lync Server 2013 部署中加载和查看 CAC 网络拓扑。

  - 以图形格式从带宽策略服务器日志文件中加载和查看 CAC 网络拓扑。

  - 以 XML 格式在磁盘上保存和存储 CAC 网络拓扑。

  - 以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图。

  - 查看 CAC 网络拓扑配置数据。

  - 在树视图样式中查看 CAC 网络拓扑。

  - 为 CAC 网络拓扑链接（例如，站点到区域、区域到区域和站点到站点链接）定义自定义连接器。

  - 查看 CAC 网络拓扑网站信息、区域信息，以及预配的带宽策略和网络链接。

</div>

<div>

## <a name="purpose"></a>用途

在图形界面中查看企业 CAC 网络拓扑链接。

</div>

<div>

## <a name="examples"></a>示例

**以图形格式从 Lync Server 2013 部署加载和查看 CAC 网络拓扑：** Lync Server 2013 管理员可以使用 "**下载网络配置**" 选项在任何 Lync server 2013 计算机上加载并查看 CAC 网络拓扑配置，如下图所示。 在没有连接到 Lync 配置存储的计算机上部署时，该工具将无法下载或查看此类配置。

![下载网络配置。](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "下载网络配置。")

**以图形格式从带宽策略服务器日志文件中加载和查看 CAC 网络拓扑：** Lync Server 2013 带宽策略服务器将 CAC 网络拓扑保存为 Lync Server 2013 文件共享位置下的日志记录机制的一部分。 Lync Server 管理员可以使用 "**打开网络配置**" 选项以图形格式查看此类文件，如下所示。

![打开带宽策略服务器日志文件。](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "打开带宽策略服务器日志文件。")

在磁盘上以 XML 格式保存和存储 CAC 网络拓扑： Lync Server 2013 管理员可以使用 "**保存网络配置**" 选项的副本以 xml 格式保存 cac 网络拓扑配置文件，如下所示。 然后，可以将已保存的配置文件脱机用于图形化查看目的。

![将网络配置另存为 XML 文件。](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "将网络配置另存为 XML 文件。")

以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图： Lync Server 2013 管理员可以使用 "**将网络配置图表另存为图片**" 选项以图形格式（JPG 和 BMP 文件格式）保存 cac 网络拓扑配置，如下所示。

![将网络配置另存为图片。](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "将网络配置另存为图片。")

**查看 CAC 网络拓扑配置数据：** Lync Server 2013 管理员可以使用如下所示的 "查看网络配置数据" 选项，以文本格式查看相关网络配置数据，例如网络区域、网络站点、带宽配置文件和站点子网 IP 地址。

![查看网络配置数据。](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "查看网络配置数据。")

**在树视图样式中查看 CAC 网络拓扑：** Lync Server 2013 管理员可以使用工具窗口左侧的 "控制面板" 中的 "控制" 面板查看图形树视图样式中的相关网络配置数据，如下所示。

![在树视图中查看网络配置数据。](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "在树视图中查看网络配置数据。")

**为 CAC 网络拓扑链接定义自定义连接器（如站点到区域、区域到区域和站点到站点链接）：** Lync Server 2013 管理员可使用如下所示的 "设置" 选项定义自定义的 CAC 网络配置 WAN 链接的图形连接器。 这有助于区分在网络配置中预配的各种类型的网络链接。

![为 CAC 网络拓扑定义自定义连接器](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "为 CAC 网络拓扑定义自定义连接器")

**查看 CAC 网络拓扑网站信息、区域信息和预配的带宽策略：** Lync Server 2013 管理员可以通过使用下面所示的选项查看相关的 CAC 网络区域信息、网站信息和 CAC 带宽设置信息。 （例如，单击 "网络区域" 或 "网络站点" 对象中的 "**信息**"。）

![为你的网络定义自定义连接器。](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "为你的网络定义自定义连接器。")

</div>

<div>

## <a name="summary"></a>总结

对于希望以图形格式查看其部署的 CAC 网络拓扑的 Lync Server 2013 管理员，此工具可能是一种宝贵的资源。

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>响应组代理实时

响应组应用程序使代理能够使用其内置 Web 服务访问有用的实时信息。 遗憾的是，在应用程序外，此数据的图形视图不可用。 响应组代理实时资源工具包工具解决了此问题，方法是提供一种简单且图形化的方式来访问此信息，并使用实时 Microsoft Lync 2013 通信软件信息（如其他代理的状态）进行了改进。

<div>

## <a name="description"></a>说明

响应组代理 Live 是一种 Windows 应用程序，它向响应组代理提供登录和注销功能以及一些实时信息（如组成员身份和当前呼叫数）。 它应是 "代理组" 页面的增强版本（可从 Lync 2013 访问）。

</div>

<div>

## <a name="purpose"></a>用途

响应组应用程序对传入呼叫进行排队，然后将其路由到代理组。 为了对要服务的呼叫做出有根据的决定，代理可以访问有关其代理组的实时信息，例如，哪些其他代理可用以及每个队列中等待的呼叫数。 最初仅可通过响应组服务访问的此信息将以直观方式由响应组代理实时提供。

<div>

## <a name="features"></a>功能

响应组代理 Live 工具建立在响应组服务和 Microsoft Lync 2013 SDK 之上。 它提供响应组代理响应组服务提供的信息和功能（如组成员身份、其他代理的状态以及等待呼叫数）。

下图展示了响应组代理的主接口。

![响应组代理 Live 工具。](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "响应组代理 Live 工具。")

以下三个主要功能可用于响应组代理 Live 中的代理：

  - **登录/注销：** 与 "代理组" 页相反（可从 Lync 2013 访问），响应组代理 Live 仅允许代理同时登录或注销所有代理组。 此应用程序提供了三种快速代理登录或注销的方法：
    
      - 单击应用程序中的 "登录/注销" （绿色和红色）按钮。
    
      - 右键单击 "系统" 任务栏图标，并选择 "登录" 或 "注销"。
    
      - 使用可配置的键盘快捷方式。

  - **组成员身份：** 如果选择了代理组，响应组代理 Live 将在右侧窗格中显示此组中的代理列表。 如果 Lync 2013 在此应用程序所在的同一台计算机上运行，状态信息和联系人卡片将显示在响应组代理 Live 中。 代理可以直接从那里发送即时消息或呼叫其他代理。

  - **实时统计信息：** 响应组代理 Live 提供所有代理组的实时统计信息。 更新频率为一分钟。 当响应组接听呼叫时，将在组名称旁边添加当前已排队呼叫的可视指示器。 将指针暂停在某个组上还会显示最长等待时间。

</div>

</div>

<div>

## <a name="requirements"></a>Requirements

响应组代理 Live 需要 .NET Framework 4.0。 此外，若要利用状态和联系人卡片功能，必须在本地安装 Lync 2013 （并运行）。

<div>

## <a name="configuration"></a>配置

通过使用应用程序中的 "选项" 对话框，可以将响应组代理 Live 自定义为单个首选项。 此外，管理员还可以通过直接编辑 RGAgentLive 文件的 defaultHostAddress 属性来定义默认的主机地址。

下图说明了代理可用于配置主机地址和快捷键的 "选项" 对话框。 通过单击主界面右上方的 "选项" 按钮可访问此对话框。

!["响应组代理实时选项" 对话框。](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg ""响应组代理实时选项" 对话框。")

可以在响应组代理 Live 配置中自定义以下三种不同的设置：

  - 主机地址：这通常是属于代理主池的 web 池 FQDN。 确切的响应组服务地址将自动从此信息的后台派生（通过在主机后面追加正确的路径）。

  - 快捷方式：可以自定义登录/注销的确切快捷方式。 唯一的限制是，这两个快捷方式都必须包含 "Windows 徽标" 键（除了至少一个密钥）。

  - 从 Windows 开始：可以将应用程序配置为在 Windows 中自动启动。

</div>

</div>

<div>

## <a name="examples"></a>示例

下图说明了如何通过右键单击右侧窗格中的联系人呼叫或发送 IM 到另一个代理。

![发出呼叫或发送即时消息。](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "发出呼叫或发送即时消息。")

下图说明了响应组代理实时如何显示队列中的当前呼叫数以及所有这些传入呼叫中的最长等待时间。

![查看队列信息。](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "查看队列信息。")

</div>

<div>

## <a name="summary"></a>总结

快速登录和注销、组成员身份和基本实时统计信息是仅在来自响应组服务的应用程序外部可用的响应组代理功能。 通过 "响应组代理实时资源工具包" 工具，Lync 管理员可以向其代理提供 Windows 应用程序，使其能够以更快速的图形方式执行任务。

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil （辅助扩展功能激活）是一种命令行工具，可让 Microsoft Lync Server 2013 通信软件管理员和支持人员代理配置代理响铃、呼叫转接、同时响铃、团队呼叫代表 Lync Server 2013 用户的设置和组呼叫应答。 该工具还允许管理员查询为特定用户发布的呼叫路由设置。使用 SEFAUtil 工具，管理员可以代表用户启用/禁用/修改呼叫转接或同时响铃。 管理员可以指定目标（采用 SIP URI 的形式），也可以使用用户已发布的目标。 此工具还允许管理员代表用户添加或删除代理人或团队呼叫组成员。此工具建立在 Microsoft 统一通信托管 API （UCMA）3.0 的基础上，并要求管理员在中央管理存储中为 SEFAUtil 创建受信任的应用程序

SEFAUtil （辅助扩展功能激活）使 Lync Server 2013 管理员和支持人员代理能够代表 Lync Server 2013 用户配置代理响铃、呼叫转接、同时响铃、团队呼叫设置和组呼叫应答. 此工具还允许管理员查询为特定用户发布的呼叫路由设置。

<div>

## <a name="description"></a>说明

SEFAUtil 的当前版本只是一个命令行工具;不支持图形用户界面。 此工具基于 Microsoft 统一通信托管 API （UCMA）3.0。 此工具中的功能允许管理员和支持人员代理执行以下操作：

  - 查看用户的所有呼叫路由设置（包括呼叫转接、委派、同时响铃、团队呼叫和组呼叫装货）

  - 启用/禁用/修改呼叫转接设置（包括目标和无应答计时器）

  - 启用/禁用/修改呼叫转接即时配置

  - 启用/禁用/修改委派设置

  - 启用/禁用/修改团队呼叫组设置
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 SEFAUtil 工具中的新增工具

    
    </div>

  - 启用/禁用/修改同时响铃设置（包括目标）
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 SEFAUtil 工具中的新增工具

    
    </div>

  - 启用/禁用/修改组呼叫装货设置
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013 SEFAUtil 工具中的新增工具

    
    </div>

此工具具有以下限制：

  - 仅对驻留在 Lync Server 池中的用户受支持

  - 不支持批量编辑多个用户的呼叫路由设置

</div>

<div>

## <a name="output"></a>Output

此工具的当前版本仅在命令提示符窗口中提供输出。 有关详细信息，请参阅本文档后面的示例部分。

</div>

<div>

## <a name="purpose"></a>用途

以下是可能使用此工具的一些关键方案：

  - 小明是一名行政人员，已移至 Lync Server 电话服务。 他在其现有的 PBX 系统上拥有委派。 作为移动到 Lync 的一部分，管理员可以配置王俊元的路由，以反映其预先存在的委派配置。

  - Alice 正在出差，认识到她需要来自一个客户的重要呼叫。 但是，她在宾馆中，没有对计算机的访问权限。 她呼叫帮助台并请求将其转接至移动电话号码对她的工作电话号码的所有呼叫。 帮助台人员可以代表她进行配置。

  - 当用户在工作时，Joe 对他的工作电话号码的呼叫将进入移动电话语音邮件;但是，在大多数其他位置看似乎工作正常。 帮助台技术人员可以查看 Joe 的路由配置，并发现 Joe 已将呼叫配置为移动电话。 技术人员在他的办公室中向 Joe 提问，并能够确定同时响铃的规则是，当网络覆盖范围较差时，会导致呼叫进入 Joe 的移动语音邮件。

  - Mike 是 Contoso 的新员工，他加入了一个新团队，在该团队中为团队呼叫配置所有成员后，在为 Microsoft Lync 启用时，管理员可以将他的团队呼叫组设置设置为包含所有新团队成员，此外，管理员将 Mike 添加为团队中每个成员的团队呼叫组成员。

  - Contoso 中的人力资源部门的客户服务实践是在第一次呼叫后为所有呼叫者提供个人服务。 如果部门的所有成员都非常接近，团队呼叫将同时拨打所有电话，同时对团队造成中断。 若要在不中断团队成员的情况下提供最佳服务，Lync 管理员可以利用组呼叫应答功能。 管理员将所有部门成员添加到一个装货组，并向该部门传达装货组编号。 当她的办公桌中缺少 Samantha 时，Joe 会通知她的电话响铃，他将继续应答来自他的办公桌的呼叫。

</div>

<div>

## <a name="requirements"></a>Requirements

SEFAUtil 工具只能在属于受信任应用程序池一部分的计算机上运行。 UCMA 3.0 必须安装在该计算机上。 若要运行该工具，必须在该池上创建一个具有 SEFAUtil 应用程序 ID 的新受信任应用程序。

**为 SEFAUtil 工具创建新的受信任应用程序**

1.  SEFAUTil 工具只能在属于受信任应用程序池一部分的计算机上运行。 如果需要，可以通过 Lync Server 命令行管理程序将池添加为新的受信任应用程序池，其中包含以下 cmdlet：
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > UCMA 3.0 必须安装在将用于运行 SEFAUtil 工具的任何计算机上。

    
    </div>

2.  需要在 SEFAUtil 工具的拓扑中定义受信任的应用程序。 若要将 SEFAUtil 定义为新的受信任应用程序，请使用 Lync Server 命令行管理程序，并执行以下 cmdlet：
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 如果需要，可以使用其他端口。

    
    </div>

3.  需要启用拓扑更改。 通过执行以下 cmdlet，可以通过 Lync Server 命令行管理程序来启用拓扑更改：
    
        Enable-CsToplogy

4.  如果需要，请在将用于运行 SEFAUtil 工具的服务器中安装 Lync Server 2013 资源工具包工具（该服务器必须是受信任的应用程序池的一部分）。

5.  验证 SEFAUtil 是否正常运行。 为此，请从具有管理员权限的 windows 命令提示符处运行该工具，以在部署中显示用户的呼叫转接设置。 默认情况下，该工具将位于： ".。。\\Program Files\\Microsoft Lync Server 2013\\\reskit "。 若要显示用户的呼叫转接设置，请使用以下命令：
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    应显示用户的呼叫转接设置。

<div>

## <a name="group-call-pickup"></a>组间电话提货

组内呼叫应答需要在 Lync Server 中进行其他配置，才能完全启用此功能。 在向用户分配分拣组之前，请参阅组的 "呼叫装货产品文档"，了解此功能的规划和部署步骤。

</div>

</div>

<div>

## <a name="examples"></a>示例

<div>

## <a name="display-current-call-handling-settings"></a>显示当前呼叫处理设置

以下命令将显示用户的呼叫处理。 `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> 此示例使用<STRONG>/server</STRONG>开关指定要连接到的 Lync server。



</div>

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>设置呼叫转接/无应答目的地

本示例设置呼叫转接/无应答目的地和环延迟。 这里不提供/server 开关;SEFAUtil 尝试自动发现 Lync Server。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>立即启用呼叫转接

此示例立即启用到另一个用户的呼叫转接。

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>立即禁用呼叫转接

本示例将立即禁用呼叫转接。

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>将用户添加为代理人并设置代理人的同时响铃

本示例将用户添加为代理人并设置代理人的同时响铃。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>更改代理人的同时响铃规则

本示例将上一示例中设置的同时响铃规则更改为延迟的震铃规则。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>删除委派

本示例删除代理。

<div>


> [!NOTE]  
> 删除最后一个委派时，将自动禁用委派震铃。



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>添加代理并设置呼叫转发到代理人规则

本示例添加一个代理人并设置 "呼叫前转到代理人" 规则。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>启用同时响铃并设置目标号码

本示例启用同时响铃并设置同时响铃的目标号码。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> 若要更改已启用同时响铃的用户的同时响铃的目标号码，请使用/enablesimulring 开关保留该命令，否则将不会更改目标号码。



</div>

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>禁用同时响铃

本示例禁用同时响铃。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>为团队呼叫添加团队成员，并将同时响铃设置为 "团队呼叫成员" 组

此示例向用户的团队呼叫组添加团队成员，并允许同时响铃到团队呼叫组。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> 将成员添加到用户的团队呼叫组将自动切换用户的同时响铃响铃，以同时他的团队呼叫组。



</div>

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>从团队呼叫组中删除成员

本示例将删除用户的团队呼叫组的团队成员。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> 如果要删除的成员是团队呼叫组的唯一成员，同时响铃到团队呼叫组将自动禁用。



</div>

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>将延迟环设置为团队呼叫组

本示例将延迟的环更改为 "团队呼叫组时间" 设置。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>启用团队呼叫

此示例为给定用户启用团队呼叫。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> 如果用户的团队呼叫组没有成员，则不会启用团队呼叫。



</div>

"输出"

</div>

<div>

## <a name="disable-team-call"></a>禁用团队呼叫

本示例为给定用户禁用团队呼叫。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>启用组呼叫应答并将分拣组分配给用户

本示例将一个分拣组分配给一个用户，并启用组呼叫应答。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

"输出"

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>禁用组呼叫应答

本示例为给定用户禁用组呼叫应答。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> 当您为用户禁用组呼叫应答时，分配给该用户的组号码将不会保留。 如果您随后要为该用户重新启用组呼叫应答，则必须使用/enablegrouppickup 开关再次分配该组编号。



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep. ps1

<div>

## <a name="description"></a>说明

Sysprep.inf 是一个 Windows PowerShell 脚本，它将在 Windows Server 2008 操作系统计算机上安装以下 Lync Server 2013 必备组件。

  - Microsoft .Net Framework 4。5

  - Microsoft SQL Server Express

  - Windows Powershell 版本3。0

  - Visual c + + 2010 可再发行组件

  - Internet information Server 更新

  - Windows Identity Foundation

  - Lync Server 2013 核心文件

尽管脚本名称类似于 Microsoft Windows 操作系统的系统准备工具，但它们是不同的。 此脚本将仅安装 Lync Server 2013 所需的必备组件。 安装这些必备组件后，即可使用 Windows SYSPrep 工具创建服务器的映像。

</div>

<div>

## <a name="requirements"></a>Requirements

在运行 Sysprep.inf. ps1 脚本之前，必须将必备文件复制到 Windows Server 2008 操作系统计算机上的本地文件夹（例如**D：\\Setup）**。 此文件夹还必须包含 Lync Server 2013 文件（特别是 setup.exe）的副本 **。** 可以从以下位置下载必备文件：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>先决条件</th>
<th>位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .Net Framework 4。5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows Powershell 版本3。0</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual c + + 2010 可再发行组件</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Internet information Server 更新</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup.exe</p></td>
<td><p>从 Lync Server 2013 媒体复制</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>参数

**– SetupFolder**参数采用参数作为参数必备文件的目录位置

</div>

<div>

## <a name="examples"></a>示例

若要运行 Sysprep.inf 脚本并安装 Lync Server 2013 必备组件，请从提升的命令提示符处运行以下命令：

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>未分配号码通知迁移

"未分配号码" 通知迁移工具使 Lync 管理员能够将由通知应用程序提供服务的未分配号码配置从源 Lync 服务器或池移动到目标 Lync Server 或池。

<div>

## <a name="description"></a>说明

未分配号码通知迁移工具是一个 Windows PowerShell 脚本，它将源服务器或池的通知应用程序提供服务的未分配号码配置移动到不同的服务器或池。

执行时，"未分配号码" 通知迁移脚本将执行以下操作：

1.  将源服务器或池中承载的通知应用程序的未分配号码通知所使用的所有音频文件移动到目标服务器或池的文件存储区。
    
    <div>
    

    > [!NOTE]  
    > 在将音频文件复制到目标池后，会从源池中将其删除。

    
    </div>

2.  将为源服务器或池中承载的通知应用程序配置的所有未分配号码通知移动到目标服务器或池。

3.  将由源服务器或池中承载的通知应用程序提供服务的所有未分配号码范围重新分配给目标服务器或池。

在成功运行脚本后，源服务器或池中承载的通知应用程序所提供的所有未分配号码范围将通过目标服务器或池的相同配置进行服务。

</div>

<div>

## <a name="output"></a>Output

**Move-csannouncementconfiguration**脚本在 Lync 命令行管理程序窗口中指示其执行迁移操作成功或失败的位置。

如果在发生任何错误时中断操作的执行，则已成功移动到目标的未分配号码范围将保留在操作表单的目标中，并且要迁移的未分配号码范围的剩余部分将保留在源和操作表单中的源。 若要完全迁移配置的其余部分，请在解决错误后重新运行脚本。

</div>

<div>

## <a name="purpose"></a>用途

未分配号码通知迁移脚本可用于以下三种方案：

  - **将配置设置迁移到新版本的 Lync Server：** Contoso 正处于迁移到 Lync Server 2013 的过程中，作为迁移过程的一部分，Lync Server 管理员希望将通知应用程序提供的未分配号码配置从 Lync Server 2010 部署移动到新的 Lync Server 2013 部署。 为了移动配置设置，Lync Server 管理员使用 "未分配号码" 通知迁移工具。

  - **将部署从 Lync server 2013 回滚到 Lync server 2010：** 由于意外因素，Contoso 必须将迁移回滚到新的 Lync Server 2013 部署。 为了最大限度地减少对服务的中断，Lync Server 管理员使用 "未分配号码" 通知迁移工具将配置从 Lync Server 2013 部署回滚到 Lync Server 2010 部署。

  - **在 Lync 部署之间移动数据：** Contoso 正处于将一个池的所有服务器替换为较新服务器的过程。 他们的策略是部署新的 Lync Server 2013 池，将所有数据从旧池移动到新池，然后弃用旧池。 部署新池后，将使用 "未分配号码通知" 迁移工具将配置从旧池移动到新池。

<div>

## <a name="requirements"></a>Requirements

若要成功运行此工具，需要满足以下主要要求：

1.  必须在安装了 Lync Server 2013 命令行管理程序的计算机上运行该脚本。

2.  必须在源和目标 Lync 服务器或池中成功部署通知应用程序。

<div>

## <a name="move-csannouncementconfiguration-script"></a>Move-csannouncementconfiguration 脚本

Move-csannouncementconfiguration 脚本需要下表中所述的两个参数。

![Move-csannouncementconfiguration 参数。](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-csannouncementconfiguration 参数。")

</div>

</div>

</div>

<div>

## <a name="examples"></a>示例

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>将未分配的号码通知配置从 Lync Server 2010 池移动到 Lync Server 2013 池

本示例将源池（Lync Server 2010）中未分配的号码宣告移动到目标池（Lync Server 2013）。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>将未分配的号码通知配置从 Lync Server 2013 池移动到 Lync Server 2010 池

本示例将源池（Lync Server 2013）中未分配的号码宣告移动到目标池（Lync Server 2010）。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Web 会议数据

通过 Web 会议数据工具，Lync Server 2013 通信软件的管理员可以更好地控制与组织者的 Web 会议关联的数据。 方案包括基于时间戳条件删除特定用户的会议数据的功能。

<div>

## <a name="description"></a>说明

此工具允许管理员执行以下操作：

1.  查找与单个用户相关联的所有 Web 会议数据。

2.  删除与单个用户相关联的所有 Web 会议数据。

3.  删除与某一日期之前的单个用户相关联的所有 Web 会议数据。

4.  当用户从一个池移动到另一个池时，移动与单个用户相关联的所有 Web 会议数据。

<div>


> [!NOTE]  
> 当用户从一个池移动到另一个池时，支持 Lync Server 2010 的资源工具包工具移动与单个用户相关联的所有 Web 会议数据。 现在，此工具中的功能已被弃用，取而代之的是<STRONG>MoveConferenceData</STRONG>参数。 有关此参数的详细信息，请参阅<A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">get-csuser</A> cmdlet。



</div>

该工具仅删除处于非活动状态的会议的会议数据。 无法删除活动会议（或会话中的会议）。

必须从与目标用户位于同一池中的计算机运行此工具。 此工具管理其会议内容数据的用户必须驻留在相同的用户池中。

</div>

<div>

## <a name="output"></a>Output

此工具将输出每个操作的结果：

  - 如果执行了查询，该工具会将具有该用户的所有非活动会议数据文件夹的列表输出为组织者。

  - 如果执行删除，该工具将输出其数据将被删除的所有会议数据文件夹的列表。

</div>

<div>

## <a name="requirements"></a>Requirements

该工具需要在组织者当前托管的同一个池中运行。

必须使用具有对内容文件存储的访问权限的管理员权限运行该工具。

</div>

<div>

## <a name="examples"></a>示例

下表介绍了这些参数，其中一些参数在示例中使用。

![Web 会议数据工具参数。](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web 会议数据工具参数。")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

上面的示例展示了查询命令的工作原理。 此类命令的输出将是受此工具影响的所有会议内容文件夹的列表。

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

上一个示例是 "删除" 命令。 "删除" 命令将删除此用户的所有非活动会议文件夹。

</div>

<div>

## <a name="summary"></a>总结

对于需要更精确控制会议会议数据的管理员来说，此工具可能是一项宝贵的资源。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
