---
title: Skype for Business Server 2019 管理工具
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 了解 Skype for Business Server 2019 中的服务管理工具。'
ms.openlocfilehash: c666d76a232d64bb81892be96e64da1d544fe9cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306324"
---
# <a name="skype-for-business-server-2019-management-tools"></a><span data-ttu-id="09147-103">Skype for Business Server 2019 管理工具</span><span class="sxs-lookup"><span data-stu-id="09147-103">Skype for Business Server 2019 Management Tools</span></span>
 
<span data-ttu-id="09147-104">**摘要:** 了解 Skype for Business Server 2019 中的服务管理工具。</span><span class="sxs-lookup"><span data-stu-id="09147-104">**Summary:** Learn about the service management tools in Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="09147-105">Skype for Business Server 2019 提供支持企业级协作要求的即时消息 (IM)、状态、会议和电话解决方案。</span><span class="sxs-lookup"><span data-stu-id="09147-105">Skype for Business Server 2019 offers instant messaging (IM), presence, conferencing, and telephony solutions that support enterprise-level collaboration requirements.</span></span> <span data-ttu-id="09147-106">用于管理这些服务的工具灵活而强大。</span><span class="sxs-lookup"><span data-stu-id="09147-106">The tools to manage these services are both flexible and powerful.</span></span>
  
## <a name="skype-for-business-server-2019-tools"></a><span data-ttu-id="09147-107">Skype for Business Server 2019 工具</span><span class="sxs-lookup"><span data-stu-id="09147-107">Skype for Business Server 2019 Tools</span></span>

||<span data-ttu-id="09147-108">**内容**</span><span class="sxs-lookup"><span data-stu-id="09147-108">**Content**</span></span>|<span data-ttu-id="09147-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="09147-109">**Description**</span></span>|
|:-----|:-----|:-----|
|![仪表板图标](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="09147-111">呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="09147-111">Call Quality Dashboard</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534842) <br/> |<span data-ttu-id="09147-112">通话质量仪表板 (CQD) 是一种 web 门户, 用于根据 Skype for Business 环境中的经验 (QoE) 数据快速创建和组织报表。</span><span class="sxs-lookup"><span data-stu-id="09147-112">The Call Quality Dashboard (CQD) is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data from your Skype for Business environment.</span></span> <span data-ttu-id="09147-113">CQD 部署 SSAS 多维数据集以在 QoEMetrics 数据库中汇总数据，使得用户能够创建和修改报告，并实时查看报告更新。</span><span class="sxs-lookup"><span data-stu-id="09147-113">The CQD deploys a SSAS cube to aggregate the data in the QoEMetrics database, which enables users to create and modify reports and see them update in real-time.</span></span> <span data-ttu-id="09147-114">此外，CQD 还显示了 Web API，使得用户可以编程访问要用于自定义仪表板的多维数据集数据。</span><span class="sxs-lookup"><span data-stu-id="09147-114">Additionally, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>  <br/> |
|![KHI 的图标](../SfbServer/media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[<span data-ttu-id="09147-116">KHI 资源</span><span class="sxs-lookup"><span data-stu-id="09147-116">KHI Resources</span></span>](https://www.microsoft.com/download/details.aspx?id=57519) <br/> |<span data-ttu-id="09147-p103">关键运行状况指示器 (KHI) 是提供了建议阀值的性能计数器，旨在找出可能影响用户体验的问题。KHI 指南概述了用于维持部署正常运行的操作流程和补救步骤，并包含了一个用于配置 KHI 数据收集器的 PowerShell 示例脚本和一份可分析 KHI 性能数据的分析和定义工作簿。</span><span class="sxs-lookup"><span data-stu-id="09147-p103">Key Health Indicators (KHI) are Performance Counters with recommended thresholds aimed at revealing problems that can impact the user experience. The KHI Guide outlines the operational process and remediation steps to maintain a healthy deployment, and includes a sample PowerShell script used to configure KHI Data Collectors and an Analysis and Definitions Workbook which can analyze KHI performance data.</span></span>  <br/> |
|![仪表板图标](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="09147-120">Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09147-120">Statistics Manager for Skype for Business Server 2015</span></span>](../SfbServer/management-tools/statistics-manager/statistics-manager.md) <br/> |<span data-ttu-id="09147-121">StatsMan 是一个用于实时查看 KHI 计算和查看跨基础结构聚合的图形式性能计数器的仪表板解决方案。</span><span class="sxs-lookup"><span data-stu-id="09147-121">StatsMan is a dashboard solution for viewing KHI calculations in real-time as well as graphed performance counters aggregated across your infrastructure.</span></span> <span data-ttu-id="09147-122">可以使用该仪表板准确指明持续出现的性能问题、查看对您的环境所做的计划更改的结果、跟踪中断的解决方法等。</span><span class="sxs-lookup"><span data-stu-id="09147-122">The dashboard can be used to pinpoint ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="09147-123">在该对话框中, 它配置了来自 KHI 资源的 KHI 阈值, 并且可以进行自定义以满足你的部署的独特需求。</span><span class="sxs-lookup"><span data-stu-id="09147-123">Out of the box, it is configured with KHI thresholds from the KHI Resources, and can be customized to suit your deployment's unique needs.</span></span>  <br/> |
|![SCOM 图标](../SfbServer/media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[<span data-ttu-id="09147-125">使用 SCOM 管理包管理 Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="09147-125">Manage Skype for Business Server 2019 using SCOM Management pack</span></span>](tools/scom-management-pack-use-2019.md) <br/> |<span data-ttu-id="09147-126">通过使用 Skype for Business Server 2019 管理包, 您可以主动识别并解决潜在问题。</span><span class="sxs-lookup"><span data-stu-id="09147-126">By using Skype for Business Server 2019 Management Packs, you can identify and address potential issues proactively.</span></span> <span data-ttu-id="09147-127">通过这种方式, Skype for business Server 2019 管理包扩展了 System Center Operations Manager 的功能。</span><span class="sxs-lookup"><span data-stu-id="09147-127">In this way, the Skype for Business Server 2019 Management Packs extend the capabilities of System Center Operations Manager.</span></span>  <br/> |
|![仪表板图标](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="09147-129">Skype for Business Server 容量计划计算器</span><span class="sxs-lookup"><span data-stu-id="09147-129">Skype for Business Server Capacity Planning Calculator</span></span>](../SfbServer/management-tools/capacity-planning-calculator.md) <br/> |<span data-ttu-id="09147-130">Skype for Business Server 2015/2019 容量规划计算器可帮助你为组织的需求建模拓扑。</span><span class="sxs-lookup"><span data-stu-id="09147-130">The Skype for Business Server 2015/2019 Capacity Planning Calculator helps you model a topology for your organization's needs.</span></span>  <br/> |
||
