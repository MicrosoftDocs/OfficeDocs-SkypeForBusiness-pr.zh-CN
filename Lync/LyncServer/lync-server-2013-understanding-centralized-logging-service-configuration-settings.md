---
title: 了解日志记录服务配置设置
TOCTitle: 了解日志记录服务配置设置
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49888380
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 了解日志记录服务配置设置

 

_**上一次修改主题：** 2015-03-09_

集中日志记录服务被配置为定义日志记录服务的以下设置：收集的对象、收集的方式、收集的位置以及日志设置是怎样的。您将为全局（即整个部署）或站点（即部署中的命名站点）定义这些设置。您定义的任何日志记录都将使用适用于某个标识（对启动、停止、刷新和搜索日志的命令使用）的设置。

## 显示当前集中日志记录服务配置

启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

在命令行提示符处键入以下内容：

    Get-CsClsConfiguration

> [!TIP]
> 您可以缩小或扩大返回的配置设置的作用域，方法是定义 <code>-Identity</code> 和一个作用域（如“Site:Redmond”）以仅返回 Redmond 站点的 CsClsConfiguration。如果要获得有关给定部分的配置的详细信息，则可以在输出和其他 Windows PowerShell cmdlet 之间建立管道。例如，若要获得有关站点“Redmond”的配置中定义的方案的详细信息，请键入：<code>Get-CsClsConfiguration -Identity &quot;site:Redmond&quot; | Select-Object -ExpandPropery Scenarios</code>


![来自 Get-CsClsConfiguration 的示例输出。](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "来自 Get-CsClsConfiguration 的示例输出。")

该 cmdlet 生成的结果显示了集中日志记录服务的当前配置。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>配置设置</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>标识此配置的作用域和名称。只有一个“全局”配置，且每个站点只有一个配置。</p></td>
</tr>
<tr class="even">
<td><p><strong>Scenarios</strong></p></td>
<td><p>为此配置定义的所有方案的列表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SearchTerms</strong></p></td>
<td><p>为此配置定义的搜索词。Office 365，非本地部署。</p></td>
</tr>
<tr class="even">
<td><p><strong>SecurityGroups</strong></p></td>
<td><p>定义的安全组，用于控制能查看计算机的人员（即，安全组的成员），具体取决于这些人员所在的站点。在此上下文中，“站点”指的是在拓扑生成器中定义的站点。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Regions</strong></p></td>
<td><p>定义了用于将 SecurityGroups 收集到某个区域（例如，EMEA）中的区域。</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileFolder</strong></p></td>
<td><p>定义了在计算机上写入日志文件的位置的路径。CLSAgent 将写入日志文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
</tr>
<tr class="odd">
<td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
<td><p>该参数指示在创建新的事件跟踪日志 (.etl) 文件之前日志文件需要达到的最大大小。在达到定义的大小之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverMinutes 中设置的最长时间也是如此。</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileRolloverMinutes</strong></p></td>
<td><p>在创建新的 .etl 文件之前日志可等待的定义的最大时间量（以分钟为单位）。在计时器过期之后将创建新的日志文件，即使尚未达到在 EtlFileRolloverSizeMB 中设置的最大大小也是如此。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TmfFileSearchPath</strong></p></td>
<td><p>搜索跟踪消息格式文件的位置。跟踪消息格式文件用于将二进制文件转换为用户可读的格式。</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalFolders</strong></p></td>
<td><p>定义了在计算机上写入缓存文件的位置的路径。CLSAgent 将写入缓存文件并在网络服务的上下文中运行。在这种情况下，%TEMP% 将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。默认情况下，缓存文件和日志文件将写入相同的目录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileNetworkFolder</strong></p></td>
<td><p>您可以定义在日志记录操作过程中接收缓存文件的通用命名约定 (UNC) 路径。</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
<td><p>已定义为保留缓存文件的最长时间（以天为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
<td><p>已定义为可由缓存文件使用的磁盘空间的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>ComponentThrottleLimit</strong></p></td>
<td><p>已定义为在触发自动阻止限制器之前组件每秒可生成的最大跟踪数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ComponentThrottleSample</strong></p></td>
<td><p>在 60 秒内可超出 ComponentThrottleLimit 的次数。</p></td>
</tr>
<tr class="even">
<td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
<td><p>允许运行的 CLSAgent 的最低版本。此元素适用于 Office 365。</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[集中日志记录服务的概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### 其他资源

[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)

