---
title: Skype for Business Server 2015 资源工具包工具文档
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 本主题介绍 Skype for Business Server 2015 资源工具包中的工具，包括每个工具的用途及其使用示例。 Skype for Business Server 2015 资源工具包可帮助部署和管理 Skype for Business Server 2015 的 IT 管理员更轻松地执行常规任务。 例如，Web Conf Data 工具可用于轻松控制用户在联机会议期间上载的数据。 SEFAUtil 工具可用于为用户设置代理人呼叫转发和应答。 我们鼓励 IT 管理员使用这些工具更有效地管理 Skype for Business Server 2015。
ms.openlocfilehash: bf1a1d946c998466b118e0ab2038044a48d90970
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822032"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server 2015 资源工具包工具文档

本主题介绍 Skype for Business Server 2015 资源工具包中的工具，包括每个工具的用途及其使用示例。 Skype for Business Server 2015 资源工具包可帮助部署和管理 Skype for Business Server 2015 的 IT 管理员更轻松地执行常规任务。 例如 **，Web Conf Data** 工具可用于轻松控制用户在联机会议期间上载的数据。 **SEFAUtil** 工具可用于为用户设置代理人呼叫转发和应答。 我们鼓励 IT 管理员使用这些工具更有效地管理 Skype for Business Server 2015。

## <a name="installation-of-the-resource-kit-tools"></a>安装资源工具包工具

若要安装 Skype for Business Server 2015 资源工具包，请 [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) 下载中心下载。

运行 **OCSResKit.msi** 以执行简单的安装。 .msi 将安装以下路径中的所有工具 **：%Program Files%\Skype for Business Server 2015\ResKit。** 自包含可执行文件的工具在此文件夹中。 也具有支持文件的工具在其自己的子文件夹内。

## <a name="supported-environments"></a>支持的环境

Skype for Business Server 2015 资源工具包应安装在符合 Skype for Business Server 2015（通常用于运行 Skype for Business Server 2015）所需的规范的服务器上。

## <a name="resource-kit-tools-overview"></a>资源工具包工具概述

以下是 Skype for Business Server 2015 资源工具包中提供的工具列表。 以下各节介绍了每个工具的说明，包括要求和示例用法。

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [带宽策略服务监视器](resource-kit-tools.md#bpsm)

- [带宽使用率分析器](resource-kit-tools.md#bua)

- [呼叫 Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [导入存储服务数据](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [查找用户控制台](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [网络配置查看器](resource-kit-tools.md#NCV)

- [响应组代理实时](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [未分配号码通知迁移](resource-kit-tools.md#UNAM)

- [Web Conf 数据](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

"通讯簿服务配置" (ABSConfig) 是一种管理工具，可帮助管理员在 Skype for Business Server 2015 中自定义通讯簿服务配置。 此工具还使 Skype for Business Server 2015 管理员能够还原默认通讯簿服务设置。

### <a name="description"></a>说明

ABSConfig 是一个图形用户界面应用程序，使管理员能够配置与通讯簿服务相关的 Active Directory 域服务属性。

该工具的主要方案如下：

- 使管理员能够将 Active Directory 域服务中的属性映射到 Skype for Business Server 2015 的属性。

- 使管理员能够指定要包含在通讯簿服务文件中或要排除的 Active Directory 域服务属性。

- 使管理员能够还原默认的通讯簿服务设置。

ABSConfig 工具可通过使用文件启动ABSConfig.exe文件。 该工具将打开到" **配置属性"** 选项卡。此表具有将 Active Directory 域服务属性映射到 Skype for Business Server 2015 的属性字段以及根据特定属性筛选器指定在通讯簿服务文件中包括或排除哪些用户的选项。 它还具有自定义要包含在通讯簿文件中的电话号码值的选项。 通过 **"还原默认值** "选项，管理员可以将通讯簿服务设置还原为默认值。

> [!NOTE]
> 将 AD 属性重新映射到不同的 OC 字段名称仅适用于通讯簿文件下载，并且不受通讯簿 Web 查询支持。

### <a name="output"></a>输出

ABSConfig 将通讯簿服务配置存储在数据库中。

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>用途

ABSConfig 提供了一种快速而轻松地自定义 Skype for Business Server 2015 通讯簿服务的方法。

### <a name="requirements"></a>要求

#### <a name="computer"></a>计算机

ABSConfig 只能从安装了 Skype for Business Server 2015 的已加入域的计算机运行。 对于 Skype for Business Server 2015 Enterprise Edition，此工具可在安装期间启用了通讯簿服务的任何前端服务器上运行。

#### <a name="network"></a>Network

计算机应能够连接到前端池和后端数据库。

#### <a name="software"></a>软件

在运行 ABSConfig 工具之前，必须安装以下软件组件：

- Skype for Business Server 2015

#### <a name="users"></a>用户

具有更新 Skype for Business Server 2015 部署所需的权限的管理员。

### <a name="examples"></a>示例

ABSConfig 可通过在命令 **提示符ABSConfig.exe** 命令提示符下键入命令命令。 下面是 ABSConfig 工具用户界面。

![ABSConfig.exe工具。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>摘要

ABSConfig 工具为管理员提供了一个快速且易于使用的工具来自定义 Skype for Business Server 2015 通讯簿服务。

## <a name="bandwidth-policy-service-monitor"></a>带宽策略服务监视器
<a name="bpsm"> </a>

带宽策略服务监视器工具旨在允许管理员查看以下列表：

1. 拓扑中配置的所有 Skype for Business Server 2015 带宽 (身份验证) 核心策略服务

2. 每个服务与其他带宽策略服务和边缘服务器的连接

3. 网络配置文档中配置的所有链接以及每个带宽策略服务报告的实际带宽使用量

### <a name="description"></a>说明

带宽策略服务监视器工具作为基于 GUI 的应用程序实现。 管理员通过运行 PDPMonUI.exe 来启动PDPMonUI.exe。

当该工具启动时，它会尝试发现拓扑中的带宽策略服务列表。 初始更新完成后，窗口左侧的窗格将填充一个服务列表，这些服务按它们所属的群集进行分组。

当管理员选择特定带宽策略服务时，右侧窗格将显示有关该特定服务的信息。 该窗格还有两个显示信息的主要选项卡。

#### <a name="machine-info-tab"></a>计算机信息选项卡

" **计算机信息** "选项卡显示所选带宽策略服务的详细信息，以及所选带宽策略服务与其他服务建立的所有连接的列表和状态。

#### <a name="topology-info-tab"></a>拓扑信息选项卡

" **拓扑信息** "选项卡显示了在网络配置设置中配置的所有链接的列表。 对于每个链接，将显示音频和视频带宽容量。 此外，当前利用的带宽以 Kbps 为单位和容量百分比显示。 该工具使用颜色编码突出显示利用率接近容量的链接，这允许管理员快速隔离此类链接。

> [!NOTE]
>  如果带宽策略服务监视器工具连接到任何配置的带宽策略服务时遇到故障，将不会填充计算机信息和拓扑 **信息** 选项卡中的信息。  但是，该工具可能最初连接，但随后会失去与服务的连接。 在这种情况下，管理员可能会看到过时的信息。 每个选项卡 **上都有** "上次更新时间"时间戳，管理员可以查看上次为特定带宽策略服务更新数据的时间。

### <a name="output"></a>输出

没有命令行输出;程序输出包含在主图形用户界面中 (GUI) 。

### <a name="purpose"></a>用途

带宽策略服务监视器工具的目的是允许管理员查看拓扑中定义的每个带宽策略服务的状态。 此外，管理员可以查看网络配置文档中定义的所有链接实时带宽使用情况。

### <a name="requirements"></a>要求

带宽策略服务监视器工具需要在属于 Skype for Business Server 拓扑的一部分的计算机上运行。

### <a name="summary"></a>摘要

带宽策略服务监视器工具对于管理员来说可能是一项有价值的资源，以便管理员可以检查拓扑中所有带宽策略服务的状态，更重要的是，他们可以获取在网络配置设置中定义的链接实时带宽利用率。

## <a name="bandwidth-utilization-analyzer"></a>带宽使用率分析器
<a name="bua"> </a>

带宽利用率分析器是一种工具，可创建有关企业网络中跨 WAN 链路的 UC 终结点的各种带宽消耗视图的报告。 这些报告可用于了解当前带宽消耗模式，并有助于进行带宽容量规划。

### <a name="description"></a>说明

带宽利用率分析器作为基于 GUI 的应用程序实现。 此工具专门为整个网络的音频使用率生成报告，并帮助进行容量规划。 它还对分配给各种链接的带宽容量进行访问。

### <a name="output"></a>输出

带宽利用率分析器为系统中配置的所有 WAN 链路提供带宽容量和音频利用率的图形。

### <a name="purpose"></a>用途

在任何语音和视频部署中，监视并了解企业网络中媒体流量的带宽使用率趋势至关重要。 带宽利用率分析器工具使管理员可以实现此目的。 此工具执行以下操作：

- 生成特定报告以用于整个网络的音频使用率

- 有助于对分配给各种链路的带宽容量进行更有效的容量规划和迭代

带宽利用率分析器可以生成带宽容量和使用率报告的图形绘图;它们如下所示：

- 企业网络内的所有 WAN 链路

- 按所选的 WAN 链接进行筛选

- 按超过链接容量的 WAN 链接进行筛选

- 按未充分利用预配带宽的 WAN 链路进行筛选

- 按已到达关键级别的 WAN 链路进行筛选 (带宽使用率大于 WAN 链路带宽容量的 90) 

- 按 WAN 链接类型（网络站点链接、区域间链接和站点内的链接）进行筛选

- 按网络区域筛选

#### <a name="applications"></a>应用程序

带宽使用率分析器具有以下两个应用程序 (工具) ：

- **WanLinkLogCollector.exe** 利用此工具，用户可以输入所需信息。

- **BandwidthUtilizationAnalyzer.xlsm** Microsoft Excel 电子表格软件报告由用户自动WanLinkLogCollector.exe。 此应用程序允许用户将筛选器应用于报告，如本文稍后部分所示。

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>使用带宽使用率分析器阶段

使用带宽使用率分析器有两个阶段：

- 收集日志，使用日志WanLinkLogCollector.exe

- 自定义报告，使用 BandwidthUtilizationAnalyzer.xlsm 执行

    > [!IMPORTANT]
    > 我们强烈建议BandwidthUtilizationAnalyzer.xls最终用户不要手动启动。

#### <a name="starting-bandwidth-utilization-analyzer"></a>启动带宽利用率分析器

在WanLinkLogCollector.exe提示符或 Windows 资源管理器启动命令。

 **使用WanLinkLogCollector.exe**

使用应用程序有三WanLinkLogCollector.exe：

1. **记录日程表** 提供需要生成报告的日程表

2. **指定文件目录** 提供文件位置信息

3. **收集日志并启动报告查看器** 执行命令以生成报告

#### <a name="step-1---log-the-timeline"></a>步骤 1 - 记录日程表

通过记录时间线，工具用户可以指定以下内容，如下图所示。

1. **开始日期** 这是要生成报告的日程表的开始日期;例如，2010 年 8 月 1 日。

2. **结束日期** 这是要生成报告的日程表的结束日期;例如，2010 年 9 月 30 日。

     ![带宽利用率 A 中的开始日期和结束日期](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>步骤 2 - 指定文件目录

用户可以按如下所示指定以下文件目录。

- **服务器日志文件位置** 存储带宽策略服务器日志的文件夹位置。 这通常位于<\<fileserver\> \\ \> FE \AppServerFiles\PDP 中。

- **临时文件存储位置** 生成报告时存储中间文件的临时文件位置。

    ![带宽利用率 Anal 中的文件目录](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > 确保向工具用户提供了对服务器日志和临时文件存储文件夹的足够文件访问权限。

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>步骤 3 - 收集日志并启动报告查看器

若要收集日志并启动报告查看器 **，请单击"** 执行"，如下所示。 此步骤将收集所需数据。

![在带宽利用率中定期收集数据](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

输入验证成功后，将显示如下所示的消息。

![记录带宽 Utili 中收集的通知](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

单击“确定”。 BandwidthUtilizationAnalyzer.xlsm 自动启动。 按照消息框中的说明操作。 有关详细信息，请参阅下一 **BandwidthUtilizationAnalyzer.xls中的** "使用 m"。


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>使用 BandwidthUtilizationAnalyzer.xlsm

1. 当BandwidthUtilizationAnalyzer.xlsm 时，请单击 **"刷新** "，如下所示。

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. 打开文件文件夹后，consolidated.csv消息框中指定的位置选择一个文件夹，如下所示。 它还将显示位置为 **C：\Temp。**

     ![在 BandwidthUtilizationAnalyzer 中打开文件夹。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. 单击 **“导入”**。

4. 图形绘图自动生成。 当在后台工作的指针消失时，它可用。

     ![在报表视图中应用筛选器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>将筛选器应用于报表视图

可应用于筛选器的筛选器报表视图如下所示：

![在报表视图中应用筛选器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **名称** 按 WAN 链接 (筛选器位于图形视图右侧) 。前缀表示以下链接类型;查看垂直 (蓝色) 框：

   - **S 网站** 从网络站点到网络区域之间的 WAN 链路

   - **IS 站点间** 两个网络站点之间的 WAN 链路

   - **R 区域间** 两个网络区域之间的 WAN 链路

2. **超出限制** 按带宽利用率大于带宽容量的 WAN 链路进行筛选

3. **关键级别** 按带宽利用率达到 90% 或大于带宽容量的 WAN 链路进行筛选

4. **利用不足** 按带宽利用率低于带宽容量的 25% 的 WAN 链路进行筛选

5. **链接类型** 按以下 WAN 链接类型进行筛选：

   - **网络站点** 类型

   - **站点间** 类型

   - **区域间链接** 类型

6. **区域** 按网络区域筛选

下图显示了上述筛选器。

按 **名称筛选**。 选择需要在图形中显示的链接列表。

![在 BandwidthUtilizationAnalyzer 中按名称筛选。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

按 **超出限制筛选**。 选择 **True** 以强制执行筛选器。

![按超出限制进行筛选。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

按 **关键级别筛选**。 选择 **True** 以强制执行筛选器。

![按关键级别筛选。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

按 **"利用不足"进行筛选**。 选择 **True** 以强制执行筛选器。

![按"利用不足"进行筛选。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

按链接 **类型筛选**。 选择需要显示的一个或多个类型。

![按链接类型筛选。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

按区域 **筛选**。 选择需要显示其链接的区域列表。

![按区域筛选。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>要求

- .NET Framework 3.5

- Microsoft Excel 2010 或 Excel 2007

### <a name="summary"></a>摘要

带宽利用率分析器用于绘制网络中 UC 流量的音频带宽利用率。 此工具还可用于报告网络上视频带宽的使用情况。

## <a name="call-parkometer"></a>呼叫 Parkometer
<a name="callpark"> </a>

呼叫 Parkometer 是一个命令行应用程序，可轻松访问呼叫 Park 通道数据库。

### <a name="description"></a>说明

呼叫 Parkometer 是跟踪当前已呼叫的一种工具。 它还收集有关通道和呼叫 (CPS) 使用情况的统计信息。 此命令行工具提供从本地或远程连接的计算机对 CPS 通道SQL Server数据库的读写访问权限。

所有选项都是互斥的。 命令行语法如下所示：

- **-o** 参数 - 列出为此池配置的所有通道范围。

- **-n** 参数- 列出此池中当前使用的所有通道。 显示的信息如下所示：

  - SIP 统一资源 (URI) 的 URI。

  - 呼叫所位于的 CPS 的主机名。

  - 呼叫被叫到的时间戳。

- **-f** 参数 - 列出池中当前可用通道的数量。

- **-r \<n\>** parameter - 列出 \<n\> 最后一次被叫的呼叫。 显示的信息如下所示：

  - 被方 SIP URI。

  - 小马 SIP URI。

  - 呼叫已托管的 CPS 的主机名。

  - 检索或删除呼叫的时间戳。

- **-t \<n\>** 参数 - 测试在数据库中保留通道以显示分配的通道号码的随机性。

### <a name="output"></a>输出

根据在命令提示符下指定的输入参数，呼叫呼叫时间表将显示以下输出：

- 为此池配置的所有通道范围

- 当前已呼叫的已呼叫

- 通道中 (可用) 数量

- 最近接听的呼叫

- 用于测试统一和随机通道值的保留通道

### <a name="purpose"></a>用途

CPS 工具的用途是提供对 CPS 数据库的命令行访问。 管理员可以查看 CPS 使用情况并确定分配给池的通道数。

### <a name="requirements"></a>要求

如果在运行 CPS 的同一计算机上运行此工具，则没有任何要求。 如果此工具在远程计算机上运行，则必须SQL Server Skype for Business Server 2015 使用的远程数据库以允许远程访问。 必须使用数据库连接字符串配置呼叫SQL Server以连接到池的呼叫SQL Server。 此SQL Server数据库连接字符串在配置文件中定义 **，parkometer.exe.config。** 它必须放置在用户所在的parkometer.exe目录中。 以下 XML 文件是示例parkometer.exe.config。必须配置的参数包括用户名 (例如，mydomain\Administrator) 、密码 (（例如，mypassword) ）和主机名 (例如，myserver) 。

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

已部署的通道范围：-o 参数列出为此池配置的所有通道范围，如下所示

![呼叫 Parkometer 中的通道范围。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Currently parked calls： the -n parameter lists all currently used orbits on this pool as shown

![呼叫 Parkometer 中当前已呼叫的呼叫。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

可用通道数：-f 参数列出池中当前可用通道的数量，如下所示

![呼叫 Parkometer 中的免费通道。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

最近已停呼叫：-r \<n\> 参数列出最后 \<n\> 一个已停呼叫，如下所示

![呼叫 Parkometer 中的最近呼叫。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

测试通道保留：-t 参数测试在数据库中保留通道 \<n\> ，如下所示

![在呼叫 Parkometer 中测试通道保留。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>摘要

呼叫 Parkometer 是一个命令行工具，可提供有关呼叫管理服务器的详细信息。

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>说明

DBAnalyze 是一个命令行工具，可帮助管理员收集有关 Skype for Business Server 2015 数据库的分析报告。 DBAnalyze 具有以下模式：诊断、用户数据、会议、MCUs 和磁盘碎片：

- **诊断模式** 创建一个报告，其中包含有关表 (记录数的信息， 碎片、数据大小和索引大小) 、数据和 日志文件 大小、上次备份时间、运行 Microsoft Office Communications Server 的服务器之间的联系人分布、平均权限数、联系人、容器、订阅、出版物、每个用户的终结点、任何未正确存储的用户、无法路由的用户、每个用户组织的平均会议数、计划的会议、活动会议以及数据库版本。

    > [!NOTE]
    > 运行诊断模式可能会影响服务器性能。

- **用户数据模式** 报告指定用户或联系人和权限列表中具有该用户的用户的联系人、容器、订阅、发布、权限和联系人组数据。 此模式还会报告用户组织或受邀参加的会议的摘要数据。

- **会议模式** 报告特定会议的详细数据，包括会议的所有计划时详细信息、被邀请者列表、允许参加会议的媒体类型列表、活动 MCUs (多点控制单元) 、活动参与者列表以及每个参与者的信号状态。

- **解码会议 ID** 解码公用电话交换网 (PSTN) **/pstnid** 开关指定的会议 ID，但不连接到后端获取详细信息。

- **解析会议** 解码 **/pstnid** 开关指定的 PSTN 会议 ID，并显示有关 ID 指示的会议的信息。

- **MCUs 模式** 报告池中每个 MCU 的 ID、媒体类型、URL、检测信号状态、会议负载和参与者负载。

- **磁盘碎片模式** 显示所有磁盘的碎片状态。

此工具可用于诊断各种问题或帮助管理员进行容量规划。 例如，如果服务器 A 上的大多数用户选择服务器 B 上作为联系人的用户，管理员可以将服务器 A 上的用户移动到服务器 B 以减少跨服务器通信。

### <a name="output"></a>输出

此工具输出有关 Skype for Business Server 2015 数据库的预定义报告。 **路径**： %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>用途

若要安装Dbanalyze.exe，请将其复制到本地文件夹，然后运行该工具。 若要使用该工具，请从命令行运行以下命令。 `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 命令行选项的说明如下所示。

![用于命令的命令行Dbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>要求

 **计算机** DBAnalyze 只能从安装了 Skype for Business Server 2015 的已加入域的计算机运行。

 **网络** 计算机应能够连接到后端数据库。

 **软件** 运行 DBAnalyze 之前，必须安装 Skype for Business Server 2015 软件组件。

 **用户** 下表显示了具有访问 Skype for Business Server 2015 数据库的必要权限的管理员。

![权限表Dbanalyze.exe。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> **/report：disk** 模式需要本地管理员帐户。

### <a name="examples"></a>示例

下面是有效命令Dbanalyze.exe示例：

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>摘要

DBAnalyzer 为管理员提供了快速而轻松地分析 Skype for Business Server 2015 数据库。

## <a name="import-storage-service-data"></a>导入存储服务数据
<a name="Issd"> </a>

ImportStorageServiceData 资源工具包工具允许将从存储服务 (LYSS) 刷新的队列和终结点数据重新导入存储服务。

### <a name="description"></a>说明

从存储服务中刷新的数据可能是自动 (，) 队列项目状态或数据库大小进行定期刷新。 这可能是由于手动调用池故障转移 cmdlet 或 StorageServiceFullFlush cmdlet (池故障转移 cmdlet 调用了) 。 请注意，如果前端的任何存储服务 (LYSS ) 数据库大小高于正常级别，则理想情况下不应重新导入数据，因为这样做可能会导致更多数据导出回。此外，应首先解决可能导致存储服务队列增长的错误的任何问题 (例如 Exchange 终结点错误、网络问题或其他) 。

 **方案 1：** 在池故障转移期间，可能会从每个前端的存储服务中刷新文件。 故障转移完成后，应运行该工具以重新导入数据。

 方案 **2：** 每天自动刷新数据或响应超过特定大小阈值的存储服务数据库 (例如 60%、80%、90% ) 。 此自动刷新的数据应由管理员定期重新导入。 在以上情况下，如果未部署监控 SCOM 包，则存在与从存储服务刷新数据相关的 Skype for Business Server 存储服务事件。 32075 (完全刷新操作的事件 ID 已启动) ，32076 (完全刷新已完成) ，32082 (维护级别刷新开始) ，32083 (维护级别刷新完成) ，32089 (刷新由于填充数据库) 而发生。 请注意，这些事件 ID 对应于 RTM 版本。 当管理员看到这些事件时，这意味着有一些文件已刷新。应定期使用此工具重新导入此数据，例如每周导入一次。

对于联机服务版本，如果部署了 Skype for Business Server 的运行状况监控 SCOM 包，则可能会引发新的警报，要求管理员将刷新的数据重新导入到存储服务。 前端服务器上事件日志中将存在触发警报的相应事件。 该事件将说明刷新的数据文件所在的父路径，以及满足警报条件的文件数。 警报条件是，特定父路径下存在至少 ( Y 天的文件，其中 X 和 Y 在 StorageService 中预设，但可以通过更改 APPCONFIG 文件覆盖。) 下面显示了两个可触发运行状况警报的事件示例，区别在于其父路径不同。 一种可能位于 Web 服务文件共享下，另一种可能性是每个前端的本地应用程序数据目录。  (例如 c：\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ) 。 然后，管理员将运行此 reskit 工具。

如果运行此工具的前端不拥有数据，则此工具将增加它所运行的前端以及其他前端上的 CPU 和 IO 负载。 建议在前端不负载过重的 CPU 和 IO 负载（例如高峰时段之外）时运行此工具。 其次，此工具可以 2 到 3 分钟导入一个数据文件。 在估计工具将运行的时间时，请记住这一点。 默认情况下，日志文件生成的详细内容将显示在文件存储中。 如果未报告任何错误，请将其删除，因为日志文件数十 MB 或更多。

![示例存储服务器事件日志事件。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>要求

安装 Skype for Business Server 2015 资源工具包工具。 该工具在安装了 Skype for Business Server 和 Skype for Business Server 命令行管理程序的已加入域的计算机上运行。 该工具使用命令行管理程序中的 cmdlet 标识池中的所有前端服务器。 其次，必须从池中安装了 **RtcLocal** 数据库的计算机执行该工具。 该工具使用该数据库检索池的 WEBSERVICE 文件共享的位置。 此外，在使用该工具之前，每台前端服务器必须先在每个前端服务器上以及从其中执行该工具的计算机上使用 **Enable-PSRemoting** 启用 Windows PowerShell 远程处理。 否则，此工具Windows PowerShell远程命令将失败。 Windows PowerShell后，可以在池中的所有前端服务器上关闭远程。 最后，调用该工具的帐户或凭据必须具有对正在执行此工具的池的 webservice 文件共享的读/写权限。 否则，该工具将失败，出现 IO 权限错误。

> [!NOTE]
> 在Windows Server 2012，Windows PowerShell默认启用远程，但在 Windows Server 2008 操作系统上不启用远程。

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

LCSSync 工具有助于在多林环境中部署 Skype for Business Server 2015 通信软件。 此工具用于将不同用户林中的用户和组作为 Active Directory 域服务联系人对象同步到安装了 Skype for Business Server 2015 的中央林。

### <a name="description"></a>说明

 LCSSync 使用中央林中同步的 Active Directory 域服务联系对象为用户启用 Skype for Business Server。 若要提供单一登录，主用户帐户必须映射到 Skype for Business Server 2015 中央林中的 Active Directory 域服务联系人对象。 此工具可帮助执行该映射。 此工具提供在 Microsoft Identity Integration Server 中创建管理代理的模板。

### <a name="summary"></a>摘要

LCSSync 工具有助于在多林环境中部署 Skype for Business Server 2015。

## <a name="lookup-user-console"></a>查找用户控制台
<a name="LUC"> </a>

LookupUserConsole 工具显示有关特定用户的内部 Skype for Business Server 路由信息。 此信息对于 Microsoft 支持人员诊断部署和路由问题可能很有用。

### <a name="description"></a>说明

 执行LookupUserConsole.exe将打开接受 SIP 地址的命令提示符，并尝试显示与 SIP 地址相关的内部 Skype for Business Server 路由信息。 键入 **exit** 以退出 LookupUserConsole 工具。

### <a name="requirements"></a>要求

安装 Skype for Business Server 2015 资源工具包。 该工具在安装了 Skype for Business Server 的已加入域的计算机上运行。

### <a name="examples"></a>示例

C：\Program Files\Skype for Business Server 2015\ResKit \>LookupUserConsole.exe

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

MSTurnPing 工具允许 Skype for Business Server 2015 通信软件的管理员检查运行音频/视频边缘和音频/视频身份验证服务的服务器以及拓扑中运行带宽策略服务的服务器的状态。

### <a name="description"></a>说明

MSTurnPing 工具允许 Skype for Business Server 2015 通信软件的管理员检查运行音频/视频边缘和音频/视频身份验证服务的服务器以及拓扑中运行带宽策略服务的服务器的状态。

该工具允许管理员执行以下测试：

1. A/V 边缘服务器测试：该工具通过执行以下操作对拓扑中所有 A/V 边缘服务器执行测试：

   - 验证 Skype for Business Server 音频/视频身份验证服务是否已启动，并可以发出正确的凭据。

   - 验证 Skype for Business Server 音频/视频边缘服务是否已启动，并可以成功分配外部边缘上的资源。

2. 带宽策略服务测试：该工具通过执行以下操作，对在拓扑中运行带宽策略服务的所有服务器执行测试：

   - 验证 Skype for Business Server 带宽策略服务 (身份验证) 并可以发出正确的凭据。

   - 验证 Skype for Business Server 带宽策略服务 (核心) 并可以成功执行带宽检查。

必须从属于拓扑并安装了本地存储的计算机运行此工具。

### <a name="output"></a>输出

该工具输出每个操作的结果。

- 如果 **执行了 AudioVideoEdgeServer** 测试，该工具的输出如下所示：

  - 在拓扑中提供 Skype for Business Server 2015 音频/视频身份验证服务的计算机的测试结果

  - 在拓扑中提供 Skype for Business Server 2015 音频/视频边缘服务的计算机的测试结果

- 如果 **执行 BandwidthPolicyServer** 测试，则该工具输出如下：

  - 在拓扑中提供 Skype for Business Server 2015 带宽策略服务 (身份验证) 测试结果

  - 在拓扑中提供 Skype for Business Server 2015 带宽策略服务 (核心) 测试结果

### <a name="requirements"></a>要求

- 必须从拓扑中具有本地存储的计算机运行此工具。

- 该工具必须以有权访问本地存储的管理员角色运行。

### <a name="examples"></a>示例

下面是工具输入的示例。

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>摘要

对于要检查运行音频/视频和带宽策略服务的服务器状态的 Skype for Business Server 2015 管理员来说，此工具可能是一项有价值的资源。

## <a name="network-configuration-viewer"></a>网络配置查看器
<a name="NCV"> </a>

Skype for Business Server 2015 通信软件管理员可以使用网络配置查看器查看企业的呼叫允许控制 (CAC) 网络拓扑，该拓扑已预配为允许实时通信会话，例如基于指定带宽容量的语音或视频呼叫。 Skype for Business Server 2015 管理员定义 CAC 策略，这些策略由随 Skype for Business Server 2015 一起安装的带宽策略服务强制执行。

### <a name="description"></a>说明

网络配置查看器 (NetworkConfigurationViewer.exe) 允许管理员执行以下任务：

- 以图形格式从 Skype for Business Server 2015 部署加载和查看 CAC 网络拓扑。

- 以图形格式从带宽策略服务器服务器日志文件和查看 CAC 网络拓扑。

- 以 XML 格式在磁盘上保存和存储 CAC 网络拓扑。

- 以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图。

- 查看 CAC 网络拓扑配置数据。

- 以树视图样式查看 CAC 网络拓扑。

- 定义 CAC 网络拓扑链接的自定义连接器 (例如，站点到区域、区域到区域以及站点到站点链接) 。

- 查看 CAC 网络拓扑站点信息、区域信息以及已预配的带宽策略和网络链接。

### <a name="purpose"></a>用途

在图形界面中查看企业 CAC 网络拓扑链接。

### <a name="examples"></a>示例

 以图形格式从 **Skype for Business Server 2015** 部署加载和查看 CAC 网络拓扑：Skype for Business Server 2015 管理员可以使用"下载网络配置"选项在任何 Skype for Business Server  2015 计算机上加载和查看 CAC 网络拓扑配置，如下图所示。 在未连接到 Skype for Business Server 2015 配置存储的计算机上部署该工具时，将无法下载或查看此类配置。

![下载网络配置。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **以图形格式从带宽策略服务器日志文件和查看 CAC 网络拓扑：** Skype for Business Server 2015 带宽策略服务器将 CAC 网络拓扑保存为 Skype for Business Server 2015 文件共享位置下的日志记录机制的一部分。 Skype for Business Server 2015 管理员可以使用"开放网络配置"选项以图形格式查看此类文件，如下所示。

![打开带宽策略服务器日志文件。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

以 XML 格式在磁盘上保存和存储 CAC 网络拓扑：Skype for Business Server 2015 管理员可以使用"保存网络配置副本"选项以 XML 格式保存 CAC 网络拓扑配置文件，如下所示。 然后，保存的配置文件可以脱机用于图形查看目的。

![将网络配置另存为 XML 文件。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

以 JPG 或 BMP 格式保存和存储 CAC 网络拓扑图：Skype for Business Server 2015 管理员可以使用"保存网络配置"图表作为图片选项以图形格式保存 CAC 网络拓扑配置 ( JPG 和 BMP 文件格式) ，如下所示。

![将网络配置保存为图片。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>查看 CAC 网络拓扑配置数据：</strong>Skype for Business Server 2015 管理员可以使用如下所示的"查看网络配置"数据选项，以文本格式查看相关的网络配置数据，如网络区域、网络站点、带宽配置文件和站点子网 IP 地址。

![查看网络配置数据。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **以树视图样式查看 CAC 网络拓扑：** Skype for Business Server 2015 管理员可以使用工具窗口左侧的控制面板以图形树视图样式查看相关的网络配置数据，如下所示。

![在树视图中查看网络配置数据。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **定义 CAC** 网络拓扑链接的自定义 (，如站点到区域、区域到区域以及站点到站点链接) ：Skype for Business Server 2015 管理员可以使用如下所示的"设置"选项为 CAC 网络配置 WAN 链接定义自定义图形连接器。 这有助于区分在网络配置中预配的各种类型的网络链接。

![工具](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **查看 CAC 网络拓扑站点信息、区域信息和已设置带宽策略：** Skype for Business Server 2015 管理员可以使用如下所示的选项查看相关的 CAC 网络区域信息、站点信息和 CAC 带宽设置信息。  (例如， **单击网络区域** 或网络站点对象中的"信息"。) 

![为网络定义自定义连接器。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>摘要

对于希望以图形格式查看部署的 CAC 网络拓扑的 Skype for Business Server 2015 管理员来说，此工具可能是一项有价值的资源。

## <a name="response-group-agent-live"></a>响应组代理实时
<a name="RGAL"> </a>

响应组应用程序使代理能够使用其内置 Web 服务访问有用的实时信息。 遗憾的是，此数据的图形视图在应用程序外部不可用。 响应组代理实时资源工具包工具通过提供一种简单、图形的方式访问此信息，从而解决了此问题，通过实时 Skype for Business 通信软件信息（如存在其他代理）进行增强。

### <a name="description"></a>说明

响应组代理实时是一个 Windows 应用程序，提供登录和注销功能以及一些实时信息 (例如组成员身份和当前呼叫数) 响应组代理。 它旨在成为可从 Skype for Business 访问的 (组页面的增强版本。

### <a name="purpose"></a>用途

响应组应用程序将传入呼叫排入队列，然后将这些呼叫路由到代理组。 为了做出有关哪些呼叫服务的明智决定，代理可以访问有关其代理组实时信息，例如哪些其他代理可用以及每个队列中等待的呼叫数。 此信息最初只能通过响应组服务访问，由响应组代理 Live 以直观方式提供。

#### <a name="features"></a>功能

响应组代理实时工具基于响应组服务和 Skype for Business Server 2015 SDK 构建。 它向响应组代理提供响应组服务 (的信息和功能，例如组成员身份、其他代理的存在以及呼叫等待) 。

下图说明了响应组代理 Live 的主接口。

![响应组代理实时工具。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

响应组代理实时中的代理可以使用以下三个主要功能：

- **登录/注销：** (与可从 Skype for Business Server 2015) 访问的"代理组"页面相反，响应组代理实时仅允许代理一次登录或注销所有代理组。 此应用程序为代理提供三种快速登录或注销方法：

  - 单击应用程序中的 (和) 登录/注销按钮。

  - 右键单击系统托盘图标，然后选择登录或注销。

  - 使用可配置的键盘快捷方式。

- **组成员身份：** 选择代理组后，响应组代理实时将在右窗格中显示此组中代理的列表。 如果 Skype for Business Server 2015 与此应用程序在同一计算机上运行，状态信息和联系人卡片将显示在响应组代理 Live 中。 代理可以直接从该发送 IM 或呼叫其他代理。

- **实时统计信息：** 响应组代理实时功能提供所有代理组实时统计信息。 更新频率为一分钟。 响应组应答呼叫时，在组名称旁边添加一个可视指示器，其中显示当前排队的呼叫数。 将指针停留在组上还会显示最长等待时间。

### <a name="requirements"></a>要求

响应组代理 Live 需要 .NET Framework 4.0。 此外，若要利用状态和联系人卡片功能，必须在本地安装 Skype for Business (并运行) 。

#### <a name="configuration"></a>配置

通过使用应用程序中的"选项"对话框，可以将响应组代理实时自定义为单个首选项。 此外，管理员还可以定义默认主机地址，方法为直接编辑默认主机RGAgentLive.exe.config属性。

下图说明了代理可用于配置主机地址和快捷键的"选项"对话框。 通过单击主界面右上方的"选项"按钮可以访问此对话框。

!["响应组代理实时选项"对话框。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

可以在响应组代理实时配置中自定义以下三个不同的设置：

- 主机地址：这通常是属于代理主池的 Web 池 FQDN。 确切的响应组服务地址会在后台自动派生自此信息 (主机地址后追加正确的) 。

- 快捷方式：可以自定义登录/注销的确切快捷方式。 唯一的限制是，这两个快捷方式都必须包含"Windows 徽标" (以及至少另一个键) 。

- 从 Windows 开始：可以将应用程序配置为自动启动 Windows。

### <a name="examples"></a>示例

下图说明如何通过右键单击右窗格中的联系人来呼叫其他代理或向其他代理发送 IM。

![发出呼叫或发送 IM。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

下图说明了响应组代理 Live 如何显示队列中的当前呼叫数以及所有这些传入呼叫中的最长等待时间。

![查看队列信息。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>摘要

快速登录和注销、组成员身份和基本实时统计信息是有趣的响应组代理功能，仅在应用程序外部从响应组服务提供。 通过响应组代理实时资源工具包工具，Skype for Business Server 2015 管理员可以为代理提供 Windows 应用程序，以便他们以更快、图形的方式执行任务。

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (辅助扩展功能激活) 是一个命令行工具，使 Skype for Business Server 2015 通信软件管理员和技术支持代理能够代表 Skype for Business Server 2015 用户配置代理人响铃、呼叫转发、同时响铃、团队呼叫设置和组内呼叫接听。 该工具还允许管理员查询为特定用户发布的呼叫路由设置。SEFAUtil 工具允许管理员代表用户启用/禁用/修改呼叫转发或同时响铃。 管理员可以以 SIP URI (的形式指定目标) 或使用用户已发布的目标。 此工具还允许管理员代表用户添加或删除代理人或团队呼叫组的成员。此工具基于 Microsoft 统一通信托管 API (UCMA) 3.0 构建，要求管理员在 SEFAUtil 的中央管理存储中创建受信任的应用程序。

SEFAUtil (辅助扩展功能激活) 使 Skype for Business Server 2015 管理员和技术支持代理可以代表 Skype for Business Server 2015 用户配置代理人响铃、呼叫转发、同时响铃、团队呼叫设置和组内呼叫接听。 此工具还允许管理员查询为特定用户发布的呼叫路由设置。

### <a name="description"></a>说明

当前版本的 SEFAUtil 只是一个命令行工具;没有支持的图形用户界面。 此工具基于 Microsoft 统一通信托管 API (UCMA) 3.0。 此工具中的功能允许管理员和技术支持代理执行以下操作：

- 查看用户呼叫的所有呼叫路由 (包括呼叫转发、委派、同时响铃、团队呼叫和组内呼叫) 

- 启用/禁用/修改呼叫 (包括目标计时器和无应答计时器) 

- 启用/禁用/修改呼叫转发即时配置

- 启用/禁用/修改委派设置

- 启用/禁用/修改团队呼叫组设置

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil 工具中的新增功能

- 启用/禁用/修改同时响铃设置 (目标) 

    > [!NOTE]
    > Skype for Business Server 2015 SEFAUtil 工具中的新增功能

- 启用/禁用/修改组内呼叫接听设置

    > [!CAUTION]
    > Skype for Business Server 2015 SEFAUtil 工具中的新增功能

此工具具有以下限制：

- 仅支持位于 Skype for Business Server 池中的用户

- 不支持批量编辑多个用户的呼叫路由设置

### <a name="output"></a>输出

此工具的当前版本仅在命令提示符窗口中提供输出。 有关详细信息，请参阅本文档稍后的"示例"部分。

### <a name="purpose"></a>用途

以下是可能使用此工具的一些关键方案：

- Bob 是一名主管，已移至 Skype for Business Server 电话服务。 他对现有 PBX 系统具有委派。 作为移动到 Skype for Business Server 2015 的一部分，管理员能够配置 Bob 的路由以反映其预先存在的委派配置。

- Alice 正在出差，意识到她需要她的一位客户拨打重要电话。 但是，她位于酒店中，无法访问计算机。 她呼叫支持人员，并请求他们将拨打她的工作电话号码的所有呼叫转发到其移动电话号码。 支持人员可以代表她执行配置。

- Joe 每次工作时，拨打工作号码的呼叫都会发至其移动语音邮件;但是，在大多数其他位置，情况似乎可以正常运行。 技术支持人员可以查看 Joe 的路由配置，并发现 Joe 已配置了同时响铃到其移动电话。 技术人员询问 Joe 办公室的移动覆盖情况，并可以确定同时响铃规则是导致呼叫在网络覆盖较差时转到 Joe 的移动语音邮件的原因。

- Mike 是 Contoso 的新员工，他加入了一个新团队，其中所有成员都配置为团队呼叫，启用 Skype for Business Server 2015 后，管理员能够设置其团队呼叫组设置以包括所有新的团队成员，此外，管理员将 Mike 添加为团队中每个成员的团队呼叫组成员。

- Contoso 人力资源部门的客户服务做法是自第一次呼叫以来，为所有呼叫者提供个人服务。 鉴于部门的所有成员彼此非常接近，让所有电话通过团队呼叫同时响铃会对团队造成很大干扰。 为了提供最佳服务而不会干扰团队成员，Skype for Business Server 2015 管理员利用组内呼叫接听功能。 管理员将所有部门成员添加到分拣组，并与部门沟通分拣组号码。 当 Samantha 不在桌面上时，Joe 注意到她的电话在响铃，然后继续从自己的桌面接听电话。

### <a name="requirements"></a>要求

SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。 UCMA 3.0 必须安装在该计算机上。 若要运行该工具，必须在该池中创建具有 SEFAUtil 应用程序 ID 的新受信任应用程序。

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>为 SEFAUtil 工具创建新的受信任应用程序

1. SEFAUTil 工具只能在属于受信任应用程序一部分的计算机上应用程序池。 如果需要，可以使用以下 cmdlet 通过 Skype for Business Server 命令行应用程序池将池添加为新的受信任池：

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > 必须在将用于运行 SEFAUtil 工具的任何计算机上安装 UCMA 3.0。

2. 需要在 SEFAUtil 工具的拓扑中定义受信任应用程序。 若要将 SEFAUtil 定义为新的受信任应用程序，请使用 Skype for Business Server 命令行管理程序并执行以下 cmdlet：

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > 如果需要，可以使用其他端口。
    
    > [!NOTE]
    > 池 FQDN：将承载 SEFAUtil 应用程序的服务器或池的 FQDN (通常是 Skype for Business 前端服务器>池) 。
    > 池注册器 FQDN：与此域关联的 Skype for Business 前端服务器或池的 FQDN 应用程序池。
    > 池站点：此池所位于的站点的站点 ID。

3. 需要启用拓扑更改。 可以通过执行以下 cmdlet 通过 Skype for Business Server 命令行管理程序启用拓扑更改：

   ```powershell
   Enable-CsToplogy
   ```

4. 如果需要，在将用于运行 SEFAUtil 工具的服务器中安装 Skype for Business Server 2015 资源工具包工具 (服务器必须是受信任服务器的一应用程序池) 。

5. 验证 SEFAUtil 是否正常运行。 为此，请通过具有管理员权限的 Windows 命令提示符运行该工具，以显示部署中用户的呼叫转发设置。 默认情况下，该工具位于："...\Program Files\Skype for Business Server 2015\Reskit"中。 若要显示用户的呼叫转发设置，请使用以下命令：

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    应显示用户的呼叫转发设置。

#### <a name="group-call-pickup"></a>群组代接

组内呼叫分拣需要在 Skype for Business Server 2015 中进行其他配置，以完全启用该功能。 在将分拣组分配给用户之前，请参阅组内呼叫分拣产品文档，以参阅此功能的规划和部署步骤。

### <a name="examples"></a>示例

#### <a name="display-current-call-handling-settings"></a>显示当前呼叫处理设置

以下命令显示用户的呼叫处理。  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> 此示例使用 **/server** 开关指定要连接到的 Skype for Business Server。

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>设置呼叫转发/无应答目标

本示例设置呼叫前向/无应答目标以及响铃延迟。 此处未提供 /server 开关;SEFAUtil 尝试自动发现 Skype for Business Server 2015。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
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

#### <a name="enable-call-forwarding-immediately"></a>立即启用呼叫转发

此示例立即启用呼叫转发给其他用户。

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

#### <a name="disable-call-forwarding-immediately"></a>立即禁用呼叫转发

此示例立即禁用呼叫转发。

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
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

本示例将用户添加为代理人，并设置代理人同时响铃。

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

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>更改代理人同时响铃规则

本示例将上一示例中设置的同时响铃规则更改为延迟响铃规则。

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

#### <a name="remove-the-delegate"></a>删除代理

本示例删除委托。

> [!NOTE]
> 删除最后一个委派时，将自动禁用委派响铃。

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

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>添加代理并设置Call-Forward委派规则

本示例添加一个代理，并设置呼叫转发给代理人规则。

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

本示例启用同时响铃并设置同时响铃目标号码。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> 若要更改已启用同时响铃的用户的同时响铃目标号码，请保持使用 /enablesimulring 开关的命令，否则不会更改目标号码。

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

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>将团队成员添加到Team-Call设置同时响铃到Team-Call成员组

本示例向用户的团队呼叫组添加团队成员，并启用团队呼叫组同时响铃。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> 向用户的团队呼叫组添加成员将自动切换用户的同时响铃设置，以模拟其团队呼叫组。

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>从组中删除Team-Call成员

此示例将删除用户团队呼叫组的团队成员。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> 如果要删除的成员是团队呼叫组的唯一成员，将自动禁用同时响铃到团队呼叫组。

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>将延迟响铃设置为Team-Call组

此示例将延迟响铃更改为团队呼叫组时间设置。

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

#### <a name="enable-team-call"></a>启用Team-Call

本示例为给定用户启用团队呼叫。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> 如果用户的团队呼叫组没有成员，将不会启用团队呼叫。

 "输出"

#### <a name="disable-team-call"></a>禁用Team-Call

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

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>启用组内呼叫接听并将分拣组分配给用户

本示例为用户分配一个分拣组，并启用组内呼叫分拣。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 "输出"

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>禁用组内呼叫接听

本示例为给定用户禁用组内呼叫接听。

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> 为用户禁用组内呼叫接听时，不会保留分配给该用户的组号码。 如果随后希望为该用户重新启用组内呼叫接听，则必须使用 /enablegrouppickup 开关再次分配组号码。

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>说明

SYSPrep.ps1一Windows PowerShell脚本，它将在 Windows Server 2008 操作系统计算机上安装以下 Skype for Business Server 2015 必备组件。

- Microsoft .Net Framework 4.5

- Microsoft SQL Server Express

- Windows Powershell 版本 3.0

- Visual C++ 2010 可再发行组件

- Internet Information Server 更新

- Windows Identity Foundation

- Skype for Business Server 2015 核心文件

  虽然脚本名称类似于 Microsoft Windows 操作系统的系统准备工具，但二者有所不同。 此脚本将仅安装 Skype for Business Server 2015 所需的必备组件。 安装这些必备组件后，可以使用 Windows SYSPrep 工具创建服务器映像。

### <a name="requirements"></a>要求

在运行 SYSPrep.ps1 脚本之前，必须将必备文件复制到 Windows Server 2008 操作系统计算机上本地文件夹中 (例如 **D：\Setup) 。** 此文件夹还必须包含 Skype for Business Server 2015 文件的副本，特别是 **Setup.exe。** 可以从以下位置下载必备文件：


| **先决条件**                                | **位置**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .Net Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows Powershell 版本 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 可再发行组件  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| Internet Information Server 更新  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | 从 Skype for Business Server 2015 媒体复制  <br/>                   |

### <a name="parameter"></a>参数

**-SetupFolder** 参数将必备文件的目录位置作为参数

### <a name="examples"></a>示例

若要运行 SYSPrep.ps1 脚本并安装 Skype for Business Server 2015 必备组件，请从提升的命令提示符运行以下命令：

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>未分配号码通知迁移
<a name="UNAM"> </a>

未分配号码通知迁移工具使 Skype for Business Server 2015 管理员能够将通知应用程序服务未分配号码配置从源 Skype for Business Server 或池移动到目标 Skype for Business Server 或池。

### <a name="description"></a>说明

未分配号码通知迁移工具是一个 Windows PowerShell 脚本，用于将源服务器或池的公告应用程序所服务的未分配号码配置移动到其他服务器或池。

执行时，未分配号码通知迁移脚本将执行以下操作：

1. 将源服务器或池中托管通知应用程序的未分配号码通知使用的所有音频文件移动到目标服务器或池的文件存储。

    > [!NOTE]
    > 将音频文件复制到目标池后，将从源池中删除它们。

2. 将为源服务器或池中承载的公告应用程序配置的所有未分配号码通知移动到目标服务器或池。

3. 将源服务器或池中托管通知应用程序服务的所有未分配号码范围重新分配给目标服务器或池。

成功运行脚本后，由源服务器或池中承载的公告应用程序服务的所有未分配号码范围现在都由目标服务器或池使用相同的配置提供服务。

### <a name="output"></a>输出

**Move-CsAnnouncementConfiguration** 脚本指示在 Skype for Business Server 命令行管理程序窗口中执行迁移操作的成功或失败。

如果操作执行因任何错误而中断，则成功移动到目标位置的未分配号码范围将保留在目标中，并且其余要迁移的未分配号码范围将保留在源中以及操作表单中。 若要完全迁移其余配置，请解决错误后重新运行脚本。

### <a name="purpose"></a>用途

未分配号码通知迁移脚本可用于以下三种方案：

- **将配置设置迁移到新版本的 Skype for Business Server：** Contoso 正在迁移到 Skype for Business Server 2015，作为迁移过程的一部分，Skype for Business Server 管理员希望将通知应用程序服务未分配号码配置从 Lync Server 2013 部署移动到新的 Skype for Business Server 2015 部署。 若要移动配置设置，Skype for Business Server 管理员使用未分配号码通知迁移工具。

- **将部署从 Skype for Business Server 2015 回滚到 Lync Server 2013：** 由于意外因素，Contoso 必须回滚到新 Skype for Business Server 2015 部署的迁移。 为了最大限度地减少服务中断，Skype for Business Server 管理员使用未分配号码通知迁移工具将配置从 Skype for Business Server 2015 部署回滚到 Lync Server 2013 部署。

- **在部署之间移动数据：** Contoso 正在将一个池的所有服务器替换为较新的服务器。 其策略是部署新的 Skype for Business Server 2015 池，将旧池的所有数据移动到新池，然后弃用旧池。 部署新池后，使用未分配号码通知迁移工具将配置从旧池移动到新池。

#### <a name="requirements"></a>要求

以下是成功运行该工具所需的主要要求：

1. 该脚本必须从安装了 Skype for Business Server 命令行管理程序 的计算机运行。

2. 通知应用程序必须成功部署在源和目标 Skype for Business 服务器或池中。

#### <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration脚本

the Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.

![Move-CsAnnouncementConfiguration参数。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>示例

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>将未分配号码通知配置从 Lync Server 2013 池移动到 Skype for Business Server 2015 池

此示例将未分配号码通知从源池 (Lync Server 2013) 移动到目标池 (Skype for Business Server 2015) 。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>将未分配号码通知配置从 Skype for Business Server 2015 池移动到 Lync Server 2013 池

此示例将未分配号码通知从源池 (Skype for Business Server 2015) 移动到目标池 (Lync Server 2013) 。

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf 数据
<a name="WebConfData"> </a>

Web Conf Data Tool 允许 Skype for Business Server 2015 通信软件的管理员对与组织者的 Web 会议关联的数据进行更多控制。 方案包括基于时间戳条件删除特定用户的会议数据的能力。

### <a name="description"></a>说明

此工具允许管理员执行以下操作：

1. 查找与单个用户关联的所有 Web 会议数据。

2. 删除与单个用户关联的所有 Web 会议数据。

3. 删除与某个用户关联的所有超过特定日期的 Web 会议数据。

4. 将单个用户从一个池移动到另一个池时，移动与该用户关联的所有 Web 会议数据。

    > [!NOTE]
    > Lync Server 2010 的资源工具包工具支持在将单个用户从一个池移动到另一个池时移动与该用户关联的所有 Web 会议数据。 此工具现在弃用此功能，而支持 **MoveConferenceData** 参数。 有关此参数的详细信息，请参阅 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet。

该工具仅删除非活动会议的会议数据。 无法 (活动会议或) 中的会议。

必须从与目标用户位于同一池中的计算机运行此工具。 此工具管理其会议内容数据的用户必须托管在同一个用户池中。

### <a name="output"></a>输出

此工具输出每个操作的结果：

- 如果执行查询，该工具将输出将该用户作为组织者的所有非活动会议数据文件夹的列表。

- 如果执行删除操作，该工具将输出其数据将被删除的所有会议数据文件夹的列表。

### <a name="requirements"></a>要求

该工具需要在组织者当前所位于的同一池中运行。

该工具必须使用具有内容文件存储访问权限的管理员权限运行。

### <a name="examples"></a>示例

下表介绍参数，其中一些参数在示例中使用。

![Web Conf Data Tool 参数。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

前面的示例演示查询命令如何工作。 此类命令的输出将是受此工具影响的所有会议内容文件夹的列表。

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

前面的示例是删除命令。 删除命令将从该用户中删除所有非活动会议文件夹。

### <a name="summary"></a>摘要

此工具对于需要更精确地控制会议数据的管理员来说，可能是一项有价值的资源。


