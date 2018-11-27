---
title: 规划业务 Server 为统计信息管理器中的 Skype
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要： 阅读本主题可为 Skype 业务服务器了解有关统计信息管理器。
ms.openlocfilehash: 390a49a4346af5ab1bc2005db04d99fd60bad056
ms.sourcegitcommit: 160ced7013c1c46595c4362c2f32c5769b082294
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699850"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>规划业务 Server 为统计信息管理器中的 Skype

**摘要：** 阅读此主题以业务服务器的 Skype 了解有关统计信息管理器。

 适用于业务服务器 Skype 的统计信息管理器是一个强大的工具，允许您查看 Skype 的实时业务服务器运行状况和性能数据。 可以跨服务器数百每隔几秒钟轮询性能数据，并立即统计信息管理器网站上查看结果。

统计信息管理器可用于确定持续的性能问题，与您的环境中查看计划更改的结果，跟踪的中断，分辨率和更多。 现成，统计信息管理器中使用键运行状况指示器 (KHI) 阈值配置，可以对其进行自定义，以满足您的部署唯一需求。

您可以在本地部署中的单个服务器承载的所有服务器端统计信息管理器组件部署统计信息管理器。 有关部署统计信息管理器的详细信息，请参阅[适用于业务服务器 Skype 部署统计信息管理器](deploy.md)。 如果您已有现有部署的统计信息管理器中，但尚未升级到版本 2.0，请参阅[What's new in 版本 2.0](plan.md#BKMK_WhatsNew)和[Skype 业务服务器的升级统计信息管理器](upgrade.md)。

本主题包括以下部分：

- [特性和功能](plan.md#BKMK_Features)

- [What's new in 版本 2.0](plan.md#BKMK_WhatsNew)

- [组件](plan.md#BKMK_Components)

- [在本地部署](plan.md#BKMK_DeploymentOptions)

- [要求](plan.md#BKMK_Requirements)

- [安全注意事项](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>特性和功能
<a name="BKMK_Features"> </a>

统计信息管理器，您可以：

- 实时查看所有服务器的原始的数据。 （数据取样速率非常高和小于一秒内发送到网站。）

- 为特定的角色; 聚合的视图数据例如，前端服务器、 中介服务器、 边缘服务器，等。

- 查看特定网站、 网站内的特定池和池中然后特定服务器的数据向下钻取。

- 创建自定义图表，以便选择计数器显示默认情况下。

- 缩放和平移上两个 x 轴和 y 轴或仅在 x 轴上。

- 筛选数据的时间使用日期范围或点。

- 查看服务器性能基于建立关键运行状况指示器 (KHIs)。 KHIs 表示取值范围定义为正常的性能计数器的集合。

- 查看每个计数器的详细的指标。

- 比较跨多个选中或服务器的数据。

- 查看延迟计数器报告来标识不当前数据报告到仪表板服务的代理。

- 保存到文件的图表数据的特定实例。

- 实时，包括更新视图 KHIs。 如果已启用的历史记录视图，显示仅新失败。

  - 一次查看所有 KHIs

  - 查看 KHIs 服务器 （横向视图）

  - 视图 KHI 定义

## <a name="whats-new-in-release-20"></a>What's new in 版本 2.0
<a name="BKMK_WhatsNew"> </a>

以下介绍 what's new in 版本 2.0。 如果您拥有现有部署的统计信息管理器中，并且尚未升级，请参阅[适用于业务服务器 Skype 升级统计信息管理器](upgrade.md)。

- 已为边缘媒体、 结构运行状况、 池故障转移和注册方案添加了方案视图。

- 许多新计数器已添加为 SQL 服务器和多个 Skype 的业务使用率计数器，等等。

- 观察程序节点集成的统计信息管理器代理-如果观察程序节点上安装代理将报告综合事务统计信息计数器为返回到统计信息管理器。

- 大量的可靠性和性能改进。

若要验证您运行的统计信息管理器网站的版本：

- 在文件资源管理器，打开 （默认目录） 的业务服务器 StatsMan WebSite\bin C:\Program Files\Skype

- 右键单击 StatsManHubWebSite.dll 并查看其属性

- 产品版本将在“说明”详细信息中显示。

## <a name="components"></a>组件
<a name="BKMK_Components"> </a>

统计信息管理器包括以下组件：

- **代理。** 每个监控服务器运行轻型代理。 代理允许具有本地聚合的性能计数器的可配置率太高轮询。

- **侦听器。** 服务器端 API 的从所有代理接收数据，并选中跨汇总数据。

- **集线器。** 客户端 API 系统上的 web 服务器，请运行并向客户端连接通过网站提供实时数据更新充当。 （集线器会自动安装网站 msi 的一部分。）

- **网站。** 用户界面的组合系统中可用的所有功能。

此外，统计信息管理器要求**Redis**，用于在内存缓存的开放源代码数据结构服务器。 有关下载 Redis 的详细信息，请参阅[部署统计信息管理器](deploy.md#BKMK_Deploy)。

## <a name="on-premises-deployment"></a>在本地部署
<a name="BKMK_DeploymentOptions"> </a>

在本地部署中，一台服务器承载的所有服务器端统计信息管理器组件。

下图显示在本地部署中，在其中统计信息管理器网站、 集线器、 侦听器和 Redis 缓存系统承载一台计算机。 统计信息管理器所监控业务服务器，其中每个具有一个代理将数据传输到侦听器的三个的 Skype。 用户连接到单个网站以查看聚合由统计信息管理器中的所有数据：

![统计管理器本地部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>要求
<a name="BKMK_Requirements"> </a>

您将需要部署统计信息管理器之前，请考虑以下软件、 网络和硬件要求。

### <a name="software-requirements"></a>软件要求

- Windows Server 2016 和 2019

- IIS （自动安装）

- Redis

- （自动安装） 的统计信息管理器服务

- PSExec-需要执行远程代理部署

- 代理和服务器端组件所需的.NET 4.5 （附带 2012 R2）-
- 下载[Skype 的业务服务器实时统计信息管理器 （64 位）](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>网络要求


|**承载服务器**|**代理**|**侦听器**|
|:-----|:-----|:-----|
|全双工最低千兆位网络。  <br/> |出站 TCP 端口 8443 （可自定义端口号） 与侦听器进行通信。  <br/> |侦听器端口必须在所有服务器上相同。  <br/> |
|入站 TCP 端口 80 或 443 打开来承载网站。  <br/> |||
|入站代理与其通信的 TCP 端口 8443 （可自定义端口号）。  <br/> |||

安装过程中，将自动创建的侦听器和网站的防火墙端口。 针对代理，安装假定，默认情况下允许出站 TCP 连接。

### <a name="hardware-requirements"></a>硬件要求

在本地部署中，在其中一台服务器承载的所有服务器端统计信息管理器组件的服务器具有 16 GB 的 RAM 和 4 应能够支持大约 150 示例每秒平均 CPU 的。 若要确定可以支持多少个计数器/代理，请使用以下计算：

100 服务器\*80 计数器\*每分钟每个代理 / 60 秒 1 示例 = ~ 每秒 133 示例。

## <a name="security-considerations"></a>安全注意事项
<a name="BKMK_Security"> </a>

服务器之间的所有通信进行都加密。

- 加密的 HTTPS 通信将会通过端口 8443 （默认） 从代理发送到侦听器服务器。

- 代理将验证以确保侦听器服务器是预期的收件人的服务器上的 SSL 指纹。 请注意，代理使用证书指纹验证（而不是链验证）。 由于可能使用自签名证书，因此它不会执行完整证书验证。

- 代理是满足后侦听器是可信，将其然后由侦听器验证的代理必须提供密码。

- 代理开始通过连接到侦听器传输性能数据。

## <a name="for-more-information"></a>有关详细信息
<a name="BKMK_Security"> </a>

有关详细信息，请参阅以下文章：

- [为业务 Server 部署的 Skype 的统计信息管理器](deploy.md)

- [为业务服务器升级的 Skype 的统计信息管理器](upgrade.md)

- [解决的 Skype 的统计信息管理器的企业服务器](troubleshoot.md)

- [Skype for Business Server 统计信息管理器博客](https://blogs.technet.microsoft.com/dodeitte/2015/10/24/skype-for-business-server-real-time-statistics-manager)


