---
title: Microsoft Teams 监视和警报
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: 了解 Microsoft Teams 管理中心提供的 Teams 警报和通知功能。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1be3ca52d4b03cfbf82d82310148ef4c2bb7f06d
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819435"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="bc2f6-103">Microsoft Teams 监视和警报</span><span class="sxs-lookup"><span data-stu-id="bc2f6-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="bc2f6-104">Teams 管理中心提供 Microsoft Teams 的新监视和警报功能。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="bc2f6-105">使用 Teams 管理中心中"通知和&"部分下提供的不同规则集来监视 Teams 功能和接收警报。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="bc2f6-106">例如，如果 Teams 设备意外脱机，可以主动监视其运行状况，例如 IP 电话、协作栏和其他设备。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="bc2f6-107">组织可以使用 Teams 监视和警报执行以下项目：</span><span class="sxs-lookup"><span data-stu-id="bc2f6-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="bc2f6-108">自动管理 Teams 功能</span><span class="sxs-lookup"><span data-stu-id="bc2f6-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="bc2f6-109">如果它们显示意外内容，会发出警报。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="bc2f6-110">采取纠正措施，让一切回到正轨。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="bc2f6-111">如何管理监视和警报</span><span class="sxs-lookup"><span data-stu-id="bc2f6-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="bc2f6-112">必须是 Microsoft 365 中的全局管理员或 Teams 服务管理员才能配置警报规则。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="bc2f6-113">请参阅 [使用 Teams 管理员角色管理 Teams，](../using-admin-roles.md) 了解有关 Teams 管理员角色以及每个管理员角色可以访问的报告。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="bc2f6-114">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="bc2f6-115">在左侧导航栏中，选择 **"通知&警报"。**</span><span class="sxs-lookup"><span data-stu-id="bc2f6-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="bc2f6-116">从"规则"中选择要 **配置的规则**。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="bc2f6-117">团队监视规则参考</span><span class="sxs-lookup"><span data-stu-id="bc2f6-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="bc2f6-118">我们通过添加各种监视功能和配置功能，继续添加和改进 Teams 监视体验。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="bc2f6-119">下面是 Teams 管理中心当前可用的 Teams 监视规则列表。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="bc2f6-120">规则</span><span class="sxs-lookup"><span data-stu-id="bc2f6-120">Rule</span></span>  |<span data-ttu-id="bc2f6-121">监视功能</span><span class="sxs-lookup"><span data-stu-id="bc2f6-121">Monitoring capability</span></span>|<span data-ttu-id="bc2f6-122">监视什么？</span><span class="sxs-lookup"><span data-stu-id="bc2f6-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="bc2f6-123">设备运行状况</span><span class="sxs-lookup"><span data-stu-id="bc2f6-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="bc2f6-124">Teams 设备</span><span class="sxs-lookup"><span data-stu-id="bc2f6-124">Teams Devices</span></span> | <span data-ttu-id="bc2f6-125">如果 Teams 设备脱机，请主动监视这些设备。</span><span class="sxs-lookup"><span data-stu-id="bc2f6-125">Pro-actively monitor Teams devices if they go offline.</span></span>|
