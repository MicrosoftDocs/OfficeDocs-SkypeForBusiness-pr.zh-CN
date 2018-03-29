---
title: 监视使用操作管理套件 (OMS) 的云连接器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 阅读本主题，以了解如何通过使用 Microsoft 操作管理套件 (OMS) 监视您的云连接器 2.1 版和更高版本的部署。
ms.openlocfilehash: 5e03504f27eadbb235c1b5c84e8c7a19d66aea7d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>监视使用操作管理套件 (OMS) 的云连接器
 
阅读本主题，以了解如何通过使用 Microsoft 操作管理套件 (OMS) 监视您的云连接器 2.1 版和更高版本的部署。
  
现在可以通过使用操作管理套件 (OMS)，Microsoft IT 管理解决方案云监视您的云连接器 2.1 版和更高版本的部署。 OMS 日志分析功能使您能够监视和分析可用性和资源，包括物理和虚拟机的性能。 关于 OMS 和日志分析的详细信息，请参阅[操作管理套件 (OMS) 是什么？](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)。
  
本主题包括以下部分：
  
- 先决条件
    
- 云将连接器配置为使用 OMS
    
- 配置 OMS
    
- 分析日志分析资料库中的警报
    
- 建议使用的监控集
    
## <a name="prerequisites"></a>先决条件

您可以使用 OMS 监视云连接器部署之前，您需要以下：
  
- **Azure 帐户，OMS 区。** 如果没有 Azure 帐户，您需要创建一个使用 OMS 日志分析。 有关如何创建 Azure 帐户并设置 OMS 工作区的信息，请参阅[入门日志分析区](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started)。
    
- **云的连接器版本 2.1 或更高版本**
    
- **新日志分析的日志搜索**时需要监控云连接器。 有关详细信息，请参阅[升级到新的日志搜索您 Azure 日志分析的工作区](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade)。
    
## <a name="configure-cloud-connector-to-use-oms"></a>云将连接器配置为使用 OMS

您将需要配置使用 OMS 云接头内部环境。 要执行此操作，您将需要您的 OMS 区 ID 和密钥，您可以通过按如下方式使用 OMS 门户网站查找： 设置--\>连接源--\> Windows 服务器：
  
![云连接器 OMS 屏幕截图](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
配置云连接器使用 OMS 的方式取决于您的情况：
  
- **如果要安装新的云接头装置或要重新部署设备**，请按照下列步骤运行安装 CcAppliance 之前：
    
1. 在 CloudConnector.ini 文件 [公共] 部分中，将 OMSEnabled 参数设置为 True。
    
    每次部署或升级，云连接器时它会尝试安装到虚拟机自动 OMS 代理。 因此 OMS 代理可以经受得住云接头自动更新，请启用此功能。
    
2. 若要配置的 OMS ID 和密钥，请运行组 CcCredential AccountType OMSWorkspace。 
    
- **如果您正在安装到现有的云接头装置 OMS 代理**，请执行以下步骤：
    
1. 在 CloudConnector.ini 文件 [公共] 部分中，设置 OMSEnabled = true。 
    
2. 运行导入 CcConfiguration。 
    
3. 运行安装 CcOMSAgent。 
    
    > [!NOTE]
    > 如果从未设置 OMSWorkspace 凭据，您的凭据运行时安装 CcOMSAgent。 
  
- **如果您想要更新的 OMS 区 ID 或云接头装置中的密钥的已安装 OMS 代理：**
    
1. 若要配置的 OMS ID 和密钥，请运行组 CcCredential AccountType OMSWorkspace。 
    
2. 若要应用这些更新，请运行安装 CcOMSAgent。 
    
- **对于所有方案，验证的代理连接，如下所示：**
    
    在 OMS 门户中，转到设置-\>连接源-\> Windows 服务器。 您将看到已连接的计算机的列表。 
    
## <a name="configure-oms"></a>配置 OMS

接下来，需要指定使用 OMS 门户的 OMS 配置。 具体来说，您将需要：
  
- 指定事件日志和性能计数器的信息。
    
- 创建通知。 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定事件日志和性能计数器信息

在 OMS 门户中，必须如下所示指定事件日志和性能计数器的信息：
  
1. 转到设置-\>数据-\>Windows 事件日志，并添加为事件日志： 
    
  - Lync Server
    
  - 应用程序
    
    > [!NOTE]
    > 您必须在文本框中手动输入 Lync Server。 它不会不显示为下拉列表中的选项。 
  
    有关详细信息，请参阅[日志分析中的 Windows 事件日志数据源](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)
    
2. 转到设置-\>数据-\> Windows 性能计数器，并将添加性能计数器： 
    
  - **操作系统级的计数器**。 您可以添加 OS 级别的计数器，例如处理器使用率、 内存使用率、 网络使用情况，也可以使用现有的解决方案，如容量和性能，而无需显式添加计数器的网络性能监视器。 无论您决定如何进行监视，Microsoft 建议您监视这些操作系统计数器。
    
  - **Skype 业务的计数器**。 有大量业务的 Skype 所提供的计数器。 通过登录到任何中介服务器并打开性能监视器，您可以找到这些计数器。 这些计数器开始"LS:"。 Microsoft 建议您开始至少下列容量计数器并添加其他感兴趣的人：
    
    总的活动联络：
    
  - LS:MediationServer-站 Calls(_Total)\-当前 
    
  - LS:MediationServer-出站 Calls(_Total)\-当前 
    
    总的活动媒体绕过调用：
    
  - LS:MediationServer-站 Calls(_Total)\-活动媒体绕过电话 
    
  - LS:MediationServer-出站 Calls(_Total)\-活动媒体绕过电话 
    
    > [!NOTE]
    > 您必须在文本框中手动输入的性能计数器。 它们不显示为下拉列表中的选项。 
  
    有关详细信息，请参阅[Windows 和 Linux 日志分析中的性能数据源](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)
    
### <a name="create-alerts"></a>创建通知

有两种类型中 OMS 的警报： 结果通知和警报公制度量单位的数量。 有关创建通知的详细信息，请参阅[使用日志分析中的警报规则](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating)。
  
创建警报时，您应该考虑以下：
  
- 请确保通知结果数的警报，这是默认选择。 
    
- 演示的查询要求，"结果数"设置为"大于 0"。 
    
- 建议您将设置时间窗口和警报的频率为 5 分钟。 
    
- 建议您不要启用"隐藏警报"演示通知。 
    
- 通常警告的情况下，Microsoft 建议创建警报一对： 一个错误警报和一个重置警报。 对于错误警报，选择严重性级别严重;重置警报，选择严重级别信息。
    
以下各节介绍如何创建示例通知。
  
 **创建警报对:"RTCMEDSRV 不在服务器上运行中介"和"RTCMEDSRV 是在中介服务器上运行"**
  
若要创建此警报对：
  
- 是错误警报的查询：
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    该查询使用计算机筛选器*的计算机都包含"MediationServer"* 。 筛选器选择的计算机名称中包含字符串"MediationServer"。
    
     将替换为计算机筛选器的筛选器，或只是将其删除。 您可以创建复杂的字符串没有正则表达式的筛选器。 有关详细信息，请参阅[字符串运算符](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。 您还可以使用正则表达式。 此外，您可以保存搜索查询，并为计算机筛选器警报查询中使用该组来创建计算机组。 有关详细信息，请参阅[日志分析中的计算机组记录搜索](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups)。
    
    为每台计算机，查询时发生错误将最后一个事件日志获取 RTCMEDSRV 服务启动和停止提供服务。 它会返回一个记录的最后一个事件是否服务停止事件;该属性将返回 nothing 的最后一个事件是否服务启动事件。 简单地说，则查询将返回其 RTCMEDSRV 停止的时间窗口中的服务器的列表。 
    
- 重置警报查询是：
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重置查询执行查询时发生错误的完全相反的事情。 对于每个计算机，它会返回一个如果最后一个事件是启动服务的事件;该属性将返回 nothing 的最后一个事件是否服务停止事件。
    
 **创建警报对:"太中介服务器中的多个并发调用"和"并行调用回退到正常负载"**
  
若要创建此警报：
  
- 是错误警报的查询：
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    对于每个计算机，查询将得到的入站的调用和出站呼叫之和最后一个计数器这两个值。 它会返回一个记录的总计值超过 500; 如果该属性将返回 nothing 如果它不存在。 简单地说，则查询将返回其并发调用具有太多的时间窗口中的服务器的列表。
    
- 重置警报查询是：
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    重置查询执行查询时发生错误的完全相反的事情。 对于每个计算机，查询将得到的入站的调用和出站呼叫之和最后一个计数器这两个值。 它将返回一个日志的总和值是否小于 500;它将否则返回 nothing。
    
 **创建一个通知:"CPU 使用率\>90 或 RTCMEDIARELAY 中的服务器停止"警报**
  
若要创建此警报，该查询在：
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

查询将从所有计算机并返回曾经停止一个日志，如果任一处理器使用率超过 90%或服务来获取所有的处理器使用情况计数器和服务停止事件。 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析日志分析资料库中的警报

要分析您的存储库中的警报，请使用警报管理解决方案。 有关详细信息，请参阅[警报管理解决方案中操作管理套件 (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)
  
## <a name="recommended-minimal-monitoring-set"></a>建议使用最小的监控集

确定问题与事件日志和性能计数器： 
  
- **事件日志。** 对于任何问题，应为事件对，一套事件以指示有问题，而其他表示一切都好。 对于任何给定的时间段，它是最后一个记录表明是否有异常情况该时间段的事件。
    
- **性能计数器。** 应该有个受监视的计数器的阈值。
    
下表列出了 Microsoft 建议监视通过停止和开始事件 Id 列出的服务：
  
|||||
|:-----|:-----|:-----|:-----|
|服务名称  <br/> |目标服务器角色  <br/> |停止事件 ID  <br/> |开始事件 ID  <br/> |
|RTCMEDSRV  <br/> |中介服务器  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |边缘服务器  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |边缘服务器  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |边缘服务器  <br/> |22003  <br/> |22002  <br/> |
   
下表列出了 Microsoft 建议监视的网络问题：
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|监视器名称  <br/> |目标服务器角色  <br/> |成功事件 ID 表达式  <br/> |错误事件 ID 表达式  <br/> |失败的示例  <br/> |
|中介服务器到网关连接失败  <br/> |中介服务器  <br/> |25062 || 25002  <br/> |25061  <br/> |MS PING （选项） 网关失败  <br/> |
|中介服务器到网关呼叫完成故障  <br/> |中介服务器  <br/> |25064 || 25002  <br/> |25063  <br/> |MS 试图使到网关呼叫失败  <br/> |
|关键网络问题  <br/> |边缘服务器  <br/> |14353 || 12288  <br/> |14624  <br/> |TLS 传输本地 IP 地址 192.168.231.14 在端口 5061 上启动失败  <br/> |
   
下面列出了您应该监视电话容量计数器。 这些数字应该是，小于 500 的云接口标准版;低于 50 云连接器最小版。
  
- LS:MediationServer-站 Calls(_Total)\-当前 
    
- LS:MediationServer-出站 Calls(_Total)\-当前 
    
- LS:MediationServer-站 Calls(_Total)\-活动媒体绕过电话
    
- LS:MediationServer-出站 Calls(_Total)\-活动媒体绕过电话
    
## <a name="see-also"></a>另请参阅

有关使用 OMS 的详细信息，请参阅以下资源：
  
- [日志分析中使用日志搜索查找数据](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [Azure 日志分析语言参考](https://docs.loganalytics.io/docs/Language-Reference)
    
- [日志分析中了解警报](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [连接到 Azure 中的日志分析服务的 Windows 的计算机](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

