---
title: Lync Server 2013 资源工具包工具文档
TOCTitle: Lync Server 2013 资源工具包工具文档
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945604(v=OCS.15)
ms:contentKeyID: 52061196
ms.date: 08/03/2014
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 资源工具包工具文档

 

_**上一次修改主题：** 2014-01-09_

本主题介绍属于 Lync Server 2013 资源工具包一部分的工具，包括每个工具的用途及其用法示例。Lync Server 2013 资源工具包工具 可帮助负责部署和管理 Lync Server 2013 的 IT 管理员更轻松地完成日常任务。例如，**Web Conf Data** 工具可用于轻松控制召开联机会议期间用户上载的数据。**SEFAUtil** 工具可用于为用户设置代理人呼叫转接和应答。 鼓励 IT 管理员使用这些工具更高效地管理 Lync Server 2013。

## 安装资源工具包工具

要安装 Lync Server 2013 资源工具包工具，请下载 **OCSReskit.msi**。您可以从下载中心下载资源工具包工具安装程序，网址为 [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)。

运行 **OCSResKit.msi** 以执行简单安装。.msi 将所有工具安装在以下路径中：**%Program Files%\\Microsoft Lync Server 2013\\ResKit**。属于自包含可执行文件的工具位于此文件夹中。也具有文件的工具位于其自己的子文件夹中。

## 支持的环境

为了获得最佳性能，应在 Lync Server 2013 要求的相同环境中并按照相同规范安装 Lync Server 2013 资源工具包工具。

## 资源工具包工具概述

下面的列表介绍了 Lync Server 2013 资源工具包中提供的工具。下面的部分涵盖每个工具的描述（包括要求和示例用法）。

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

  - Web 会议数据

## ABSConfig

通讯簿服务配置工具 (ABSConfig) 是一个管理工具，可帮助管理员在 Lync Server 2013 中自定义通讯簿服务配置。此工具也使 Lync Server 2013 管理员能够还原默认通讯簿服务设置。

## 说明

ABSConfig 是一个图形用户界面应用程序，使管理员能够配置与通讯簿服务相关的 Active Directory 域服务 属性。

工具的主要方案如下所示：

  - 使管理员能够将 Active Directory 域服务中的属性映射到 Lync Server 2013 的属性。

  - 使管理员能够指定要在通讯簿服务文件中包括或排除的 Active Directory 域服务属性。

  - 使管理员能够还原默认通讯簿服务设置。

可使用 absConfig.exe 文件启动 ABSConfig 工具。该工具将打开至“配置属性”选项卡。此表具有用于将 Active Directory 域服务属性映射到 Lync Server 2013 的属性指定的选项以及基于特定属性筛选器指定要在通讯簿服务文件中包括或排除哪些用户的选项。它也具有用于自定义在通讯簿文件中包括电话号码的哪个值的选项。“还原默认值”选项使管理员能够将通讯簿服务设置还原为默认值。

## 自 Lync Server 2010 以来的更改

在 Lync Server 2013 ABS 配置工具中，可通过取消选中属性的“启用”复选框来删除属性（行）。这与 Lync Server 2010 中的删除行操作具有相同效果。

> [!NOTE]  
> “启用”复选框位于最右侧列中；您可能需要向右滚动才能看到该列


## 输出

ABSConfig 将通讯簿服务配置存储在数据库中。

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

## 用途

ABSConfig 提供快速且轻松的自定义 Lync Server 2013 通讯簿服务的方式。

## 要求

## 计算机

ABSConfig 只能从安装了 Lync Server 2013 并且加入域的计算机运行。对于 Lync Server 2013 Enterprise Edition，此工具只能在安装期间启用了通讯簿服务的任何前端服务器上运行。

## 网络

计算机应能够连接到前端池和后端数据库。

## 软件

在运行 ABSConfig 工具之前，必须安装以下软件组件：

  - Microsoft Lync Server 2013

## 用户

具有更新 Lync Server 2013 部署所需权限的管理员。

## 示例

可以通过在命令提示符处键入 **ABSConfig.exe** 启动 ABSConfig。ABSConfig 工具用户界面如下所示。

![ABSConfig.exe 工具。](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig.exe 工具。")

## 摘要

ABSConfig 使管理员能够快速且轻松地自定义 Lync Server 2013 通讯簿服务。

## 带宽策略服务监视器

带宽策略服务监视器工具旨在允许管理员查看以下内容的列表：

1.  拓扑中配置的所有 Lync Server 2013 带宽策略服务

2.  每个服务与其他带宽策略服务和边缘服务器的连接

3.  网络配置文档中配置的所有链接以及每个带宽策略服务报告的实时带宽使用量

## 说明

带宽策略服务监视器工具作为基于 GUI 的应用程序进行实施。管理员可通过运行 PDPMonUI.exe 启动该工具。

当该工具启动时，它将尝试发现拓扑中的带宽策略服务列表。完成初始更新之后，窗口左侧的窗格将填充服务列表，按服务所属的群集进行分组。

当管理员选择特定带宽策略服务时，右侧的窗格显示有关该特定服务的信息。该窗格也有两个主要选项卡可显示信息。

## “计算机信息”选项卡

“计算机信息”选项卡显示选中的带宽策略服务的详细信息以及所选带宽策略服务与其他服务之间建立的连接。

## “拓扑信息”选项卡

“拓扑信息”选项卡显示在网络配置设置中配置的所有链接。对于每个链接，显示音频和视频带宽容量。此外，以 Kbps 和容量百分比形式显示当前利用的带宽。该工具使用颜色编码突出显示利用率接近容量的链接，这使得管理员可快速隔离此类链接。

> [!NOTE]  
> 如果带宽策略服务监视器工具在连接到配置的任何带宽策略服务时遇到故障，则“计算机信息”和“拓扑信息”选项卡不会填充。然而，该工具可能最初连接成功，后来却丢失了与服务的连接。在这种情况下，管理员可能会看到过时的信息。每个选项卡上的“上次更新时间”时间戳允许管理员查看特定带宽策略服务的数据上次更新的时间。


## 输出

没有命令行输出；程序输出包含在主图形用户界面 (GUI) 中。

## 用途

带宽策略服务监视器工具旨在允许管理员查看拓扑中定义的每个带宽策略服务的状态。此外，管理员可以查看网络配置文档中定义的所有链接的实时带宽用量。

## 要求

带宽策略服务监视器工具需要在属于 Lync Server 拓扑一部分的计算机上运行。

## 摘要

带宽策略服务监视器工具对于管理员而言是一项宝贵资源，通过该工具，管理员可以检查拓扑中所有带宽策略服务的状态，他们可以获得网络配置设置中定义的链接的实时带宽用量。

## 带宽用量分析器

带宽用量分析器工具可创建 UC 终结点跨企业网络中的 WAN 链接消耗的带宽的各种视图的报告。这些报告可用于了解当前带宽消耗模式并帮助进行带宽容量规划。

## 说明

带宽用量分析器作为基于 GUI 的应用程序进行实施。此工具专门针对跨网络的音频利用生成报告，从而帮助进行容量规划。它也统计分配给各个链接的带宽容量。

## 输出

带宽用量分析器可将系统中配置的所有 WAN 链接的带宽容量和音频利用率绘制成图形。

## 用途

在任何音频和视频部署中，监视并了解企业网络中媒体流量的带宽用量趋势非常重要。带宽用量分析器工具允许管理员达成该目标。此工具可执行以下操作：

  - 针对跨网络的音频利用率生成具体报告

  - 帮助更高效地进行容量规划并统计分配给各个链接的带宽容量

带宽用量分析器可将带宽容量和用量报告绘制成图形；如下所示：

  - 企业网络中的所有 WAN 链接

  - 按选中的 WAN 链接进行筛选

  - 按超过链接容量的 WAN 链接进行筛选

  - 按用量低于设置的带宽的 WAN 链接进行筛选

  - 按已达到严重级别（带宽用量大于 WAN 链接带宽容量的 90%）的 WAN 链接进行筛选

  - 按 WAN 链接类型（网络站点链接、区域与区域间的链接以及站点内的链接）进行筛选

  - 按网络区域进行筛选

## 应用程序

带宽用量分析器具有以下两个应用程序（工具）：

  - **WanLinkLogCollector.exe**   此工具使用户能够输入所需信息。

  - **BandwidthUtilizationAnalyzer.xlsm**  WanLinkLogCollector.exe 将启动 Microsoft Excel 电子表格软件报告。此应用程序允许对报告应用筛选器，如本文后面所示。

## 使用带宽用量分析器的阶段

使用带宽用量分析器时有两个阶段：

  - 收集日志，使用 WanLinkLogCollector.exe 执行

  - 自定义报告，使用 BandwidthUtilizationAnalyzer.xlsm 执行

> [!IMPORTANT]
> 强烈建议最终用户不要手动启动 BandwidthUtilizationAnalyzer.xlsm。


## 启动带宽用量分析器

在命令提示符处或使用 Windows 资源管理器启动 WanLinkLogCollector.exe

**使用 WanLinkLogCollector.exe**

使用 WanLinkLogCollector.exe 有三个步骤：

1.  **记录日程表**   提供需要为其生成报告的日程表

2.  **指定文件目录**   提供文件位置信息

3.  **收集日志并启动报告查看器**  执行命令以生成报告

## 步骤 1 - 记录日程表

记录日程表允许工具用户指定下图所示的信息。

1.  **开始日期** 这是为其生成报告的日程表的开始日期，例如 2010 年 8 月 1 日。

2.  **结束日期** 这是为其生成报告的日程表的结束日期，例如 2010 年 9 月 30 日。
    
    ![带宽用量分析中的开始日期和结束日期](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "带宽用量分析中的开始日期和结束日期")  

## 步骤 2 - 指定文件目录

用户可指定以下所示的文件目录。

  - **服务器日志文件位置** 存储带宽策略服务器日志的文件夹位置。这通常位于 \<文件服务器\>\\\<FE 选择\>\\AppServerFiles\\PDP 中。

  - **临时文件存储位置** 生成报告时存储中间文件的临时文件位置。

![带宽用量分析中的文件目录](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "带宽用量分析中的文件目录")

> [!NOTE]  
> 确保向工具用户提供对服务器日志和临时文件存储文件夹足够的文件访问权限。


## 步骤 3 - 收集日志并启动报告查看器

要收集日志并启动报告查看器，请单击“**执行**”如下所示。此步骤收集所需的数据。

![收集带宽用量分析中的数据](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "收集带宽用量分析中的数据")

当输入验证成功时，将显示下面所示的消息。

![带宽实用程序中的日志收集通知。](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "带宽实用程序中的日志收集通知。")

单击“确定”。BandwidthUtilizationAnalyzer.xlsm 自动启动。按照消息框中的说明进行操作。有关详细信息，请参阅下一节中的“**使用 BandwidthUtilizationAnalyzer.xlsm**”。


**使用 BandwidthUtilizationAnalyzer.xlsm**

1.  当 BandwidthUtilizationAnalyzer.xlsm 自动启动时，单击“刷新”，如下所示。
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  当文件夹打开时，请从消息框指定的位置中选择 consolidated.csv，如下所示。它也将位置显示为 **C:\\Temp**。
    
    ![在 BandwidthUtilizationAnalyzer 中打开一个文件夹。](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "在 BandwidthUtilizationAnalyzer 中打开一个文件夹。")

3.  单击“导入”。

4.  将自动生成绘图。当在后台工作的指针消失时，它便可用。
    
    ![在报告视图中应用筛选器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在报告视图中应用筛选器。")

## 对报告视图应用筛选器

下面介绍了可对如下所示的报告视图应用的筛选器：

![在报告视图中应用筛选器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在报告视图中应用筛选器。")

1.  **名称** 按 WAN 链接进行筛选（筛选器位于图形右侧）。前缀表示以下链接类型，请查看垂直（蓝色）框：
    
      - **S Site** 从网络站点到网络区域的 WAN 链接
    
      - **IS Inter-Site** 两个网络站点之间的 WAN 链接
    
      - **R Inter-Region** 两个网络区域之间的 WAN 链接

2.  **超出限制** 按带宽用量超过带宽容量的 WAN 链接进行筛选

3.  **严重级别** 按带宽用量达到 90% 或超过带宽容量的 WAN 链接进行筛选

4.  **利用不足** 按带宽用量少于带宽容量的 25% 的 WAN 链接进行筛选

5.  **链接类型** 按以下 WAN 链接类型进行筛选：
    
      - **网络站点**类型
    
      - **站点间**类型
    
      - **区域间链接**类型

6.  **区域** 按网络区域进行筛选

下图显示了上述筛选器。

按“名称”进行筛选。选择需要在图形中显示的链接的列表。

![在 BandwidthUtilizationAnalyzer 中按名称筛选。](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "在 BandwidthUtilizationAnalyzer 中按名称筛选。")

按“超出限制”进行筛选。选择“True”可强制实施筛选器。

![按“超出限制”进行筛选。](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "按“超出限制”进行筛选。")

按“严重级别”进行筛选。选择“True”可强制实施筛选器。

![按“严重级别”进行筛选。](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "按“严重级别”进行筛选。")

按“利用不足”进行筛选。选择“True”可强制实施筛选器。

![按“利用不足”进行筛选。](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "按“利用不足”进行筛选。")

按“链接类型”进行筛选。选择需要显示的类型。

![按“链接类型”进行筛选。](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "按“链接类型”进行筛选。")

按“区域”进行筛选。选择需要显示其链接的区域列表。

![按“区域”进行筛选。](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "按“区域”进行筛选。")

## 要求

  - .NET Framework 3.5

  - Microsoft Excel 2010 或 Excel 2007

## 摘要

带宽用量分析器用于将网络上 UC 流量的音频带宽用量绘成图形。此工具也可用于报告网络上的视频带宽用量。

## 呼叫寄存时间记录器

呼叫寄存时间记录器是一个命令行应用程序，允许轻松地访问呼叫寄存轨道数据库。

## 说明

呼叫寄存时间记录器工具可跟踪当前寄存的呼叫。它也收集有关轨道和呼叫寄存服务器 (CPS) 使用的统计信息。此命令行提供从本地或远程连接的计算机对 CPS 轨道 SQL Server 数据库进行读写访问的权限。

所有选项相互排斥。命令行语法如下所示：

  - **–o** 参数 - 列出为此池配置的所有轨道范围。

  - **–n** 参数 - 列出此池中当前使用的所有轨道。显示的信息如下所示：
    
      - 呼叫被寄存者和寄存者的 SIP 统一资源标识符 (URI)。
    
      - 在其中寄存呼叫的 CPS 的主机名称。
    
      - 寄存呼叫时的时间戳。

  - **–f** 参数 - 列出池中当前可用的轨道数。

  - **–r \<n\>** 参数 - 列出 \<n\> 个最近寄存的呼叫。显示的信息如下所示：
    
      - 呼叫被寄存者 SIP URI。
    
      - 呼叫寄存者 SIP URI。
    
      - 在其中寄存呼叫的 CPS 的主机名称。
    
      - 取回或丢弃呼叫时的时间戳。

  - **-t\<n\>** 参数 - 测试在数据库中保留某个轨道，表明分配的轨道号码的随机性。

## 输出

根据在命令提示符处指定的输入参数，呼叫寄存时间记录器显示以下输出：

  - 为此池配置的所有轨道范围

  - 当前寄存的呼叫

  - 可用轨道数

  - 最近寄存的呼叫

  - 保留用于测试统一和随机轨道值的轨道

## 用途

该 CPS 工具旨在提供对 CPS 数据库的命令行访问。管理员可以查看 CPS 使用并确定分配给池的轨道的号码。

## 要求

如果此工具在运行 CPS 的相同计算机上运行，则没有要求。如果此工具在远程计算机上运行，Lync Server 2013 使用的 SQL Server 数据库必须配置为允许远程访问。必须为呼叫寄存时间记录器配置 SQL Server 数据库连接字符串才能连接到 SQL Server。此 SQL Server 数据库连接字符串在配置文件 **parkometer.exe.config** 中进行定义。它必须放在 parkometer.exe 所在的相同目录中。以下 XML 文件是一个 parkometer.exe.config 示例。必须配置的参数包括用户名（例如 mydomain\\Administrator）、密码（例如 mypassword）和主机名称（例如 myserver）。

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

## 示例

部署的轨道范围：–o 参数列出为此池配置的所有轨道范围，如下所示

![呼叫寄存时间记录器中的轨道范围。](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "呼叫寄存时间记录器中的轨道范围。")

当前寄存的呼叫：–n 参数列出当前在此池上使用的所有轨道，如下所示

![呼叫寄存时间记录器中当前寄存的呼叫。](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "呼叫寄存时间记录器中当前寄存的呼叫。")

可用轨道数：–f 参数列出池中当前可用的轨道数，如下所示

![呼叫寄存时间记录器中的可用轨道。](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "呼叫寄存时间记录器中的可用轨道。")

最近寄存的呼叫：–r \<n\> 参数列出 \<n\> 个最近寄存的呼叫，如下所示

![呼叫寄存时间记录器中最近寄存的呼叫。](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "呼叫寄存时间记录器中最近寄存的呼叫。")

测试轨道保留：–t \<n\> 测试在数据库中保留某个轨道，如下所示

![测试呼叫寄存时间记录器中的轨道保留。](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "测试呼叫寄存时间记录器中的轨道保留。")

## 摘要

呼叫寄存时间记录器是一个命令行工具，可提供有关呼叫寄存服务器的详细信息。

## CleanupStorageServiceData

CleanupStorageServiceData 资源工具包工具允许从 Lync Server 存储服务 (LYSS) 所使用的数据库中删除孤立的数据。存储服务的一个功能是缓冲 Lync Server 与各种后端数据存储终结点之间的通信，例如 SQL Server 与 Exchange 之间。

## 说明

为实现高可用性，LYSS 临时在池中的多台后端服务器上保存数据副本，一旦数据传递到最终长期存储位置就会删除该数据。正常操作过程中，如果服务器可能崩溃或遇到处理问题，并且一些数据无法正确清理，则可能会发生异常清理。此数据是无害的，但是它占用有限的处理资源。将自动执行正常的必需数据维护，但是当无法执行自动删除操作时，此工具允许安全地识别并删除此类孤立的数据。如果生成了运行状况监视 System Center Operations Manager (SCOM) 警报，要求管理员从池的本地 LYSS 数据库中删除不需要的数据，那么需要使用此工具。前端的事件日志中有对应的事件会触发该警报。事件详细信息将包含有关前端上包括的孤立数据量的信息，并在该数据超过预先确定的特定阈值时生成警报

## 要求

安装 Lync Server 2013 资源工具包工具。该工具在安装了 Lync Server 和 Lync Server 2013 命令行管理程序 并且已加入域的计算机上运行。该工具使用命令行管理程序中的 cmdlet 识别池中的所有前端服务器。其次，必须从池中安装了 **RtcLocal** 数据库的计算机运行该工具。CleanupStorageServiceData 工具使用此数据库来获取与 Lync Server 路由服务通信所需的连接详细信息。最后，调用该工具的帐户或凭据必须对它们希望在其中写入输出日志的文件共享具有读取/写入权限。此外，此工具依赖于处于稳定状态的池。实质上，这意味着每个前端服务器应正常运行，SQL Server LYNCLOCAL 实例和 LYSS 数据库必须能够连接，而每个路由组必须具有完整的一组前端服务器（1 个主前端服务器，2 个辅助前端服务器）。

## 示例

C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe

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

## DBAnalyze

## 说明

DBAnalyze 是一个命令行工具，可帮助管理员收集有关 Lync Server 2013 数据库的分析报告。DBAnalyze 具有以下模式：诊断、用户数据、会议、MCU 和磁盘碎片：

  - **诊断模式**   创建报告，信息涵盖表（记录数、碎片、数据大小和索引大小）、数据和日志文件大小、上次备份时间、运行 Microsoft Office Communications Server 的服务器之间的联系人分布、平均权限数、联系人、容器、订阅、出版物、每个用户的终结点、任何未正确驻留的用户、无法路由的用户、每个用户组织的平均会议数、计划内会议、活动会议和数据库版本。
    
    > [!NOTE]
    > 运行诊断模式可能会影响服务器性能。


  - **用户数据模式**  为指定用户或者其联系人和权限列表中具有该用户的用户报告联系人、容器、订阅、出版物、权限和联系人组数据。此模式也报告用户组织或受邀加入的会议的摘要数据。

  - **会议模式**   为特定会议报告详细数据，包括会议的所有日程安排时间、被邀请者列表、会议允许的媒体类型列表、活动的 MCU（多点控制单元）、活动参与者列表以及每个参与者的信号传输状态。

  - **解码会议 ID**  解码由 **/pstnid** 开关指定的公用电话交换网 (PSTN) 会议 ID，但不连接到后端获取详细信息。

  - **解析会议**   解码由 **/pstnid** 开关指定的 PSTN 会议 ID，并显示有关会议的信息（通过 ID 表示）。

  - **MCU 模式**  报告池中每个 MCU 的 ID、媒体类型、URL、检测信号状态、会议负载和参与者负载。

  - **磁盘碎片模式**  显示所有磁盘的碎片状态。

此工具可用于诊断各种问题或帮助管理员进行容量规划。例如，如果驻留在服务器 A 上的大多数用户选择驻留在服务器 B 上的用户作为其联系人，管理员可以将服务器 A 的用户移动到服务器 B，从而减少跨服务器流量。

## Output

此工具输出有关 Lync Server 2013 数据库的预定义报告。**路径：**%ProgramFiles%\\Microsoft Lync Server 2013\\Reskit

## 意义

要安装 Dbanalyze.exe，请将其复制到本地文件夹，然后运行该工具。要使用该工具，请从命令行运行以下命令：`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 命令行选项的描述如下所示。

![适用于 Dbanalyze.exe 的命令行选项。](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "适用于 Dbanalyze.exe 的命令行选项。")

## 要求

**计算机** DBAnalyze 只能从安装了 Lync Server 2013 并且加入域的计算机运行。

**网络** 计算机应能够连接到后端数据库。

**软件** 运行 DBAnalyze 之前必须安装 Lync Server 2013 软件组件。

**用户** 下表显示了具有访问 Lync Server 2013 数据库所需权限的管理员。

![适用于 Dbanalyze.exe 的权限标签。](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "适用于 Dbanalyze.exe 的权限标签。")

> [!NOTE]  
> <strong>/report:disk</strong> 模式要求使用本地管理员帐户。


## 示例

以下是有效的 Dbanalyze.exe 命令示例：

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

## 摘要

DBAnalyzer 使管理员能够快速且轻松地分析 Lync Server 2013 数据库。

## ImportStorageServiceData

ImportStorageServiceData 资源工具包工具允许将已从存储服务 (LYSS) 刷出的队列和终结点数据重新导入到存储服务中。

## 说明

可能已基于队列项目状态或数据库大小自动（定期）从存储服务刷出数据。发生这种情形是因为手动调用了池故障转移 cmdlet 或 StorageServiceFullFlush cmdlet（由池故障转移 cmdlet 调用）。请注意，理想情况下，如果前端上的任何存储 (LYSS) 数据库大小高于正常水平则不应重新导入数据，因为这样做可能会导致导出更多数据。而且，应首先解决引发错误从而导致存储服务队列增长的任何问题（例如 Exchange 终结点错误、网络问题或其他问题）。

**方案 1：** 池故障转移期间，每个前端的文件可能已从存储服务刷出。故障转移完成之后，应运行该工具以重新导入数据。

**方案 2：** 数据每天自动刷新或者为响应超过特定大小阈值（例如 60%、80%、90%、已满）的存储服务数据库而自动刷新。此自动刷新的数据应由管理员定期重新导入。在上述情形下，如果未部署监视 SCOM 包，那么存在与从存储服务刷新的数据相关的 Lync Server 存储服务的事件。事件 ID 为 32075（已启动完全刷新操作）、32076（已完成完全刷新）、32082（已启动维护级别刷新）、32089（由于数据库填满而刷新）。请注意，这些事件 ID 对应于 RTM 版本。当管理员看到这些事件时，意味着已刷出一些文件。应使用此工具定期导入此数据，例如每周一次。

对于联机服务版本，如果部署了适用于 Lync Server 的运行状况监视 SCOM 包，则可能会生成一些新警报，要求管理员将刷新的数据重新导入到存储服务中。前端服务器的事件日志中有对应的事件会触发该警报。事件将提供刷新的数据文件所在的父路径的描述以及符合警报条件的文件数。警报条件是特定父路径下存在保留时间至少 Y 天的一个或多个文件（其中，X 和 Y 在 StorageService 中预设，但是可通过更改 APPCONFIG 文件进行覆盖）。下面介绍了可触发运行状况警报的两个事件示例及其父路径的区别。一个可能性是在 Web 服务文件共享下，另一个可能性是在每个前端的 Application Data 目录中。（例如 c:\\ProgramData\\Microsoft\\Lync Server\\StorageService。）然后，管理员将运行此资源工具包工具。

此工具将增加运行该工具的前端以及其他前端（如果执行该工具的前端不拥有数据）的 CPU 和 IO 负载。建议在前端的 CPU 和 IO 负载不太繁重时运行此工具，例如非高峰时间。其次，此工具 2 到 3 分钟可导入一个数据文件。估计该工具运行的时间长短时必须牢记这一点。默认情况下，该工具生成的详细日志文件显示在文件存储上。如果未报告错误，请将其删除，因为日志文件可能达 10 MB 或更大。

![示例存储服务器事件日志事件。](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "示例存储服务器事件日志事件。")

## 要求

安装 Lync Server 2013 资源工具包工具。该工具在安装了 Lync Server 和 Lync Server 命令行管理程序 并且已加入域的计算机上运行。该工具使用命令行管理程序中的 cmdlet 识别池中的所有前端服务器。其次，必须从池中安装了 **RtcLocal** 数据库的计算机运行该工具。该工具使用此数据库检索池的 WEBSERVICE 文件共享的位置。此外，在使用该工具之前，必须首先在每个前端服务器上以及从中执行该工具的计算机上使用 **Enable-PSRemoting** 启用 Windows PowerShell Remoting。否则，从此工具运行远程 Windows PowerShell 命令将会失败。完成后，可在所有前端服务器上禁用 Windows PowerShell Remoting。最后，调用该工具的帐户或凭据必须对池中执行此工具的 webservice 文件共享具有读/写权限。否则，该工具将失败并出现 IO 权限错误。

> [!NOTE]  
> Windows Server 2012 上默认启用 Windows PowerShell Remoting，Windows Server 2008 操作系统 上并不默认启用。


## 示例

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

## LCSSync

LCSSync 工具可帮助在多林环境中部署 Lync Server 2013 通信软件。此工具用于将不同用户林中的用户和组作为 Active Directory 域服务联系人对象同步到安装了 Lync Server 2013 的中央林。

## 说明

LCSSync 使用中央林中已同步的 Active Directory 域服务联系人对象为用户启用 Lync Server。要提供单一登录，主用户帐户必须映射到 Lync Server 2013 的中央林中的 Active Directory 域服务联系人对象。此工具可帮助执行该映射。此工具提供用于在 Microsoft Identity Integration Server 中创建管理代理的模板。

## 摘要

LCSSync 工具可帮助在多林环境中部署 Lync Server。

## LookupUserConsole

LookupUserConsole 工具显示有关特定用户的内部 Lync Server 路由信息。Microsoft 支持人员可使用此信息帮助诊断部署和路由问题。

## 说明

执行 LookupUserConsole.exe 将打开一个命令提示符，该命令提示符将接受 SIP 地址并尝试显示相关的内部 Lync Server 路由信息。键入 **exit** 可退出 LookupUserConsole 工具。

## 要求

该工具在安装了 Lync Server 并且已加入域的计算机上运行

## 示例

C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe

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

## MsTurnPing

MSTurnPing 工具允许 Microsoft Lync Server 2013 通信软件的管理员检查拓扑中运行音频/视频边缘和音频/视频身份验证服务的服务器以及运行带宽策略服务的服务器的状态。

## 说明

MSTurnPing 工具允许 Lync Server 2013 通信软件的管理员检查拓扑中运行音频/视频边缘和音频/视频身份验证服务的服务器以及运行带宽策略服务的服务器的状态。

该工具允许管理员执行以下测试：

1.  A/V 边缘服务器测试：该工具通过执行以下操作来对拓扑中的所有 A/V 边缘服务器执行测试：
    
      - 验证 Lync Server 音频/视频身份验证服务是否已启动并且可颁发正确的凭据。
    
      - 验证 Lync Server 音频/视频边缘服务是否已启动并且可成功地在外部边缘上分配资源。

2.  带宽策略服务测试：该工具通过执行以下操作来对运行带宽策略服务的所有服务器执行测试：
    
      - 验证 Lync Server 带宽策略服务（身份验证）是否已启动并且可颁发正确的凭据。
    
      - 验证 Lync Server 带宽策略服务（核心）是否已启动并且可成功地执行带宽检查。

必须从属于拓扑的一部分并且安装了本地存储的计算机运行此工具。

## 输出

该工具输出每个操作的结果。

  - 如果执行了 **AudioVideoEdgeServer** 测试，则工具输出为以下内容：
    
      - 拓扑中提供 Lync Server 音频/视频身份验证服务的计算机的测试结果
    
      - 拓扑中提供 Lync Server 音频/视频边缘服务的计算机的测试结果

  - 如果执行了 **BandwidthPolicyServer** 测试，则工具输出为以下内容：
    
      - 拓扑中提供 Lync Server 带宽策略服务（身份验证）的计算机的测试结果
    
      - 拓扑中提供 Lync Server 带宽策略服务（核心）的计算机的测试结果

## 要求

  - 必须从拓扑中具有本地存储的计算机运行此工具。

  - 该工具必须以对本地存储具有访问权限的管理员身份运行。

## 示例

下面是工具输入示例。

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

## 摘要

此工具对于希望检查运行音频/视频和带宽策略服务的服务器的状态的 Lync Server 2013 管理员而言是一项宝贵资源。

## 网络配置查看器

Microsoft Lync Server 2013 通信软件的管理员可以使用网络配置查看器查看企业的呼叫允许控制 (CAC) 网络拓扑，该拓扑设置为基于指定的带宽容量允许实时通信会话（例如语音或视频呼叫）。Lync Server 2013 管理员定义 CAC 策略，随 Lync Server 2013 一起安装的带宽策略服务将强制实施这些策略。

## 说明

网络配置查看器 (NetworkConfigurationViewer.exe) 允许管理员执行以下任务：

  - 以图形格式从 Lync Server 2013 部署中加载和查看 CAC 网络拓扑。

  - 以图形格式从带宽策略服务器日志文件中加载并查看 CAC 网络拓扑。

  - 以 XML 格式在磁盘上保存和存储 CAC 网络拓扑。

  - 以 JPG 或 BMP 格式在磁盘上保存和存储 CAC 网络拓扑图。

  - 查看 CAC 网络拓扑配置数据。

  - 以树视图查看 CAC 网络拓扑。

  - 定义 CAC 网络拓扑链接（例如，站点至区域、区域至区域和站点至站点链接）的自定义连接器。

  - 查看 CAC 网络拓扑站点信息、区域信息以及设置的带宽和网络链接。

## 用途

在图形界面中查看企业 CAC 网络拓扑链接。

## 示例

**以图形格式从 Lync Server 2013 中部署加载和查看 CAC 网络拓扑：** Lync Server 2013 管理员可以使用下图所示的“下载网络配置”选项在任何 Lync Server 2013 计算机上加载并查看 CAC 网络拓扑配置。当部署在未与 Lync 配置存储建立连接的计算机上时，该工具将无法下载或查看此类配置。

![下载网络配置。](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "下载网络配置。")

**以图形格式从带宽策略服务器日志文件中加载并查看 CAC 网络拓扑：** Lync Server 2013 带宽策略服务器将 CAC 网络拓扑作为日志记录机制的一部分保存在 Lync Server 2013 文件共享位置之下。Lync Server 管理员可以使用如下所示的“打开网络配置”选项以图形格式查看此类文件。

![打开带宽策略服务器日志文件。](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "打开带宽策略服务器日志文件。")

以 XML 格式在磁盘上保存和存储 CAC 网络拓扑：Lync Server 2013 管理员可以使用如下所示的“保存网络配置的副本”选项以 XML 格式保存 CAC 网络拓扑配置文件。然后，可脱机使用保存的配置文件以便查看图形。

![将网络配置另存为 XML 文件。](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "将网络配置另存为 XML 文件。")

以 JPG 或 BMP 格式在磁盘上保存和存储 CAC 网络拓扑图：Lync Server 2013 管理员可以使用如下所示的“将网络配置图另存为图片”选项以图形格式（JPG 和 BMP 文件格式）保存 CAC 网络拓扑配置。

![将网络配置另存为图片。](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "将网络配置另存为图片。")

**查看 CAC 网络拓扑配置数据：** Lync Server 2013 管理员可以使用如下所示的“查看网络配置数据”选项以文本格式查看相关的网络配置数据（如网络区域、网络站点、带宽配置文件以及站点子网 IP 地址。

![查看网络配置数据。](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "查看网络配置数据。")

**以树视图查看 CAC 网络拓扑：** Lync Server 2013 管理员可以使用工具窗口左侧的控制面板以图形树视图查看相关的网络配置数据，如下所示。

![以树视图查看网络配置数据。](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "以树视图查看网络配置数据。")

**定义 CAC 网络拓扑链接（例如，站点至区域、区域至区域和站点至站点链接）的自定义连接器：** Lync Server 2013 管理员可以使用如下所示的“设置”选项定义 CAC 网络配置 WAN 链接的自定义图形连接器。这样做可帮助区分网络配置中设置的各种类型的网络链接。

![b20bea67-c8e1-453e-b1dd-e2aa17b62566](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "b20bea67-c8e1-453e-b1dd-e2aa17b62566")

**查看 CAC 网络拓扑站点信息、区域信息以及设置的带宽和网络链接：** Lync Server 2013 管理员可以使用如下所示的选项查看相关的 CAC 网络区域信息、站点信息以及 CAC 带宽设置信息。（例如，单击网络区域或网络站点对象中的“信息”。）

![定义您的网络的自定义连接器。](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "定义您的网络的自定义连接器。")

## 摘要

此工具对于希望以图形格式查看其部署的 CAC 网络拓扑的 Lync Server 2013 管理员而言是一项宝贵资源。

## 响应组代理实时

响应组应用程序使代理能够使用其内置的 Web 服务访问有用的实时信息。遗憾的是，在应用程序外部无法以图形形式查看此数据。“响应组代理实时”资源工具包工具提供一种简单的图形方式来访问此信息，并采用实时的 Microsoft Lync 2013 通信软件信息（如其他代理的状态）进行了增强，从而解决此问题。

## 说明

“响应组代理实时”是一种 Windows 应用程序，向响应组代理提供登录和注销功能以及一些实时信息（例如，组成员身份和当前呼叫号码）。它是代理组页面（可从 Lync 2013 访问）的增强版本。

## 用途

响应组应用程序将传入呼叫排成队列，然后将它们路由到代理组。 为对服务于哪些呼叫做出明智的决策，代理可以访问有关其代理组的实时信息，例如，其他哪些代理组可用以及每个队列中有多少呼叫正在等候。 此信息最初只能通过响应组服务进行访问，现在由“响应组代理实时”以直观方式提供。

## 功能

“响应组代理实时”工具是基于响应组服务和 Microsoft Lync 2013 SDK 进行构建的。它向响应组代理提供可从响应组服务访问的信息和功能（例如，组成员身份、其他代理的状态和正在等待的呼叫数）。

下图说明了“响应组代理实时”的主要界面。

![“响应组代理实时”工具。](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "“响应组代理实时”工具。")

“响应组代理实时”有三个主要功能适用于代理：

  - **登录/注销：** 与代理组页面（可从 Lync 2013 访问）不同，“响应组代理实时”仅允许代理一次性登录或注销所有代理组。此应用程序为代理提供三种快速登录或注销的方式：
    
      - 单击应用程序中的登录/注销（绿色和红色）按钮。
    
      - 右键单击系统任务栏图标，然后选择登录或注销。
    
      - 使用可配置的键盘快捷方式。

  - **组成员身份：** 当选中一个代理组时，“响应组代理实时”将在右侧窗格中显示此组的代理列表。如果 Lync 2013 正在此应用程序所在的相同计算机上运行，“响应组代理实时”中将显示状态信息和联系人卡片。代理可以直接从这里发送 IM 或呼叫其他代理。

  - **实时统计信息：** “响应组代理实时”提供所有代理组的实时统计信息。更新频率为一分钟。当响应组应答呼叫时，将在组名称旁边添加一个可视指示器并显示当前排队等候的呼叫数。将指针暂停在某个组上方将显示最长等待时间。

## 要求

“响应组代理实时”需要 .NET Framework 4.0。此外，为利用状态和联系人卡片功能，必须在本地安装（并且运行）Lync 2013。

## 配置

可以使用应用程序中的“选项”对话框根据个人偏好自定义“响应组代理实时”。此外，管理员可以通过直接编辑 RGAgentLive.exe.config 文件的 defaultHostAddress 属性来定义默认主机地址。

下图展示了代理可用于配置主机地址和快捷方式的“选项”对话框。可通过单击主界面右上方的“选项”按钮来访问此对话框。

![“响应组代理实时”的“选项”对话框。](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "“响应组代理实时”的“选项”对话框。")

以下三个不同设置可以在“响应组代理实时”配置中自定义：

  - 主机地址：这通常是指属于代理主池的 Web 池 FQDN。确切的响应组服务地址将在后台自动从此信息中检索（在主机后面附加正确的路径）。

  - 快捷方式：可以自定义登录/注销的确切快捷方式。唯一限制是两个快捷方式都必须包含“Windows 徽标”键（以及至少另一个键）。

  - 与 Windows 一起启动：该应用程序可配置为自动与 Windows 一起启动。

## 示例

下图说明了如何通过右键单击右窗格中的联系人来呼叫其他代理或向其他代理发送 IM。

![呼叫或发送即时消息。](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "呼叫或发送即时消息。")

下图说明了“响应组代理实时”如何显示队列中的当前呼叫数以及所有这些传入呼叫的最长等待时间。

![查看队列信息。](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "查看队列信息。")

## 摘要

快速登录和注销、组成员身份和基本的实时统计信息是有趣的响应组代理功能，只能从响应组服务访问并在应用程序外部使用。使用“响应组代理实时”资源工具包工具，Lync 管理员可以向其代理提供一个 Windows 应用程序，使他们能够以更快的图形方式执行任务。

## SEFAUtil

SEFAUtil（辅助扩展功能激活）是一个命令行工具，使 Microsoft Lync Server 2013 通信软件管理员和技术支持代理能够代表 Lync Server 2013 用户配置代理人响铃、呼叫转接、同时响铃、团队呼叫设置和组内呼叫应答。该工具还允许管理员查询为特定用户发布的呼叫路由设置。SEFAUtil 工具允许管理员代表用户启用/禁用/修改呼叫转接或同时响铃。管理员可以指定目标（以 SIP URI 形式）或使用用户发布的目标。此工具还允许管理员代表用户添加或删除代理人或团队呼叫组成员。此工具是基于 Microsoft 统一通信托管 API (UCMA) 3.0 进行构建的，要求管理员为 SEFAUtil 在中央管理存储中创建一个受信任的应用程序。

SEFAUtil（辅助扩展功能激活）使 Lync Server 2013 管理员和技术支持代理能够代表 Lync Server 2013 用户配置代理人响铃、呼叫转接、同时响铃、团队呼叫设置和组内呼叫应答。 此工具还允许管理员查询为特定用户发布的呼叫路由设置。

## 说明

当前 SEFAUtil 版本仅仅是一个命令行工具；没有支持的图形用户界面。此工具是基于 Microsoft 统一通信托管 API (UCMA) 3.0 进行构建的。此工具中的功能允许管理员和技术支持代理执行以下操作：

  - 查看用户的所有呼叫路由设置（包括呼叫转接、委派、同时响铃、团队呼叫和组内呼叫应答）

  - 启用/禁用/修改呼叫转接设置（包括目标和无应答计时器）

  - 启用/禁用/修改呼叫转接即时配置

  - 启用/禁用/修改委派设置

  - 启用/禁用/修改团队呼叫组设置
    
    > [!NOTE]
    > Lync Server 2013 SEFAUtil 工具新增功能


  - 启用/禁用/修改同时响铃设置（包括目标）
    
    > [!NOTE]
    > Lync Server 2013 SEFAUtil 工具新增功能


  - 启用/禁用/修改组内呼叫应答设置
    
    > [!WARNING]
    > Lync Server 2013 SEFAUtil 工具新增功能


此工具存在以下限制：

  - 仅对驻留在 Lync Server 池中的用户提供支持

  - 不支持批量编辑许多用户的呼叫路由设置

## 输出

此工具的当前版本仅在命令提示符窗口中提供输出。有关详细信息，请参阅本文档后面的“示例”部分。

## 用途

以下介绍了可能使用此给工具的一些主要方案：

  - Bob 是一名行政管理人员，已迁移到 Lync Server 电话服务。他在其现有 PBX 系统上设置了委派。作为 Lync 迁移的一部分，管理员能够配置 Bob 的路由以反映其预先存在的委派配置。

  - Alice 正在出差，意识到她将收到一位客户的重要来电。然而，她住在酒店，没办法使用计算机。她致电给技术支持人员，请求他们将拨打她的工作电话号码的所有呼叫转接到其移动电话号码。技术支持人员能够代表她执行该配置。

  - 每当 Joe 工作时，拨打其工作电话号码的呼叫进入其移动语音邮件；但是，在大多数其他位置似乎一切正常。技术支持人员能够查看 Joe 的路由配置，发现 Joe 将同时响铃配置为其移动电话。技术人员询问 Joe 其办公室的移动网络覆盖，能够确定是同时响铃功能导致在网络覆盖较差时呼叫进入 Joe 的移动语音邮件。

  - Mike 是 Contoso 公司的新员工，他加入了一个新团队，该团队的所有成员都配置了团队呼叫，当启用 Microsoft Lync 时，管理员能够将其团队呼叫组设置设定为包括其所有新团队成员，此外，管理员为其团队中的每个成员将 Mike 添加为团队呼叫组成员。

  - Contoso 人力资源部门的一个客户服务做法是自第一个呼叫开始为所有呼叫者提供个性化服务。倘若部门所有成员的就坐位置距离非常近，让所有电话与团队呼叫同时响铃会给团队造成干扰。为提供最出色的服务而不干扰团队成员，Lync 管理员利用组内呼叫应答功能。管理员将所有部门成员添加到一个应答组并告知他们应答组号码。当 Samantha 不在座位上时，Joe 注意到其电话响铃，随后从自己的桌面应答呼叫。

## 要求

SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。必须在计算机上安装 UCMA 3.0。要运行该工具，必须在该池上创建新的具有 SEFAUtil 应用程序 ID 的受信任的应用程序。

**为 SEFAUtil 工具创建新的受信任的应用程序**

1.  SEFAUTil 工具只能在属于受信任应用程序池的一部分的计算机上运行。如果需要，可通过 Lync Server 命令行管理程序使用以下 cmdlet 将池添加为新的受信任的应用程序池：
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    > [!NOTE]
    > 必须安装在将用于运行 SEFAUtil 工具的任何计算机上安装 UCMA 3.0。


2.  需要在拓扑中为 SEFAUtil 工具定义受信任的应用程序。要将 SEFAUtil 定义为新的受信任的应用程序，请使用 Lync Server 命令行管理程序并执行以下 cmdlet：
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    > [!NOTE]
    > 如果需要则可以使用其他端口。


3.  需要启用拓扑更改。可通过 Lync Server 命令行管理程序执行以下 cmdlet 来启用拓扑更改：
    
        Enable-CsToplogy

4.  如果需要，请在将用于运行 SEFAUtil 工具的服务器中安装 Lync Server 2013 资源工具包工具（服务器必须属于受信任的应用程序池的一部分）。

5.  验证 SEFAUtil 是否正确运行。为此，请使用管理员特权从命令提示符处运行该工具，以在您的部署中显示用户的呼叫转接设置。默认情况下，该工具位于“…\\Program Files\\Microsoft Lync Server 2013\\Reskit”中。要显示用户的呼叫转接设置，请使用以下命令：
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    应显示用户的呼叫转接设置。

## 组内呼叫应答

组内呼叫应答需要 Lync Server 中的其他配置才能完全启用功能。在向用户分配呼叫应答组之前，请参阅组内呼叫应答产品文档，了解此功能的规划和部署步骤。

## 示例

## 显示当前呼叫处理设置

以下命令显示用户的呼叫处理。`SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

> [!NOTE]  
> 此示例使用 <strong>/server</strong> 开关指定要连接到的 Lync Server。


**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

## 设置呼叫转接/无应答目标

此示例设置呼叫转接/无应答目标和响铃延迟。在这里，不提供 /server 开关；SEFAUtil 将尝试自动发现 Lync Server。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

## 立即启用呼叫转接

此示例立即启用至其他用户的呼叫转接。

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

## 立即禁用呼叫转接

此示例立即禁用呼叫转接。

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## 将用户添加为代理人并设置代理人的同时响铃

此示例将用户添加为代理人并设置代理人的同时响铃。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

## 更改代理人的同时响铃规则

此示例将在上一示例中设置的同时响铃规则设置为延迟的响铃规则。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

## 删除代理人

此示例将删除代理人。

> [!NOTE]  
> 当删除了最后一个代理人时，代理人响铃将自动禁用。


    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## 添加代理人并设置代理人呼叫转接规则

此示例将添加代理人并设置代理人呼叫转接规则。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

## 启用同时响铃并设置目标号码

此示例将启用同时响铃并设置同时响铃目标号码。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

> [!NOTE]  
> 要更改已经启用了同时响铃的用户的同时响铃目标号码，请带 /enablesimulring 开关使用命令，否则目标号码不会更改。


**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

## 禁用同时响铃

此示例将禁用同时响铃。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## 为团队呼叫添加团队成员并将同时响铃设置为团队呼叫成员组

此示例向用户的团队呼叫组添加团队成员，并启用团队呼叫组同时响铃。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

> [!NOTE]  
> 向用户的团队呼叫组添加成员会自动将用户的同时响铃设置切换为同时拨打团队呼叫组。


**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

## 从团队呼叫组中删除成员

此示例将删除用户的团队呼叫组的团队成员。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

> [!NOTE]  
> 如果正在删除的成员是团队呼叫组的唯一成员，那么团队呼叫组同时响铃将自动禁用。


**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## 将延迟响铃设置为团队呼叫组

此示例将延迟响铃设置为团队呼叫组时间设置。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

## 启用团队呼叫

此示例为给定用户启用团队呼叫。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

> [!NOTE]  
> 如果用户的团队呼叫组没有成员，则不会启用团队呼叫。


**输出**

## 禁用团队呼叫

此示例为给定用户禁用团队呼叫。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## 启用组内呼叫应答并为用户分配应答组

此示例为用户分配应答组并启用组内呼叫应答。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**输出**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

## 禁用组内呼叫应答

此示例为给定用户禁用组内呼叫应答。

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

> [!NOTE]  
> 当为某个用户禁用组内呼叫应答时，分配给该用户的组号码不再保留。如果您随后想为该用户重新启用组内呼叫应答，必须使用 /enablegrouppickup 开关再次分配组号码。


    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

## SYSPrep.ps1

## 说明

SYSPrep.ps1 是一个 Windows PowerShell 脚本，将在 Windows Server 2008 操作系统 计算机上安装以下 Lync Server 2013 必备软件。

  - Microsoft .Net Framework 4.5

  - Microsoft SQL Server Express

  - Windows Powershell 3.0 版

  - Visual C++ 2010 可再发行软件包

  - Internet Information Server 更新

  - Windows Identity Foundation

  - Lync Server 2013 核心文件

虽然脚本名称类似于适用于 Microsoft Windows 操作系统的系统准备工具，但是实际上有所不同。此脚本仅安装适用于 Lync Server 2013 的必备软件。安装这些必备软件之后，Windows SYSPrep 工具可用于创建服务器映像。

## 要求

运行 SYSPrep.ps1 脚本之前，您必须将必备文件复制到 Windows Server 2008 操作系统 计算机上的本地文件夹（例如 **D:\\Setup**）。此文件夹也必须包含 Lync Server 2013 文件的副本，特别是 **Setup.exe**。必备文件可以从以下位置下载：


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


## 参数

**–SetupFolder** 形式参数使用必备文件的目录位置作为实际参数

## 示例

要运行 SYSPrep.ps1 脚本并安装 Lync Server 2013 必备软件，请从提升的命令提示符处运行以下命令：

    ./SysPrep.PS1 -SetupFolder D:\Setup

## 未分配号码通知迁移

未分配号码通知迁移工具使 Lync 管理员能够将由通知应用程序提供服务的未分配号码配置从源 Lync Server 或池移动到目标 Lync Server 或池。

## 说明

未分配号码通知迁移工具是一个 Windows PowerShell 脚本，可将由源服务器或池的通知应用程序提供服务的未分配号码配置移动到其他服务器或池。

执行时，未分配号码通知迁移脚本将执行以下操作：

1.  将源服务器或池中承载的通知应用程序的未分配号码通知使用的所有音频文件移动到目标服务器或池的文件存储。
    
    > [!NOTE]
    > 音频文件一旦复制到目标池，将从源池中删除。


2.  将为源服务器或池中承载的通知应用程序配置的所有未分配号码通知移动到目标服务器或池。

3.  将由源服务器或池中承载的通知应用程序提供服务的所有未分配号码范围重新分配给目标服务器或池。

成功运行该脚本之后，由源服务器或池中承载的通知应用程序提供服务的所有未分配号码范围现在由目标服务器或池提供服务，采用相同配置。

## 输出

**Move-CsAnnouncementConfiguration** 脚本在执行脚本的 Lync 命令行管理程序窗口中指明迁移操作成功还是失败。

如果操作执行过程因错误而中断，则已成功移动到目标的额未分配号码范围将以可操作形式保留在目标中，其余待迁移的未分配号码范围将以可操作形式保留在源中。要完全迁移其余配置，请在解决错误之后重新运行脚本。

## 用途

未分配号码通知迁移脚本可以在以下三种方案中使用：

  - **将配置设置迁移到新版本的 Lync Server：** Contoso 正在迁移到 Lync Server 2013，作为迁移过程的一部分，Lync Server 管理员想要将由通知应用程序提供服务的未分配号码通知从 Lync Server 2010 部署移动到新的 Lync Server 2013 部署。为移动配置设置，Lync Server 管理员使用未分配号码通知迁移工具。

  - **将部署从 Lync Server 2013 回滚到 Lync Server 2010：** 由于意外因素，Contoso 必须将迁移回滚到新的 Lync Server 2013 部署。为最大程度地减少服务中断，Lync Server 管理员使用未分配号码通知迁移工具将配置从 Lync Server 2013 部署回滚到 Lync Server 2010 部署。

  - **在 Lync 部署之间迁移数据：** Contoso 正在将一个池中的所有服务器替换为较新的服务器。其战略是部署新的 Lync Server 2013 池，将所有数据从旧池移动到新池，然后废弃旧池。部署新池之后，将使用未分配号码通知迁移工具将配置从旧池迁移到新池。

## 要求

下面列出了成功运行该工具所需的主要要求：

1.  该脚本只能从安装了 Lync Server 2013 命令行管理程序 的计算机运行。

2.  必须在源和目标 Lync Server 或池中成功地部署通知应用程序。

## Move-CsAnnouncementConfiguration 脚本

Move-CsAnnouncementConfiguration 脚本需要下表所述的两个参数。

![Move-CsAnnouncementConfiguration 参数。](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration 参数。")

## 示例

## 将未分配号码通知配置从 Lync Server 2010 池移动到 Lync Server 2013 池

此示例将未分配号码通知从源池 (Lync Server 2010) 移动到目标池 (Lync Server 2013)。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

## 将未分配号码通知配置从 Lync Server 2013 池移动到 Lync Server 2010 池

此示例将未分配号码通知从源池 (Lync Server 2013) 移动到目标池 (Lync Server 2010)。

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

## Web 会议数据

Web 会议数据工具允许 Lync Server 2013 通信软件的管理员更好地控制与组织者的 Web 会议相关联的数据。方案包括能够基于时间戳条件删除特定用户的会议数据。

## 说明

此工具允许管理员执行以下操作：

1.  查找与单个用户相关联的所有 Web 会议数据。

2.  删除与单个用户相关联的所有 Web 会议数据。

3.  删除与单个用户相关联且早于特定日期的所有 Web 会议数据。

4.  当单个用户从一个池移动到另一个池时，移动与该用户相关联的所有 Web 会议数据。

> [!NOTE]  
> Lync Server 2010 资源工具包工具 支持当单个用户从一个池移动到另一个池时移动与该用户相关联的所有 Web 会议数据。该功能现在已从此工具中弃用，而采用了 <strong>MoveConferenceData</strong> 参数。有关此参数的详细信息，请参阅 <a href="https://technet.microsoft.com/zh-cn/library/gg398528(v=ocs.15)">Move-CsUser</a> cmdlet。


该工具仅删除处于非活动状态的会议的会议数据。活动会议（或正在进行会话的会议）无法删除。

必须从与目标用户相同的池中的计算机运行此工具。由此工具管理其会议内容数据的用户必须驻留在相同用户池中。

## 输出

此工具输出每个操作的结果：

  - 如果执行查询，该工具将输出将该用户作为组织者的所有非活动会议数据文件夹的列表。

  - 如果执行删除，该工具将输出其数据将被删除的所有会议数据文件夹的列表。

## 要求

该工具需要在组织者当前驻留的相同池中运行。

该工具必须使用对内容文件存储具有访问权限的管理员特权运行。

## 示例

下表介绍了参数，其中包含示例中使用的一些参数。

![Web 会议数据工具参数。](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web 会议数据工具参数。")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

上述示例介绍了查询命令如何工作。此类命令的输出是受此工具影响的所有会议内容文件夹的列表。

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

上述示例是一个 delete 命令示例。delete 命令将删除此用户的所有非活动会议文件夹。

## 摘要

此工具对于需要更精确控制会议数据的管理员而言是一项宝贵资源。
