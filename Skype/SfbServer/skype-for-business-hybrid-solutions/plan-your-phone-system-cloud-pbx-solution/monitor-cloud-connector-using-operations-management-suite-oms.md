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
description: 阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 监视云连接器版本 2.1 及更高版本的部署。
ms.openlocfilehash: c10eac34e065ab76cb570a21752838c308b6afd8
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676504"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>使用 Operations Management Suite (OMS) 监视云连接器

> [!Important]
> Cloud Connector Edition 将于 2021 年 7 月 31 日停用，Skype for Business Online。 组织升级到Teams后，了解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到Teams。

阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 监视云连接器版本 2.1 及更高版本的部署。

现在可以使用 Operations Management Suite (OMS) （Microsoft 云 IT 管理解决方案）监视云连接器版本 2.1 及更高版本的部署。 通过 OMS Log Analytics，可以监视和分析包括物理和虚拟机在内的资源的可用性和性能。 有关 OMS 和 Log Analytics 的详细信息，请参阅 [什么是 Operations Management Suite (OMS) ？](/azure/operations-management-suite/operations-management-suite-overview)

本主题包含以下各部分：

- 先决条件

- 将云连接器配置为使用 OMS

- 配置 OMS

- 分析 Log Analytics 存储库中的警报

- 建议的监视集

## <a name="prerequisites"></a>先决条件

在使用 OMS 监视云连接器部署之前，需要以下各项：

- **Azure 帐户和 OMS 工作区。** 如果还没有 Azure 帐户，则需要创建一个帐户来使用 OMS Log Analytics。 有关如何创建 Azure 帐户和设置 OMS 工作区的信息，请参阅 [log Analytics 工作区的开始](/azure/log-analytics/log-analytics-get-started)。

- **云连接器版本 2.1 或更高版本**

- 云连接器 **监视需要 Log Analytics 新的日志搜索**。 有关详细信息，请参阅将 [Azure Log Analytics 工作区升级到新的日志搜索](/azure/log-analytics/log-analytics-log-search-upgrade)。

## <a name="configure-cloud-connector-to-use-oms"></a>将云连接器配置为使用 OMS

需要将云连接器本地环境配置为使用 OMS。 为此，需要 OMS 工作区 ID 和密钥，可以使用 OMS 门户查找这些 ID 和密钥，如下所示：设置 --\>Connected Sources --\> Windows服务器：

![Cloud Connector OMS 的屏幕截图。](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

如何将 Cloud Connector 配置为使用 OMS 取决于你的方案：

- **如果要安装新的云连接器设备或想要重新部署设备**，请在运行 Install-CcAppliance 之前执行以下步骤：

  1. 在CloudConnector.ini文件 [Common] 部分中，将 OMSEnabled 参数设置为 True。

     每次部署或升级云连接器时，都会尝试将 OMS 代理自动安装到 VM 上。 启用此功能，使 OMS 代理能够在云连接器自动更新后生存。

  2. 若要配置 OMS ID 和密钥，请运行 Set-CcCredential -AccountType OMSWorkspace。

- **如果要将 OMS 代理安装到现有的云连接器设备** 上，请执行以下步骤：

  1. 在CloudConnector.ini文件 [Common] 部分中，设置 OMSEnabled=true。

  2. 运行 Import-CcConfiguration。

  3. 运行 Install-CcOMSAgent。

     > [!NOTE]
     > 如果从未设置过 OMSWorkspace 凭据，则在运行 install-CcOMSAgent 时会提示输入凭据。

- **如果想要更新已安装 OMS 代理的云连接器设备中的 OMS 工作区 ID 或密钥：**

  1. 若要配置 OMS ID 和密钥，请运行 Set-CcCredential -AccountType OMSWorkspace。

  2. 若要应用更新，请运行 Install-CcOMSAgent。

- **对于所有方案，请验证代理是否已连接，如下所示：**

    在 OMS 门户中，转到设置 -\> 连接的源 -\> Windows服务器。 你将看到连接的计算机的列表。

## <a name="configure-oms"></a>配置 OMS

接下来，需要使用 OMS 门户指定 OMS 配置。 具体而言，需要：

- 指定有关事件日志和性能计数器的信息。

- 创建通知。

### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定有关事件日志和性能计数器的信息

在 OMS 门户中，必须指定有关事件日志和性能计数器的信息，如下所示：

1. 转到设置数据\>\>Windows事件日志，并为以下内容添加事件日志：

   - Lync Server

   - 应用

     > [!NOTE]
     > 必须在文本框中手动输入 Lync Server。 它不显示为下拉列表中的选项。

     有关详细信息，请参阅 [Log Analytics 中的Windows事件日志数据源](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 转到设置数据\>-\>Windows性能计数器，并为以下项添加性能计数器：

   - **OS 级别计数器**。 可以添加 OS 级别计数器，例如处理器使用情况、内存使用情况、网络使用情况，或者可以使用现有解决方案，如容量和性能、网络性能监视器，而无需显式添加计数器。 无论你如何决定监视它们，Microsoft 都建议监视这些 OS 计数器。

   - **Skype for Business计数器**。 Skype for Business提供了许多计数器。 可以通过登录到任何中介服务器并打开性能监视器来查找这些计数器。 这些计数器以“LS：”开头。 Microsoft 建议你至少从以下容量计数器开始，并添加其他感兴趣的计数器：

     活动呼叫总数：

     - LS：MediationServer - 入站呼叫 (_Total) \- 当前

     - LS：MediationServer - 当前 (_Total) \- 出站呼叫

     活动媒体旁路呼叫总数：

     - LS：MediationServer - 入站呼叫 (_Total) \- 主动媒体旁路呼叫

     - LS：MediationServer - 主动媒体旁路呼叫 (_Total) \- 出站呼叫

     > [!NOTE]
     > 必须在文本框中手动输入性能计数器。 它们不显示为下拉列表中的选项。

     有关详细信息，请参阅 [Log Analytics 中的 Windows 和 Linux 性能数据源](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>创建警报

OMS 中有两种类型的警报：结果警报数和指标度量警报数。 有关创建警报的详细信息，请参阅 [Log Analytics 中的警报规则。](/azure/log-analytics/log-analytics-alerts-creating)

创建警报时，应考虑以下事项：

- 请确保警报是结果数警报，这是默认选择。

- 演示查询要求将“结果数”设置为“大于 0”。

- 建议将时间窗口和警报频率设置为 5 分钟。

- 建议不要为演示警报启用“禁止警报”。

- 对于典型的警报方案，Microsoft 建议创建警报配对：一个错误警报和一个重置警报。 对于错误警报，请选择严重级别严重;对于重置警报，请选择严重性级别信息。

以下部分介绍如何创建示例警报。

#### <a name="create-an-alert-pair-rtcmedsrv-is-not-running-in-mediation-servers-and-rtcmedsrv-is-back-in-running-in-mediation-servers"></a>创建警报配对：“RTCMEDSRV 未在中介服务器中运行”和“RTCMEDSRV 在中介服务器中恢复运行”

若要创建此警报配对：

- 错误警报的查询是：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    查询使用  *计算机包含“MediationServer”的*  计算机筛选器。 筛选器仅选择其名称包含字符串“MediationServer”的计算机。

     可以将筛选器替换为自己的计算机筛选器，或者只需将其删除即可。 可以创建不带正则表达式的复杂字符串筛选器。 还可以选择使用正则表达式。 此外，还可以通过保存搜索查询并使用该组作为警报查询中的计算机筛选器来创建计算机组。 有关详细信息，请参阅 [Log Analytics 日志搜索中的计算机组](/azure/log-analytics/log-analytics-computer-groups)。

    对于每台计算机，错误查询将获取 RTCMEDSRV 服务启动和服务停止的最后一个事件日志。 如果最后一个事件是服务停止事件，它将返回一个日志;如果最后一个事件是服务启动事件，它将不返回任何内容。 简而言之，查询将返回其 RTCMEDSRV 在时间窗口中停止的服务器列表。

- 重置警报的查询是：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重置查询与错误查询完全相反。 对于每台计算机，如果最后一个事件是服务启动事件，它将返回一台：如果最后一个事件是服务停止事件，它将不返回任何内容。

#### <a name="create-an-alert-pair--too-many-concurrent-calls-in-mediation-servers-and-concurrent-calls-fall-back-to-normal-load"></a>创建警报配对：“中介服务器中的并发调用过多”和“并发调用回正常负载”

若要创建此警报，请执行以下操作：

- 错误警报的查询是：

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    对于每台计算机，查询将获取入站呼叫和出站调用的最后一个计数器，并将这两个值求和。 如果总和值超过 500，它将返回一个日志;如果没有，它将返回任何内容。 简言之，查询将返回一个服务器列表，这些服务器的并发调用在时间窗口中过多。

- 重置警报的查询是：

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    重置查询与错误查询完全相反。 对于每台计算机，查询将获取入站呼叫和出站调用的最后一个计数器，并将这两个值求和。 如果总和值小于 500，它将返回一个日志;否则，它将不返回任何内容。

#### <a name="create-an-alert-cpu-usage--90-or-rtcmediarelay-stopped-in-servers-alert"></a>创建警报：“CPU 使用率 \> 90 或 RTCMEDIARELAY 已在服务器中停止”警报

若要创建此警报，查询为：

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

查询将从所有计算机获取所有处理器使用情况计数器和服务停止事件，如果处理器使用率超过 90% 或服务已停止，则返回一个日志。

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析 Log Analytics 存储库中的警报

若要分析存储库中的警报，请使用警报管理解决方案。 有关详细信息，请参阅 [Operations Management Suite (OMS) 中的警报管理解决方案 ](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>建议的最小监视集

若要识别事件日志和性能计数器的问题，

- **事件日志。** 对于任何问题，应配对事件，其中一组事件表示出错，而另一组表示一切正常。 对于任何给定时间段，记录的最后一个事件将指示该时间段是否有问题。

- **性能计数器。** 受监视计数器应具有阈值。

下表列出了 Microsoft 建议通过列出停止和启动事件 ID 来监视的服务：

|服务名称  <br/> |目标服务器角色  <br/> |停止事件 ID  <br/> |"开始"菜单事件 ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |中介服务器  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |边缘服务器  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |边缘服务器  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |边缘服务器  <br/> |22003  <br/> |22002  <br/> |

下表列出了 Microsoft 建议监视的网络问题：


| 监视器名称  <br/>                                        | 目标服务器角色  <br/> | Success 事件 ID 表达式  <br/> | 错误事件 ID 表达式  <br/> | 失败示例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 中介服务器到网关连接失败  <br/>    | 中介服务器  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 中介服务器到网关调用完成失败  <br/> | 中介服务器  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 严重网络问题  <br/>                           | 边缘服务器  <br/>        | 14353                              |                                  | 12288  <br/>           |

下面列出了应监视的调用容量计数器。 对于云连接器标准版，这些数字应该小于 500;云连接器最低版本小于 50。

- LS：MediationServer - 入站呼叫 (_Total) \- 当前

- LS：MediationServer - 当前 (_Total) \- 出站呼叫

- LS：MediationServer - 入站呼叫 (_Total) \- 主动媒体旁路呼叫

- LS：MediationServer - 主动媒体旁路呼叫 (_Total) \- 出站呼叫

## <a name="see-also"></a>另请参阅

有关使用 OMS 的详细信息，请参阅以下内容：

- [在 Log Analytics 中使用日志搜索查找数据](/azure/log-analytics/log-analytics-log-searches)

- [了解 Log Analytics 中的警报](/azure/log-analytics/log-analytics-alerts)

- [将计算机连接 Windows到 Azure 中的 Log Analytics 服务](/azure/log-analytics/log-analytics-windows-agents)