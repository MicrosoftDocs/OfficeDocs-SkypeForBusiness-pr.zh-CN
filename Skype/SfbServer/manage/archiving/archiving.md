---
title: 在 Skype for Business Server 中管理存档
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要：了解如何管理 Skype for Business Server 的存档。
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817732"
---
# <a name="manage-archiving-in-skype-for-business-server"></a><span data-ttu-id="c8ee5-103">在 Skype for Business Server 中管理存档</span><span class="sxs-lookup"><span data-stu-id="c8ee5-103">Manage archiving in Skype for Business Server</span></span>

<span data-ttu-id="c8ee5-104">**摘要：** 了解如何管理 Skype for Business Server 的存档。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-104">**Summary:** Learn how to manage archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="c8ee5-105">为组织部署存档时，在部署过程中指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="c8ee5-106">但是，有时可能需要更改对日常管理实施存档支持或满足组织的新要求。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="c8ee5-107">例如，您可能需要为组织中特定站点、特定池或特定用户设置不同的存档支持。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="c8ee5-108">对于位于 Skype for Business Server 上的用户，通过创建和自定义存档配置选项和用户策略来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="c8ee5-109">在阅读本主题之前，请确保你熟悉规划 [Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) 中的存档和为 Skype for Business [Server](../../deploy/deploy-archiving/deploy-archiving.md)部署存档的信息。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8ee5-110">如果为部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否对位于 Exchange 上且其邮箱置于"保留"状态的用户In-Place存档。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="c8ee5-111">有关详细信息，请参阅[Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="c8ee5-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="c8ee5-112">存档配置选项</span><span class="sxs-lookup"><span data-stu-id="c8ee5-112">Archiving configuration options</span></span>

<span data-ttu-id="c8ee5-113">存档配置选项指定是否：</span><span class="sxs-lookup"><span data-stu-id="c8ee5-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="c8ee5-114">启用或禁用存档</span><span class="sxs-lookup"><span data-stu-id="c8ee5-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="c8ee5-115">存档 IM 会话</span><span class="sxs-lookup"><span data-stu-id="c8ee5-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="c8ee5-116">存档 Web 会议会话</span><span class="sxs-lookup"><span data-stu-id="c8ee5-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="c8ee5-117">存档不可用时阻止活动</span><span class="sxs-lookup"><span data-stu-id="c8ee5-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="c8ee5-118">使用 Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="c8ee5-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="c8ee5-119">设置清除和导出数据</span><span class="sxs-lookup"><span data-stu-id="c8ee5-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="c8ee5-120">可以在全局、站点或池级别设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="c8ee5-121">有关详细信息，请参阅管理 [Skype for Business Server 中的存档选项](options.md)。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-121">For more information, see [Manage archiving options in Skype for Business Server](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="c8ee5-122">存档策略</span><span class="sxs-lookup"><span data-stu-id="c8ee5-122">Archiving policies</span></span>

<span data-ttu-id="c8ee5-123">存档策略确定是否存档以下内容：</span><span class="sxs-lookup"><span data-stu-id="c8ee5-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="c8ee5-124">内部通信</span><span class="sxs-lookup"><span data-stu-id="c8ee5-124">Internal communications</span></span>
    
- <span data-ttu-id="c8ee5-125">外部通信</span><span class="sxs-lookup"><span data-stu-id="c8ee5-125">External communications</span></span>
    
<span data-ttu-id="c8ee5-126">可以在全局、站点或用户级别设置这些策略。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="c8ee5-127">有关详细信息，请参阅管理 [Skype for Business Server 中的存档策略](policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-127">For more information, see [Manage archiving policies in Skype for Business Server](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="c8ee5-128">使用控制面板或管理存档Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8ee5-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="c8ee5-129">您可以使用控制面板或管理存档Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="c8ee5-130">下表总结了可帮助您管理存档的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="c8ee5-131">有关语法的详细信息，包括所有可用参数，请参阅 Skype [for Business Server 命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-131">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="c8ee5-132">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="c8ee5-132">**Cmdlet**</span></span>|<span data-ttu-id="c8ee5-133">**说明**</span><span class="sxs-lookup"><span data-stu-id="c8ee5-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c8ee5-134">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="c8ee5-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="c8ee5-135">导出存储在 Skype for Business Server 存档数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-136">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8ee5-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c8ee5-137">返回有关组织中存档配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-138">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c8ee5-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c8ee5-139">返回有关组织的内部和外部通信存档策略的信息。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-140">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c8ee5-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c8ee5-141">将即时消息 (IM) 会话存档策略分配给用户或一组用户。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="c8ee5-142">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-143">Invoke-CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="c8ee5-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="c8ee5-144">手动清除存档数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-145">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8ee5-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c8ee5-146">创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存，并阻止无法存档的任何即时消息。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-147">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c8ee5-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c8ee5-148">创建新的即时消息 (IM) 会话存档策略。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="c8ee5-149">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-150">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8ee5-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c8ee5-151">删除指定的存档设置集合，这些设置用于启用或禁用即时消息 (IM) 会话的自动保存，并选择性地阻止任何无法存档的即时消息。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-152">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c8ee5-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c8ee5-153">删除指定的即时消息 (IM) 存档策略，该策略确定 Skype for Business Server 是否将自动保存内部用户之间发生的所有 IM 会话，以及/或内部用户和联盟伙伴之间的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-154">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8ee5-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c8ee5-155">修改现有的即时消息传递集合 (IM) 存档配置选项。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-156">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c8ee5-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="c8ee5-157">修改现有的即时消息 (IM) 存档策略。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="c8ee5-158">通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="c8ee5-159">Set-CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="c8ee5-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="c8ee5-160">使您可以指定一个或多个存档服务器的新数据库位置。</span><span class="sxs-lookup"><span data-stu-id="c8ee5-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

