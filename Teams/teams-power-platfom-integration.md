---
title: Teams 与 Microsoft Power Platform 集成
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解 Teams 与 Microsoft Power Platform 工具（包括 Power BI、Power 应用、Power automate 和 Power Virtual Agents）的集成。
ms.openlocfilehash: 0fb05596fb5fa87ab4e209325cc35b7a3eae56d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804562"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="558a7-103">Teams 与 Microsoft Power Platform 集成</span><span class="sxs-lookup"><span data-stu-id="558a7-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="558a7-104">Microsoft Power Platform 可帮助用户使用低代码工具加速开发，以便使用 **Power BI** 分析数据、使用 **Power Apps** 构建自定义应用、使用 Power **Automate** 自动执行过程，以及使用 Power **Virtual Agents** 更快创建智能机器人。</span><span class="sxs-lookup"><span data-stu-id="558a7-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="558a7-105">随着远程和混合工作的转换，Microsoft Teams 使世界各地的人员能够继续创建、协作和沟通。</span><span class="sxs-lookup"><span data-stu-id="558a7-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="558a7-106">每天活动用户超过 7500 万，Teams 是用户完成工作的一种工作。</span><span class="sxs-lookup"><span data-stu-id="558a7-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="总结 Teams 和 Microsoft Power Platform 的图像":::

<span data-ttu-id="558a7-108">Microsoft Power Platform 与 Teams 提供了许多集成功能，可在 Teams 工作区中嵌入 **Power BI** 报表、嵌入使用 **Power Apps** 作为选项卡或个人应用创建的应用、触发来自任何消息的 Power **Automate** 流或使用自适应卡，以及将使用 Power **Virtual Agents** 创建的机器人添加到 Teams，供组织的其他成员交互。</span><span class="sxs-lookup"><span data-stu-id="558a7-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="558a7-109">从 2020 年 9 月开始，与 Microsoft Power Platform 的集成已改进，让用户无需离开 Teams 界面即可 *执行以下操作*：</span><span class="sxs-lookup"><span data-stu-id="558a7-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="558a7-110">使用 **Power BI** 创建和共享仪表板、报表和应用，以做出数据驱动的决策。</span><span class="sxs-lookup"><span data-stu-id="558a7-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="558a7-111">通过连接到新的基础数据平台 (Microsoft Dataverse for Teams) 、Microsoft 365 或其他数据源中通过连接器存储的业务数据，使用集成的 **Power Apps** Studio 创建和共享低代码、特意构建的应用。</span><span class="sxs-lookup"><span data-stu-id="558a7-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="558a7-112">使用 Power Automate 在应用和服务之间创建自动化工作流，以同步文件、获取通知、 **收集数据等**。</span><span class="sxs-lookup"><span data-stu-id="558a7-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="558a7-113">使用 Power **Virtual Agents** 的引导式无代码图形界面生成机器人，在 Teams 中轻松创建数字助手，并可供同事聊天。</span><span class="sxs-lookup"><span data-stu-id="558a7-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="558a7-114">用于创建应用、机器人和工作流的新功能由 [Teams、Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541)的新内置低代码数据平台作为后盾，该平台提供关系数据存储、丰富的数据类型、企业级治理和一键式解决方案部署。</span><span class="sxs-lookup"><span data-stu-id="558a7-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="558a7-115">Dataverse for Teams 构建在 [Microsoft Dataverse 的顶层](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)。</span><span class="sxs-lookup"><span data-stu-id="558a7-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="558a7-116">借助 Dataverse for Teams，Teams 用户可以从 Teams 应用商店中查找并安装自定义的现成解决方案，这些解决方案可展示各个行业的常见方案。</span><span class="sxs-lookup"><span data-stu-id="558a7-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="558a7-117">可以自定义和扩展这些自定义解决方案，以适应组织的品牌和要求。</span><span class="sxs-lookup"><span data-stu-id="558a7-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="558a7-118">许可</span><span class="sxs-lookup"><span data-stu-id="558a7-118">Licensing</span></span>

<span data-ttu-id="558a7-119">新功能适用于选定 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="558a7-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="558a7-120">有关 Power Apps、Power Automate、Power Virtual Agents 和 Dataverse for Teams 的许可要求详细信息，请参阅["许可"。](https://go.microsoft.com/fwlink/?linkid=2143647)</span><span class="sxs-lookup"><span data-stu-id="558a7-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="558a7-121">有关 Power BI 许可要求详细信息，请参阅"要求["。](https://go.microsoft.com/fwlink/?linkid=2143490)</span><span class="sxs-lookup"><span data-stu-id="558a7-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="558a7-122">如何开始？</span><span class="sxs-lookup"><span data-stu-id="558a7-122">How do I get started?</span></span>

- [<span data-ttu-id="558a7-123">Power BI 和 Teams</span><span class="sxs-lookup"><span data-stu-id="558a7-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="558a7-124">Power Apps 和 Teams</span><span class="sxs-lookup"><span data-stu-id="558a7-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="558a7-125">Power Automate 和 Teams</span><span class="sxs-lookup"><span data-stu-id="558a7-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="558a7-126">Power Virtual Agents 和 Teams</span><span class="sxs-lookup"><span data-stu-id="558a7-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
