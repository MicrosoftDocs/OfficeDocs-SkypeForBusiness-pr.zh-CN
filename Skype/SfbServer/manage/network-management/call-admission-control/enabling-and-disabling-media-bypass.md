---
title: 启用和禁用媒体旁路
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用本文中的过程通过 Skype for Business Server 控制面板启用或禁用媒体旁路。
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816492"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="9b6eb-103">在 Skype for Business Server 中启用和禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9b6eb-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="9b6eb-104">使用本文中的过程通过 Skype for Business Server 控制面板启用或禁用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="9b6eb-105">启用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9b6eb-105">Enable network media bypass</span></span> 

<span data-ttu-id="9b6eb-106">媒体旁路设置在 Skype for Business Server 部署中全局应用。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="9b6eb-107">媒体旁路允许呼叫绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="9b6eb-108">有关何时使用媒体旁路的详细信息，请参阅["规划媒体旁路"。](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="9b6eb-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="9b6eb-109">你可以从 Skype for Business Server 控制面板启用和配置媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="9b6eb-110">启用和配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9b6eb-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="9b6eb-111">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b6eb-112">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9b6eb-113">在左侧导航栏中，单击 **"网络配置**"，然后单击"**全局"。**</span><span class="sxs-lookup"><span data-stu-id="9b6eb-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="9b6eb-114">在“全局”页上，单击“全局”配置。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="9b6eb-115">始终只有一个配置，并且始终命名为 Global。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="9b6eb-116">在"**编辑"** 菜单上，单击 **"查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="9b6eb-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="9b6eb-117">在 **"编辑全局设置** "页上，单击 **"启用媒体旁路"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="9b6eb-118">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="9b6eb-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="9b6eb-119">**始终绕过**   选择此选项可尝试在所有呼叫上绕过媒体。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="9b6eb-120">如果启用了呼叫允许控制或 CAC (，此选项) 不可用。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="9b6eb-121">如果未启用 CAC，请在以下情况下选择此选项：</span><span class="sxs-lookup"><span data-stu-id="9b6eb-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="9b6eb-122">不需要带宽控制。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="9b6eb-123">无需进行精细配置来确定何时应发生旁路。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="9b6eb-124">网关和客户端之间具有完全连接。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="9b6eb-125">**使用站点和地区配置**   如果启用 CAC，则此选项默认为选中状态，且无法更改。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="9b6eb-126">选择此选项后，网络配置站点和地区将用于确定何时可以绕过媒体。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="9b6eb-127">如果选择此选项，可以选择为未映射的网站启用旁路。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="9b6eb-128">只有当有一个或多个大型站点与没有带宽限制的同一区域（例如，大型中央站点 () ）关联，并且某些分支站点与具有带宽限制的同一区域关联时，才单击"为非映射站点启用绕过"复选框。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="9b6eb-129">为非映射站点启用绕过时，配置会简化，因为您仅指定与分支站点关联的子网，无需指定所有与所有站点关联的子网。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="9b6eb-130">如果启用了 CAC，则建议您不要选中"启用非映射站点绕过"复选框。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="9b6eb-131">单击 **"** 提交"保存更改。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="9b6eb-132">禁用网络媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9b6eb-132">Disable network media bypass</span></span>

<span data-ttu-id="9b6eb-133">媒体旁路设置在 Skype for Business Server 部署中全局应用。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="9b6eb-134">媒体旁路允许呼叫绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="9b6eb-135">有关何时使用媒体旁路的详细信息，请参阅["规划媒体旁路"。](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="9b6eb-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="9b6eb-136">可以从 Skype for Business Server 控制面板禁用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="9b6eb-137">禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9b6eb-137">To disable media bypass</span></span>

1.  <span data-ttu-id="9b6eb-138">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b6eb-139">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9b6eb-140">在左侧导航栏中，单击 **"网络配置**"，然后单击"**全局"。**</span><span class="sxs-lookup"><span data-stu-id="9b6eb-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="9b6eb-141">在“全局”页上，单击“全局”配置。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="9b6eb-142">始终只有一个配置，并且始终命名为 Global。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="9b6eb-143">在"**编辑"** 菜单上，单击 **"查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="9b6eb-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="9b6eb-144">在" **编辑全局设置** "页上，清除 **"启用媒体旁路"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="9b6eb-145">单击 **"** 提交"保存更改。</span><span class="sxs-lookup"><span data-stu-id="9b6eb-145">Click **Commit** to save your changes.</span></span>

  
