---
title: 规划 Skype for Business Server 的统计信息管理器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要：阅读本主题，了解适用于 Skype for Business Server 的统计信息管理器。
ms.openlocfilehash: 166390fe0f034c907e21a3d3147b516d9f502954
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857399"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>规划 Skype for Business Server 的统计信息管理器

**摘要：** 阅读本主题，了解适用于 Skype for Business Server 的统计信息管理器。

 统计信息管理器Skype for Business Server一个强大的工具，可用于实时Skype for Business Server运行状况和性能数据。 你可以每隔几秒钟轮询数百台服务器的性能数据，并立即在统计信息管理器网站上查看结果。

可以使用统计信息管理器来确定持续的性能问题、查看环境计划更改的结果、跟踪中断的解决等等。 统计信息管理器开箱即用，配置了关键运行状况指示器 (KHI) 阈值，可进行自定义以满足部署的独特需求。

您可以在本地部署中部署统计信息管理器，其中一台服务器承载所有服务器端统计信息管理器组件。 有关部署统计信息管理器的信息，请参阅部署统计信息管理器[Skype for Business Server。](deploy.md) 如果你已拥有统计信息管理器的现有部署，但尚未升级到 2.0 版，请参阅[2.0](plan.md#BKMK_WhatsNew)版中的新增功能和升级统计信息管理器[Skype for Business Server。](upgrade.md)

本主题包含以下各部分：

- [特性和功能](plan.md#BKMK_Features)

- [2.0 版中的新增功能](plan.md#BKMK_WhatsNew)

- [组件](plan.md#BKMK_Components)

- [本地部署](plan.md#BKMK_DeploymentOptions)

- [要求](plan.md#BKMK_Requirements)

- [安全注意事项](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>特性和功能
<a name="BKMK_Features"> </a>

统计信息管理器允许你：

- 实时查看所有服务器的原始数据。  (数据以非常高的速率进行采样，并不到一秒钟就发送到网站。) 

- 查看为特定角色聚合的数据;例如，前端服务器、中介服务器、边缘服务器等。

- 向下钻取以查看特定站点、站点中的特定池以及池中的特定服务器的数据。

- 创建自定义图表，以便默认显示选择的计数器。

- 仅在 x 轴和 y 轴或 x 轴上缩放和平移。

- 使用日期范围或时间点筛选数据。

- 根据 KHIS 中已建立的关键运行状况 (查看) 。 KHIS 表示具有定义的正常范围的性能计数器的集合。

- 查看每个计数器的详细指标。

- 跨多个用户或服务器比较数据。

- 查看潜在计数器报告，以标识未向仪表板服务报告当前数据的代理。

- 将图表数据的特定实例保存到文件中。

- 实时查看 KHIS，包括更新。 如果启用历史记录视图，则只显示新故障。

  - 一次查看所有 KHIS

  - 按服务器和横向视图视图 (KHIS) 

  - 查看 KHI 定义

## <a name="whats-new-in-release-20"></a>2.0 版中的新增功能
<a name="BKMK_WhatsNew"> </a>

下面介绍了 2.0 版中的新增功能。 如果你有统计信息管理器的现有部署，并且尚未升级，请参阅升级统计信息管理器[了解Skype for Business Server。](upgrade.md)

- 已针对边缘媒体、Fabric 运行状况、池故障转移和注册方案添加了方案视图。

- 为服务器添加了许多新的计数器SQL添加了更多Skype for Business计数器，等等。

- 统计信息管理器代理的观察程序节点集成 - 如果代理安装在观察程序节点上，它将综合事务统计信息作为计数器报告回统计信息管理器。

- 大量可靠性和性能改进。

要验证您正在运行的统计信息管理器网站的版本，请运行：

- 在文件资源管理器中，打开 () C：\Program Files\Skype for Business Server StatsMan WebSite\bin 的默认目录

- 右键单击StatsManHubWebSite.dll并查看其属性

- 产品版本将显示在"说明详细信息"中。

## <a name="components"></a>组件
<a name="BKMK_Components"> </a>

统计信息管理器由以下组件组成：

- **代理。** 在每个受监控服务器上运行的轻型代理。 代理允许使用本地聚合对性能计数器进行可配置的高速率轮询。

- **侦听器。** 接收来自所有代理的数据并聚合各总体数据的服务器端 API。

- **中心。** 充当系统的客户端 API，在 Web 服务器 () ，并提供通过网站连接的客户端实时数据更新。  (中心将自动安装为网站 msi.) 

- **网站。** 将系统中所有可用功能汇集在一起的用户界面。

此外，统计信息管理器需要 **Redis，** 这是一个开源数据结构服务器，用于内存中缓存。 有关下载 Redis 的信息，请参阅 [部署统计信息管理器](deploy.md#BKMK_Deploy) 。

## <a name="on-premises-deployment"></a>本地部署
<a name="BKMK_DeploymentOptions"> </a>

在本地部署中，单台服务器承载所有服务器端统计信息管理器组件。

下图显示了本地部署，其中统计信息管理器网站、中心、侦听器和 Redis 缓存系统托管在单个计算机上。 统计信息管理器监视三Skype for Business服务器，每个服务器都有一个将数据传输到侦听器的代理。 用户连接到单个网站以查看统计信息管理器聚合的所有数据：

![统计数据管理器本地部署。](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>要求
<a name="BKMK_Requirements"> </a>

在部署统计信息管理器之前，需要考虑以下软件、网络和硬件要求。

### <a name="software-requirements"></a>软件要求

- Windows Server 2016 和 2019

- IIS (自动安装) 

- Redis

- 自动安装统计信息 (管理器) 

- PSExec - 需要执行远程代理部署

- 2012 R2 (中包含的 .NET 4.5) - 代理和服务器端组件需要
- 下载[64 Skype for Business ServerReal-Time统计信息管理器 (64 位) ](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>网络要求


|**托管服务器**|**Agents**|**侦听器**|
|:-----|:-----|:-----|
|最小千兆位全双工网络。  <br/> |出站 TCP 端口 8443 (与侦听器) 可自定义的端口号。  <br/> |侦听器端口在所有服务器上必须相同。  <br/> |
|入站 TCP 端口 80 或 443 打开以承载网站。  <br/> |||
|入站 TCP 端口 8443 (代理) 可自定义的端口号。  <br/> |||

在安装过程中，将自动创建侦听器和网站的防火墙端口。 对于代理，安装假定默认情况下允许出站 TCP 连接。

### <a name="hardware-requirements"></a>硬件要求

在单台服务器托管所有服务器端统计信息管理器组件的本地部署中，具有 16 GB RAM 和 4 个 CPU 的服务器平均每秒应支持大约 150 个样本。 若要确定可以支持的计数器/代理数，请使用以下计算：

100 台服务器 80 个计数器，每个代理每分钟 1 个样本 \* \* /60 秒 = ~ 133 个样本/秒。

## <a name="security-considerations"></a>安全考虑事项
<a name="BKMK_Security"> </a>

服务器之间的所有通信都经过加密。

- 默认情况下，加密的 HTTPS 流量通过端口 8443 (代理) 代理服务器发送。

- 代理将验证服务器上 SSL 指纹，以确保侦听器服务器是预期收件人。 请注意，代理使用证书指纹验证 (而不是链验证) 。 它将不会执行完整证书验证，因为可以使用自签名证书。

- 在代理得到确认后，侦听器将呈现一个密码，然后由侦听器验证该代理。

- 代理开始通过连接到侦听器来传输性能数据。

## <a name="for-more-information"></a>更多详细信息
<a name="BKMK_Security"> </a>

有关详细信息，请参阅：

- [部署 Skype for Business Server 的统计信息管理器](deploy.md)

- [更新 Skype for Business Server 的统计信息管理器](upgrade.md)

- [对 Skype for Business Server 的统计信息管理器进行故障排除](troubleshoot.md)
