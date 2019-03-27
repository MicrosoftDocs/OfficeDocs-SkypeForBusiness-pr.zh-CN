---
title: 管理 Business Server Skype 中的存档选项
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 摘要： 了解如何配置的 Skype 业务服务器的存档选项。
ms.openlocfilehash: db0fbe113f38065e85419b05d39fd0176b5ba845
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877781"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="9e38a-103">管理 Business Server Skype 中的存档选项</span><span class="sxs-lookup"><span data-stu-id="9e38a-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="9e38a-104">**摘要：** 了解如何配置的 Skype 业务服务器的存档选项。</span><span class="sxs-lookup"><span data-stu-id="9e38a-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="9e38a-105">您最初在部署时配置存档，但您可以在部署后更改、添加和删除配置。</span><span class="sxs-lookup"><span data-stu-id="9e38a-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="9e38a-106">存档选项决定了是否：</span><span class="sxs-lookup"><span data-stu-id="9e38a-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="9e38a-107">启用或禁用存档</span><span class="sxs-lookup"><span data-stu-id="9e38a-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="9e38a-108">存档 IM 会话</span><span class="sxs-lookup"><span data-stu-id="9e38a-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="9e38a-109">存档 Web 会议会话</span><span class="sxs-lookup"><span data-stu-id="9e38a-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="9e38a-110">在存档不可用时阻止活动</span><span class="sxs-lookup"><span data-stu-id="9e38a-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="9e38a-111">使用  Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="9e38a-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="9e38a-112">设置数据的清除和导出</span><span class="sxs-lookup"><span data-stu-id="9e38a-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="9e38a-113">您可以在以下级别指定配置选项：</span><span class="sxs-lookup"><span data-stu-id="9e38a-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="9e38a-114">为业务 Server 部署 Skype 时默认创建的全局级配置</span><span class="sxs-lookup"><span data-stu-id="9e38a-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="9e38a-115">指定如何为特定站点实施存档的可选站点级别配置</span><span class="sxs-lookup"><span data-stu-id="9e38a-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="9e38a-116">指定如何实现存档的特定池的可选池级配置</span><span class="sxs-lookup"><span data-stu-id="9e38a-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="9e38a-117">可以删除站点配置或池配置，但无法删除全局配置。</span><span class="sxs-lookup"><span data-stu-id="9e38a-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="9e38a-118">如果删除全局配置，该配置将自动重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="9e38a-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="9e38a-119">有关详细信息如何实现存档配置和层次结构的存档配置，请参阅[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="9e38a-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="9e38a-120">使用控制面板配置存档选项</span><span class="sxs-lookup"><span data-stu-id="9e38a-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="9e38a-121">可以使用控制面板配置存档选项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e38a-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="9e38a-122">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="9e38a-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9e38a-123">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="9e38a-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9e38a-124">在左侧导航栏中，单击“**存档配置**”</span><span class="sxs-lookup"><span data-stu-id="9e38a-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="9e38a-125">使用 Windows PowerShell 配置存档选项</span><span class="sxs-lookup"><span data-stu-id="9e38a-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="9e38a-126">也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档选项。</span><span class="sxs-lookup"><span data-stu-id="9e38a-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="9e38a-127">有关语法，包括所有可用的参数的详细信息，请参阅[Business Server Management Shell 的 Skype](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="9e38a-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="9e38a-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="9e38a-128">**Cmdlet**</span></span>|<span data-ttu-id="9e38a-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e38a-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e38a-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9e38a-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="9e38a-131">返回有关组织的存档配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="9e38a-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="9e38a-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9e38a-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="9e38a-133">创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。</span><span class="sxs-lookup"><span data-stu-id="9e38a-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="9e38a-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9e38a-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="9e38a-135">删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。</span><span class="sxs-lookup"><span data-stu-id="9e38a-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="9e38a-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9e38a-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="9e38a-137">修改即时消息 (IM) 存档配置选项的现有集合。</span><span class="sxs-lookup"><span data-stu-id="9e38a-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
