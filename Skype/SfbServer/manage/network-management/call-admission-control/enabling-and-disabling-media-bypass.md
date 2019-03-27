---
title: 启用和禁用媒体旁路
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用本文中过程以启用或禁用媒体旁路使用 Skype 业务 Server Control Panel。
ms.openlocfilehash: eebbc111f0d205be8dced9ec8ddb5150deff8119
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874283"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="c1836-103">在 Skype for Business Server 中启用和禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="c1836-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="c1836-104">使用本文中过程以启用或禁用媒体旁路使用 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c1836-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="c1836-105">启用网络媒体绕过</span><span class="sxs-lookup"><span data-stu-id="c1836-105">Enable network media bypass</span></span> 

<span data-ttu-id="c1836-106">媒体绕过设置跨业务服务器部署 Skype 全局适用。</span><span class="sxs-lookup"><span data-stu-id="c1836-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="c1836-107">媒体绕过允许绕过中介服务器的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c1836-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="c1836-108">有关详细信息何时使用媒体绕过，请参阅[Plan for 媒体绕过](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="c1836-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="c1836-109">您可以启用和配置媒体绕过从 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c1836-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="c1836-110">启用和配置媒体绕过</span><span class="sxs-lookup"><span data-stu-id="c1836-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="c1836-111">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c1836-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c1836-112">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c1836-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c1836-113">在左侧的导航栏中，单击**网络配置**，然后单击**全局**。</span><span class="sxs-lookup"><span data-stu-id="c1836-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="c1836-114">在**全局**页上，单击**全局**配置。</span><span class="sxs-lookup"><span data-stu-id="c1836-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="c1836-115">始终没有只有一个配置，并且其始终名为 Global。</span><span class="sxs-lookup"><span data-stu-id="c1836-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="c1836-116">在**编辑**菜单上，单击**查看详细信息**。</span><span class="sxs-lookup"><span data-stu-id="c1836-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="c1836-117">在**编辑全局设置**页上，单击**启用媒体绕过**复选框。</span><span class="sxs-lookup"><span data-stu-id="c1836-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="c1836-118">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="c1836-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="c1836-119">**始终绕过**   选择此选项可尝试媒体绕过所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="c1836-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="c1836-120">如果已启用呼叫允许控制 (CAC)，则此选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="c1836-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="c1836-121">如果未启用 CAC，请在下列情况下选择此选项：</span><span class="sxs-lookup"><span data-stu-id="c1836-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="c1836-122">没有需要带宽控制。</span><span class="sxs-lookup"><span data-stu-id="c1836-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="c1836-123">没有需要精确的配置以确定何时发生旁路。</span><span class="sxs-lookup"><span data-stu-id="c1836-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="c1836-124">没有网关与客户端之间的完全连接。</span><span class="sxs-lookup"><span data-stu-id="c1836-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="c1836-125">**使用站点和区域配置**   如果 CAC 处于启用状态，默认情况下选中此选项，并不能更改。</span><span class="sxs-lookup"><span data-stu-id="c1836-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="c1836-126">选中此选项后，将使用网络配置站点和区域，以确定何时可能发生媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="c1836-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="c1836-127">如果选择此选项，您可以选择启用绕过的未映射的网站。</span><span class="sxs-lookup"><span data-stu-id="c1836-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="c1836-128">单击**启用非映射站点的绕过**复选框，只有您已在一个或多个大站点与同一区域关联的没有带宽限制 （例如，大型中央站点），并且您还可以与关联某些分支站点具有带宽限制的相同区域。</span><span class="sxs-lookup"><span data-stu-id="c1836-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="c1836-129">当您启用时为非映射站点绕过，请配置简化，因为指定仅与的分支站点相关联的子网，而无需指定的所有子网与所有网站关联。</span><span class="sxs-lookup"><span data-stu-id="c1836-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="c1836-130">我们建议您执行选择**启用非映射站点的绕过**复选框，如果已启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="c1836-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="c1836-131">单击**提交**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c1836-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="c1836-132">禁用网络媒体绕过</span><span class="sxs-lookup"><span data-stu-id="c1836-132">Disable network media bypass</span></span>

<span data-ttu-id="c1836-133">媒体绕过设置跨业务服务器部署 Skype 全局适用。</span><span class="sxs-lookup"><span data-stu-id="c1836-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="c1836-134">媒体绕过允许绕过中介服务器的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c1836-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="c1836-135">有关详细信息何时使用媒体绕过，请参阅[Plan for 媒体绕过](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="c1836-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="c1836-136">您可以禁用从 Skype 的媒体绕过业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c1836-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="c1836-137">若要禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="c1836-137">To disable media bypass</span></span>

1.  <span data-ttu-id="c1836-138">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c1836-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c1836-139">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c1836-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c1836-140">在左侧的导航栏中，单击**网络配置**，然后单击**全局**。</span><span class="sxs-lookup"><span data-stu-id="c1836-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="c1836-141">在**全局**页上，单击**全局**配置。</span><span class="sxs-lookup"><span data-stu-id="c1836-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="c1836-142">始终没有只有一个配置，并且其始终名为 Global。</span><span class="sxs-lookup"><span data-stu-id="c1836-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="c1836-143">在**编辑**菜单上，单击**查看详细信息**。</span><span class="sxs-lookup"><span data-stu-id="c1836-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="c1836-144">在**编辑全局设置**页上，清除**启用媒体绕过**复选框。</span><span class="sxs-lookup"><span data-stu-id="c1836-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="c1836-145">单击**提交**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c1836-145">Click **Commit** to save your changes.</span></span>

  
