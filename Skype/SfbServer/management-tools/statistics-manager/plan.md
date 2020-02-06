---
title: Skype for Business Server 的统计信息管理器规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要：阅读本主题，了解 Skype for business 服务器的统计信息管理器。
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816231"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>Skype for Business Server 的统计信息管理器规划

**摘要：** 阅读本主题，了解 Skype for business 服务器的统计信息管理器。

 Skype for Business Server 统计信息管理器是一个功能强大的工具，可让你实时查看 Skype for Business Server 运行状况和性能数据。 你可以每隔几秒钟轮询数百台服务器的性能数据，并且在统计信息管理器网站上立即查看结果。

你可以使用统计管理器确定持续的性能问题、查看你的环境的计划更改的结果、跟踪中断的解决情况以及更多功能。 在该框外，统计管理器配置有关键运行状况指示器（KHI）阈值，并且可以进行自定义以满足你的部署的独特需求。

你可以在单个服务器托管所有服务器端统计信息管理器组件的本地部署中部署统计信息管理器。 有关部署统计信息管理器的详细信息，请参阅[部署 Skype for Business 服务器的统计管理器](deploy.md)。 如果已有一个现有的统计信息管理器部署，但尚未升级到版本2.0，请参阅[版本2.0 中的新增功能](plan.md#BKMK_WhatsNew)和[Skype for Business 服务器的升级统计管理器](upgrade.md)。

本主题包括以下部分：

- [功能和功能](plan.md#BKMK_Features)

- [版本2.0 中的新增功能](plan.md#BKMK_WhatsNew)

- [组件](plan.md#BKMK_Components)

- [本地部署](plan.md#BKMK_DeploymentOptions)

- [要求](plan.md#BKMK_Requirements)

- [安全注意事项](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>功能和功能
<a name="BKMK_Features"> </a>

统计信息管理器允许您：

- 实时查看所有服务器的原始数据。 （数据以极其高的费率进行采样，并在不到一秒钟的时间内发送到网站。）

- 查看针对特定角色聚合的数据;例如，前端服务器、中介服务器、边缘服务器等。

- 向下钻取以查看特定网站、网站内特定池的数据，以及池中的特定服务器的数据。

- 创建自定义图表，以便默认显示所选计数器。

- 仅在 x 轴和 y 轴上或在 x 轴上缩放和平移。

- 使用日期范围或时间点来筛选数据。

- 基于已建立的密钥运行状况指示器（KHIs）查看服务器性能。 KHIs 表示具有定义的正常范围的性能计数器的集合。

- 查看每个计数器的详细指标。

- 比较多个人口或服务器上的数据。

- 查看潜在计数器报表，以标识不向仪表板服务报告当前数据的代理。

- 将图表数据的特定实例保存到文件。

- 实时查看 KHIs，包括更新。 如果启用了 "历史记录" 视图，则仅显示新的失败。

  - 一次查看所有 KHIs

  - 按服务器查看 KHIs （横向视图）

  - 查看 KHI 定义

## <a name="whats-new-in-release-20"></a>版本2.0 中的新增功能
<a name="BKMK_WhatsNew"> </a>

下面介绍了版本2.0 中的新增功能。 如果你有现有的统计信息管理器部署，但尚未升级，请参阅[升级 Skype for Business 服务器的统计信息管理器](upgrade.md)。

- 已为 Edge 媒体、结构运行状况、池故障转移和注册方案添加了方案视图。

- 为 SQL server 添加了许多新的计数器、更多 Skype for Business 使用率计数器等。

- 统计信息管理器代理的观察程序节点集成-如果在观察程序节点上安装了代理，它会将合成事务统计信息作为计数器报告回统计信息管理器。

- 许多可靠性和性能改进。

若要验证你正在运行的统计信息管理器网站的版本，请执行以下操作：

- 在文件资源管理器中，打开（默认目录） C:\Program Files\Skype for Business Server StatsMan WebSite\bin

- 右键单击 StatsManHubWebSite 并查看其属性

- 产品版本将在“说明”详细信息中显示。

## <a name="components"></a>组件
<a name="BKMK_Components"> </a>

统计信息管理器包含以下组件：

- **工程师.** 在每个受监视的服务器上运行的轻量代理。 代理允许对具有本地聚合的性能计数器进行可配置的高速率轮询。

- **监听器.** 从所有代理接收数据并跨人口聚合数据的服务器端 API。

- **中心.** 充当系统的客户端 API，在 web 服务器上运行，并向通过网站连接的客户端提供实时数据更新。 （中心将自动作为网站 msi 的一部分进行安装。）

- **网站.** 将系统中可用的所有功能集中在一起的用户界面。

此外，统计信息管理器需要**Redis**，这是一个开放来源的数据结构服务器，用于内存中的缓存。 有关下载 Redis 的详细信息，请参阅[部署统计信息管理器](deploy.md#BKMK_Deploy)。

## <a name="on-premises-deployment"></a>本地部署
<a name="BKMK_DeploymentOptions"> </a>

在本地部署中，单个服务器托管所有服务器端统计信息管理器组件。

下图显示了一个本地部署，其中统计信息管理器网站、中心、侦听器和 Redis 缓存系统托管在一台计算机上。 统计信息管理器监视三个 Skype for Business 服务器，每个服务器都有一个代理将数据传输到侦听器。 用户连接到单个网站以查看统计信息管理器聚合的所有数据：

![统计管理器本地部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>要求
<a name="BKMK_Requirements"> </a>

部署统计信息管理器之前，需要考虑以下软件、网络和硬件要求。

### <a name="software-requirements"></a>软件要求

- Windows Server 2016 和2019

- IIS （自动安装）

- Redis

- 统计管理器服务（自动安装）

- PSExec-执行远程代理部署所需

- .NET 4.5 （包含于 2012 R2）-工程师和服务器端组件所需
- 下载[Skype For Business 服务器，实时统计信息管理器（64位）](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>网络要求


|**托管服务器**|**代理**|**监听器**|
|:-----|:-----|:-----|
|最低千兆位全双工网络。  <br/> |出站 TCP 端口8443（可自定义端口号）与侦听器通信。  <br/> |侦听器端口在所有服务器上必须是相同的。  <br/> |
|已打开入站 TCP 端口80或443以托管网站。  <br/> |||
|代理与之通信的入站 TCP 端口8443（可自定义端口号）。  <br/> |||

在安装过程中，将自动创建侦听器和网站的防火墙端口。 对于代理，安装假定默认情况下允许出站 TCP 连接。

### <a name="hardware-requirements"></a>硬件要求

在本地部署中，如果单个服务器托管所有服务器端统计信息管理器组件，则具有 16 GB RAM 和 4 CPU 的服务器应该能够支持平均每秒150样本。 若要确定可以支持多少个计数器/代理，请使用以下计算：

100 server \*80 每\*秒从每个代理/60 秒开始每分钟1采样 = 大约每秒133采样。

## <a name="security-considerations"></a>安全注意事项
<a name="BKMK_Security"> </a>

服务器之间的所有流量均已加密。

- 加密 HTTPS 流量将通过端口8443（默认情况）从代理发送到侦听器服务器。

- 代理将在服务器上验证 SSL 指纹，以确保监听器服务器是预期的收件人。 请注意，代理使用证书指纹验证（而不是链验证）。 由于可能使用自签名证书，因此它不会执行完整证书验证。

- 当该代理达到可信后，该监听器将由监听器验证，然后由监听器验证。

- 代理将通过与侦听器的连接开始传输性能数据。

## <a name="for-more-information"></a>有关详细信息
<a name="BKMK_Security"> </a>

有关详细信息，请参阅：

- [部署 Skype for Business Server 的统计信息管理器](deploy.md)

- [更新 Skype for Business Server 的统计信息管理器](upgrade.md)

- [对 Skype for Business Server 的统计信息管理器进行故障排除](troubleshoot.md)
