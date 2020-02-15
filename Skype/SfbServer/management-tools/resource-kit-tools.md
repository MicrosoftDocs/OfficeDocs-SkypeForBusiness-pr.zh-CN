---
title: Skype for Business Server 2015 资源工具包工具文档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 本主题介绍了 Skype for Business Server 2015 资源工具包中的工具，包括每个工具的用途以及它的使用示例。 Skype for Business Server 2015 资源工具包可帮助部署和管理 Skype for business Server 2015 的 IT 管理员更轻松地执行日常任务。 例如，可以使用 Web 会议数据工具轻松地控制用户在联机会议期间上载的数据。 SEFAUtil 工具可用于为用户设置代理呼叫转发和应答。 我们鼓励 IT 管理员使用这些工具更有效地管理 Skype for Business Server 2015。
ms.openlocfilehash: ab43d8e951308fab5a4aefc25d9dad2804ea5d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005987"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server 2015 资源工具包工具文档

本主题介绍了 Skype for Business Server 2015 资源工具包中的工具，包括每个工具的用途以及它的使用示例。 Skype for Business Server 2015 资源工具包可帮助部署和管理 Skype for business Server 2015 的 IT 管理员更轻松地执行日常任务。 例如，可以使用**Web 会议数据**工具轻松地控制用户在联机会议期间上载的数据。 **SEFAUtil**工具可用于为用户设置代理呼叫转发和应答。 我们鼓励 IT 管理员使用这些工具更有效地管理 Skype for Business Server 2015。

## <a name="installation-of-the-resource-kit-tools"></a>资源工具包工具的安装

若要安装 Skype for Business Server 2015 资源工具包，请从下载中心下载[ocsreskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) 。

运行**ocsreskit.msi**以执行简单安装。 .Msi 在以下路径中安装所有工具： **% Program Files%\Skype For Business Server 2015 \ \reskit**。 包含自包含可执行文件的工具位于此文件夹中。 还包含支持文件的工具位于自己的子文件夹中。

## <a name="supported-environments"></a>支持的环境

Skype for Business Server 2015 资源工具包应安装在符合 Skype for business Server 2015 所需规范（通常用于运行 Skype for Business Server 2015）的服务器上。

## <a name="resource-kit-tools-overview"></a>资源工具包工具概述

以下是 Skype for Business Server 2015 资源工具包中提供的工具列表。 以下各节介绍了每个工具的说明，包括要求和示例用法。

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [带宽策略服务监视器](resource-kit-tools.md#bpsm)

- [带宽利用率分析器](resource-kit-tools.md#bua)

- [调用寄存时间记录器](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [导入存储服务数据](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [查找用户控制台](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [网络配置查看器](resource-kit-tools.md#NCV)

- [响应组代理实时](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep. ps1](resource-kit-tools.md#SYSPrep)

- [未分配号码通知迁移](resource-kit-tools.md#UNAM)

- [Web 会议数据](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

通讯簿服务配置工具（ABSConfig）是一种管理工具，可帮助管理员在 Skype for business Server 2015 中自定义通讯簿服务配置。 此工具还使 Skype for Business Server 2015 管理员能够还原默认通讯簿服务设置。

### <a name="description"></a>说明

ABSConfig 是一个图形用户界面应用程序，使管理员能够配置与通讯簿服务相关的 Active Directory 域服务属性。

该工具的主要方案如下所示：

- 使管理员能够将 Active Directory 域服务中的属性映射到 Skype for Business Server 2015 的属性。

- 使管理员能够指定要在通讯簿服务文件中包含或排除的 Active Directory 域服务属性。

- 使管理员能够还原默认通讯簿服务设置。

可以使用 ABSConfig 文件启动 ABSConfig 工具。 该工具将打开 "**配置属性**" 选项卡。此表中的选项可用于将 Active Directory 域服务属性映射到 Skype for Business Server 2015 的属性字段，并指定哪些用户在通讯簿服务文件中根据特定的属性筛选器包含或排除。 它还具有自定义要在通讯簿文件中包含的电话号码的值的选项。 "**还原默认**值" 选项使管理员能够将通讯簿服务设置还原为默认值。

> [!NOTE]
> 将 AD 属性重新映射到不同的 OC 字段名称仅适用于通讯簿文件下载，且不受通讯簿 Web 查询支持。

### <a name="output"></a>Output

ABSConfig 将通讯簿服务配置存储在数据库中。

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>用途

ABSConfig 提供了一种快速而简单的自定义 Skype for business Server 2015 通讯簿服务的方法。

### <a name="requirements"></a>Requirements

#### <a name="computer"></a>计算机

只能从安装了 Skype for business Server 2015 的加入域的计算机运行 ABSConfig。 在 Skype for business Server 2015 （Enterprise Edition）的情况下，可以在安装过程中启用了通讯簿服务的任何前端服务器上运行此工具。

#### <a name="network"></a>网络

计算机应能够连接到前端池和后端数据库。

#### <a name="software"></a>软件

在运行 ABSConfig 工具之前，必须安装以下软件组件：

- Skype for Business Server 2015

#### <a name="users"></a>用户

拥有更新 Skype for Business Server 2015 部署所需权限的管理员。

### <a name="examples"></a>示例

可以通过在命令提示符处键入**ABSConfig**来启动 ABSConfig。 下面显示的是 ABSConfig 工具用户界面。

![ABSConfig 工具。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>摘要

ABSConfig 工具为管理员提供了一个快速且易于使用的工具，可用于自定义 Skype for Business Server 2015 通讯簿服务。

## <a name="bandwidth-policy-service-monitor"></a>带宽策略服务监视器
<a name="bpsm"> </a>

带宽策略服务监视器工具旨在允许管理员查看以下项的列表：

1. 拓扑中配置的所有 Skype for business Server 2015 带宽策略服务（身份验证和核心）

2. 每个服务对其他带宽策略服务和边缘服务器所做的连接

3. 在网络配置文档中配置的所有链接，以及每个带宽策略服务报告的实时带宽使用率

### <a name="description"></a>说明

带宽策略服务监视器工具以基于 GUI 的应用程序的形式实现。 管理员通过运行 PDPMonUI 启动该工具。

当工具启动时，它将尝试发现拓扑中的带宽策略服务列表。 完成初始更新后，窗口左侧的窗格将使用由其所属群集分组的服务列表进行填充。

当管理员选择特定的带宽策略服务时，右侧窗格将显示有关该特定服务的信息。 该窗格还包含两个显示信息的主选项卡。

#### <a name="machine-info-tab"></a>计算机信息选项卡

"**计算机信息**" 选项卡显示已选择的带宽策略服务的详细信息，以及由选定带宽策略服务对其他服务所做的所有连接的列表和状态。

#### <a name="topology-info-tab"></a>拓扑信息选项卡

"**拓扑信息**" 选项卡显示在网络配置设置中配置的所有链接的列表。 对于每个链接，都会显示音频和视频带宽容量。 此外，当前使用的带宽以 Kbps 和容量百分比的形式显示。 该工具使用颜色编码突出显示具有接近容量的使用率的链接，这使管理员能够快速隔离此类链接。

> [!NOTE]
>  如果带宽策略服务监视器工具在连接到任何已配置的带宽策略服务时遇到故障，则不会填充**计算机信息**和**拓扑信息**选项卡中的信息。 但是，该工具可能会在最初连接但随后失去与该服务的连接。 在这种情况下，管理员可能会看到过时的信息。 每个选项卡上都有**最后更新**的时间戳，这些选项卡可允许管理员查看特定带宽策略服务的上次更新数据的时间。

### <a name="output"></a>Output

没有命令行输出;程序输出包含在主图形用户界面（GUI）中。

### <a name="purpose"></a>用途

带宽策略服务监视器工具旨在使管理员能够查看拓扑中定义的每个带宽策略服务的状态。 此外，管理员可以查看网络配置文档中定义的所有链接的实时带宽使用率。

### <a name="requirements"></a>Requirements

带宽策略服务监视器工具需要在作为 Skype for Business Server 拓扑的一部分的计算机上运行。

### <a name="summary"></a>摘要

带宽策略服务监视器工具对于管理员来说是一项宝贵的资源，这样他们就可以检查拓扑中所有带宽策略服务的状态—更重要的是，它们可以获取链接的实时带宽利用率，在网络配置设置中定义。

## <a name="bandwidth-utilization-analyzer"></a>带宽利用率分析器
<a name="bua"> </a>

带宽利用率分析器是一种工具，该工具通过企业网络中的多个 WAN 链接的 UC 终结点创建有关带宽消耗的各种视图的报告。 这些报告可用于了解当前带宽消耗模式，并可帮助进行带宽容量规划。

### <a name="description"></a>说明

带宽利用率分析器是作为基于 GUI 的应用程序实现的。 此工具专门针对网络中的音频利用率生成报告，并帮助进行容量规划。 它还会对分配给各个链路的带宽容量进行迭代。

### <a name="output"></a>Output

带宽利用率分析器为系统中配置的所有 WAN 链路提供了图形 al 的带宽容量和使用情况的视频。

### <a name="purpose"></a>用途

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

#### <a name="applications"></a>应用程序

带宽使用率分析器包含以下两个应用程序（工具）：

- **Wanlinklogcollector.exe**此工具使其用户能够输入所需的信息。

- **Bandwidthutilizationanalyzer.xlsm Xlsm** Microsoft Excel 电子表格软件报告由 wanlinklogcollector.exe 自动启动。 此应用程序允许用户将筛选器应用于报表，如本文后面所示。

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>使用带宽使用率分析器的各个阶段

使用带宽使用率分析器时有两个阶段：

- 收集使用 Wanlinklogcollector.exe 执行的日志

- 自定义报表，通过使用 Bandwidthutilizationanalyzer.xlsm 执行。 xlsm

    > [!IMPORTANT]
    > 强烈建议最终用户手动启动 xlsm Bandwidthutilizationanalyzer.xlsm。

#### <a name="starting-bandwidth-utilization-analyzer"></a>启动带宽使用率分析器

在命令提示符处或使用 Windows 资源管理器启动 Wanlinklogcollector.exe。

 **使用 Wanlinklogcollector.exe**

使用 Wanlinklogcollector.exe 有三个步骤：

1. **记录日程表**提供需要为其生成报告的日程表

2. **指定文件目录**提供文件位置信息

3. **收集日志并启动报告查看器**执行命令以生成报告

#### <a name="step-1---log-the-timeline"></a>步骤 1-记录日程表

记录日程表时，工具用户可以按下图所示指定以下各项。

1. **开始日期**这是要为其生成报告的时间线的开始日期;例如，2010年8月1日。

2. **结束日期**这是要为其生成报告的时间线的结束日期;例如，2010年9月30日。

     ![带宽利用率中的开始和结束日期](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>步骤 2-指定文件目录

用户可以按如下所示指定文件目录。

- **服务器日志文件位置**存储带宽策略服务器日志的文件夹位置。 这通常在 \AppServerFiles\PDP. \<\> \\<中，FE\>的选择

- **临时文件存储位置**生成报告时存储中间文件的临时文件位置。

    ![带宽利用率用量中的文件目录](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > 确保向工具用户提供了对服务器日志和临时文件存储文件夹的足够文件访问权限。

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>步骤 3-收集日志并启动报告查看器

若要收集日志并启动报告查看器，请单击 "**执行**"，如下所示。 此步骤将收集所需的数据。

![在带宽利用率用量中收集数据](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

输入验证成功后，将显示下面显示的消息。

![在带宽 Utili 中记录收集的通知](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

单击“确定”。 Bandwidthutilizationanalyzer.xlsm 将自动启动。 按照消息框中的说明进行操作。 有关详细信息，请参阅下一节中的**Using bandwidthutilizationanalyzer.xlsm. xlsm** 。


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>使用 Bandwidthutilizationanalyzer.xlsm。 xlsm

1. 如果 xlsm 自动启动，请单击 "**刷新**"，如下所示。

     ![Bandwidthutilizationanalyzer.xlsm。 xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. 打开文件文件夹后，从消息框中指定的位置选择 "合并" .csv，如下所示。 它还将位置显示为**C：\Temp**。

     ![打开 Bandwidthutilizationanalyzer.xlsm 中的文件夹。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. 单击“导入”****。

4. 图形绘图将自动生成。 它在后台工作指针消失时可用。

     ![在报告视图中应用筛选器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>将筛选器应用于报告视图

可应用于报告视图的筛选器如下所示：

![在报告视图中应用筛选器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **名称**按 WAN 链接筛选（筛选器位于图形右侧）。前缀表示以下链接类型;请参阅垂直（蓝色）框：

   - **S 网站**从网络站点到网络区域的 WAN 链接

   - **是站点间**两个网络站点之间的 WAN 链路

   - **R 区域间**两个网络区域之间的 WAN 链路

2. **超出限制**按带宽利用率大于带宽容量的 WAN 链路进行筛选

3. **关键级别**按带宽利用率达到90% 或大于带宽容量的 WAN 链路进行筛选

4. 未**充分利用**按 WAN 链路进行筛选，其带宽使用率已少于带宽容量的25%

5. **链接类型**按以下 WAN 链接类型进行筛选：

   - **网络站点**类型

   - **站点间**类型

   - **区域间链接**类型

6. **区域**按网络区域筛选

下图显示了前面介绍的筛选器。

按**名称**筛选。 选择需要在图形中显示的链接的列表。

![按名称在 Bandwidthutilizationanalyzer.xlsm 中进行筛选。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

按**超出限制**进行筛选。 选择 " **True** " 以强制执行筛选器。

![按超出限制进行筛选。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

按**临界级别**进行筛选。 选择 " **True** " 以强制执行筛选器。

![按关键级别进行筛选。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

按**使用**情况筛选。 选择 " **True** " 以强制执行筛选器。

![按使用情况进行筛选。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

按**链接类型**筛选。 选择需要显示的一个或一种类型。

![按链接类型筛选。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

按**区域**筛选。 选择需要显示其链接的区域列表。

![按区域筛选。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requirements

- .NET Framework 3。5

- Microsoft Excel 2010 或 Excel 2007

### <a name="summary"></a>摘要

带宽利用率分析器用于绘制网络中 UC 流量的音频带宽使用率。 此工具还可用于报告网络上的视频带宽使用率。

## <a name="call-parkometer"></a>调用寄存时间记录器
<a name="callpark"> </a>

调用寄存时间记录器是一个命令行应用程序，可提供对呼叫寄存轨道数据库的轻松访问。

### <a name="description"></a>说明

呼叫寄存时间记录器是一种跟踪当前寄存的呼叫的工具。 它还收集有关轨道式和呼叫寄存服务器（CPS）使用情况的统计信息。 此命令行工具提供对来自本地或远程连接的计算机上的 CPS 轨道 SQL Server 数据库的读写访问权限。

所有选项都是相互排斥的。 命令行语法如下所示：

- **-o**参数-列出为此池配置的所有轨道范围。

- **-n**参数—列出此池中所有当前使用的轨道式。 显示的信息如下所示：

  - Parkee 和 parker 的 SIP 统一资源标识符（URI）。

  - 寄存呼叫的 CPS 的主机名。

  - 寄存呼叫时的时间戳。

- **-f**参数-列出池中当前可用的轨道的数目。

- **-r \<n\> **参数—列出\<n\>个最近寄存的呼叫。 显示的信息如下所示：

  - Parkee SIP URI。

  - Parker SIP URI。

  - 寄存呼叫的 CPS 的主机名。

  - 检索或丢弃呼叫时的时间戳。

- **-t\<n\> **参数-测试在数据库中保留一种轨道，以显示分配的轨道编号的随机性。

### <a name="output"></a>Output

根据在命令提示符处指定的输入参数，调用寄存时间记录器显示以下输出：

- 为此池配置的所有轨道范围

- 当前寄存的呼叫

- 空闲（可用）轨道式的数目

- 最近寄存的呼叫

- 用于测试统一和随机轨道值的保留轨道

### <a name="purpose"></a>用途

CPS 工具的目的是提供对 CPS 数据库的命令行访问。 管理员可以查看 CPS 使用情况，并确定分配给池的轨道式的数目。

### <a name="requirements"></a>Requirements

如果在运行 CPS 的同一台计算机上运行此工具，则没有任何要求。 如果此工具在远程计算机上运行，则必须将 Skype for Business Server 2015 使用的 SQL Server 数据库配置为允许远程访问。 必须使用 SQL Server 数据库连接字符串配置调用寄存时间记录器以连接到池的 SQL Server。 此 SQL Server 数据库连接字符串是在配置文件**寄存时间记录器**中定义的。它必须放在寄存时间记录器所在的同一目录中。 下面的 XML 文件是一个寄存时间记录器的示例。必须配置的参数为用户名（例如，mydomain\Administrator）、密码（例如，mypassword）和主机名（例如 myserver）。

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

### <a name="examples"></a>示例

已部署的轨道范围：-o 参数列出为此池配置的所有轨道范围，如图所示

![呼叫寄存时间记录器中的轨道范围。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

当前寄存的呼叫：-n 参数列出此池中当前使用的所有轨道，如下所示

![呼叫寄存时间记录器中当前寄存的呼叫。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

自由轨道式的数目：-f 参数列出池中当前可用的轨道式的数目，如图所示

![调用寄存时间记录器中的自由轨道式。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

最近寄存的呼叫：-r \<n\>参数列出 n \<\>个最近寄存的呼叫，如下所示

![呼叫寄存时间记录器中最近寄存的呼叫。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

测试轨道保留：-t \<n\>参数测试在数据库中保留一个轨道，如下所示

![在呼叫寄存时间记录器中测试轨道保留。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>摘要

呼叫寄存时间记录器是一个命令行工具，提供有关呼叫寄存服务器的详细信息。

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>说明

DBAnalyze 是一个命令行工具，可帮助管理员收集有关 Skype for business Server 2015 数据库的分析报告。 DBAnalyze 具有以下模式：诊断、用户数据、会议、Mcu 和磁盘碎片：

- **诊断模式**创建一个报表，其中包含有关表的信息（记录数、碎片数、数据大小、索引大小、数据和日志文件大小、最近的备份时间、运行 Microsoft Office 通信服务器的服务器之间的联系人分布、平均权限数、联系人、容器、订阅、发布、每个用户的终结点、任何不正确的托管用户、无法路由的用户、按用户组织的会议数、安排的会议、活动会议、和数据库版本。

    > [!NOTE]
    > 运行诊断模式可能会影响服务器性能。

- **用户数据模式**报告指定用户或其联系人和权限列表中具有该用户的用户的联系人、容器、订阅、发布、权限和联系人组数据。 此模式还报告用户组织或受邀的会议的摘要数据。

- **会议模式**报告特定会议的详细数据，包括会议的所有计划时间详细信息、被邀请者列表、会议允许的媒体类型列表、活动 Mcu （multipoint 控制单位）、活动参与者列表和每个参与者的信号状态。

- **解码会议 ID**解码由 **/pstnid**开关指定的公用电话交换网（PSTN）会议 ID，但不连接到后端以了解详细信息。

- **解决会议**对由 **/pstnid**开关指定的 PSTN 会议 ID 进行解码，并显示由 ID 指示的会议的相关信息。

- **Mcu 模式**报告池中每个 MCU 的 ID、媒体类型、URL、检测信号状态、会议加载和参与者负载。

- **磁盘碎片模式**显示所有磁盘的碎片状态。

此工具可用于诊断各种问题或帮助管理员进行容量规划。 例如，如果驻留在服务器上的大多数用户都选择用户驻留在服务器 B 上作为其联系人，则管理员可以将服务器 A 上的用户移动到服务器 B 以减少跨服务器流量。

### <a name="output"></a>Output

此工具输出有关 Skype for Business Server 2015 数据库的预定义报告。 **路径**：%ProgramFiles%\Skype For Business Server 2015 \ \reskit

### <a name="purpose"></a>用途

若要安装 Dbanalyze，请将其复制到本地文件夹，然后运行该工具。 若要使用此工具，请从命令行运行以下命令。 `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`下面显示了有关命令行选项的说明。

![Dbanalyze 的命令行选项。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requirements

 **计算机**只能从安装了 Skype for business Server 2015 的加入域的计算机运行 DBAnalyze。

 **网络**计算机应能够连接到后端数据库。

 **软件**在运行 DBAnalyze 之前，必须安装 Skype for Business Server 2015 软件组件。

 **用户**下表显示了拥有访问 Skype for business Server 2015 数据库所需的权限的管理员。

![Dbanalyze 的权限表。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> **/Report：磁盘**模式需要本地管理员帐户。

### <a name="examples"></a>示例

以下是有效 Dbanalyze 命令的示例：

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>摘要

DBAnalyzer 为管理员提供了快速且轻松地分析 Skype for business Server 2015 数据库的情况。

## <a name="import-storage-service-data"></a>导入存储服务数据
<a name="Issd"> </a>

ImportStorageServiceData 资源工具包工具允许将在存储服务（LYSS）上刷新的队列和终结点数据重新导入到存储服务中。

### <a name="description"></a>说明

从存储服务中刷新的数据可能已基于队列项目状态或数据库大小自动（定期）。 由于手动调用池故障转移 cmdlet 或 StorageServiceFullFlush cmdlet （池故障转移 cmdlet 调用），可能会发生此问题。 请注意，如果前端上的任何存储服务（LYSS）数据库大小高于正常级别，则不应重新导入数据，因为这样做可能只会导致更多数据被导出回来。此外，应首先解决导致存储服务队列增长的错误可能会导致出现的任何问题（例如 Exchange 终结点错误、网络问题或其他问题）。

 **方案1：** 在池故障转移过程中，可能会从每个前端的存储服务中刷新文件。 故障转移完成后，应运行该工具以重新导入数据。

 **方案2：** 每日自动刷新数据或响应超过特定大小阈值的 Storage Service 数据库（例如，60%、80%、90% 已满）。 此自动刷新的数据应由管理员定期重新导入。 在上述情况下，如果未部署监控 SCOM 包，则会有与从存储服务刷新的数据相关的 Skype for Business Server 存储服务事件。 事件 Id 为32075（已启动完全刷新操作）、32076（已完成完全刷新）、32082（维护级别刷新已启动）、32083（维护级别刷新完成）、32089（因填充数据库而发生刷新）。 注意，这些事件 Id 对应于 RTM 版本。 当管理员看到这些事件时，意味着已清除的文件。应使用此工具定期导入此数据，例如每周一次。

对于在线服务版本，如果部署了 Skype for business Server 的运行状况监视 SCOM 包，则可能会引发新警报，要求管理员将刷新后的数据重新导入到 Storage Service 中。 在触发警报的前端服务器上的事件日志中将会有相应的事件。 该事件将提供刷新数据文件所在的父路径的说明，以及有多少个文件符合警报条件。 警报条件是特定父路径下的 X 或更多文件，这些文件至少为 Y 天旧（其中 X 和 Y 是在 StorageService 中预设的，但可以通过更改 APPCONFIG 文件进行重写。）下面显示了可以触发运行状况警报的事件的两个示例，区别在于它们的父路径。 有一种可能的情况是 Web 服务文件共享，而另一个可能的是每个前端的本地应用程序数据目录。 （例如，c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService）。 然后，管理员将运行此 \reskit 工具。

此工具会在其运行的前端上增加 CPU 和 IO 负载，以及其他前端，在数据不是在其上执行该工具的前端所拥有的情况下。 我们建议在前端不低于 CPU 和 IO 负载（例如在高峰时段之外）时 runng 此工具。 其次，此工具可以2至3分钟导入一个数据文件。 在估计工具的运行时间时，请记住这一点。 默认情况下，该工具生成的详细日志文件将显示在文件存储上。 如果没有报告错误，则将其删除，因为日志文件可能是数十 MB 或更多。

![示例存储服务器事件日志事件。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requirements

安装 Skype for Business Server 2015 资源工具包工具。 该工具在安装了 Skype for Business Server 和 Skype for business Server 命令行管理程序的加入域的计算机上运行。 该工具使用命令行管理程序中的 cmdlet 来标识池中的所有前端服务器。 其次，该工具必须从安装了**RtcLocal**数据库的池中的计算机执行。 工具使用此数据库检索池的 WEBSERVICE 文件共享的位置。 此外，在使用此工具之前，每台前端服务器必须首先在每台前端服务器上使用**enable-psremoting**启用 Windows PowerShell 远程，以及执行该工具的计算机。 否则，此工具的远程 Windows PowerShell 命令将失败。 完成后，可以在池中的所有前端服务器上关闭 Windows PowerShell 远程处理。 最后，调用该工具的帐户或凭据必须具有对要在其上执行此工具的池的 webservice 文件共享的读/写权限。 否则，该工具将因 IO 权限错误而失败。

> [!NOTE]
> 在 Windows Server 2012 中，Windows PowerShell 远程处理在默认情况下处于启用状态，而不是在 Windows Server 2008 操作系统上启用。

### <a name="examples"></a>示例

```console
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
```

## <a name="lcssync"></a>LCSSync
<a name="LCSSync"> </a>

LCSSync 工具可帮助在多林环境中部署 Skype for Business Server 2015 通信软件。 此工具用于将不同用户林的用户和组作为 Active Directory 域服务联系人对象同步到安装了 Skype for Business Server 2015 的中央林。

### <a name="description"></a>说明

 LCSSync 使用中央林中的同步 Active Directory 域服务联系人对象为 Skype for Business Server 启用用户。 若要提供单一登录，必须将主用户帐户映射到适用于 Skype for business Server 2015 的中央林中的 Active Directory 域服务联系人对象。 此工具可帮助执行该映射。 此工具提供用于在 Microsoft Identity Integration Server 中创建管理代理的模板。

### <a name="summary"></a>摘要

LCSSync 工具可帮助在多林环境中部署 Skype for Business Server 2015。

## <a name="lookup-user-console"></a>查找用户控制台
<a name="LUC"> </a>

LookupUserConsole 工具显示有关特定用户的内部 Skype for Business Server 路由信息。 此信息可能对 Microsoft 支持个人在诊断部署和路由问题方面有用。

### <a name="description"></a>说明

 执行 LookupUserConsole 将打开一个命令提示符，该命令提示符接受 SIP 地址，并尝试显示与它们相关的内部 Skype for Business Server 路由信息。 键入**exit**退出 LookupUserConsole 工具。

### <a name="requirements"></a>Requirements

安装 Skype for Business Server 2015 资源工具包。 该工具在安装了 Skype for Business Server 的加入域的计算机上运行。

### <a name="examples"></a>示例

C:\Program Files\Skype for Business Server 2015 \ \Reskit\>LookupUserConsole

```console
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
```

## <a name="msturnping"></a>MsTurnPing
<a name="MsTurnPing"> </a>

MSTurnPing 工具允许 Skype for Business Server 2015 通信软件的管理员检查运行 "音频/视频边缘" 和 "音频/视频身份验证服务" 的服务器的状态，以及在拓扑中运行带宽策略服务的服务器的状态。

### <a name="description"></a>说明

MSTurnPing 工具允许 Skype for Business Server 2015 通信软件的管理员检查运行 "音频/视频边缘" 和 "音频/视频身份验证服务" 的服务器的状态，以及在拓扑中运行带宽策略服务的服务器的状态。

此工具允许管理员执行以下测试：

1. A/V 边缘服务器测试：该工具通过执行以下操作，对拓扑中的所有 A/V 边缘服务器执行测试：

   - 验证 Skype for Business Server 音频/视频身份验证服务是否已启动，并可颁发正确的凭据。

   - 验证 Skype for Business Server 音频/视频边缘服务是否已启动，并可以成功地在外部边缘上分配资源。

2. 带宽策略服务测试：该工具通过执行以下操作，对运行此拓扑中的带宽策略服务的所有服务器执行测试：

   - 验证 Skype for Business Server 带宽策略服务（身份验证）是否已启动，并可颁发正确的凭据。

   - 验证 Skype for Business Server 带宽策略服务（核心）是否已启动，并且能否成功执行带宽检查。

必须从作为拓扑一部分的计算机运行此工具，并安装本地存储。

### <a name="output"></a>Output

该工具将输出每个操作的结果。

- 如果执行了**AudioVideoEdgeServer**测试，则工具输出如下所示：

  - 在拓扑中提供 Skype for Business Server 2015 音频/视频身份验证服务的计算机的测试结果

  - 在拓扑中提供 Skype for Business Server 2015 音频/视频边缘服务的计算机的测试结果

- 如果执行了**BandwidthPolicyServer**测试，则工具输出如下所示：

  - 在拓扑中提供 Skype for Business Server 2015 带宽策略服务（身份验证）的计算机的测试结果

  - 在拓扑中提供 Skype for Business Server 2015 带宽策略服务（核心）的计算机的测试结果

### <a name="requirements"></a>Requirements

- 此工具必须从拓扑中的计算机运行，且具有本地存储。

- 该工具必须以具有本地存储访问权限的管理员身份运行。

### <a name="examples"></a>示例

以下是工具输入的一个示例。

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>摘要

对于要检查运行音频/视频和带宽策略服务的服务器的状态的 Skype for Business Server 2015 管理员来说，此工具可能是一种宝贵的资源。

## <a name="network-configuration-viewer"></a>网络配置查看器
<a name="NCV"> </a>

Skype for Business Server 2015 通信软件管理员可使用网络配置查看器查看已预配的企业的呼叫允许控制（CAC）网络拓扑，以允许实时通信会话（如根据指定带宽容量的语音或视频呼叫。 Skype for Business Server 2015 管理员定义 CAC 策略，这些策略由随 Skype for Business Server 2015 一起安装的带宽策略服务强制实施。

### <a name="description"></a>说明

网络配置查看器（NetworkConfigurationViewer）允许管理员执行以下任务：

- 以图形格式从 Skype for business Server 2015 部署中加载和查看 CAC 网络拓扑。

- 以图形格式从带宽策略服务器日志文件中加载和查看 CAC 网络拓扑。

- 以 XML 格式在磁盘上保存和存储 CAC 网络拓扑。

- 以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图。

- 查看 CAC 网络拓扑配置数据。

- 在树视图样式中查看 CAC 网络拓扑。

- 为 CAC 网络拓扑链接（例如，站点到区域、区域到区域和站点到站点链接）定义自定义连接器。

- 查看 CAC 网络拓扑网站信息、区域信息，以及预配的带宽策略和网络链接。

### <a name="purpose"></a>用途

在图形界面中查看企业 CAC 网络拓扑链接。

### <a name="examples"></a>示例

 **以图形格式从 skype for Business server 2015 部署中加载和查看 CAC 网络拓扑**： Skype For business server 2015 管理员可以使用 "**下载网络配置**" 选项在任何 Skype for business server 2015 计算机上加载和查看 cac 网络拓扑配置，如下图中所示。 在没有连接到 Skype for business Server 2015 配置存储的计算机上部署时，该工具将无法下载或查看此类配置。

![下载网络配置。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **以图形格式从带宽策略服务器日志文件中加载和查看 CAC 网络拓扑：** Skype for Business Server 2015 带宽策略服务器将 CAC 网络拓扑保存为 Skype for Business Server 2015 文件共享位置下的日志记录机制的一部分。 Skype for Business Server 2015 管理员可以使用 "**打开网络配置**" 选项以图形格式查看此类文件，如下所示。

![打开带宽策略服务器日志文件。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

以 XML 格式在磁盘上保存和存储 CAC 网络拓扑： Skype for Business Server 2015 管理员可以通过使用 "**保存网络配置**" 选项的副本以 XML 格式保存 cac 网络拓扑配置文件，如下所示。 然后，可以将已保存的配置文件脱机用于图形化查看目的。

![将网络配置另存为 XML 文件。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图： Skype for Business Server 2015 管理员可以使用 "**将网络配置图表另存为图片**" 选项以图形格式（JPG 和 BMP 文件格式）保存 cac 网络拓扑配置，如下所示。

![将网络配置另存为图片。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>查看 CAC 网络拓扑配置数据：</strong>Skype for Business Server 2015 管理员可以使用如下所示的 "查看网络配置数据" 选项，以文本格式查看相关网络配置数据，例如网络区域、网络站点、带宽配置文件和站点子网 IP 地址。

![查看网络配置数据。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **在树视图样式中查看 CAC 网络拓扑：** Skype for Business Server 2015 管理员可以使用工具窗口左侧的 "控制面板" 中的 "控制" 面板查看图形树视图样式中的相关网络配置数据，如下所示。

![在树视图中查看网络配置数据。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **为 CAC 网络拓扑链接定义自定义连接器（如站点到区域、区域到区域和站点到站点链接）：** Skype for Business Server 2015 管理员可使用如下所示的 "设置" 选项定义自定义的 CAC 网络配置 WAN 链接的图形连接器。 这有助于区分在网络配置中预配的各种类型的网络链接。

![工具](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **查看 CAC 网络拓扑网站信息、区域信息和预配的带宽策略：** Skype for Business Server 2015 管理员可以通过使用下面所示的选项查看相关 CAC 网络区域信息、网站信息和 CAC 带宽设置信息。 （例如，单击 "网络区域" 或 "网络站点" 对象中的 "**信息**"。）

![为你的网络定义自定义连接器。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>摘要

对于要以图形格式查看其部署的 CAC 网络拓扑的 Skype for business Server 2015 管理员，此工具可能是一种宝贵的资源。

## <a name="response-group-agent-live"></a>响应组代理实时
<a name="RGAL"> </a>

响应组应用程序使代理能够使用其内置 Web 服务访问有用的实时信息。 遗憾的是，在应用程序外，此数据的图形视图不可用。 响应组代理实时资源工具包工具解决了此问题，方法是提供一种简单且图形化的方式来访问此信息，并使用实时 Skype for Business 通信软件信息（如其他代理的状态）进行了改进。

### <a name="description"></a>说明

响应组代理 Live 是一种 Windows 应用程序，它向响应组代理提供登录和注销功能以及一些实时信息（如组成员身份和当前呼叫数）。 它应是 "代理组" 页面的增强版本（可从 Skype for Business 访问）。

### <a name="purpose"></a>用途

响应组应用程序对传入呼叫进行排队，然后将其路由到代理组。 为了对要服务的呼叫做出有根据的决定，代理可以访问有关其代理组的实时信息，例如，哪些其他代理可用以及每个队列中等待的呼叫数。 最初仅可通过响应组服务访问的此信息将以直观方式由响应组代理实时提供。

#### <a name="features"></a>功能

响应组代理 Live 工具建立在响应组服务和 Skype for Business Server 2015 SDK 之上。 它提供响应组代理响应组服务提供的信息和功能（如组成员身份、其他代理的状态以及等待呼叫数）。

下图展示了响应组代理的主接口。

![响应组代理 Live 工具。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

以下三个主要功能可用于响应组代理 Live 中的代理：

- **登录/注销：** 与 "代理组" 页面相反（可从 Skype for Business Server 2015）中，响应组代理 Live 仅允许代理同时登录或注销所有代理组。 此应用程序提供了三种快速代理登录或注销的方法：

  - 单击应用程序中的 "登录/注销" （绿色和红色）按钮。

  - 右键单击 "系统" 任务栏图标，并选择 "登录" 或 "注销"。

  - 使用可配置的键盘快捷方式。

- **组成员身份：** 如果选择了代理组，响应组代理 Live 将在右侧窗格中显示此组中的代理列表。 如果 Skype for Business Server 2015 在此应用程序所在的同一台计算机上运行，状态信息和联系人卡片将显示在响应组代理 Live 中。 代理可以直接从那里发送即时消息或呼叫其他代理。

- **实时统计信息：** 响应组代理 Live 提供所有代理组的实时统计信息。 更新频率为一分钟。 当响应组接听呼叫时，将在组名称旁边添加当前已排队呼叫的可视指示器。 将指针暂停在某个组上还会显示最长等待时间。

### <a name="requirements"></a>Requirements

响应组代理 Live 需要 .NET Framework 4.0。 此外，若要利用状态和联系人卡片功能，Skype for Business 必须在本地安装（且正在运行）。

#### <a name="configuration"></a>配置

通过使用应用程序中的 "选项" 对话框，可以将响应组代理 Live 自定义为单个首选项。 此外，管理员还可以通过直接编辑 RGAgentLive 文件的 defaultHostAddress 属性来定义默认的主机地址。

下图说明了代理可用于配置主机地址和快捷键的 "选项" 对话框。 通过单击主界面右上方的 "选项" 按钮可访问此对话框。

!["响应组代理实时选项" 对话框。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

可以在响应组代理 Live 配置中自定义以下三种不同的设置：

- 主机地址：这通常是属于代理主池的 web 池 FQDN。 确切的响应组服务地址将自动从此信息的后台派生（通过在主机后面追加正确的路径）。

- 快捷方式：可以自定义登录/注销的确切快捷方式。 唯一的限制是，这两个快捷方式都必须包含 "Windows 徽标" 键（除了至少一个密钥）。

- 从 Windows 开始：可以将应用程序配置为在 Windows 中自动启动。

### <a name="examples"></a>示例

下图说明了如何通过右键单击右侧窗格中的联系人呼叫或发送 IM 到另一个代理。

![发出呼叫或发送即时消息。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

下图说明了响应组代理实时如何显示队列中的当前呼叫数以及所有这些传入呼叫中的最长等待时间。

![查看队列信息。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>摘要

快速登录和注销、组成员身份和基本实时统计信息是仅在来自响应组服务的应用程序外部可用的响应组代理功能。 使用 "响应组代理实时资源工具包" 工具，Skype for Business Server 2015 管理员可以向其代理提供 Windows 应用程序，使其能够以更快速的图形方式执行任务。

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil （辅助扩展功能激活）是一个命令行工具，它使 Skype for Business Server 2015 通信软件管理员和支持人员代理能够配置代理响铃、呼叫转接、同时响铃团队呼叫设置和代表 Skype for Business Server 2015 用户呼叫装货。 该工具还允许管理员查询为特定用户发布的呼叫路由设置。使用 SEFAUtil 工具，管理员可以代表用户启用/禁用/修改呼叫转接或同时响铃。 管理员可以指定目标（采用 SIP URI 的形式），也可以使用用户已发布的目标。 此工具还允许管理员代表用户添加或删除代理人或团队呼叫组成员。此工具建立在 Microsoft 统一通信托管 API （UCMA）3.0 的基础上，并要求管理员在 SEFAUtil 的中央管理存储中创建一个受信任的应用程序。

SEFAUtil （辅助扩展功能激活）允许 Skype for Business Server 2015 管理员和支持人员代理代表 Skype 配置代理响铃、呼叫转接、同时响铃、团队呼叫设置和组呼叫应答对于 Business Server 2015 用户。 此工具还允许管理员查询为特定用户发布的呼叫路由设置。

### <a name="description"></a>说明

SEFAUtil 的当前版本只是一个命令行工具;不支持图形用户界面。 此工具基于 Microsoft 统一通信托管 API （UCMA）3.0。 此工具中的功能允许管理员和支持人员代理执行以下操作：

- 查看用户的所有呼叫路由设置（包括呼叫转接、委派、同时响铃、团队呼叫和组呼叫装货）

- 启用/禁用/修改呼叫转接设置（包括目标和无应答计时器）

- 启用/禁用/修改呼叫转接即时配置

- 启用/禁用/修改委派设置

- 启用/禁用/修改团队呼叫组设置

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil 工具中的新增工具

- 启用/禁用/修改同时响铃设置（包括目标）

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil 工具中的新增工具

- 启用/禁用/修改组呼叫装货设置

    > [!CAUTION]
    > Skype for Business Server 2015 SEFAUtil 工具中的新增工具

此工具具有以下限制：

- 仅对驻留在 Skype for Business Server 池中的用户受支持

- 不支持批量编辑多个用户的呼叫路由设置

### <a name="output"></a>Output

此工具的当前版本仅在命令提示符窗口中提供输出。 有关详细信息，请参阅本文档后面的示例部分。

### <a name="purpose"></a>用途

以下是可能使用此工具的一些关键方案：

- 小明是一名行政人员，已移至 Skype for Business Server 电话。 他在其现有的 PBX 系统上拥有委派。 在迁移到 Skype for business Server 2015 的过程中，管理员可以配置王俊元的路由，以反映其预先存在的委派配置。

- Alice 正在出差，认识到她需要来自一个客户的重要呼叫。 但是，她在宾馆中，没有对计算机的访问权限。 她呼叫帮助台并请求将其转接至移动电话号码对她的工作电话号码的所有呼叫。 帮助台人员可以代表她进行配置。

- 当用户在工作时，Joe 对他的工作电话号码的呼叫将进入移动电话语音邮件;但是，在大多数其他位置看似乎工作正常。 帮助台技术人员可以查看 Joe 的路由配置，并发现 Joe 已将呼叫配置为移动电话。 技术人员在他的办公室中向 Joe 提问，并能够确定同时响铃的规则是，当网络覆盖范围较差时，会导致呼叫进入 Joe 的移动语音邮件。

- Mike 是 Contoso 的新员工，他加入了一个新团队，在为其启用 Skype for Business Server 2015 的所有成员后，管理员能够将其团队呼叫组设置设置为包含所有新团队成员此外，管理员将 Mike 添加为团队中每个成员的团队呼叫组成员。

- Contoso 中的人力资源部门的客户服务实践是在第一次呼叫后为所有呼叫者提供个人服务。 如果部门的所有成员都非常接近，团队呼叫将同时拨打所有电话，同时对团队造成中断。 为了在不中断团队成员的情况下提供最佳服务，Skype for Business Server 2015 管理员利用组的呼叫应答功能。 管理员将所有部门成员添加到一个装货组，并向该部门传达装货组编号。 当她的办公桌中缺少 Samantha 时，Joe 会通知她的电话响铃，他将继续应答来自他的办公桌的呼叫。

### <a name="requirements"></a>Requirements

SEFAUtil 工具只能在属于受信任应用程序池一部分的计算机上运行。 UCMA 3.0 必须安装在该计算机上。 若要运行该工具，必须在该池上创建一个具有 SEFAUtil 应用程序 ID 的新受信任应用程序。

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>为 SEFAUtil 工具创建新的受信任应用程序

1. SEFAUTil 工具只能在属于受信任应用程序池一部分的计算机上运行。 如果需要，可以通过 Skype for Business Server 命令行管理程序将池添加为新的受信任应用程序池，其中包含以下 cmdlet：

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3.0 必须安装在将用于运行 SEFAUtil 工具的任何计算机上。

2. 需要在 SEFAUtil 工具的拓扑中定义受信任的应用程序。 若要将 SEFAUtil 定义为新的受信任应用程序，请使用 Skype for Business Server 命令行管理程序，并执行以下 cmdlet：

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > 如果需要，可以使用其他端口。
    
    > [!NOTE]
    > 池 FQDN：将承载 SEFAUtil 应用程序的服务器或池的 FQDN （通常为 Skype for business 前端服务器 > 或池）。
    > 池注册器 FQDN：与此应用程序池关联的 Skype for Business 前端服务器或池的 FQDN。
    > 池网站：此池所驻留的网站的网站 ID。

3. 需要启用拓扑更改。 通过执行以下 cmdlet，可以通过 Skype for Business Server 命令行管理程序来启用拓扑更改：

   ```powershell
   Enable-CsToplogy
   ```

4. 如果需要，请在将用于运行 SEFAUtil 工具的服务器中安装 Skype for Business Server 2015 资源工具包工具（该服务器必须是受信任的应用程序池的一部分）。

5. 验证 SEFAUtil 是否正常运行。 为此，请从具有管理员权限的 windows 命令提示符处运行该工具，以在部署中显示用户的呼叫转接设置。 默认情况下，此工具位于： "..\Program Files\Skype for Business Server 2015 \ \Reskit" 中。 若要显示用户的呼叫转接设置，请使用以下命令：

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    应显示用户的呼叫转接设置。

#### <a name="group-call-pickup"></a>组间电话提货

组内呼叫应答需要在 Skype for Business Server 2015 中进行其他配置，才能充分启用此功能。 在向用户分配分拣组之前，请参阅组的 "呼叫装货产品文档"，了解此功能的规划和部署步骤。

### <a name="examples"></a>示例

#### <a name="display-current-call-handling-settings"></a>显示当前呼叫处理设置

以下命令将显示用户的呼叫处理。  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> 此示例使用 **/server**开关指定要连接到的 Skype For business 服务器。

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>设置呼叫转接/无应答目的地

本示例设置呼叫转接/无应答目的地和环延迟。 这里不提供/server 开关;SEFAUtil 尝试自动发现 Skype for Business Server 2015。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>立即启用呼叫转接

此示例立即启用到另一个用户的呼叫转接。

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>立即禁用呼叫转接

本示例将立即禁用呼叫转接。

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>将用户添加为代理人并设置代理人的同时响铃

本示例将用户添加为代理人并设置代理人的同时响铃。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>更改代理人的同时响铃规则

本示例将上一示例中设置的同时响铃规则更改为延迟的震铃规则。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>删除委派

本示例删除代理。

> [!NOTE]
> 删除最后一个委派时，将自动禁用委派震铃。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>添加代理并设置呼叫转发到代理人规则

本示例添加一个代理人并设置 "呼叫前转到代理人" 规则。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>启用同时响铃并设置目标号码

本示例启用同时响铃并设置同时响铃的目标号码。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> 若要更改已启用同时响铃的用户的同时响铃的目标号码，请使用/enablesimulring 开关保留该命令，否则将不会更改目标号码。

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>禁用同时响铃

本示例禁用同时响铃。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>为团队呼叫添加团队成员，并将同时响铃设置为 "团队呼叫成员" 组

此示例向用户的团队呼叫组添加团队成员，并允许同时响铃到团队呼叫组。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> 将成员添加到用户的团队呼叫组将自动切换用户的同时响铃响铃，以同时他的团队呼叫组。

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>从团队呼叫组中删除成员

本示例将删除用户的团队呼叫组的团队成员。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> 如果要删除的成员是团队呼叫组的唯一成员，同时响铃到团队呼叫组将自动禁用。

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>将延迟环设置为团队呼叫组

本示例将延迟的环更改为 "团队呼叫组时间" 设置。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>启用团队呼叫

此示例为给定用户启用团队呼叫。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> 如果用户的团队呼叫组没有成员，则不会启用团队呼叫。

 "输出"

#### <a name="disable-team-call"></a>禁用团队呼叫

本示例为给定用户禁用团队呼叫。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>启用组呼叫应答并将分拣组分配给用户

本示例将一个分拣组分配给一个用户，并启用组呼叫应答。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>禁用组呼叫应答

本示例为给定用户禁用组呼叫应答。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> 当您为用户禁用组呼叫应答时，分配给该用户的组号码将不会保留。 如果您随后要为该用户重新启用组呼叫应答，则必须使用/enablegrouppickup 开关再次分配该组编号。

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep. ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>说明

Sysprep.inf 是 Windows PowerShell 脚本，它将在 Windows Server 2008 操作系统计算机上安装以下 Skype for Business Server 2015 先决条件。

- Microsoft .Net Framework 4。5

- Microsoft SQL Server Express

- Windows Powershell 版本3。0

- Visual c + + 2010 可再发行组件

- Internet information Server 更新

- Windows Identity Foundation

- Skype for Business Server 2015 核心文件

  尽管脚本名称类似于 Microsoft Windows 操作系统的系统准备工具，但它们是不同的。 此脚本将仅安装 Skype for business Server 2015 所需的必备组件。 安装这些必备组件后，即可使用 Windows SYSPrep 工具创建服务器的映像。

### <a name="requirements"></a>Requirements

在运行 Sysprep.inf. ps1 脚本之前，必须将必备文件复制到 Windows Server 2008 操作系统计算机上的本地文件夹（例如**D:\Setup）**。 此文件夹还必须包含 Skype for Business Server 2015 文件（特别是 setup.exe）的副本 **。** 可以从以下位置下载必备文件：


| **必备**                                | **Location**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4。5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows Powershell 版本3。0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual c + + 2010 可再发行组件  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| Internet information Server 更新  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | 从 Skype for Business Server 2015 媒体复制  <br/>                   |

### <a name="parameter"></a>参数

**-SetupFolder**参数将必备文件的目录位置作为参数。

### <a name="examples"></a>示例

若要运行 Sysprep.inf 脚本并安装 Skype for Business Server 2015 先决条件，请从提升的命令提示符处运行以下命令：

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>未分配号码通知迁移
<a name="UNAM"> </a>

未分配号码通知迁移工具使 Skype for Business Server 2015 管理员能够将通知应用程序提供的未分配号码配置从源 Skype for Business 服务器或池移动到目标 Skype for Business 服务器或池。

### <a name="description"></a>说明

未分配号码通知迁移工具是一个 Windows PowerShell 脚本，它将源服务器或池的通知应用程序提供服务的未分配号码配置移动到不同的服务器或池。

执行时，"未分配号码" 通知迁移脚本将执行以下操作：

1. 将源服务器或池中承载的通知应用程序的未分配号码通知所使用的所有音频文件移动到目标服务器或池的文件存储区。

    > [!NOTE]
    > 在将音频文件复制到目标池后，会从源池中将其删除。

2. 将为源服务器或池中承载的通知应用程序配置的所有未分配号码通知移动到目标服务器或池。

3. 将由源服务器或池中承载的通知应用程序提供服务的所有未分配号码范围重新分配给目标服务器或池。

在成功运行脚本后，源服务器或池中承载的通知应用程序所提供的所有未分配号码范围将通过目标服务器或池的相同配置进行服务。

### <a name="output"></a>Output

**Move-csannouncementconfiguration**脚本在 Skype For Business Server 命令行管理程序窗口中指示其执行迁移操作成功或失败的位置。

如果在发生任何错误时中断操作的执行，则已成功移动到目标的未分配号码范围将保留在操作表单的目标中，并且要迁移的未分配号码范围的剩余部分将保留在源和操作表单中的源。 若要完全迁移配置的其余部分，请在解决错误后重新运行脚本。

### <a name="purpose"></a>用途

未分配号码通知迁移脚本可用于以下三种方案：

- **将配置设置迁移到新版本的 Skype For Business Server：** Contoso 正在迁移到 Skype for business Server 2015，并作为迁移过程的一部分，Skype for Business Server 管理员希望将宣告应用程序提供服务的未分配号码配置从 Lync Server 2013 部署移动到新的 Skype for Business Server 2015 部署。 为了移动配置设置，Skype for Business Server 管理员使用未分配的号码通知迁移工具。

- **将部署从 Skype For Business Server 2015 回滚到 Lync Server 2013：** 由于意外因素，Contoso 必须将迁移回滚到新的 Skype for Business Server 2015 部署。 为最大限度地减少对服务的中断，Skype for Business Server 管理员使用 "未分配号码" 通知迁移工具将配置从 Skype for Business Server 2015 部署回滚到 Lync Server 2013 部署。

- **在部署之间移动数据：** Contoso 正处于将一个池的所有服务器替换为较新服务器的过程。 他们的策略是部署新的 Skype for Business Server 2015 池，将所有数据从旧池移动到新池，然后弃用旧池。 部署新池后，将使用 "未分配号码通知" 迁移工具将配置从旧池移动到新池。

#### <a name="requirements"></a>Requirements

若要成功运行此工具，需要满足以下主要要求：

1. 必须在已安装 Skype for Business Server 命令行管理程序的计算机上运行该脚本。

2. 必须在源和目标 Skype for business 服务器或池中成功部署通知应用程序。

#### <a name="move-csannouncementconfiguration-script"></a>Move-csannouncementconfiguration 脚本

Move-csannouncementconfiguration 脚本需要下表中所述的两个参数。

![Move-csannouncementconfiguration 参数。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>示例

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>将未分配的号码通知配置从 Lync Server 2013 池移动到 Skype for Business Server 2015 池

本示例将从源池（Lync Server 2013）中未分配的号码宣告移动到目标池（Skype for Business Server 2015）。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>将未分配号码的通知配置从 Skype for business Server 2015 池移动到 Lync Server 2013 池

本示例将源池（Skype for Business Server 2015）中未分配的号码宣告移动到目标池（Lync Server 2013）。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web 会议数据
<a name="WebConfData"> </a>

通过 Web 会议数据工具，Skype for Business Server 2015 通信软件的管理员可以更好地控制与组织者的 Web 会议关联的数据。 方案包括基于时间戳条件删除特定用户的会议数据的功能。

### <a name="description"></a>说明

此工具允许管理员执行以下操作：

1. 查找与单个用户相关联的所有 Web 会议数据。

2. 删除与单个用户相关联的所有 Web 会议数据。

3. 删除与某一日期之前的单个用户相关联的所有 Web 会议数据。

4. 当用户从一个池移动到另一个池时，移动与单个用户相关联的所有 Web 会议数据。

    > [!NOTE]
    > 当用户从一个池移动到另一个池时，支持 Lync Server 2010 的资源工具包工具移动与单个用户相关联的所有 Web 会议数据。 现在，此工具中的功能已被弃用，取而代之的是**MoveConferenceData**参数。 有关此参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet。

该工具仅删除处于非活动状态的会议的会议数据。 无法删除活动会议（或会话中的会议）。

必须从与目标用户位于同一池中的计算机运行此工具。 此工具管理其会议内容数据的用户必须驻留在相同的用户池中。

### <a name="output"></a>Output

此工具将输出每个操作的结果：

- 如果执行了查询，该工具会将具有该用户的所有非活动会议数据文件夹的列表输出为组织者。

- 如果执行删除，该工具将输出其数据将被删除的所有会议数据文件夹的列表。

### <a name="requirements"></a>Requirements

该工具需要在组织者当前托管的同一个池中运行。

必须使用具有对内容文件存储的访问权限的管理员权限运行该工具。

### <a name="examples"></a>示例

下表介绍了这些参数，其中一些参数在示例中使用。

![Web 会议数据工具参数。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

上面的示例展示了查询命令的工作原理。 此类命令的输出将是受此工具影响的所有会议内容文件夹的列表。

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

上一个示例是 "删除" 命令。 "删除" 命令将删除此用户的所有非活动会议文件夹。

### <a name="summary"></a>摘要

对于需要更精确控制会议会议数据的管理员来说，此工具可能是一项宝贵的资源。


