---
title: 使用 PowerShell 管理集中日志记录服务配置设置
TOCTitle: 使用 PowerShell 管理集中日志记录服务配置设置
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49888687
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 PowerShell 管理集中日志记录服务配置设置

 

_**上一次修改主题：** 2012-11-01_

集中日志记录服务 由通过 集中日志记录服务 控制器 (CLSController) 创建和使用的设置和参数进行控制和配置以将命令发送到单个计算机的 集中日志记录服务 代理 (CLSAgent)。该代理处理发送给它的命令，并（如果是启动命令）根据提供的配置信息使用方案、提供程序、日志大小、跟踪持续时间和标志的配置开始收集跟踪日志。

> [!IMPORTANT]  
> 请注意，为 集中日志记录服务 列出的所有 Windows PowerShell cmdlet 专门用于与 Lync Server 2013 内部部署结合使用。尽管它们显示为处于工作状态，但未将下列 cmdlet 设计为与 Lync Server 2013 内部部署配合运行：
> <ul>
> <li><p><strong>CsClsRegion cmdlet：</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsRegion">Get-CsClsRegion</a>、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsRegion">Set-CsClsRegion</a>、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsRegion">New-CsClsRegion</a> 和 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsRegion">Remove-CsClsRegion</a>。</p></li>
> <li><p><strong>CsClsSearchTerm cmdlet：</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSearchTerm">Get-CsClsSearchTerm</a> 和 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSearchTerm">Set-CsClsSearchTerm</a>。</p></li>
> <li><p><strong>CsClsSecurityGroup cmdlet：</strong> <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSecurityGroup">Get-CsClsSecurityGroup</a>、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSecurityGroup">Set-CsClsSecurityGroup</a>、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsSecurityGroup">New-CsClsSecurityGroup</a> 和 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsSecurityGroup">Remove-CsClsSecurityGroup</a>。</p></li>
> </ul>
> 在这些 cmdlet 中定义的设置将不会成为阻碍或导致任何不良行为，但它们设计为与 Microsoft Office 365 结合使用，并将在内部部署中产生预期结果。这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。


## 本部分内容

本节中的主题定义用于 集中日志记录服务 的配置选项、参数和设置。下列主题包含有关如何配置 集中日志记录服务，如果检索配置设置、方案创建、集中日志记录服务 的安全组管理、搜索等信息。

  - [管理计算机、站点和全局中心日志记录服务配置](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [为集中日志记录服务配置提供商](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [为集中日志记录服务配置方案](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

## 另请参阅

#### 概念

[集中日志记录服务的概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[集中日志记录 Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/)

