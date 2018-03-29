---
title: 为业务服务器 2015年计划为 Skype 统计信息经理
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要： 请阅读本主题，以学习为 Skype 业务服务器 2015年有关统计数据管理器。
ms.openlocfilehash: 63f064f9a6632250f3cfadddbcbb5fca2120f07b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a>为业务服务器 2015年计划为 Skype 统计信息经理
 
**摘要：**阅读本主题，以学习为 Skype 业务服务器 2015年有关统计数据管理器。
  
 Skype 业务服务器的统计信息管理器是一个强大的工具，允许您查看 Skype 实时业务服务器运行状况和性能数据。 可以跨数百个服务器每隔几秒钟轮询性能数据和统计数据管理器网站上可立即查看结果。
  
统计管理器用于标识正在进行性能问题，对您的环境中查看计划修改的结果，跟踪解决停机的情况，以及更多。 开箱即用，统计管理器项健康指标 (KHI) 阈值与配置，并可以进行自定义以满足您的部署的唯一需要。 
  
您可以在一台服务器承载的所有服务器端统计管理器组件在内部部署中部署统计数据管理器。 有关部署管理器统计信息的详细信息，请参阅[部署业务服务器 2015年的 Skype 统计管理](deploy.md)。 如果您已经有现有部署的统计管理器中，但尚未升级到版本 1.1，请参阅[什么是版本 1.1 版中的新增功能](plan.md#BKMK_WhatsNew)和[业务服务器 2015年的 Skype 的升级统计数据管理器](upgrade.md)。
  
本主题包括以下部分：
  
- [特性和功能](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)
    
- [什么是版本 1.1 中的新功能](plan.md#BKMK_WhatsNew)
    
- [组件](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)
    
- [内部部署](plan.md#BKMK_DeploymentOptions)
    
- [要求](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)
    
- [安全注意事项](plan.md#BKMK_Security)
    
## <a name="features-and-capabilities"></a>特性和功能
<a name="BKMK_Features"> </a>

统计信息管理器，您可以：
  
- 实时查看原始数据进行的所有服务器。 （数据采样率非常高的速率，小于一秒内发送到该网站。）
    
- 查看数据聚合为一个特定的角色;例如，前端服务器、 中介服务器、 边缘服务器等。
    
- 查看特定的站点，在站点中的特定池，池内的然后特定服务器的数据向下钻取。
    
- 创建自定义的图表，以便选择默认情况下显示的计数器。
    
- 缩放和平移在这两个 x 轴和 y 轴或 x 轴只上。
    
- 在筛选数据时使用的日期范围或点。 
    
- 查看基于已建立的关键运行状况指标 (KHIs) 的服务器性能。 KHIs 表示集合的性能计数器与定义的正常范围。 
    
- 查看每个计数器的详细的指标。
    
- 跨多个群体或服务器数据进行比较。
    
- 查看潜在的计数器报告弄不到仪表板服务报告当前数据的代理。
    
- 保存到文件的特定实例的图表数据。
    
- 实时更新包括查看 KHIs。 如果启用历史记录视图，则将显示只新故障。
    
  - 一次查看所有 KHIs
    
  - 查看 KHIs 服务器 （横向视图）
    
  - KHI 视图定义
    
## <a name="whats-new-in-release-11"></a>什么是版本 1.1 中的新功能
<a name="BKMK_WhatsNew"> </a>

下面介绍在版本 1.1 中的新增功能。 如果已经部署的统计信息管理器，您还没有升级，请参阅[升级业务服务器 2015年的 Skype 统计管理](upgrade.md)。
  
- 方案中的视图添加了边缘介质、 结构状况、 池故障转移和登记方案。
    
- 命令行 PerfAgentStorageManager.exe （安装到侦听程序） 现在可以作为 CSV 导出计数器数据。
    
- 很多新的计数器添加了 SQL 服务器，多个 Windows 结构计数器，更多的业务使用情况计数器，Skype 等等。
    
- 观察程序节点集成统计管理器代理-如果观察程序节点上安装了代理将报告综合事务统计信息计数器作为回到统计信息管理器。
    
- 许多的可靠性和性能改进。
    
若要验证您运行的统计数据管理器网站版本：
  
- 文件资源管理器中打开 （默认目录） 的业务服务器 StatsMan WebSite\bin C:\Program Files\Skype
    
- 在 StatsManHubWebSite.dll 上右键单击，然后查看其属性
    
- 产品版本将在“说明”详细信息中显示。
    
## <a name="components"></a>组件
<a name="BKMK_Components"> </a>

统计管理器包含以下组件：
  
- **代理。** 在每个被监视的服务器运行一个轻量级代理。 该代理允许具有本地的聚合性能计数器可配置高的速率轮询。
    
- **监听器。** 服务器端 API 的所有代理，从接收数据和聚合数据跨群体。
    
- **集线器。** 提供服务系统中，客户端 API 用户运行的 web 服务器，以及通过网站连接的客户端提供实时数据更新。 （集线器是自动安装的网站 msi 的一部分。
    
- **网站。** 一个用户界面，齐心协力系统中提供的所有功能。
    
此外，统计数据管理器要求**Redis**，开放源代码的数据结构服务器的内存中缓存。 有关下载 Redis 的详细信息，请参阅[部署管理器统计信息](deploy.md#BKMK_Deploy)。
  
## <a name="on-premises-deployment"></a>内部部署
<a name="BKMK_DeploymentOptions"> </a>

在内部部署中，一台服务器承载的所有服务器端统计管理器组件。 
  
下图显示在内部部署，其中统计管理器网站、 中心、 侦听器和缓存系统的 Redis 寄宿在一台计算机。 统计管理器监视三个 Skype 业务服务器，其中每个有一个代理将数据传输到侦听器。 用户连接到一个网站以查看所有数据聚合由统计数据管理器：
  
![统计管理器本地部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)
  
## <a name="requirements"></a>要求
<a name="BKMK_Requirements"> </a>

您需要在部署管理器统计信息之前，请考虑以下软件、 网络和硬件要求。 
  
### <a name="software-requirements"></a>软件要求

- Windows Server 2012 R2
    
- IIS （自动安装）
    
- Redis
    
- （自动安装） 的统计信息管理器服务
    
- PSExec 的要求做远程代理部署
    
- （附带 2012 R2）.NET 4.5-所需的服务器端组件
    
- .NET 4.0-所需的代理
    
### <a name="networking-requirements"></a>网络要求


|**托管服务器**|**代理**|**侦听器**|
|:-----|:-----|:-----|
|最小的千兆全双工的网络。  <br/> |出站 TCP 端口 8443 （可自定义的端口号） 与侦听程序进行通信。  <br/> |侦听器端口必须为所有服务器上相同。  <br/> |
|入站 TCP 端口 80 或 443 打开该网站的宿主。  <br/> |||
|要与之通信的代理程序的入站 TCP 端口 8443 （可自定义的端口号）。  <br/> |||
   
在安装期间，系统会自动创建监听器和该网站的防火墙端口。 对于代理，安装假定默认情况下允许出站 TCP 连接。
  
### <a name="hardware-requirements"></a>硬件要求

在内部部署中，一台服务器承载的所有服务器端统计管理器组件，16 gb 的 RAM 和 4 服务器 CPU 的应该是能够平均支持每秒大约 150 个样本。 若要确定可支持多少个计数器/代理，请使用以下方法计算： 
  
100 个服务器\*80 计数器\*1 示例每分钟每个代理 / 60 秒 = ~ 每秒 133 样本。
  
## <a name="security-considerations"></a>安全注意事项
<a name="BKMK_Security"> </a>

服务器之间的所有通信进行都加密。 
  
- 加密的 HTTPS 通信将是通过端口 8443 （默认值） 从代理发送到侦听器服务器。
    
- 该代理将验证以确保监听器服务器是预期的收件人的服务器上的 SSL 指纹。 请注意，代理使用证书指纹验证（而不是链验证）。 由于可能使用自签名证书，因此它不会执行完整证书验证。
    
- 代理满意后侦听器可信，必须由代理然后验证侦听器中提供密码。 
    
- 该代理开始通过向监听器连接传输性能数据。
    
## <a name="for-more-information"></a>详细信息
<a name="BKMK_Security"> </a>

有关详细信息，请参阅以下文章：
  
- [为业务服务器 2015年部署 Skype 的统计信息管理器](deploy.md)
    
- [为业务服务器 2015年升级为 Skype 的统计信息管理器](upgrade.md)
    
- [解决业务服务器 2015年的 Skype 的统计信息管理器](troubleshoot.md)
    
- [Skype 业务服务器统计信息管理器日志](https://blogs.technet.microsoft.com/skypestatsman/)
    

