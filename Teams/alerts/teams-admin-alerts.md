---
title: Microsoft Teams监视和警报
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
description: 了解 Teams 管理中心提供Microsoft Teams通知和通知功能。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: c99cc9af08fb1353e0c94e6f8bf156df04327d49
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684600"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="cfcc3-103">Microsoft Teams监视和警报</span><span class="sxs-lookup"><span data-stu-id="cfcc3-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="cfcc3-104">新的监视和警报功能Microsoft Teams管理中心提供Teams功能。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="cfcc3-105">使用管理中心中"通知 **&"** 部分Teams可用的不同规则集，监视Teams功能并接收警报。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="cfcc3-106">例如，如果 IP 电话、协作Teams等设备意外脱机，可以主动监视这些设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="cfcc3-107">组织可以使用Teams和警报功能执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cfcc3-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="cfcc3-108">自动管理Teams功能</span><span class="sxs-lookup"><span data-stu-id="cfcc3-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="cfcc3-109">如果它们显示意外内容，会发出警报。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="cfcc3-110">采取纠正措施，让一切回到正轨。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="cfcc3-111">如何管理监视和警报</span><span class="sxs-lookup"><span data-stu-id="cfcc3-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="cfcc3-112">必须是管理员中的全局管理员Microsoft 365或Teams服务管理员才能配置警报规则。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="cfcc3-113">请参阅[使用Teams管理员](../using-admin-roles.md)角色来管理Teams，详细了解Teams角色以及每个管理员角色可以访问的报告。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="cfcc3-114">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="cfcc3-115">在左侧导航栏中，选择 **"通知&警报"。**</span><span class="sxs-lookup"><span data-stu-id="cfcc3-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="cfcc3-116">从"规则"中选择要 **配置的规则**。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="cfcc3-117">Teams监视规则参考</span><span class="sxs-lookup"><span data-stu-id="cfcc3-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="cfcc3-118">通过添加各种监视功能和配置功能，Teams改进监视体验。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="cfcc3-119">下面是当前在管理中心Teams监视规则Teams列表。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="cfcc3-120">规则</span><span class="sxs-lookup"><span data-stu-id="cfcc3-120">Rule</span></span>  |<span data-ttu-id="cfcc3-121">监视功能</span><span class="sxs-lookup"><span data-stu-id="cfcc3-121">Monitoring capability</span></span>|<span data-ttu-id="cfcc3-122">监视什么？</span><span class="sxs-lookup"><span data-stu-id="cfcc3-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="cfcc3-123">设备运行状况</span><span class="sxs-lookup"><span data-stu-id="cfcc3-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="cfcc3-124">Teams设备</span><span class="sxs-lookup"><span data-stu-id="cfcc3-124">Teams Devices</span></span> | <span data-ttu-id="cfcc3-125">Pro脱机时Teams主动监视设备。</span><span class="sxs-lookup"><span data-stu-id="cfcc3-125">Pro-actively monitor Teams devices if they go offline.</span></span>|