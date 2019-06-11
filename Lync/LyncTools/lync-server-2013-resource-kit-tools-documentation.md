---
title: Lync Server 2013 资源工具包工具文档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1589285948bd9d3f82fae0ed7c7916029716514f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Lync Server 2013 资源工具包工具文档

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-01-09_

本主题介绍了属于 Lync Server 2013 资源工具包的工具, 其中包括每个工具的用途以及它的使用示例。Lync Server 2013 的资源工具包工具可帮助部署和管理 Lync Server 2013 的 IT 管理员更轻松地执行日常任务。 例如，**Web Conf Data** 工具可用于轻松控制召开联机会议期间用户上载的数据。 **SEFAUtil** 工具可用于为用户设置代理人呼叫转接和应答。 我们鼓励 IT 管理员使用这些工具更高效地管理 Lync Server 2013。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>安装资源管理包工具

若要安装 Lync Server 2013、资源工具包工具, 请下载**OCSReskit**。 您可以从下载中心下载 "资源工具包工具" 安装程序[http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)。

运行 **OCSResKit.msi** 以执行简单安装。 .Msi 将在以下路径中安装所有工具: **% Program Files%\\Microsoft Lync Server 2013\\ResKit**。 属于自包含可执行文件的工具位于此文件夹中。 也有文件的工具位于它们自己的子文件夹中。

</div>

<div>

## <a name="supported-environments"></a>支持的环境

为获得最佳性能, Lync Server 2013、资源工具包工具应安装在相同的环境中, 并具有 Lync Server 2013 所需的相同规范。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>资源管理包工具概述

下表介绍了 Lync Server 2013 资源工具包中提供的工具。 下一节介绍了每个工具的说明, 包括要求和示例用法。

  - ABSConfig

  - 带宽策略服务监视器

  - 带宽用量分析器

  - 呼叫寄存时间记录器

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - 网络配置查看器

  - 响应组代理实时

  - SEFAUtil

  - SYSPrep.ps1

  - 未分配号码通知迁移

  - Web Conf Data

</div>

<div>

## <a name="absconfig"></a>ABSConfig

通讯簿服务配置工具 (ABSConfig) 是一种管理工具, 可帮助管理员在 Lync Server 2013 中自定义通讯簿服务配置。 此工具还使 Lync Server 2013 管理员能够还原默认通讯簿服务设置。

<div>

## <a name="description"></a>说明

ABSConfig 是一种图形用户界面应用程序, 使管理员能够配置与通讯簿服务相关的 Active Directory 域服务属性。

该工具的主要方案如下所示：

  - 使管理员能够将 Active Directory 域服务中的属性映射到 Lync Server 2013 的属性。

  - 使管理员能够指定要在通讯簿服务文件中包括或排除的 Active Directory 域服务属性。

  - 使管理员能够还原默认通讯簿服务设置。

可使用 absConfig 文件启动 ABSConfig 工具。 该工具将打开 "**配置属性**" 选项卡。此表具有将 Active Directory 域服务属性映射到 Lync Server 2013 的属性字段的选项, 并指定哪些用户在通讯簿服务文件中包含或排除特定的属性筛选器。 它还具有用于自定义在通讯簿文件中包括电话号码的哪个值的选项。 “**还原默认值**”选项使管理员能够将通讯簿服务设置还原为默认值。

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Lync Server 2010 的更改

在 Lync Server 2013 ABS 配置工具中, 可通过取消选中属性的 "启用" 复选框来删除属性 (行)。 这与在 Lync Server 2010 中删除行的效果相同。

<div>


> [!NOTE]  
> "启用" 复选框位于最右侧的列中;您可能需要向右滚动才能看到列



</div>

</div>

<div>

## <a name="output"></a>输出

ABSConfig 将通讯簿服务配置存储在数据库中。

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>用途

ABSConfig 提供了一种快速简便的自定义 Lync Server 2013 通讯簿服务的方法。

</div>

<div>

## <a name="requirements"></a>要求

<div>

## <a name="computer"></a>计算机

ABSConfig 只能从安装了 Lync Server 2013 的加入域的计算机运行。 在 Lync Server 2013 (企业版) 的情况下, 此工具可在安装期间启用了通讯簿服务的任何前端服务器上运行。

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

可以通过在命令提示符中键入 **ABSConfig.exe** 来启动 ABSConfig。ABSConfig 工具用户界面如下所示。

![ABSConfig 工具。](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig 工具。")

</div>

<div>

## <a name="summary"></a>摘要

ABSConfig 工具为管理员提供了一种快速易用的工具, 可用于自定义 Lync Server 2013 通讯簿服务。

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>带宽策略服务监视器

带宽策略服务监视器工具旨在使管理员能够查看以下内容的列表：

1.  拓扑中所有已配置的 Lync Server 2013 带宽策略服务 (身份验证和核心)

2.  每个服务与其他带宽策略服务和边缘服务器的连接

3.  网络配置文档中配置的所有链路以及每个带宽策略服务报告的实时带宽使用量

<div>

## <a name="description"></a>说明

带宽策略服务监视器工具作为基于 GUI 的应用程序进行实施。管理员可通过运行 PDPMonUI.exe 启动该工具。

当该工具启动时，它将尝试发现拓扑中的带宽策略服务列表。完成初始更新之后，窗口左侧的窗格将填充服务列表，其中的服务按其所属的群集进行分组。

当管理员选择特定带宽策略服务时，右侧的窗格将显示有关该特定服务的信息。该窗格还包含两个可显示信息的主选项卡。

<div>

## <a name="machine-info-tab"></a>“计算机信息”选项卡

“**计算机信息**”选项卡显示所选带宽策略服务的详细信息以及所选带宽策略服务与其他服务建立的连接的列表和状态。

</div>

<div>

## <a name="topology-info-tab"></a>“拓扑信息”选项卡

“**拓扑信息**”选项卡显示在网络配置设置中配置的所有链路的列表。对于每个链路，显示音频和视频带宽容量。此外，以 Kbps 和容量百分比形式显示当前利用的带宽。该工具使用颜色编码突出显示利用率接近容量的链路，这使得管理员可快速隔离此类链路。

<div>


> [!NOTE]  
>  如果带宽策略服务监视器工具在连接到已配置的任何带宽策略服务时遇到故障，则“<STRONG>计算机信息</STRONG>”和“<STRONG>拓扑信息</STRONG>”选项卡中不会填充信息。但是，该工具可能最初连接成功，后来却断开与服务的连接。在这种情况下，管理员可能会看到过时的信息。每个选项卡上会显示“<STRONG>上次更新时间</STRONG>”时间戳，管理员可以通过该时间戳查看特定带宽策略服务的数据的上次更新时间。



</div>

</div>

</div>

<div>

## <a name="output"></a>输出

没有命令行输出；程序输出包含在主图形用户界面 (GUI) 中。

</div>

<div>

## <a name="purpose"></a>用途

带宽策略服务监视器工具旨在使管理员能够查看拓扑中定义的每个带宽策略服务的状态。此外，管理员可以查看网络配置文档中定义的所有链路的实时带宽用量。

</div>

<div>

## <a name="requirements"></a>要求

带宽策略服务监视器工具需要在属于 Lync Server 拓扑的计算机上运行。

</div>

<div>

## <a name="summary"></a>摘要

带宽策略服务监视器工具对于管理员而言是一项宝贵资源，通过该工具，管理员可以检查拓扑中所有带宽策略服务的状态，更重要的是，他们可以获取网络配置设置中定义的链路的实时带宽用量。

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>带宽用量分析器

带宽用量分析器工具可创建有关企业网络中各个 WAN 链路上 UC 端点的带宽消耗的各种视图的报告。这些报告有助于了解当前带宽消耗模式以及进行带宽容量规划。

<div>

## <a name="description"></a>说明

带宽用量分析器作为基于 GUI 的应用程序进行实施。此工具可针对网络中的音频利用率生成特定报告，从而帮助进行容量规划。它还会循环访问分配给各个链路的带宽容量。

</div>

<div>

## <a name="output"></a>输出

带宽用量分析器可将系统中配置的所有 WAN 链路的带宽容量和音频利用率绘制成图形。

</div>

<div>

## <a name="purpose"></a>用途

在任何语音和视频部署中，监视并了解企业网络中媒体流量的带宽用量趋势非常重要。带宽用量分析器工具可让管理员达成该目标。此工具可执行以下操作：

  - 针对网络中的音频利用率生成特定报告

  - 帮助更高效地进行容量规划并循环访问分配给各个链路的带宽容量

带宽用量分析器可将带宽容量和用量报告绘制成图形；如下所示：

  - 企业网络中的所有 WAN 链路

  - 按所选 WAN 链路进行筛选

  - 按已超过链路容量的 WAN 链路进行筛选

  - 按用量低于设置的带宽的 WAN 链路进行筛选

  - 按已达到严重级别（带宽用量大于 WAN 链路带宽容量的 90%）的 WAN 链路进行筛选

  - 按 WAN 链路类型（网络站点链路、区域间链路以及站点内链路）进行筛选

  - 按网络区域进行筛选

<div>

## <a name="applications"></a>应用程序

带宽用量分析器具有以下两个应用程序（工具）：

  - **WanLinkLogCollector**   此工具使其用户能够输入所需的信息。

  - **BandwidthUtilizationAnalyzer .xlsm**  Microsoft Excel 电子表格软件报表由 WanLinkLogCollector 自动启动。 此应用程序允许用户将筛选器应用于报表, 如本文后面部分所示。

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>使用带宽用量分析器的各个阶段

使用带宽用量分析器时有两个阶段：

  - 收集日志，使用 WanLinkLogCollector.exe 执行

  - 自定义报告，使用 BandwidthUtilizationAnalyzer.xlsm 执行

<div>


> [!IMPORTANT]  
> 强烈建议最终用户不要手动启动 BandwidthUtilizationAnalyzer.xlsm。



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>启动带宽用量分析器

在命令提示符中或使用 Windows 资源管理器启动 WanLinkLogCollector.exe。

**使用 WanLinkLogCollector.exe**

使用 WanLinkLogCollector.exe 有三个步骤：

1.  **记录日程表**   提供报表需要生成的时间线

2.  **指定文件目录**   提供文件位置信息

3.  **收集日志并启动报表查看器**  执行命令以生成报表

<div>

## <a name="step-1---log-the-timeline"></a>步骤 1 - 记录日程表

通过记录日程表，工具用户可以指定下图所示的信息。

1.  **开始日期** - 表示要为其生成报告的日程表的开始日期，例如 2010 年 8 月 1 日。

2.  **结束日期** - 表示要为其生成报告的日程表的结束日期，例如 2010 年 9 月 30 日。
    
    !["带宽利用率" 中的开始和结束日期](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "\"带宽利用率\" 中的开始和结束日期")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>步骤 2 - 指定文件目录

用户可指定如下所示的文件目录。

  - **服务器日志文件位置**存储带宽策略服务器日志的文件夹位置。 这通常位于 FE \<\>\\\\\<\>AppServerFiles\\PDP 的 "登录" 选项中。

  - **临时文件存储位置**生成报表时存储中间文件的临时文件位置。

![带宽利用率 Anal 中的文件目录](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "带宽利用率 Anal 中的文件目录")

<div>


> [!NOTE]  
> 确保向工具用户提供对服务器日志和临时文件存储文件夹足够的文件访问权限。



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>步骤 3 - 收集日志并启动报告查看器

要收集日志并启动报告查看器，请单击如下所示的“**执行**”。此步骤收集所需的数据。

![在带宽利用率 Analy 中收集数据](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "在带宽利用率 Analy 中收集数据")

当输入验证成功时，将显示下面所示的消息。

![在带宽 Utili 中记录收集的通知](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "在带宽 Utili 中记录收集的通知")

单击“**确定**”。BandwidthUtilizationAnalyzer.xlsm 会自动启动。按照消息框中的说明进行操作。有关详细信息，请参阅下一节中的“**使用 BandwidthUtilizationAnalyzer.xlsm**”。

</div>

<div>


**使用 BandwidthUtilizationAnalyzer.xlsm**

1.  当 BandwidthUtilizationAnalyzer.xlsm 自动启动时，单击如下所示的“**刷新**”。
    
    ![BandwidthUtilizationAnalyzer .xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer .xlsm")

2.  打开文件夹时，请从如下所示的消息框中指定的位置中选择 consolidated.csv。 它还将位置显示为**C:\\Temp**。
    
    ![在 BandwidthUtilizationAnalyzer 中打开文件夹。](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "在 BandwidthUtilizationAnalyzer 中打开文件夹。")

3.  单击“**导入**”。

4.  将自动生成绘图。当在后台工作的指针消失时，它便可用。
    
    ![在 "报表" 视图中应用筛选器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在 \"报表\" 视图中应用筛选器。")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>对报告视图应用筛选器

下面介绍了可对如下所示的报告视图应用的筛选器：

![在 "报表" 视图中应用筛选器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在 \"报表\" 视图中应用筛选器。")

1.  **名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。前缀表示以下链路类型，请查看垂直（蓝色）框：
    
      - **S Site** - 从网络站点到网络区域的 WAN 链路
    
      - **IS Inter-Site** - 两个网络站点之间的 WAN 链路
    
      - **R Inter-Region** - 两个网络区域之间的 WAN 链路

2.  **超出限制** - 按带宽用量超过带宽容量的 WAN 链路进行筛选

3.  **严重级别** - 按带宽用量已达到 90% 或超过带宽容量的 WAN 链路进行筛选

4.  **利用不足** - 按带宽用量少于带宽容量的 25% 的 WAN 链路进行筛选

5.  **链路类型** - 按以下 WAN 链路类型进行筛选：
    
      - **网络站点**类型
    
      - **站点间**类型
    
      - **区域间链路**类型

6.  **区域** - 按网络区域进行筛选

以下图显示了上述筛选器。

按**名称**进行筛选。选择需要在图形中显示的链路的列表。

![按名称在 BandwidthUtilizationAnalyzer 中进行筛选。](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "按名称在 BandwidthUtilizationAnalyzer 中进行筛选。")

按**超出限制**进行筛选。 选择 **True** 可强制实施筛选器。

![按超过限制进行筛选。](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "按超过限制进行筛选。")

按**严重级别**进行筛选。 选择 **True** 可强制实施筛选器。

![按关键级别进行筛选。](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "按关键级别进行筛选。")

按**利用不足**进行筛选。 选择 **True** 可强制实施筛选器。

![按利用率进行筛选。](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "按利用率进行筛选。")

按**链路类型**进行筛选。 选择需要显示的类型。

![按链接类型筛选。](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "按链接类型筛选。")

按**区域**进行筛选。 选择需要显示其链路的区域的列表。

![按区域进行筛选。](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "按区域进行筛选。")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>要求

  - .NET Framework 3.5

  - Microsoft Excel 2010 或 Excel 2007

</div>

<div>

## <a name="summary"></a>摘要

带宽用量分析器用于将网络中 UC 流量的音频带宽用量绘制成图形。此工具也可用于报告网络上的视频带宽用量。

</div>

</div>

<div>

## <a name="call-parkometer"></a>呼叫寄存时间记录器

呼叫寄存时间记录器是一个命令行应用程序，可让用户轻松访问呼叫寄存轨道数据库。

<div>

## <a name="description"></a>说明

呼叫寄存时间记录器工具可跟踪当前寄存的呼叫。 它还可收集有关轨道和呼叫寄存服务器 (CPS) 使用情况的统计信息。 此命令行工具提供对本地或远程连接的计算机上的 CPS 轨道 SQL Server 数据库的读和写访问。

所有选项相互排斥。命令行语法如下所示：

  - **–o** 参数 - 列出为此池配置的所有轨道范围。

  - **–n** 参数 - 列出此池中当前使用的所有轨道。显示的信息如下所示：
    
      - 呼叫被寄存者和寄存者的 SIP 统一资源标识符 (URI)。
    
      - 在其中寄存呼叫的 CPS 的主机名。
    
      - 寄存呼叫时的时间戳。

  - **–f** 参数 - 列出池中当前可用的轨道数。

  - **– r \<n\> **参数-列出 n \<\>个上次寄存的呼叫。 显示的信息如下所示：
    
      - 呼叫被寄存者的 SIP URI。
    
      - 呼叫寄存者的 SIP URI。
    
      - 在其中寄存呼叫的 CPS 的主机名。
    
      - 取回或丢弃呼叫时的时间戳。

  - **-t\<n\> **参数-测试在数据库中保留轨道, 以显示分配的轨道编号的随机性。

</div>

<div>

## <a name="output"></a>输出

根据在命令提示符中指定的输入参数，呼叫寄存时间记录器显示以下输出：

  - 为此池配置的所有轨道范围

  - 当前寄存的呼叫

  - 可用轨道数

  - 最近寄存的呼叫

  - 保留用于测试统一和随机轨道值的轨道

</div>

<div>

## <a name="purpose"></a>用途

该 CPS 工具用于提供对 CPS 数据库的命令行访问。管理员可以查看 CPS 使用情况并确定分配给池的轨道数量。

</div>

<div>

## <a name="requirements"></a>要求

如果此工具在运行 CPS 的相同计算机上运行，则没有任何要求。 如果此工具在远程计算机上运行, 则必须将 Lync Server 2013 使用的 SQL Server 数据库配置为允许远程访问。 必须使用 SQL Server 数据库连接字符串配置调用 Parkometer, 以连接到池的 SQL Server。 此 SQL Server 数据库连接字符串在配置文件**parkometer**中定义。它必须放置在 parkometer 所在的同一目录中。 以下 XML 文件是 parkometer 的示例。必须配置的参数为用户名 (例如, mydomain\\管理员)、密码 (例如, mypassword) 和主机名 (例如 myserver)。

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

部署的轨道范围：–o 参数列出为此池配置的所有轨道范围，如下所示

!["呼叫 Parkometer" 中的轨道范围。](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "\"呼叫 Parkometer\" 中的轨道范围。")

当前寄存的呼叫：–n 参数列出此池中当前使用的所有轨道，如下所示

![通话 Parkometer 中的当前寄存通话。](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "通话 Parkometer 中的当前寄存通话。")

可用轨道数：–f 参数列出池中当前可用的轨道数，如下所示

![通话 Parkometer 中的免费轨道式。](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "通话 Parkometer 中的免费轨道式。")

最近寄存的通话:-r \<n\>参数列出 n \<\>个最后寄存的通话, 如下所示

![通话 Parkometer 中最近寄存的通话。](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "通话 Parkometer 中最近寄存的通话。")

测试轨道保留: – t \<n\>参数测试在数据库中保留轨道, 如下所示

![通话 Parkometer 中的测试轨道保留。](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "通话 Parkometer 中的测试轨道保留。")

</div>

<div>

## <a name="summary"></a>摘要

呼叫寄存时间记录器是一个命令行工具，可提供有关呼叫寄存服务器的详细信息。

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

CleanupStorageServiceData 资源工具包工具允许从 Lync Server 存储服务 (LYSS) 使用的数据库中删除孤立数据。 存储服务的一个功能是缓冲 Lync Server 和各种后端数据存储终结点 (如 SQL Server 和 Exchange) 之间的通信。

<div>

## <a name="description"></a>说明

为了支持高可用性, LYSS 将在池中的多个前端服务器上暂时接受和保存数据的副本, 并在将数据传送到其最终长期存储位置后将其删除。 在其他正常操作过程中可能会发生不寻常的情况, 当服务器可能崩溃或遇到处理问题时, 某些数据可能无法正确清理。 此数据是无害的, 但它会占用有限的处理资源。 大部分正常需要的数据维护都是自动化的, 但是此工具允许在不能自动删除时进行安全识别和删除此类孤立数据。 当引发运行状况监视 System Center Operations Manager (SCOM) 警报时, 将会指示管理员从池中的本地 LYSS 数据库中删除不需要的数据的情况下使用此工具。 在触发警报的前端的事件日志中将存在相应的事件。 事件详细信息将包含有关前端中包含的孤立数据量的信息, 并在该数据超过某些预确定阈值时引发

</div>

<div>

## <a name="requirements"></a>要求

安装 Lync Server 2013、资源工具包工具。 该工具在安装了 Lync Server 和 Lync Server 2013 管理外壳的已加入域的计算机上运行。 该工具使用来自管理外壳的 cmdlet 来标识池中的所有前端服务器。 其次, 该工具必须从安装了**RtcLocal**数据库的池中的计算机执行。 此数据库由 CleanupStorageServiceData 工具用于获取与 Lync Server 路由服务通信所需的连接详细信息。最后, 调用该工具的帐户或凭据必须具有对文件共享的读/写权限。他们希望写入输出日志。此外, 此工具还依赖于处于稳定状态的池。 实际上, 这意味着每个前端服务器都应保持正常运行, SQL Server LYNCLOCAL 实例和 LYSS 数据库必须能够连接到, 并且每个路由组必须具有一组完整的1个主前端服务器和2个辅助前端 servers.

</div>

<div>

## <a name="examples"></a>示例

C:\\程序文件\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData

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

DBAnalyze 是一种命令行工具, 可帮助管理员收集有关 Lync Server 2013 数据库的分析报告。 DBAnalyze 具有以下模式：诊断、用户数据、会议、MCU 和磁盘碎片：

  - **诊断模式**   创建一个报表, 其中包含有关表的信息 (记录数、碎片、数据大小和索引大小)、数据和日志文件大小、上次备份时间、运行 Microsoft 的服务器之间的联系人分布。Office 通信服务器、每个权限的平均数量、联系人、容器、订阅、发布、每个用户的终结点、任何不正确的托管用户、无法路由的用户、按用户安排的平均会议数会议、活动会议和数据库版本。
    
    <div>
    

    > [!NOTE]  
    > 运行诊断模式可能会影响服务器性能。

    
    </div>

  - **用户数据模式** 为指定用户或在其联系人和权限列表中拥有该用户的用户报告联系人、容器、订阅、发布、权限和联系人组数据。 此模式还报告用户组织或受邀参加的会议的摘要数据。

  - **会议模式**   报告特定会议的详细数据, 包括会议的所有计划时间详细信息、被邀请者列表、会议所允许的媒体类型列表、活动 MCUs (multipoint control units)、active参与者列表和每个参与者的信号状态。

  - **解码会议 id**  对由 **/pstnid**开关指定的公共交换电话网络 (PSTN) 会议 id 进行解码, 但不连接到后端以了解详细信息。

  - **解析会议**   解码由 **/pstnid**开关指定的 PSTN 会议 ID, 并显示有关由 ID 指示的会议的信息。

  - **MCUs 模式**  报告池中每个 MCU 的 ID、媒体类型、URL、检测信号状态、会议加载和参与者负载。

  - **磁盘碎片模式**  显示所有磁盘的碎片状态。

此工具可用于诊断各种问题或帮助管理员进行容量规划。例如，如果驻留在服务器 A 上的大多数用户选择驻留在服务器 B 上的用户作为其联系人，管理员可以将服务器 A 的用户移动到服务器 B，从而减少跨服务器流量。

</div>

<div>

## <a name="output"></a>输出

此工具输出有关 Lync Server 2013 数据库的预定义报告。 **路径:** % ProgramFiles%\\Microsoft Lync Server 2013\\Reskit

</div>

<div>

## <a name="purpose"></a>用途

若要安装 Dbanalyze, 请将其复制到本地文件夹, 然后运行该工具。 若要使用该工具, 请从命令行运行以下命令。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 命令行选项的说明如下所示。

![Dbanalyze 的命令行选项。](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze 的命令行选项。")

</div>

<div>

## <a name="requirements"></a>要求

**计算机**DBAnalyze 只能从安装了 Lync Server 2013 的加入域的计算机运行。

**网络** - 计算机应能够连接到后端数据库。

**软件**在运行 DBAnalyze 之前, 必须安装 Lync Server 2013 软件组件。

**用户**下表显示了具有访问 Lync Server 2013 数据库所需权限的管理员。

![Dbanalyze 的权限表。](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze 的权限表。")

<div>


> [!NOTE]  
> <STRONG>/report:disk</STRONG> 模式要求使用本地管理员帐户。



</div>

</div>

<div>

## <a name="examples"></a>示例

以下是有效 Dbanalyze.exe 命令的示例：

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>摘要

DBAnalyzer 使管理员能够快速轻松地分析 Lync Server 2013 数据库。

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

ImportStorageServiceData 资源管理包工具允许将已从存储服务 (LYSS) 刷出的队列和端点数据重新导入到存储服务中。

<div>

## <a name="description"></a>说明

可能已基于队列项目状态或数据库大小自动（定期）从存储服务刷出数据。 发生这种情形是因为手动调用了池故障转移 cmdlet 或 StorageServiceFullFlush cmdlet（由池故障转移 cmdlet 调用）。 请注意, 如果前端的任何存储服务 (LYSS) 数据库大小均高于正常级别, 则不应重新导入数据, 因为这样做很可能只会导致更多数据要输出回来。此外, 可能会首先解决导致存储服务队列增长的错误所产生的任何问题 (例如 Exchange 终结点错误、网络问题或其他问题)。

**方案 1**：池故障转移期间，每个前端的文件可能会从存储服务刷出。 故障转移完成之后，应运行该工具以重新导入数据。

**方案 2**：数据每天自动刷新或者为响应超过特定大小阈值（例如 60%、80%、90%、已满）的存储服务数据库而自动刷新。 此自动刷新的数据应由管理员定期重新导入。 在上述情况下, 如果未部署监视 SCOM 包, 则会出现与从存储服务刷新的数据相关的 Lync Server 存储服务的事件。 事件 ID 为 32075（已启动完全刷新操作）、32076（已完成完全刷新）、32082（已启动维护级别刷新）、32083（已完成维护级别刷新）和 32089（由于数据库填满而刷新）。 请注意，这些事件 ID 对应于 RTM 版本。 当管理员看到这些事件时, 这意味着有文件已被刷新。此数据应定期使用此工具 (例如每周一次) 导入。

对于联机服务版本, 如果部署了 Lync Server 的运行状况监视 SCOM 包, 则可能会引发新的警报, 要求管理员将刷新后的数据重新导入到存储服务中。 在触发警报的前端服务器上的事件日志中将存在相应的事件。 该事件将提供刷新数据文件所在的父路径的说明, 以及有多少个文件可以满足警报条件。 警报条件是特定父路径下的 X 或更多文件, 这些文件至少为最早的 Y 天 (其中 X 和 Y 是在 StorageService 内预设置的, 但可以通过更改 APPCONFIG 文件进行替代)。下面显示了可触发运行状况警报的事件的两个示例, 区别在于它们的父路径。 其中一种可能性是 Web 服务文件共享, 另一种可能性是每个前端的本地应用程序数据目录。 (例如, c:\\ProgramData\\Microsoft\\Lync Server\\StorageService)。 管理员随后将运行此 reskit 工具。

此工具将增加其运行于的前端服务器以及其他前端服务器（如果在其上面执行此工具的前端服务器不拥有数据）的 CPU 和 IO 负载。 建议在前端服务器的 CPU 和 IO 负载不太繁重时运行此工具，例如非高峰时间。 其次，此工具 2 到 3 分钟可导入一个数据文件。 在估计工具的运行时间时, 请注意这一点。默认情况下, 该工具生成的详细日志文件将显示在文件存储中。 如果未报告错误，请删除日志文件，因为日志文件的大小会增长到数十 MB 或以上。

![存储服务器事件日志事件示例。](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "存储服务器事件日志事件示例。")

</div>

<div>

## <a name="requirements"></a>要求

安装 Lync Server 2013、资源工具包工具。 该工具在安装了 Lync Server 和 Lync Server Management Shell 的已加入域的计算机上运行。 该工具使用来自管理外壳的 cmdlet 来标识池中的所有前端服务器。 其次, 该工具必须从安装了**RtcLocal**数据库的池中的计算机执行。 此数据库由工具用于检索池的 WEBSERVICE 文件共享的位置。此外, 在使用该工具之前, 每个前端服务器必须首先在每台前端服务器上使用**enable-PSRemoting**以及执行该工具的计算机上启用 Windows PowerShell 远程。 否则, 此工具中的远程 Windows PowerShell 命令将失败。 在完成后, 将在池中的所有前端服务器上关闭 Windows PowerShell 远程处理。 最后, 调用该工具的帐户或凭据必须具有对其执行此工具的池的 webservice 文件共享的读/写权限。 否则, 该工具将无法正常工作, 并出现 IO 权限错误。

<div>


> [!NOTE]  
> 在 Windows Server 2012 上, Windows PowerShell 远程处理在默认情况下处于启用状态, 而不是在 Windows Server 2008 操作系统上启用。



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

LCSSync 工具有助于在多目录林环境中部署 Lync Server 2013 通信软件。 此工具用于将不同用户林的用户和组作为 Active Directory 域服务联系人对象同步到安装了 Lync Server 2013 的中央林。

<div>

## <a name="description"></a>说明

LCSSync 使用中央林中的同步 Active Directory 域服务联系人对象为 Lync Server 启用用户。 若要提供单一登录, 主要用户帐户必须映射到 Lync Server 2013 的中央林中的 Active Directory 域服务联系人对象。 此工具可帮助执行该映射。 此工具提供用于在 Microsoft Identity Integration Server 中创建管理代理的模板。

</div>

<div>

## <a name="summary"></a>摘要

LCSSync 工具有助于在多目录林环境中部署 Lync Server。

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

LookupUserConsole 工具显示特定用户的内部 Lync Server 路由信息。 Microsoft 支持人员可使用此信息来诊断部署问题和路由问题。

<div>

## <a name="description"></a>说明

执行 LookupUserConsole 将打开一个命令提示符, 该命令提示符接受 SIP 地址并尝试显示与其相关的内部 Lync Server 路由信息。 键入 **exit** 可退出 LookupUserConsole 工具。

</div>

<div>

## <a name="requirements"></a>要求

安装 Lync Server 2013、资源工具包工具。 该工具在安装了 Lync Server 的加入域的计算机上运行

</div>

<div>

## <a name="examples"></a>示例

C:\\程序文件\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole

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

MSTurnPing 工具允许 Microsoft Lync Server 2013 通信软件的管理员检查运行 "音频/视频边缘" 和 "音频/视频身份验证" 服务以及运行带宽策略的服务器的服务器的状态拓扑中的服务。

<div>

## <a name="description"></a>说明

MSTurnPing 工具允许 Lync Server 2013 通信软件的管理员检查运行音频/视频边缘和音频/视频身份验证服务的服务器的状态, 以及运行带宽策略服务的服务器的状态拓扑.

该工具使管理员能够执行以下测试：

1.  A/V 边缘服务器测试：该工具通过执行以下操作来对拓扑中的所有 A/V 边缘服务器执行测试：
    
      - 验证是否已启动 Lync Server 音频/视频身份验证服务, 并且是否可以颁发正确的凭据。
    
      - 验证是否已启动 Lync Server 音频/视频边缘服务, 并且可以成功分配外部边缘上的资源。

2.  带宽策略服务测试：该工具通过执行以下操作来对运行带宽策略服务的所有服务器执行测试：
    
      - 验证是否已启动 Lync Server 带宽策略服务 (身份验证), 并且是否可以颁发正确的凭据。
    
      - 验证是否已启动 Lync Server 带宽策略服务 (Core), 并且能否成功执行带宽检查。

必须从属于拓扑的一部分并且安装了本地存储的计算机运行此工具。

</div>

<div>

## <a name="output"></a>输出

该工具会输出每个操作的结果。

  - 如果执行了 **AudioVideoEdgeServer** 测试，则工具输出为以下内容：
    
      - 提供拓扑中的 Lync Server 音频/视频身份验证服务的计算机的测试结果
    
      - 提供拓扑中的 Lync Server 音频/视频边缘服务的计算机的测试结果

  - 如果执行了 **BandwidthPolicyServer** 测试，则工具输出为以下内容：
    
      - 在拓扑中提供 Lync Server 带宽策略服务 (身份验证) 的计算机的测试结果
    
      - 提供拓扑中的 Lync Server 带宽策略服务 (Core) 的计算机的测试结果

</div>

<div>

## <a name="requirements"></a>要求

  - 必须从拓扑中具有本地存储的计算机运行此工具。

  - 必须以具有本地存储的访问权限的管理员身份运行该工具。

</div>

<div>

## <a name="examples"></a>示例

以下是工具输入的示例。

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>摘要

对于希望检查运行音频/视频和带宽策略服务的服务器状态的 Lync Server 2013 管理员, 此工具可能是一种有价值的资源。

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>网络配置查看器

Microsoft Lync Server 2013 通信软件管理员可以使用网络配置查看器查看配置为允许实时通信会话的企业的呼叫许可控制 (CAC) 网络拓扑 (如语音或基于指定带宽容量的视频通话。 Lync Server 2013 管理员定义 CAC 策略, 这些策略由使用 Lync Server 2013 安装的带宽策略服务强制执行。

<div>

## <a name="description"></a>说明

网络配置查看器 (NetworkConfigurationViewer.exe) 使管理员能够执行以下任务：

  - 以图形格式从 Lync Server 2013 部署加载和查看 CAC 网络拓扑。

  - 以图形格式从带宽策略服务器日志文件中加载并查看 CAC 网络拓扑。

  - 以 XML 格式在磁盘上保存和存储 CAC 网络拓扑。

  - 以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图。

  - 查看 CAC 网络拓扑配置数据。

  - 以树视图样式查看 CAC 网络拓扑。

  - 定义 CAC 网络拓扑链路（例如，站点到区域、区域到区域和站点到站点链路）的自定义连接器。

  - 查看 CAC 网络拓扑站点信息、区域信息以及设置的带宽策略和网络链路。

</div>

<div>

## <a name="purpose"></a>用途

在图形界面中查看企业 CAC 网络拓扑链路。

</div>

<div>

## <a name="examples"></a>示例

**以图形格式从 Lync Server 2013 部署加载和查看 CAC 网络拓扑:** Lync Server 2013 管理员可以使用 "**下载网络配置**" 选项在任何 Lync server 2013 计算机上加载和查看 CAC 网络拓扑配置, 如下图所示。 当在没有与 Lync 配置存储连接的计算机上部署时, 该工具将无法下载或查看此类配置。

![下载网络配置。](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "下载网络配置。")

**以图形格式从带宽策略服务器日志文件加载和查看 CAC 网络拓扑:** Lync Server 2013 带宽策略服务器将 CAC 网络拓扑保存为 Lync Server 2013 文件共享位置下的日志记录机制的一部分。 Lync Server 管理员可以使用 "**打开网络配置**" 选项以图形格式查看此类文件, 如下所示。

![打开带宽策略服务器日志文件。](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "打开带宽策略服务器日志文件。")

在磁盘上以 XML 格式保存和存储 CAC 网络拓扑: Lync Server 2013 管理员可以使用 "**保存网络配置**" 选项的副本以 xml 格式保存 cac 网络拓扑配置文件, 如下所示。 然后，可以脱机使用已保存的配置文件以图形格式进行查看。

![将网络配置保存为 XML 文件。](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "将网络配置保存为 XML 文件。")

以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图: Lync Server 2013 管理员可以使用 "**将网络配置图表另存为图片**" 以图形格式 (JPG 和 BMP 文件格式) 保存 cac 网络拓扑配置选项, 如下所示。

![将网络配置保存为图片。](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "将网络配置保存为图片。")

**查看 CAC 网络拓扑配置数据:** Lync Server 2013 管理员可以使用 "查看网络配置数据" 选项以文本格式查看相关的网络配置数据, 例如网络区域、网络站点、带宽配置文件和站点子网 IP 地址, 如下所示。

![查看网络配置数据。](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "查看网络配置数据。")

**在树视图样式中查看 CAC 网络拓扑:** Lync Server 2013 管理员可以使用 "图形树" 视图样式查看相关的网络配置数据, 方法是使用工具窗口左侧的 "控制面板", 如下所示。

![在树视图中查看网络配置数据。](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "在树视图中查看网络配置数据。")

**为 CAC 网络拓扑链接定义自定义连接器 (如站点到区域、区域到区域和站点到站点链接):** Lync Server 2013 管理员可以使用 "设置" 选项定义 CAC 网络配置 WAN 链接的自定义图形连接线, 如下所示。 这样做可帮助区分网络配置中设置的各种类型的网络链路。

![定义 CAC 网络拓扑的自定义连接器](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "定义 CAC 网络拓扑的自定义连接器")

**查看 CAC 网络拓扑网站信息、区域信息和预配的带宽策略:** Lync Server 2013 管理员可以使用下面所示的选项查看相关的 CAC 网络区域信息、网站信息和 CAC 带宽设置信息。 (例如, 单击 "网络区域" 或 "网络网站" 对象中的 "**信息**"。)

![为您的网络定义自定义连接器。](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "为您的网络定义自定义连接器。")

</div>

<div>

## <a name="summary"></a>摘要

此工具对于 Lync Server 2013 管理员是一种有价值的资源, 想要以图形形式查看其部署的 CAC 网络拓扑。

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>响应组代理实时

响应组应用程序使代理能够使用其内置的 Web 服务访问有用的实时信息。 遗憾的是，在应用程序外部无法以图形格式查看此数据。 响应组代理实时资源工具包工具通过提供一种简单的图形方式来访问此信息, 并通过实时 Microsoft Lync 2013 通信软件信息 (如其他代理的存在) 进行了增强, 从而解决了此问题。

<div>

## <a name="description"></a>说明

“响应组代理实时”是一个 Windows 应用程序，向响应组代理提供登录和注销功能以及一些实时信息（例如，组成员身份和当前的呼叫数）。 它应该是 "代理组" 页面的增强版本 (可从 Lync 2013 访问)。

</div>

<div>

## <a name="purpose"></a>用途

响应组应用程序将传入呼叫排入队列，然后将它们路由到代理组。为针对服务于哪些呼叫做出明智的决策，代理可以访问有关其代理组的实时信息，例如，其他哪些代理组可用以及每个队列中有多少呼叫正在等待。此信息最初只能通过响应组服务进行访问，现在由“响应组代理实时”以直观方式提供。

<div>

## <a name="features"></a>功能

响应组代理实时工具建立在响应组服务和 Microsoft Lync 2013 SDK 之上。 它向响应组代理提供可从响应组服务访问的信息和功能（例如，组成员身份、其他代理的状态和正在等待的呼叫数）。

下图展示了“响应组代理实时”的主界面。

![响应组代理实时工具。](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "响应组代理实时工具。")

“响应组代理实时”为代理提供了以下三个主要功能：

  - **登录/注销:** 与 "代理组" 页面 (可从 Lync 2013 访问) 相反, "响应组代理" 活动仅允许代理立即登录或注销所有代理组。 此应用程序提供了三种用于代理登录或注销的快速方法:
    
      - 单击应用程序中的登录/注销（绿色和红色）按钮。
    
      - 右键单击系统任务栏图标，然后选择登录或注销。
    
      - 使用可配置的键盘快捷方式。

  - **组成员身份:** 如果选择了代理组, 则响应组代理会实时在右窗格中显示此组中的代理列表。 如果 Lync 2013 在此应用程序所在的同一台计算机上运行, 则状态信息和联系人卡片将显示在响应组代理程序中。 代理可以直接从那里发送即时消息或呼叫其他代理。

  - **实时统计信息**：“响应组代理实时”提供所有代理组的实时统计信息。更新频率为一分钟。当响应组应答呼叫时，将在组名称旁边添加一个可视指示器并显示队列中的当前呼叫数。此外，将指针暂停在某个组上方可显示最长等待时间。

</div>

</div>

<div>

## <a name="requirements"></a>要求

“响应组代理实时”需要 .NET Framework 4.0。 此外, 若要利用联机状态和联系人卡片功能, 则必须在本地安装 Lync 2013 (并运行)。

<div>

## <a name="configuration"></a>配置

可以使用应用程序中的“选项”对话框根据个人偏好自定义“响应组代理实时”。此外，管理员可以通过直接编辑 RGAgentLive.exe.config 文件的 defaultHostAddress 属性来定义默认主机地址。

下图展示了“选项”对话框，代理可以使用此对话框配置主机地址和快捷键。可通过单击主界面右上角的“选项”按钮来访问此对话框。

!["响应组代理实时选项" 对话框。](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "\"响应组代理实时选项\" 对话框。")

可以在“响应组代理实时”配置中自定义以下三个不同设置：

  - 主机地址：这通常是指属于代理主池的 Web 池 FQDN。确切的响应组服务地址将在后台自动从此信息派生（在主机后面附加正确的路径）。

  - 快捷方式：可以自定义登录/注销的确切快捷方式。唯一限制是两个快捷方式都必须包含 Windows 徽标键（以及至少另一个键）。

  - 与 Windows 一起启动：该应用程序可配置为自动与 Windows 一起启动。

</div>

</div>

<div>

## <a name="examples"></a>示例

下图展示了如何通过右键单击右窗格中的联系人来呼叫其他代理或向其他代理发送 IM。

![进行呼叫或发送即时消息。](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "进行呼叫或发送即时消息。")

下图展示了“响应组代理实时”如何显示队列中的当前呼叫数以及所有这些传入呼叫的最长等待时间。

![查看队列信息。](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "查看队列信息。")

</div>

<div>

## <a name="summary"></a>摘要

快速登录和注销、组成员身份和基本的实时统计信息是有趣的响应组代理功能，只能从响应组服务访问并在应用程序外部使用。 使用 "响应组代理" 实时资源工具包工具, Lync 管理员可以为其代理提供 Windows 应用程序, 使其能够以更快的图形方式执行任务。

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (辅助扩展功能激活) 是一个命令行工具, 可使 Microsoft Lync Server 2013 通信软件管理员和支持人员代理配置代理响铃、呼叫转移、同时拨打、团队通话代表 Lync Server 2013 用户的设置和组呼叫装货。 该工具还允许管理员查询为特定用户发布的呼叫路由设置。管理员可通过 SEFAUtil 工具启用/禁用/修改呼叫转接或同时拨打用户。 管理员可以指定目标 (以 SIP URI 的形式) 或使用已由用户发布的目标。 此工具还允许管理员代表用户添加或删除代理人或团队呼叫组成员。此工具在 Microsoft 统一通信托管 API (UCMA) 3.0 上构建, 并要求管理员在 SEFAUtil 的中央管理存储中创建受信任的应用程序

SEFAUtil (辅助扩展功能激活) 使 Lync Server 2013 管理员和支持人员的代理可以通过代表 Lync Server 2013 用户配置代理响铃、呼叫转接、同时拨打、团队呼叫设置和组呼叫装货. 此工具还使管理员能够查询为特定用户发布的呼叫路由设置。

<div>

## <a name="description"></a>说明

当前 SEFAUtil 版本仅仅是一个命令行工具；没有支持的图形用户界面。 此工具基于 Microsoft 统一通信托管 API (UCMA) 3.0。 此工具中的功能使管理员和支持人员代理能够执行以下操作：

  - 查看用户的所有呼叫路由设置（包括呼叫转接、委派、同时响铃、团队呼叫和组呼叫应答）

  - 启用/禁用/修改呼叫转接设置（包括目标和无应答计时器）

  - 启用/禁用/修改呼叫转接即时配置

  - 启用/禁用/修改委派设置

  - 启用/禁用/修改团队呼叫组设置
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 SEFAUtil 工具新增

    
    </div>

  - 启用/禁用/修改同时响铃设置（包括目标）
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 SEFAUtil 工具新增

    
    </div>

  - 启用/禁用/修改组呼叫应答设置
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013 SEFAUtil 工具新增

    
    </div>

此工具存在以下限制：

  - 仅支持驻留在 Lync Server 池中的用户

  - 不支持对多个用户的呼叫路由设置进行批量编辑

</div>

<div>

## <a name="output"></a>输出

此工具的当前版本仅在“命令提示符”窗口中提供输出。有关详细信息，请参阅本文档后面的“示例”部分。

</div>

<div>

## <a name="purpose"></a>用途

以下是此工具一些可能的主要应用场景：

  - Bob 是一个总经理, 已被移动到 Lync 服务器电话。 他在其现有 PBX 系统上设置了委派。 作为移动到 Lync 的一部分, 管理员可以配置 Bob 的路由以反映其预先存在的委派配置。

  - Alice 正在出差，意识到她将收到一位客户的重要来电。然而，她住在酒店，没办法使用计算机。她致电支持人员，请求他们将拨打她的工作电话号码的所有呼叫转接到其移动电话号码。支持人员能够代表她执行该配置。

  - 每当 Joe 工作时，拨打其工作电话号码的呼叫进入其移动语音邮件；但是，在大多数其他位置似乎一切正常。支持人员能够查看 Joe 的路由配置，发现 Joe 将同时响铃配置为其移动电话。技术人员询问 Joe 其办公室的移动网络覆盖，能够确定是同时响铃规则导致呼叫在网络覆盖较差时进入 Joe 的移动语音邮件。

  - Mike 是 Contoso 的一名新员工, 他加入一个新团队, 其中所有成员都已配置为用于团队呼叫, 当为 Microsoft Lync 启用时, 管理员可以将其团队呼叫组设置设置为包括所有新团队成员, 此外,管理员将 Mike 添加为团队中每个成员的团队呼叫组成员。

  - Contoso 人力资源部门的一个客户服务做法是自第一个呼叫开始为所有呼叫者提供个性化服务。 倘若部门所有成员的就坐位置距离非常近，让所有电话与团队呼叫同时响铃会给团队造成极大干扰。 若要提供最佳服务而不中断团队成员, Lync 管理员可以利用组呼叫功能。 管理员将所有部门成员添加到一个应答组并告知他们应答组号码。 当 Samantha 不在座位上时，Joe 注意到其电话响铃，随后从自己的桌面应答呼叫。

</div>

<div>

## <a name="requirements"></a>要求

SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。必须在该计算机上安装 UCMA 3.0。要运行该工具，必须在该池上创建新的具有 SEFAUtil 应用程序 ID 的受信任应用程序。

**为 SEFAUtil 工具创建新的受信任应用程序**

1.  SEFAUTil 工具只能在属于受信任应用程序池的一部分的计算机上运行。 如果需要, 将池添加为新的受信任的应用程序池可通过 Lync Server Management Shell 使用以下 cmdlet 完成:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > 必须在将用于运行 SEFAUtil 工具的任何计算机上安装 UCMA 3.0。

    
    </div>

2.  需要在拓扑中为 SEFAUtil 工具定义受信任的应用程序。 若要将 SEFAUtil 定义为新的受信任的应用程序, 请使用 Lync Server 命令行管理程序并执行以下 cmdlet:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 如果需要，可以使用其他端口。

    
    </div>

3.  需要启用拓扑更改。 通过执行以下 cmdlet, 启用拓扑更改可通过 Lync Server Management Shell 执行:
    
        Enable-CsToplogy

4.  如果需要, 请在将用于运行 SEFAUtil 工具的服务器中安装 Lync Server 2013 资源工具包工具 (服务器必须是受信任的应用程序池的一部分)。

5.  验证 SEFAUtil 是否正常运行。 为此，请使用管理员特权从 Windows 命令提示符运行该工具，以显示部署中的用户的呼叫转接设置。 默认情况下, 该工具将位于: "..."\\程序文件\\Microsoft Lync Server 2013\\Reskit "。 要显示用户的呼叫转接设置，请使用以下命令：
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    应显示用户的呼叫转接设置。

<div>

## <a name="group-call-pickup"></a>组内呼叫应答

组呼叫分拣需要 Lync Server 中的其他配置, 才能完全启用该功能。 在向用户分配呼叫应答组之前，请参阅组呼叫应答产品文档，了解此功能的规划和部署步骤。

</div>

</div>

<div>

## <a name="examples"></a>示例

<div>

## <a name="display-current-call-handling-settings"></a>显示当前呼叫处理设置

以下命令可显示用户的呼叫处理。 `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> 此示例使用<STRONG>/server</STRONG>开关指定要连接到的 Lync 服务器。



</div>

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>设置呼叫转接/无应答目标

此示例设置呼叫转接/无应答目标和响铃延迟。 此处未提供/server 开关;SEFAUtil 将尝试自动发现 Lync 服务器。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>立即启用呼叫转接

此示例立即启用至其他用户的呼叫转接。

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>立即禁用呼叫转接

此示例立即禁用呼叫转接。

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>将用户添加为代理人并设置代理人的同时响铃

此示例将用户添加为代理人并设置代理人的同时响铃。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>更改代理人的同时响铃规则

此示例将上一示例中设置的同时响铃规则更改为延迟的响铃规则。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>删除代理人

此示例将删除代理人。

<div>


> [!NOTE]  
> 删除了最后一个代理人后，代理人响铃将自动禁用。



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>添加代理人并设置代理人呼叫转接规则

此示例将添加代理人并设置代理人呼叫转接规则。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>启用同时响铃并设置目标号码

此示例将启用同时响铃并设置同时响铃目标号码。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> 要更改已经启用了同时响铃的用户的同时响铃目标号码，请在命令中使用 /enablesimulring 开关，否则目标号码不会更改。



</div>

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>禁用同时响铃

此示例将禁用同时响铃。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>为团队呼叫添加团队成员并设置团队呼叫成员组同时响铃

此示例向用户的团队呼叫组添加团队成员，并启用团队呼叫组同时响铃。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> 向用户的团队呼叫组添加成员会自动将用户的同时响铃设置切换为同时拨打团队呼叫组。



</div>

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>从团队呼叫组中删除成员

此示例将删除用户的团队呼叫组的团队成员。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> 如果正在删除的成员是团队呼叫组的唯一成员，那么团队呼叫组同时响铃将自动禁用。



</div>

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>将延迟响铃设置为团队呼叫组

此示例将延迟响铃更改为团队呼叫组时间设置。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**输出**

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

**输出**

</div>

<div>

## <a name="disable-team-call"></a>禁用团队呼叫

此示例为给定用户禁用团队呼叫。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>启用组呼叫应答并为用户分配应答组

此示例为用户分配应答组并启用组呼叫应答。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>禁用组呼叫应答

此示例为给定用户禁用组呼叫应答。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> 当为某个用户禁用组呼叫应答时，分配给该用户的组号码不再保留。如果你随后想为该用户重新启用组呼叫应答，必须使用 /enablegrouppickup 开关再次分配组号码。



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep.ps1

<div>

## <a name="description"></a>说明

SYSPrep 是一个 Windows PowerShell 脚本, 它将在你的 Windows Server 2008 操作系统计算机上安装以下 Lync Server 2013 先决条件。

  - Microsoft .Net Framework 4.5

  - Microsoft SQL Server Express

  - Windows Powershell 3.0 版

  - Visual C++ 2010 可再发行软件包

  - Internet Information Server 更新

  - Windows Identity Foundation

  - Lync Server 2013 核心文件

虽然脚本名称类似于 Microsoft Windows 操作系统的系统准备工具，但是实际上有所不同。 此脚本将仅安装 Lync Server 2013 所需的先决条件。 安装这些必备软件之后，可以使用 Windows SYSPrep 工具创建服务器映像。

</div>

<div>

## <a name="requirements"></a>要求

在运行 SYSPrep. ps1 脚本之前, 必须将必备文件复制到 Windows Server 2008 操作系统计算机上的本地文件夹 (例如**D:\\Setup)**。 此文件夹还必须包含 Lync Server 2013 文件 (特别是 setup.exe) 的副本 **。** 可以从以下位置下载必备文件：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>必备软件</th>
<th>位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .Net Framework 4.5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows Powershell 3.0 版</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 可再发行软件包</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Internet Information Server 更新</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
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

**–SetupFolder** 形式参数使用必备文件的目录位置作为实际参数

</div>

<div>

## <a name="examples"></a>示例

若要运行 Sysprep.inf 脚本并安装 Lync Server 2013 先决条件, 请从提升的命令提示符处运行以下命令:

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>未分配号码通知迁移

"未分配的号码" 通知迁移工具使 Lync 管理员能够将由公告应用程序提供的 "未分配的号码" 配置从源 Lync 服务器或池中移动到目标 Lync 服务器或池。

<div>

## <a name="description"></a>说明

未分配号码通知迁移工具是一个 Windows PowerShell 脚本，可将由源服务器或池的通知应用程序提供服务的未分配号码配置移动到其他服务器或池。

执行时，未分配号码通知迁移脚本将执行以下操作：

1.  将源服务器或池中承载的通知应用程序的未分配号码通知所使用的所有音频文件移动到目标服务器或池的文件存储。
    
    <div>
    

    > [!NOTE]  
    > 将音频文件复制到目标池中后, 会从源池中将其删除。

    
    </div>

2.  将为源服务器或池中承载的通知应用程序配置的所有未分配号码通知移动到目标服务器或池。

3.  将由源服务器或池中承载的通知应用程序提供服务的所有未分配号码范围重新分配给目标服务器或池。

成功运行该脚本之后，由源服务器或池中承载的通知应用程序提供服务的所有未分配号码范围现在由目标服务器或池提供服务，并采用相同配置。

</div>

<div>

## <a name="output"></a>输出

**CsAnnouncementConfiguration**脚本将在 Lync Management Shell 窗口中指示其执行迁移操作成功或失败的位置。

如果操作执行过程因错误而中断，则已成功移动到目标的未分配号码范围将保留在目标中并正常工作，其余待迁移的未分配号码范围将保留在源中并正常工作。要完全迁移其余配置，请在解决错误之后重新运行脚本。

</div>

<div>

## <a name="purpose"></a>用途

未分配号码通知迁移脚本可以应用于以下三种方案：

  - **将配置设置迁移到新版本的 Lync Server:** Contoso 正在迁移到 Lync Server 2013 和迁移过程的一部分, 作为迁移过程的一部分, Lync Server 管理员希望将公告应用程序提供的未分配号码配置从 Lync Server 2010 部署移动到新的 Lync Server 2013 部署。 若要移动配置设置, Lync Server 管理员使用 "未分配号码" 通知迁移工具。

  - **将 Lync server 2013 中的部署回退到 Lync server 2010:** 由于意外因素, Contoso 必须将迁移回退到新的 Lync Server 2013 部署。 为了最大程度地减少对服务的中断, Lync Server 管理员使用 "未分配的号码" 通知迁移工具将配置从 Lync Server 2013 部署回滚到 Lync Server 2010 部署。

  - **在 Lync 部署之间移动数据:** Contoso 正在将一个池的所有服务器替换为更新的服务器。 其策略是部署新的 Lync Server 2013 池, 将旧的所有数据移动到新池, 然后弃用旧的池。 部署新池后, 将使用 "取消分配的数字公告迁移工具" 将配置从旧池移动到新池。

<div>

## <a name="requirements"></a>要求

下面列出了成功运行该工具所需的主要要求：

1.  必须在安装了 Lync Server 2013 管理外壳的计算机上运行该脚本。

2.  必须在源和目标 Lync 服务器或池中成功部署公告应用程序。

<div>

## <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration 脚本

Move-CsAnnouncementConfiguration 脚本需要下表所述的两个参数。

![CsAnnouncementConfiguration 参数。](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "CsAnnouncementConfiguration 参数。")

</div>

</div>

</div>

<div>

## <a name="examples"></a>示例

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>将 "未分配的号码" 通知配置从 Lync Server 2010 池中移动到 Lync Server 2013 池

此示例将源池 (Lync Server 2010) 的未分配数字公告移动到目标池 (Lync Server 2013)。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>将 "未分配的号码" 通知配置从 Lync Server 2013 池中移动到 Lync Server 2010 池

此示例将源池 (Lync Server 2013) 的未分配数字公告移动到目标池 (Lync Server 2010)。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Web Conf Data

Web 会议数据工具允许 Lync Server 2013 通信软件的管理员更好地控制与组织者的 Web 会议关联的数据。 方案包括能够基于时间戳条件删除特定用户的会议数据。

<div>

## <a name="description"></a>说明

此工具使管理员能够执行以下操作：

1.  查找与单个用户相关联的所有 Web 会议数据。

2.  删除与单个用户相关联的所有 Web 会议数据。

3.  删除与单个用户相关联且早于特定日期的所有 Web 会议数据。

4.  当单个用户从一个池移动到另一个池时，移动与该用户相关联的所有 Web 会议数据。

<div>


> [!NOTE]  
> 当用户从一个池移动到另一个时, Lync Server 2010 的资源工具包工具支持移动与单个用户关联的所有 Web 会议数据。 此工具现已弃用该功能，改为使用 <STRONG>MoveConferenceData</STRONG> 参数。 有关此参数的详细信息, 请参阅<A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">move-csuser</A> cmdlet。



</div>

该工具仅删除处于非活动状态的会议的会议数据。无法删除活动会议（或正在进行会话的会议）。

必须从与目标用户相同的池中的计算机运行此工具。由此工具管理其会议内容数据的用户必须驻留在同一个用户池中。

</div>

<div>

## <a name="output"></a>输出

此工具会输出每个操作的结果：

  - 如果执行查询，该工具将输出该用户作为其组织者的所有非活动会议数据文件夹的列表。

  - 如果执行删除，该工具将输出其数据将被删除的所有会议数据文件夹的列表。

</div>

<div>

## <a name="requirements"></a>要求

该工具需要在组织者当前驻留的同一个池中运行。

必须使用对内容文件存储具有访问权限的管理员特权运行该工具。

</div>

<div>

## <a name="examples"></a>示例

下表介绍了参数，其中包含示例中使用的一些参数。

![网络会议数据工具参数。](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "网络会议数据工具参数。")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

上述示例介绍了查询命令如何工作。此类命令的输出是受此工具影响的所有会议内容文件夹的列表。

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

上述示例是一个 delete 命令示例。delete 命令将删除此用户的所有非活动会议文件夹。

</div>

<div>

## <a name="summary"></a>摘要

此工具对于需要更精确控制会议数据的管理员而言是一项宝贵资源。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
