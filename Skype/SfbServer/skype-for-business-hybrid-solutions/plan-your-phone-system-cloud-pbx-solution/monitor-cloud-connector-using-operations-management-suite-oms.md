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
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 监视你的云连接器版本2.1 及更高版本的部署。
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359088"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>使用 Operations Management Suite (OMS) 监视云连接器

> [!Important]
> 云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。 组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。

阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 监视你的云连接器版本2.1 及更高版本的部署。

现在，您可以使用 Operations Management Suite (OMS) Microsoft 云 IT 管理解决方案来监视云连接器版本2.1 及更高版本的部署。 OMS 日志分析使您能够监视和分析资源（包括物理和虚拟机）的可用性和性能。 有关 OMS 和 Log Analytics 的详细信息，请参阅 [什么是 Operations Management Suite (OMS) ？](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

本主题包含以下各部分：

- 先决条件

- 将云连接器配置为使用 OMS

- 配置 OMS

- 分析 Log Analytics 存储库中的警报

- 推荐的监视集

## <a name="prerequisites"></a>先决条件

在可以使用 OMS 监视云连接器部署之前，您需要以下各项：

- **Azure 帐户和 OMS 工作区。** 如果你还没有 Azure 帐户，你将需要创建一个，才能使用 OMS 日志分析。 有关如何创建 Azure 帐户和设置 OMS 工作区的信息，请参阅 [Log Analytics workspace 入门](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)。

- **云连接器版本2.1 或更高版本**

- 需要进行日志分析：云连接器监控需要**新的日志搜索**。 有关详细信息，请参阅 [将 Azure Log Analytics 工作区升级到新的日志搜索](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)。

## <a name="configure-cloud-connector-to-use-oms"></a>将云连接器配置为使用 OMS

你需要将云连接器本地环境配置为使用 OMS。 若要执行此操作，您将需要您的 OMS 工作区 ID 和密钥，可通过以下方式使用 OMS 门户来查找：设置-- \> 连接的源-- \> Windows server：

![云连接器 OMS 的屏幕截图](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

如何配置云连接器以使用 OMS 取决于您的方案：

- **如果要安装新的云连接器设备或想要重新部署设备**，请在运行 register-ccappliance 之前执行以下步骤：

    1. 在 "CloudConnector.ini 文件 [Common]" 部分，将 OMSEnabled 参数设置为 True。

        每次部署或升级云连接器时，都会尝试将 OMS 代理自动安装到 Vm 上。 启用此功能，以便 OMS 代理可经受云连接器自动更新。

    2. 若要配置 OMS ID 和密钥，请运行 Set-cccredential-AccountType OMSWorkspace。 

- **如果要将 OMS 代理安装到现有云连接器设备上**，请执行以下步骤：

    1. 在 "CloudConnector.ini 文件 [Common]" 部分，设置 OMSEnabled = true。 

    2. 运行导入-Export-ccconfiguration。 

    3. 运行安装-CcOMSAgent。 

        > [!NOTE]
        > 如果从未设置 OMSWorkspace 凭据，则当您运行 CcOMSAgent 时，系统会提示您提供凭据。 

- **如果要更新已安装 OMS 代理的云连接器设备中的 OMS 工作区 ID 或密钥，请执行以下操作：**

    1. 若要配置 OMS ID 和密钥，请运行 Set-cccredential-AccountType OMSWorkspace。 

    2. 若要应用更新，请运行安装-CcOMSAgent。 

- **对于所有方案，请验证代理是否已连接，如下所示：**

    在 OMS 门户中，转到 "设置- \> 连接的源- \> Windows 服务器"。 你将看到已连接的计算机的列表。 

## <a name="configure-oms"></a>配置 OMS

接下来，你将需要使用 OMS 门户指定 OMS 配置。 具体来说，您将需要：

- 指定有关事件日志和性能计数器的信息。

- 创建通知。 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定有关事件日志和性能计数器的信息

在 OMS 门户中，您必须指定有关事件日志和性能计数器的信息，如下所示：

1. 转到 "设置 \> "-"Data- \> Windows 事件日志"，并为以下项添加事件日志： 

   - Lync Server

   - Application

     > [!NOTE]
     > 您必须在文本框中手动输入 Lync Server。 它不会作为选项显示在下拉列表中。 

     有关详细信息，请参阅 [Log Analytics 中的 Windows 事件日志数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 转到 "设置 \> "-"Data- \> Windows 性能计数器"，并为以下项添加性能计数器： 

   - **OS 级别计数器**。 您可以添加 OS 级别的计数器，如处理器使用情况、内存使用率、网络使用情况，或者您可以使用现有的解决方案（如容量和性能）、网络性能监视器而无需显式添加计数器。 无论您决定如何监视它们，Microsoft 建议您监视这些 OS 计数器。

   - **Skype For business 计数器**。 Skype for Business 提供了许多计数器。 您可以通过登录到任何中介服务器并打开性能监视器来查找这些计数器。 这些计数器以 "LS：" 开头。 Microsoft 建议您至少从以下容量计数器开始，添加其他感兴趣的计数器：

     活动呼叫总数：

       - LS： MediationServer) Current (_Total 的入站呼叫 \- 

       - LS： MediationServer- (_Total) Current 的出站呼叫 \- 

     活动媒体旁路呼叫总数：

       - LS： MediationServer) \- Active media 旁路呼叫 (_Total 的入站呼叫 

       - LS： MediationServer) \- Active media 旁路呼叫 (_Total 的出站呼叫 

     > [!NOTE]
     > 您必须在文本框中手动输入性能计数器。 它们不会作为选项显示在下拉列表中。 

     有关详细信息，请参阅 [Log Analytics 中的 Windows 和 Linux 性能数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>创建通知

OMS 中有两种类型的警报：结果警报和指标测量警报的数量。 有关创建通知的详细信息，请参阅 [在日志分析中使用警报规则](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)。

创建警报时，应考虑以下事项：

- 确保通知为 "结果数" 警报，这是默认选择。 

- 演示查询要求 "结果数" 设置为 "大于 0"。 

- 建议将 "时间" 窗口和 "警报频率" 设置为5分钟。 

- 建议您不要为演示通知启用 "抑制通知"。 

- 对于典型的通知方案，Microsoft 建议创建一对警报：一个错误警报和一个重置警报。 对于错误警报，请选择严重级别严重级别;对于 "重置警报"，选择 "严重级别信息"。

以下各节介绍如何创建示例警报。

 **创建警报对： "RTCMEDSRV 未在中介服务器中运行" 和 "RTCMEDSRV 已重新在中介服务器中运行"**

若要创建此通知对：

- 针对错误警报的查询是：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    查询使用计算机  *包含 "MediationServer"*  的计算机筛选器。 筛选器仅选择其名称中包含字符串 "MediationServer" 的计算机。

     您需要将筛选器替换为自己的计算机筛选器，或者只是将其删除。 您可以创建不带正则表达式的复杂字符串筛选器。 有关详细信息，请参阅 [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。 您还可以选择使用正则表达式。 此外，您还可以通过保存搜索查询并将该组用作警报查询中的计算机筛选器来创建计算机组。 有关详细信息，请参阅 [Log Analytics log 搜索中的计算机组](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)。

    对于每台计算机，错误查询将获取 RTCMEDSRV 服务启动和服务停止的最后一个事件日志。 如果最后一个事件是服务停止事件，它将返回一个日志; 否则，将返回一个日志。如果最后一个事件是服务启动事件，它将返回 nothing。 简言之，该查询将返回在时间窗口中停止的 RTCMEDSRV 的服务器的列表。 

- 对重置警报的查询为：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重置查询与错误查询完全相反。 对于每台计算机，如果最后一个事件是服务启动事件，它将返回一个，否则将返回一个。如果最后一个事件是服务停止事件，它将返回 nothing。

**创建警报对： "中介服务器中的并发呼叫过多" 和 "并发呼叫回退到正常负载"**

若要创建此警报：

- 针对错误警报的查询是：

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    对于每台计算机，查询将获取入站呼叫和出站呼叫的最后一个计数器，并对这两个值求和。 如果总和值超过500，它将返回一个日志; 否则，将返回一个日志。如果不是，它将返回 nothing。 简言之，该查询将返回时间窗口中其并发呼叫过多的服务器的列表。

- 对重置警报的查询为：

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    重置查询与错误查询完全相反。 对于每台计算机，查询将获取入站呼叫和出站呼叫的最后一个计数器，并对这两个值求和。 如果 sum 值小于500，它将返回一个日志; 否则，将返回一个日志。否则，它将返回 nothing。

**创建警报： "服务器上的 CPU 使用率 \> 90 或 RTCMEDIARELAY 已停止" 警报**

若要创建此警报，查询为：

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

如果处理器使用率超过90% 或服务被停止，则查询将从所有计算机获取所有处理器使用率计数器和服务停止事件，并返回一个日志。 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析 Log Analytics 存储库中的警报

若要分析存储库中的警报，请使用警报管理解决方案。 有关详细信息，请参阅 [Operations Management Suite 中的警报管理解决方案 (OMS) ](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>建议的最小监控集

若要确定事件日志和性能计数器的问题，请执行以下操作： 

- **事件日志。** 对于任何问题，应有一个事件对，其中有一组事件指示存在错误，另一个事件指示一切正常。 对于任何给定的时间段，它是最后记录的事件，用于指示是否某个时间段的 amiss。

- **性能计数器。** 监视的计数器应有一个阈值。

下表列出了 Microsoft 建议的用于通过列出停止和启动事件 Id 进行监视的服务：

|服务名称  <br/> |目标服务器角色  <br/> |停止事件 ID  <br/> |启动事件 ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |中介服务器  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |边缘服务器  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |边缘服务器  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |边缘服务器  <br/> |22003  <br/> |22002  <br/> |

下表列出了 Microsoft 建议监视的网络问题：


| 监视器名称  <br/>                                        | 目标服务器角色  <br/> | 成功事件 ID 表达式  <br/> | 错误事件 ID 表达式  <br/> | 故障示例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 中介服务器到网关连接失败  <br/>    | 中介服务器  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 中介服务器到网关呼叫完成失败  <br/> | 中介服务器  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 关键网络问题  <br/>                           | 边缘服务器  <br/>        | 14353                              |                                  | 12288  <br/>           |

下面列出了应监视的呼叫容量计数器。 对于云连接器标准版，这些号码应小于500。小于50的云连接器最低版本。

- LS： MediationServer) Current (_Total 的入站呼叫 \- 

- LS： MediationServer- (_Total) Current 的出站呼叫 \- 

- LS： MediationServer) \- Active media 旁路呼叫 (_Total 的入站呼叫

- LS： MediationServer) \- Active media 旁路呼叫 (_Total 的出站呼叫

## <a name="see-also"></a>另请参阅

有关使用 OMS 的详细信息，请参阅以下内容：

- [在日志分析中使用日志搜索查找数据](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure 日志分析语言参考](https://docs.loganalytics.io/docs/Language-Reference)

- [了解日志分析中的警报](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [将 Windows 计算机连接到 Azure 中的 Log Analytics 服务](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


