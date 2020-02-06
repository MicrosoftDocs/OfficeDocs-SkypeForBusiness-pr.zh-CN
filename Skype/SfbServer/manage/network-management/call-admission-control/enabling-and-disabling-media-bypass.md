---
title: 启用和禁用媒体绕过
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
description: 使用本文中的步骤，通过使用 Skype for Business 服务器控制面板启用或禁用媒体旁路。
ms.openlocfilehash: d1c0a5eb409c6bb5c07c530b4799ab8a53a9fddb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817541"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="6578c-103">在 Skype for Business Server 中启用和禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="6578c-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="6578c-104">使用本文中的步骤，通过使用 Skype for Business 服务器控制面板启用或禁用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="6578c-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="6578c-105">启用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="6578c-105">Enable network media bypass</span></span> 

<span data-ttu-id="6578c-106">媒体绕过设置跨 Skype for Business 服务器部署全局应用。</span><span class="sxs-lookup"><span data-stu-id="6578c-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="6578c-107">媒体绕过允许呼叫绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="6578c-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="6578c-108">有关何时使用 "媒体绕过" 的详细信息，请参阅[规划媒体绕过](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="6578c-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="6578c-109">您可以从 Skype for Business 服务器控制面板启用和配置 "绕过媒体"。</span><span class="sxs-lookup"><span data-stu-id="6578c-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="6578c-110">启用和配置绕过媒体</span><span class="sxs-lookup"><span data-stu-id="6578c-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="6578c-111">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6578c-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6578c-112">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="6578c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6578c-113">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**全局**"。</span><span class="sxs-lookup"><span data-stu-id="6578c-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="6578c-114">在 "**全局**" 页面上，单击 "**全局**配置"。</span><span class="sxs-lookup"><span data-stu-id="6578c-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="6578c-115">始终只有一种配置，它始终名为 Global。</span><span class="sxs-lookup"><span data-stu-id="6578c-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="6578c-116">在 "**编辑**" 菜单上，单击 "**查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="6578c-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="6578c-117">在 "**编辑全局设置**" 页面上，单击 "**启用绕过媒体**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6578c-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="6578c-118">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="6578c-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="6578c-119">**"始终绕过**   " 选择此选项可在所有呼叫中尝试媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="6578c-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="6578c-120">如果启用了 "呼叫许可控制（CAC）"，此选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="6578c-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="6578c-121">如果未启用 CAC，请在以下情况下选择此选项：</span><span class="sxs-lookup"><span data-stu-id="6578c-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="6578c-122">无需带宽控制。</span><span class="sxs-lookup"><span data-stu-id="6578c-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="6578c-123">不需要精确的配置来确定何时应发生绕过。</span><span class="sxs-lookup"><span data-stu-id="6578c-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="6578c-124">网关和客户端之间存在完全连接。</span><span class="sxs-lookup"><span data-stu-id="6578c-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="6578c-125">**使用网站和区域配置**   如果启用了 CAC，则默认情况下此选项处于选中状态，并且不能更改。</span><span class="sxs-lookup"><span data-stu-id="6578c-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="6578c-126">选中此选项时，将使用网络配置网站和区域确定何时可能使用媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="6578c-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="6578c-127">如果选择此选项，则可以选择对未映射的网站启用 "绕过"。</span><span class="sxs-lookup"><span data-stu-id="6578c-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="6578c-128">仅当你有一个或多个大型网站与不具有带宽约束的同一区域（例如，大型中央网站）关联，并且你还具有与具有带宽限制的同一区域相关联的某些分支网站时，请单击 "**为非映射网站启用绕过**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6578c-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="6578c-129">为非映射网站启用 "绕过" 时，将简化配置，因为你只需指定与分支网站相关联的子网，而无需指定与所有网站相关联的所有子网。</span><span class="sxs-lookup"><span data-stu-id="6578c-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="6578c-130">如果启用了 CAC，我们建议您不要选中 "为**未映射的网站启用旁路**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6578c-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="6578c-131">单击 "**提交**" 保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6578c-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="6578c-132">禁用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="6578c-132">Disable network media bypass</span></span>

<span data-ttu-id="6578c-133">媒体绕过设置跨 Skype for Business 服务器部署全局应用。</span><span class="sxs-lookup"><span data-stu-id="6578c-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="6578c-134">媒体绕过允许呼叫绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="6578c-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="6578c-135">有关何时使用 "媒体绕过" 的详细信息，请参阅[规划媒体绕过](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="6578c-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="6578c-136">您可以从 Skype for Business 服务器控制面板禁用 "媒体绕过"。</span><span class="sxs-lookup"><span data-stu-id="6578c-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="6578c-137">禁用媒体绕过</span><span class="sxs-lookup"><span data-stu-id="6578c-137">To disable media bypass</span></span>

1.  <span data-ttu-id="6578c-138">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6578c-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6578c-139">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="6578c-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6578c-140">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**全局**"。</span><span class="sxs-lookup"><span data-stu-id="6578c-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="6578c-141">在 "**全局**" 页面上，单击 "**全局**配置"。</span><span class="sxs-lookup"><span data-stu-id="6578c-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="6578c-142">始终只有一种配置，它始终名为 Global。</span><span class="sxs-lookup"><span data-stu-id="6578c-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="6578c-143">在 "**编辑**" 菜单上，单击 "**查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="6578c-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="6578c-144">在 "**编辑全局设置**" 页面上，清除 "**启用绕过媒体**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6578c-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="6578c-145">单击 "**提交**" 保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6578c-145">Click **Commit** to save your changes.</span></span>

  
