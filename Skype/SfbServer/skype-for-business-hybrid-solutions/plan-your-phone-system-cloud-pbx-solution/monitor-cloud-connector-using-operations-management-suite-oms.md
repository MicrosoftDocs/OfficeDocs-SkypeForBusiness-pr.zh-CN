---
title: 监视云连接器使用操作管理套件 (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 阅读本主题可了解如何使用 Microsoft 操作管理套件 (OMS) 监视您的云连接器版本 2.1 和更高版本的部署。
ms.openlocfilehash: 36d70a1504eab085d319e46d03c3c6f0bd9d14f3
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532078"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>监视云连接器使用操作管理套件 (OMS)

阅读本主题可了解如何使用 Microsoft 操作管理套件 (OMS) 监视您的云连接器版本 2.1 和更高版本的部署。

您现在可以通过使用操作管理套件 (OMS) Microsoft 云 IT 管理解决方案监视您的云连接器版本 2.1 和更高版本的部署。 OMS 日志分析，可以监视和分析的可用性和性能的资源，包括物理和虚拟机。 有关 OMS 和日志分析的详细信息，请参阅[操作管理套件 (OMS) 是什么？](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)。

本主题包括以下部分：

- 先决条件

- 配置要使用 OMS 的云连接器

- 配置 OMS

- 分析日志分析资料库中的通知

- 建议的监视设置

## <a name="prerequisites"></a>先决条件

您可以使用 OMS 监视云连接器部署之前，您将需要以下各项：

- **Azure 帐户和 OMS 工作区。** 如果您没有 Azure 帐户，您需要创建一个使用 OMS 日志分析。 有关如何创建 Azure 帐户和设置 OMS 工作区的信息，请参阅[开始使用日志分析工作区](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)。

- **云连接器 2.1 或更高版本**

- 需要云连接器监视**日志分析新的日志搜索**。 有关详细信息，请参阅[升级到新的日志搜索您 Azure 日志分析工作区](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)。

## <a name="configure-cloud-connector-to-use-oms"></a>配置要使用 OMS 的云连接器

您需要配置云连接器在本地环境若要使用 OMS。 若要执行此操作，您需要您 OMS 工作区 ID 和密钥，您可以找到使用 OMS 门户，如下所示： 设置--\>连接源--\> Windows 服务器：

![云连接器 OMS 屏幕截图](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

要使用 OMS 的云连接器的配置方式取决于您的方案：

- **如果您正在安装新的云连接器装置或想要重新部署设备**，请按照下列步骤在运行安装 CcAppliance 之前：

1. 在 CloudConnector.ini 文件 [常见] 部分中，将 OMSEnabled 参数设置为 True。

    每次云连接器部署或升级，则将尝试安装自动到虚拟机 OMS 代理。 启用此功能，以便 OMS 代理可以排除云连接器的自动更新。

2. 若要配置的 OMS ID 和密钥，请运行设置 CcCredential AccountType OMSWorkspace。 

- **如果要安装到现有云连接器设备 OMS 代理**，请按照下列步骤：

1. 在 CloudConnector.ini 文件 [常见] 部分中，设置 OMSEnabled = true。 

2. 运行导入 CcConfiguration。 

3. 运行安装 CcOMSAgent。 

    > [!NOTE]
    > 如果从未设置 OMSWorkspace 凭据，则系统会提示凭据运行安装 CcOMSAgent 时。 

- **如果您想要更新的 OMS 工作区 ID 或云连接器装置中的项的已安装 OMS 代理：**

1. 若要配置的 OMS ID 和密钥，请运行设置 CcCredential AccountType OMSWorkspace。 

2. 若要应用更新，请运行安装 CcOMSAgent。 

- **对于所有方案，确认代理相连，如下所示：**

    在 OMS 门户中，转到设置-\>连接源-\> Windows 服务器。 您将看到已连接的计算机列表。 

## <a name="configure-oms"></a>配置 OMS

接下来，您需要使用 OMS 门户指定您 OMS 的配置。 具体而言，您将需要：

- 指定的事件日志和性能计数器信息。

- 创建通知。 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定有关的事件日志和性能计数器信息

在 OMS 门户中，您必须指定的事件日志和性能计数器的信息，如下所示：

1. 转到设置-\>数据-\>Windows 事件日志，并将其添加的事件日志： 

   - Lync Server

   - 应用程序

     > [!NOTE]
     > 您必须手动在文本框中输入 Lync Server。 它不显示为下拉列表中的选项。 

     有关详细信息，请参阅[日志分析中的 Windows 事件日志数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 转到设置-\>数据-\> Windows 性能计数器，并将其添加性能计数器： 

   - **操作系统级别计数器**。 您可以添加 OS 级别计数器，如处理器使用率、 内存使用率、 网络使用情况，或者您可以使用现有的解决方案，例如容量和性能、 网络性能监视器不明确添加计数器。 无论您决定如何监视其，Microsoft 建议您监视这些 OS 计数器。

   - **Skype 的业务计数器**。 有许多 for Business 的 Skype 提供的计数器。 您可以通过在登录到的任何中介服务器并打开性能监视器中找到这些计数器。 这些计数器开头"LS:"。 Microsoft 建议您启动与至少以下容量计数器，然后添加感兴趣的其他人：

     总活动呼叫：

   - LS:MediationServer-入站 Calls(_Total)\-当前 

   - LS:MediationServer-出站 Calls(_Total)\-当前 

     总活动的媒体绕过呼叫：

   - LS:MediationServer-入站 Calls(_Total)\-活动的媒体绕过呼叫 

   - LS:MediationServer-出站 Calls(_Total)\-活动的媒体绕过呼叫 

     > [!NOTE]
     > 您必须手动在文本框中输入的性能计数器。 它们不显示为下拉列表中的选项。 

     有关详细信息，请参阅[日志分析中的 Windows 和 Linux 性能数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>创建通知

有两种类型的通知中 OMS： 结果通知和公制度量通知的数目。 有关创建通知的详细信息，请参阅[使用日志分析中的通知规则](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)。

创建通知时，您应考虑以下：

- 请确保警报结果号码的通知中，这是默认选项。 

- 演示查询都需要"的结果数"设置为"大于 0"。 

- 建议您设置时间窗口和通知的频率为 5 分钟。 

- 建议您未启用"抑制通知"演示通知。 

- 典型的警报方案，Microsoft 建议创建一对通知： 一个错误通知和一个重置通知。 对于错误通知中，选择严重级别关键;对于重置通知中，选择严重级别信息。

以下各节介绍如何创建示例通知。

 **创建通知对:"RTCMEDSRV 未运行在中介服务器"和"RTCMEDSRV is 后中在中介服务器上运行"**

若要创建此通知对：

- 错误警告的查询为：

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    查询使用计算机筛选器，*其中计算机包含"MediationServer"* 。 筛选器选择仅名称中包含字符串"MediationServer"的计算机。

     将替换计算机筛选器的筛选器，也可以只需将其删除。 您可以创建复杂的字符串不正则表达式的筛选器。 有关详细信息，请参阅[字符串运算符](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。 您还可以选择使用正则表达式。 此外，您可以创建计算机组保存搜索查询并为您计算机的筛选器警报查询中使用的组。 有关详细信息，请参阅[计算机组日志分析中的日志搜索](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)。

    为每台计算机，错误查询将获取 RTCMEDSRV 服务启动最后的事件日志和服务停止。 它将返回一个日志的最后一个事件是否服务停止事件;它将返回 nothing 的最后一个事件是否服务开始事件。 简而言之，查询将返回其 RTCMEDSRV 已停止的时间窗口中的服务器的列表。 

- 重置通知的查询为：

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重置查询执行的任务的错误查询完全相反。 对于每台计算机，它将返回一个的最后一个事件是该服务启动事件; 如果它将返回 nothing 的最后一个事件是否服务停止事件。

  **创建通知对:"太多个并发呼叫在中介服务器"和"并发呼叫回退到正常负载"**

若要创建此通知：

- 错误警告的查询为：

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    对于每台计算机，查询将获取入站的呼叫和之和出站呼叫的最后一个计数器这两个值。 它将返回一个日志的总和值超过 500; 如果它将返回 nothing 如果它不存在。 简而言之，查询将返回其并发呼叫具有太多时间窗口中的服务器的列表。

- 重置通知的查询为：

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    重置查询执行的任务的错误查询完全相反。 对于每台计算机，查询将获取入站的呼叫和之和出站呼叫的最后一个计数器这两个值。 它将返回一个日志的总和的值是否不超过 500;它将否则返回 nothing。

  **创建通知:"CPU 使用率\>90 或 RTCMEDIARELAY 服务器中停止"警报**

若要创建此通知，该查询在：

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

查询将从所有计算机并返回以往停止一个日志如果任一处理器使用率超过 90%或服务来获取所有处理器使用率计数器和服务停止事件。 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析日志分析资料库中的通知

若要分析您的库中的通知，请使用警报管理解决方案。 有关详细信息，请参阅[警报管理解决方案中操作管理套件 (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>建议的最小监控集

若要确定与事件日志和性能计数器的问题： 

- **事件日志。** 以解决任何问题，应该有一组事件，以指示有问题，而另表明一切以及带有事件对。 任何给定的时间段，它是最后一个记录的事件，指示是否异常情况的时间段内使用的内容。

- **性能计数器。** 应受监视的计数器的阈值。

下表列出了 Microsoft 建议通过列出停止和启动事件 Id 监控服务：

|服务名称  <br/> |目标服务器角色  <br/> |停止事件 ID  <br/> |启动事件 ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |中介服务器  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |边缘服务器  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |边缘服务器  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |边缘服务器  <br/> |22003  <br/> |22002  <br/> |

下表列出了 Microsoft 建议监控网络问题：


| 监视器名称  <br/>                                        | 目标服务器角色  <br/> | 成功事件 ID 表达式  <br/> | 错误事件 ID 表达式  <br/> | 故障示例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 中介服务器与网关连接失败  <br/>    | 中介服务器  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 中介服务器到网关呼叫完成故障  <br/> | 中介服务器  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 关键网络问题  <br/>                           | 边缘服务器  <br/>        | 14353                              |                                  | 12288  <br/>           |

下面列出了应受到监视的呼叫容量计数器。 这些号码应，小于 500，对于云连接器 standard edition;小于 50 云连接器的最小 edition。

- LS:MediationServer-入站 Calls(_Total)\-当前 

- LS:MediationServer-出站 Calls(_Total)\-当前 

- LS:MediationServer-入站 Calls(_Total)\-活动的媒体绕过呼叫

- LS:MediationServer-出站 Calls(_Total)\-活动的媒体绕过呼叫

## <a name="see-also"></a>另请参阅

有关使用 OMS 的详细信息，请参阅以下资源：

- [查找使用日志分析中的日志搜索的数据](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure 日志分析语言参考](https://docs.loganalytics.io/docs/Language-Reference)

- [了解日志分析中的通知](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [连接到 Azure 中的日志 Analytics service 的 Windows 计算机](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


