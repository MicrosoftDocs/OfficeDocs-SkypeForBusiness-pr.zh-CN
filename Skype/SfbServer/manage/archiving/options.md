---
title: 在 Skype for Business Server 2015 中管理存档选项
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 摘要： 了解如何配置为 Skype 业务服务器 2015年的存档选项。
ms.openlocfilehash: 29800fef7054cd0e82f203d2ad6ec1ed53251ca4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-options-in-skype-for-business-server-2015"></a><span data-ttu-id="3f237-103">在 Skype for Business Server 2015 中管理存档选项</span><span class="sxs-lookup"><span data-stu-id="3f237-103">Manage archiving options in Skype for Business Server 2015</span></span>

<span data-ttu-id="3f237-104">**摘要：**了解如何配置为 Skype 业务服务器 2015年的存档选项。</span><span class="sxs-lookup"><span data-stu-id="3f237-104">**Summary:** Learn how to configure archiving options for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3f237-105">您最初在部署时配置存档，但您可以在部署后更改、添加和删除配置。</span><span class="sxs-lookup"><span data-stu-id="3f237-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="3f237-106">存档选项决定了是否：</span><span class="sxs-lookup"><span data-stu-id="3f237-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="3f237-107">启用或禁用存档</span><span class="sxs-lookup"><span data-stu-id="3f237-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="3f237-108">存档 IM 会话</span><span class="sxs-lookup"><span data-stu-id="3f237-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="3f237-109">存档 Web 会议会话</span><span class="sxs-lookup"><span data-stu-id="3f237-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="3f237-110">在存档不可用时阻止活动</span><span class="sxs-lookup"><span data-stu-id="3f237-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="3f237-111">使用  Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="3f237-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="3f237-112">设置数据的清除和导出</span><span class="sxs-lookup"><span data-stu-id="3f237-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="3f237-113">您可以在以下级别指定配置选项：</span><span class="sxs-lookup"><span data-stu-id="3f237-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="3f237-114">为业务服务器部署 Skype 时默认创建的全局级配置</span><span class="sxs-lookup"><span data-stu-id="3f237-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="3f237-115">指定如何为特定站点实施存档的可选站点级别配置</span><span class="sxs-lookup"><span data-stu-id="3f237-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="3f237-116">可选的池级配置来指定如何存档对于一个特定的池的实现</span><span class="sxs-lookup"><span data-stu-id="3f237-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="3f237-117">可以删除站点配置或池配置，但无法删除全局配置。</span><span class="sxs-lookup"><span data-stu-id="3f237-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="3f237-118">如果删除全局配置，该配置将自动重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="3f237-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="3f237-119">有关如何实现存档配置并且存档配置的层次结构，请参阅[规划存档业务服务器 2015年的 Skype 的](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="3f237-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="3f237-120">使用控制面板配置存档选项</span><span class="sxs-lookup"><span data-stu-id="3f237-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="3f237-121">可以使用控制面板配置存档选项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3f237-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="3f237-122">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3f237-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3f237-123">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="3f237-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3f237-124">在左侧导航栏中，单击“**存档配置**”</span><span class="sxs-lookup"><span data-stu-id="3f237-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="3f237-125">使用 Windows PowerShell 配置存档选项</span><span class="sxs-lookup"><span data-stu-id="3f237-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="3f237-126">也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档选项。</span><span class="sxs-lookup"><span data-stu-id="3f237-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="3f237-127">有关语法，包括所有的可用参数的详细信息请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="3f237-127">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="3f237-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="3f237-128">**Cmdlet**</span></span>|<span data-ttu-id="3f237-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="3f237-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f237-130">获得 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f237-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="3f237-131">返回有关组织的存档配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="3f237-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="3f237-132">新 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f237-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="3f237-133">创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。</span><span class="sxs-lookup"><span data-stu-id="3f237-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="3f237-134">删除 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f237-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="3f237-135">删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。</span><span class="sxs-lookup"><span data-stu-id="3f237-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="3f237-136">一组 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f237-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="3f237-137">修改即时消息 (IM) 存档配置选项的现有集合。</span><span class="sxs-lookup"><span data-stu-id="3f237-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |