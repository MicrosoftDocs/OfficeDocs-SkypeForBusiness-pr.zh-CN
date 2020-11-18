---
title: 团队与 Microsoft Power Platform 的集成
author: lanachin
ms.author: v-lanac
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
description: 了解有关团队与 Microsoft Power Platform 工具（包括 Power BI、Power apps、Power 自动化和 Power Virtual Agent）的集成。
ms.openlocfilehash: 81d673069e972f4627a8bfab18095e81803dd4b1
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085669"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="69964-103">团队与 Microsoft Power Platform 的集成</span><span class="sxs-lookup"><span data-stu-id="69964-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="69964-104">Microsoft Power Platform 可帮助用户使用较低的代码工具加速开发，使用 power **BI**、使用 power app 构建自定义应用、使用 power **app** 构建自定义应用、 **使用 power** Virtual agent 自动化进程以及使用更快的速度 **虚拟代理** 创建智能机器人。</span><span class="sxs-lookup"><span data-stu-id="69964-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="69964-105">随着对远程和混合工作的转变，Microsoft 团队已使世界各地的人能够继续创建、协作和沟通。</span><span class="sxs-lookup"><span data-stu-id="69964-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="69964-106">使用超过75000000的每日活动用户时，团队就是用户完成工作的方式。</span><span class="sxs-lookup"><span data-stu-id="69964-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="概述团队和 Microsoft Power Platform 的图像":::

<span data-ttu-id="69964-108">Microsoft Power Platform 为团队提供了许多集成功能，您可以在团队工作区中嵌入 **POWER BI** 报表、使用 **power apps** 作为选项卡或个人应用创建的嵌入应用、触发来自任何邮件的 **power 自动化** 流或使用自适应卡，以及将使用 **power Virtual agent** 创建的 Bot 添加到组织中其他成员的团队中。</span><span class="sxs-lookup"><span data-stu-id="69964-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="69964-109">2020年9月开始，与 Microsoft Power Platform 的集成已得到改进，让用户可以在不 *离开团队界面的情况* 下执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="69964-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="69964-110">使用 **POWER BI** 创建和共享仪表板、报表和应用以做出数据驱动决策。</span><span class="sxs-lookup"><span data-stu-id="69964-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="69964-111">通过连接到存储在新的基础数据平台中的业务数据，使用集成的 **Power apps** studio 创建和共享较低代码、专门构建的应用，方法是通过连接器 (Microsoft Dataverse 团队) 、microsoft 365 或其他数据源。</span><span class="sxs-lookup"><span data-stu-id="69964-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="69964-112">在你的应用和服务之间创建自动化的工作流，以使用 **Power 自动化** 同步文件、获取通知、收集数据等。</span><span class="sxs-lookup"><span data-stu-id="69964-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="69964-113">使用 **Power Virtual agent** 构建机器人，使用无代码图形界面轻松地在团队内创建数字助理，并使其可供同事进行聊天。</span><span class="sxs-lookup"><span data-stu-id="69964-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="69964-114">用于创建应用、bot 和工作流的新功能由面向团队的新内置、低代码数据平台提供支持， [Dataverse 用于](https://go.microsoft.com/fwlink/?linkid=2143541)团队的新内置的低代码数据平台，这些团队提供了关系数据存储、丰富的数据类型、企业级管理和一次单击解决方案部署。</span><span class="sxs-lookup"><span data-stu-id="69964-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="69964-115">团队的 Dataverse 在 [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)上构建。</span><span class="sxs-lookup"><span data-stu-id="69964-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="69964-116">通过 Dataverse for 团队，团队用户可以从展示各行业的常见方案的团队应用商店找到并安装自定义、随时使用的解决方案。</span><span class="sxs-lookup"><span data-stu-id="69964-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="69964-117">你可以自定义和扩展这些自定义解决方案，以适应组织的品牌和要求。</span><span class="sxs-lookup"><span data-stu-id="69964-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="69964-118">许可</span><span class="sxs-lookup"><span data-stu-id="69964-118">Licensing</span></span>

<span data-ttu-id="69964-119">新功能可用于选择 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="69964-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="69964-120">有关 Power App、Power 自动化、Power Virtual Agent 和 Dataverse for 团队授权要求的详细信息，请参阅 [授权](https://go.microsoft.com/fwlink/?linkid=2143647)。</span><span class="sxs-lookup"><span data-stu-id="69964-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="69964-121">有关 Power BI 授权要求的详细信息，请参阅 [要求](https://go.microsoft.com/fwlink/?linkid=2143490)。</span><span class="sxs-lookup"><span data-stu-id="69964-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="69964-122">如何开始？</span><span class="sxs-lookup"><span data-stu-id="69964-122">How do I get started?</span></span>

- [<span data-ttu-id="69964-123">Power BI 和团队</span><span class="sxs-lookup"><span data-stu-id="69964-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="69964-124">高级应用和团队</span><span class="sxs-lookup"><span data-stu-id="69964-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="69964-125">为自动化和团队供电</span><span class="sxs-lookup"><span data-stu-id="69964-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="69964-126">虚拟代理和团队的高级功能</span><span class="sxs-lookup"><span data-stu-id="69964-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
