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
description: 阅读本主题，了解如何使用 Microsoft Operations Management Suite （OMS）监视你的云连接器版本2.1 和更高版本的部署。
ms.openlocfilehash: 1dcac3519624cef898622f915b08b24363453b84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799622"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>使用 Operations Management Suite (OMS) 监视云连接器

阅读本主题，了解如何使用 Microsoft Operations Management Suite （OMS）监视你的云连接器版本2.1 和更高版本的部署。

现在，你可以使用 Operations Management Suite （OMS）（Microsoft 云 IT 管理解决方案）监视你的云连接器版本2.1 和更高版本的部署。 OMS 日志分析使你能够监视和分析资源（包括物理和虚拟机）的可用性和性能。 有关 OMS 和 Log Analytics 的详细信息，请参阅[什么是操作管理套件（OMS）？](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)。

本主题包括以下部分：

- 先决条件

- 将云连接器配置为使用 OMS

- 配置 OMS

- 分析 Log Analytics 存储库中的警报

- 推荐的监视集

## <a name="prerequisites"></a>先决条件

在你可以使用 OMS 监视你的云连接器部署之前，你将需要以下内容：

- **Azure 帐户和 OMS 工作区。** 如果你尚没有 Azure 帐户，则需要创建一个才能使用 OMS 日志分析。 有关如何创建 Azure 帐户和设置 OMS 工作区的信息，请参阅[Log Analytics 工作区入门](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)。

- **云连接器版本2.1 或更高版本**

- 对于云连接器监视，需要**日志分析新的日志搜索**。 有关详细信息，请参阅[将 Azure 日志分析工作区升级到新的日志搜索](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)。

## <a name="configure-cloud-connector-to-use-oms"></a>将云连接器配置为使用 OMS

你将需要将云连接器本地环境配置为使用 OMS。 若要执行此操作，你需要你的 OMS 工作区 ID 和密钥，你可以使用 OMS 门户找到该工作区 ID 和密钥\>，如下所示\> ：设置--连接的源-Windows 服务器：

![云连接器 OMS 屏幕截图](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

将云连接器配置为使用 OMS 的方式取决于你的方案：

- **如果要安装新的云连接器装置或想要重新部署装置**，请在运行 CcAppliance 之前执行以下步骤：

1. 在 "CloudConnector file [Common]" 部分中，将 OMSEnabled 参数设置为 True。

    每当部署或升级云连接器时，它都将尝试将 OMS 代理自动安装到 Vm。 启用此功能，以便 OMS 代理可以在云连接器自动更新后继续使用。

2. 若要配置 OMS ID 和 key，请运行 CcCredential-AccountType OMSWorkspace。 

- **如果要将 OMS 代理安装到现有云连接器设备上**，请执行以下步骤：

1. 在 "CloudConnector file [Common]" 部分中，设置 OMSEnabled = true。 

2. 运行导入-CcConfiguration。 

3. 运行安装-CcOMSAgent。 

    > [!NOTE]
    > 如果从未设置 OMSWorkspace 凭据，则当你运行 install-CcOMSAgent 时，系统会提示你提供凭据。 

- **如果要在已安装 OMS 代理的云连接器装置中更新 OMS 工作区 ID 或密钥，请执行以下操作：**

1. 若要配置 OMS ID 和 key，请运行 CcCredential-AccountType OMSWorkspace。 

2. 若要应用更新，请运行安装-CcOMSAgent。 

- **对于所有方案，请验证代理是否已连接，如下所示：**

    在 OMS 门户中，转到 "设置\> -已连接\>的源-Windows 服务器"。 您将看到已连接的计算机列表。 

## <a name="configure-oms"></a>配置 OMS

接下来，你将需要使用 OMS 门户指定你的 OMS 配置。 具体地说，你需要：

- 指定有关事件日志和性能计数器的信息。

- 创建通知。 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定有关事件日志和性能计数器的信息

在 OMS 门户中，你必须指定有关事件日志和性能计数器的信息，如下所示：

1. 转到 "设置\>"-\>"数据-Windows 事件日志"，并为以下内容添加事件日志： 

   - Lync Server

   - 应用程序

     > [!NOTE]
     > 您必须在文本框中手动输入 Lync 服务器。 它不会显示为下拉列表中的一个选项。 

     有关详细信息，请参阅[日志分析中的 Windows 事件日志数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 转到 "设置\>"-\> "数据-Windows 性能计数器"，然后为以下内容添加性能计数器： 

   - **操作系统级别计数器**。 你可以添加 OS 级别计数器，如处理器使用率、内存使用情况、网络使用情况，或者你可以使用容量和性能等现有解决方案，而无需显式添加计数器。 无论您决定如何监视它们，Microsoft 建议你监视这些操作系统计数器。

   - **Skype For business 计数器**。 Skype for Business 提供许多计数器。 你可以通过登录到任何中介服务器并打开性能监视器来查找这些计数器。 这些计数器以 "LS：" 开头。 Microsoft 建议你至少从以下容量计数器开始，并添加其他感兴趣的容量计数器：

     活动呼叫总数：

   - LS： MediationServer-入站通话（_Total\- ）电流 

   - LS： MediationServer-拨出电话（_Total\- ）电流 

     总活动媒体绕过通话：

   - LS： MediationServer-入站呼叫（_Total\- ）主动媒体绕过呼叫 

   - LS： MediationServer-出站呼叫（_Total\- ）主动媒体绕过呼叫 

     > [!NOTE]
     > 必须在文本框中手动输入性能计数器。 它们不会显示为下拉列表中的选项。 

     有关详细信息，请参阅[Log Analytics 中的 Windows 和 Linux 性能数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>创建通知

OMS 中有两种类型的警报： "结果" 警报和 "指标度量" 警报的数量。 有关创建警报的详细信息，请参阅[在日志分析中使用警报规则](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)。

创建通知时应考虑以下事项：

- 确保警报为 "结果数" 警报，这是默认选择。 

- 演示查询要求 "结果数" 设置为 "大于 0"。 

- 建议你将时间窗口和警报频率设置为5分钟。 

- 建议您不要为演示通知启用 "抑制警报"。 

- 对于典型的通知方案，Microsoft 建议创建一对警报：一个错误警告和一个重置警报。 对于错误警报，选择严重级别 "严重级别";对于 "重置通知"，选择 "严重级别信息"。

以下部分介绍了如何创建示例警报。

 **创建通知对： "RTCMEDSRV 未在中介服务器中运行" 和 "RTCMEDSRV 已重新在中介服务器中运行"**

要创建此通知对，请执行以下操作：

- 针对错误警报的查询是：

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    查询使用计算机的计算机筛选器 *，其中包含 "MediationServer"* 。 筛选器仅选择其名称包含字符串 "MediationServer" 的计算机。

     你可以将筛选器替换为你自己的计算机筛选器，或只是删除它。 可以创建不带正则表达式的复杂字符串筛选器。 有关详细信息，请参阅[字符串运算符](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。 您也可以选择使用正则表达式。 此外，你可以通过保存搜索查询并使用该组作为你的警报查询中的计算机筛选器来创建计算机组。 有关详细信息，请参阅[日志分析日志搜索中的计算机组](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)。

    对于每台计算机，错误查询将获取 RTCMEDSRV 服务启动和服务停止的最后一个事件日志。 如果最后一个事件是服务停止事件，它将返回一个日志;如果最后一个事件是服务启动事件，它将返回 nothing。 简言之，该查询将返回 RTCMEDSRV 在时间窗口中停止的服务器的列表。 

- 重置警报的查询是：

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重置查询与错误查询的内容完全相反。 对于每台计算机，如果最后一个事件是服务启动事件，它将返回一个，否则返回如果最后一个事件是服务停止事件，它将返回 nothing。

  **创建通知对： "中介服务器中的并发呼叫过多" 和 "并发呼叫回退到正常负载"**

要创建此警报，请执行以下操作：

- 针对错误警报的查询是：

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    对于每台计算机，查询将获取入站呼叫和出站呼叫的最后计数器，并对这两个值求和。 如果 sum 值超过500，它将返回一个日志;如果不是，它将返回 nothing。 简而言之，该查询将返回其并发通话在时间窗口中过多的服务器的列表。

- 重置警报的查询是：

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    重置查询与错误查询的内容完全相反。 对于每台计算机，查询将获取入站呼叫和出站呼叫的最后计数器，并对这两个值求和。 如果 sum 值小于500，它将返回一个日志;否则，它将返回 nothing。

  **创建通知： "CPU 使用率\> 90 或 RTCMEDIARELAY 已停止在服务器中" 警报**

若要创建此警报，查询是：

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

如果处理器使用率超过90% 或服务被停止，查询将从所有计算机获取所有处理器使用率计数器和服务停止事件，并返回一个日志。 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析 Log Analytics 存储库中的警报

若要分析存储库中的警报，请使用警报管理解决方案。 有关详细信息，请参阅[Operations Management Suite （OMS）中的警报管理解决方案](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>建议的最低监视设置

若要识别事件日志和性能计数器的问题，请执行以下操作： 

- **事件日志。** 对于任何问题，应有一个事件对，其中一组事件指示有问题，另一组指示一切正常。 在任何给定时间段内，将显示最后记录的事件，该事件将指示是否 amiss 该时间段的内容。

- **性能计数器。** 监视的计数器应有一个阈值。

下表列出了 Microsoft 建议的通过列出停止和启动事件 Id 进行监视的服务：

|服务名称  <br/> |目标服务器角色  <br/> |停止事件 ID  <br/> |开始事件 ID  <br/> |
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

下表列出了应监视的通话容量计数器。 对于云连接器标准版，这些号码应少于 500;小于50的云连接器最小版本。

- LS： MediationServer-入站通话（_Total\- ）电流 

- LS： MediationServer-拨出电话（_Total\- ）电流 

- LS： MediationServer-入站呼叫（_Total\- ）主动媒体绕过呼叫

- LS： MediationServer-出站呼叫（_Total\- ）主动媒体绕过呼叫

## <a name="see-also"></a>另请参阅

有关使用 OMS 的详细信息，请参阅以下内容：

- [在日志分析中使用日志搜索查找数据](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure 日志分析语言参考](https://docs.loganalytics.io/docs/Language-Reference)

- [了解日志分析中的警报](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [将 Windows 计算机连接到 Azure 中的 Log Analytics 服务](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


