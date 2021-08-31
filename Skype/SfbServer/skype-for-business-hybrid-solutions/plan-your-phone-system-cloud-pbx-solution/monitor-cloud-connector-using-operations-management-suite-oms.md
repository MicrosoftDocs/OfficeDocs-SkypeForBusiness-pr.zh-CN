---
title: 使用 Operations Management Suite (OMS) 监视云连接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 监控云连接器版本 2.1 和更高版本) 。
ms.openlocfilehash: 0589df251fedb8d60ba115920e76b3aa1b327334
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729021"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>使用 Operations Management Suite (OMS) 监视云连接器

> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 一旦组织升级到 Teams，了解如何使用直接路由将本地电话网络Teams[到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 监控云连接器版本 2.1 和更高版本) 。

现在，可以使用 Operations Management Suite (OMS) （Microsoft 云 IT 管理解决方案）监控云连接器 2.1 版和更高版本的部署。 利用 OMS Log Analytics，可以监视和分析资源（包括物理和虚拟机）的可用性和性能。 有关 OMS 和 Log Analytics 详细信息，请参阅 [什么是 Operations Management Suite (OMS) ？](/azure/operations-management-suite/operations-management-suite-overview)

本主题包含以下各部分：

- 先决条件

- 配置云连接器以使用 OMS

- 配置 OMS

- 分析 Log Analytics 存储库中的警报

- 建议的监视集

## <a name="prerequisites"></a>先决条件

在可以使用 OMS 监视云连接器部署之前，你将需要以下各项：

- **Azure 帐户和 OMS 工作区。** 如果还没有 Azure 帐户，则需要创建一个帐户才能使用 OMS Log Analytics。 若要了解如何创建 Azure 帐户和设置 OMS 工作区，请参阅 Log [Analytics 工作区入门](/azure/log-analytics/log-analytics-get-started)。

- **云连接器版本 2.1 或更高版本**

- **Log Analytics 云连接器监控** 需要新的日志搜索。 有关详细信息，请参阅将 [Azure Log Analytics 工作区升级到新的日志搜索](/azure/log-analytics/log-analytics-log-search-upgrade)。

## <a name="configure-cloud-connector-to-use-oms"></a>配置云连接器以使用 OMS

你需要将云连接器本地环境配置为使用 OMS。 为此，您需要 OMS 工作区 ID 和密钥，可通过使用 OMS 门户找到，如下所示：设置 -- 连接源 -- Windows \> \> 服务器：

![云连接器 OMS 的屏幕截图。](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

配置云连接器以使用 OMS 的方式取决于你的方案：

- **如果要安装新的** 云连接器设备或要重新部署设备，请按照以下步骤操作，然后再运行 Install-CcAppliance：

    1. 在CloudConnector.ini文件 [Common] 部分中，将 OMSEnabled 参数设置为 True。

        每次部署或升级云连接器时，它都会尝试将 OMS 代理自动安装到 VM 上。 启用此功能，以便 OMS 代理可以保存云连接器自动更新。

    2. 若要配置 OMS ID 和密钥，请Set-CcCredential -AccountType OMSWorkspace。 

- **如果要将 OMS 代理安装到现有云连接器设备**，请按照以下步骤操作：

    1. 在CloudConnector.ini文件 [Common] 部分中，设置 OMSEnabled=true。 

    2. 运行 Import-CcConfiguration。 

    3. 运行 Install-CcOMSAgent。 

        > [!NOTE]
        > 如果从未设置 OMSWorkspace 凭据，则当您运行 install-CcOMSAgent 时，系统会提示您输入凭据。 

- **如果要更新已安装 OMS 代理的云连接器设备中的 OMS 工作区 ID 或密钥：**

    1. 若要配置 OMS ID 和密钥，请Set-CcCredential -AccountType OMSWorkspace。 

    2. 若要应用更新，请运行 Install-CcOMSAgent。 

- **对于所有方案，验证代理是否按如下方式连接：**

    在 OMS 门户中，转到"设置 - 连接 \> 源 - \> Windows服务器"。 你将看到已连接计算机的列表。 

## <a name="configure-oms"></a>配置 OMS

接下来，您需要使用 OMS 门户指定 OMS 配置。 具体而言，你将需要：

- 指定有关事件日志和性能计数器的信息。

- 创建通知。 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定有关事件日志和性能计数器的信息

在 OMS 门户中，必须指定有关事件日志和性能计数器的信息，如下所示：

1. 转到设置 - 数据 \> - \> Windows事件日志，并添加事件日志： 

   - Lync Server

   - Application

     > [!NOTE]
     > 您必须在文本框中手动输入 Lync Server。 它不会显示为下拉列表中的选项。 

     有关详细信息，请参阅 log [Analytics Windows事件日志数据源](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 转到设置- \> 数据Windows \> 性能计数器，并添加性能计数器： 

   - **操作系统级别计数器**。 您可以添加操作系统级别计数器（如处理器使用率、内存使用率、网络使用情况）或使用现有解决方案（如容量和性能、网络性能监视器）而无需显式添加计数器。 无论你决定如何监视它们，Microsoft 都建议您监视这些操作系统计数器。

   - **Skype for Business计数器**。 系统提供了许多计数器Skype for Business。 通过登录到任何中介服务器并打开性能监视器，可以找到这些计数器。 这些计数器以"LS："开始。 Microsoft 建议你至少从以下容量计数器开始，并添加感兴趣的其他计数器：

     总活动呼叫：

       - LS：MediationServer - (_Total) \- 呼叫 

       - LS：MediationServer - 当前 (_Total) \- 呼叫 

     活动媒体旁路呼叫总数：

       - LS：MediationServer - (_Total) \- 媒体旁路呼叫的入站呼叫 

       - LS：MediationServer - (_Total) \- 媒体旁路呼叫的出站呼叫 

     > [!NOTE]
     > 您必须手动在文本框中输入性能计数器。 它们不会显示为下拉列表中的选项。 

     有关详细信息，请参阅[Log Analytics Windows](/azure/log-analytics/log-analytics-data-sources-performance-counters)和 Linux 性能数据源

### <a name="create-alerts"></a>创建警报

OMS 中有两种类型的警报：结果警报数和指标度量警报。 有关创建警报的信息，请参阅在 [Log Analytics](/azure/log-analytics/log-analytics-alerts-creating)中处理警报规则。

在创建警报时，应考虑以下事项：

- 确保警报是结果数警报，这是默认选择。 

- 演示查询要求将"结果数"设置为"大于 0"。 

- 建议将时间窗口和警报频率都设置为 5 分钟。 

- 建议不要对演示警报启用"抑制警报"。 

- 对于典型的警报方案，Microsoft 建议创建一对警报：一个错误警报和一个重置警报。 对于错误警报，选择严重性级别"严重";对于重置警报，选择严重性级别"信息"。

以下各节介绍如何创建示例警报。

 **创建警报对："RTCMEDSRV 未在中介服务器中运行"和"RTCMEDSRV 正在中介服务器中重新运行"**

若要创建此警报对：

- 对错误警报的查询为：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    查询使用计算机筛选器，*其中 Computer 包含"MediationServer"。* 筛选器仅选择其名称包含字符串"MediationServer"的计算机。

     可以使用自己的计算机筛选器替换筛选器，或者直接将其删除。 可以创建不带正则表达式的复杂字符串筛选器。 有关详细信息，请参阅字符串 [运算符](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。 您还可以选择使用正则表达式。 此外，您可以通过保存搜索查询，以及将该组用作警报查询中的计算机筛选器来创建计算机组。 有关详细信息，请参阅 Log [Analytics 日志搜索中的计算机组](/azure/log-analytics/log-analytics-computer-groups)。

    对于每个计算机，错误查询将获取 RTCMEDSRV 服务启动和服务停止的最后一个事件日志。 如果最后一个事件是服务停止事件，它将返回一个日志;如果最后一个事件是服务启动事件，它将不返回任何值。 简而言之，查询将返回其 RTCMEDSRV 在时间窗口中停止的服务器的列表。 

- 重置警报的查询为：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重置查询与错误查询完全相反。 对于每个计算机，如果最后一个事件是服务启动事件，它将返回一个;如果最后一个事件是服务停止事件，它将不返回任何值。

**创建警报对："中介服务器中的并发呼叫过多"和"并发呼叫回退到正常负载"**

若要创建此警报：

- 对错误警报的查询为：

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    对于每个计算机，查询将获取入站呼叫和出站呼叫的最后一个计数器，并计算这两个值的总和。 如果总和值超过 500，它将返回一个日志;如果未返回任何值，则不返回任何值。 简而言之，查询将返回一个服务器列表，这些服务器的并发调用在时间窗口中太多。

- 重置警报的查询为：

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    重置查询与错误查询完全相反。 对于每个计算机，查询将获取入站呼叫和出站呼叫的最后一个计数器，并计算这两个值的总和。 如果总和值小于 500，它将返回一个日志;否则，它将不返回任何值。

**创建警报："CPU 使用率 \> 90 或 RTCMEDIARELAY 在服务器中已停止"警报**

若要创建此警报，查询为：

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

查询将获取所有计算机的所有处理器使用率计数器和服务停止事件，如果任一处理器使用率超过 90% 或者服务停止，则返回一个日志。 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析 Log Analytics 存储库中的警报

若要分析存储库中的警报，请使用警报管理解决方案。 有关详细信息，请参阅 [Operations Management Suite (OMS) ](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>建议最小监视集

标识事件日志和性能计数器的问题： 

- **事件日志。** 对于任何问题，都应该有一个事件对，其中一组事件指示出错，而另一个表示一切良好。 对于任何给定的时间段，记录的最后一个事件将指示该时间段是否有内容。

- **性能计数器。** 应存在受监视计数器的阈值。

下表列出了 Microsoft 建议通过列出停止和启动事件 ID 监视的服务：

|服务名称  <br/> |目标服务器角色  <br/> |停止事件 ID  <br/> |开始事件 ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |中介服务器  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |边缘服务器  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |边缘服务器  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |边缘服务器  <br/> |22003  <br/> |22002  <br/> |

下表列出了 Microsoft 建议监视的网络问题：


| 监视器名称  <br/>                                        | 目标服务器角色  <br/> | 成功事件 ID 表达式  <br/> | 错误事件 ID 表达式  <br/> | 失败示例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 中介服务器到网关的连接失败  <br/>    | 中介服务器  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 中介服务器到网关的呼叫完成失败  <br/> | 中介服务器  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 关键网络问题  <br/>                           | 边缘服务器  <br/>        | 14353                              |                                  | 12288  <br/>           |

下面列出了应监视的呼叫容量计数器。 对于云连接器标准版，这些数字应小于 500;云连接器最低版本低于 50。

- LS：MediationServer - (_Total) \- 呼叫 

- LS：MediationServer - 当前 (_Total) \- 呼叫 

- LS：MediationServer - (_Total) \- 媒体旁路呼叫的入站呼叫

- LS：MediationServer - (_Total) \- 媒体旁路呼叫的出站呼叫

## <a name="see-also"></a>另请参阅

有关使用 OMS 的信息，请参阅以下内容：

- [使用日志搜索在 Log Analytics 中查找数据](/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics 语言参考](https://docs.loganalytics.io/docs/Language-Reference)

- [了解 Log Analytics 中的警报](/azure/log-analytics/log-analytics-alerts)

- [连接 Windows计算机登录到 Azure 中的 Log Analytics 服务](/azure/log-analytics/log-analytics-windows-agents)