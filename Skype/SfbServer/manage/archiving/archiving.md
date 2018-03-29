---
title: 管理 Skype for Business Server 2015 中的存档
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要： 了解如何管理业务服务器 2015 Skype 的存档。
ms.openlocfilehash: fb8359d47b1933e2575685bc532d69e6b9bb6c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="df4a1-103">管理 Skype for Business Server 2015 中的存档</span><span class="sxs-lookup"><span data-stu-id="df4a1-103">Manage archiving in Skype for Business Server 2015</span></span>

<span data-ttu-id="df4a1-104">**摘要：**了解如何管理业务服务器 2015 Skype 的存档。</span><span class="sxs-lookup"><span data-stu-id="df4a1-104">**Summary:** Learn how to manage archiving for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="df4a1-105">在为组织部署存档时，可以在部署期间指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="df4a1-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="df4a1-106">但是，有时您希望针对日常管理或为了满足组织的新需求而更改实施存档支持的方式。</span><span class="sxs-lookup"><span data-stu-id="df4a1-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="df4a1-107">例如，您可能需要为组织中的特定站点、特定池或特定用户单独设置存档支持。</span><span class="sxs-lookup"><span data-stu-id="df4a1-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="df4a1-108">对于用户驻留在 Skype 上的业务服务器，您可以执行此操作通过创建和自定义存档配置选项和用户策略。</span><span class="sxs-lookup"><span data-stu-id="df4a1-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="df4a1-109">在阅读本主题之前，请确保您熟悉[存档业务服务器 2015年的 Skype 的规划](../../plan-your-deployment/archiving/archiving.md)和[部署业务服务器 2015年的 Skype 的存档](../../deploy/deploy-archiving/deploy-archiving.md)中的信息。</span><span class="sxs-lookup"><span data-stu-id="df4a1-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="df4a1-110">如果对部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否对驻留在 Exchange 上并将邮箱置于就地保留状态的用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="df4a1-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="df4a1-111">有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在归档](../../plan-your-deployment/archiving/archiving.md)和[具有的业务服务器 2015 Skype 的 Exchange 存储配置集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="df4a1-111">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="df4a1-112">存档配置选项</span><span class="sxs-lookup"><span data-stu-id="df4a1-112">Archiving configuration options</span></span>

<span data-ttu-id="df4a1-113">存档配置选项指定是否：</span><span class="sxs-lookup"><span data-stu-id="df4a1-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="df4a1-114">启用或禁用存档</span><span class="sxs-lookup"><span data-stu-id="df4a1-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="df4a1-115">存档 IM 会话</span><span class="sxs-lookup"><span data-stu-id="df4a1-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="df4a1-116">存档 Web 会议会话</span><span class="sxs-lookup"><span data-stu-id="df4a1-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="df4a1-117">在存档不可用时阻止活动</span><span class="sxs-lookup"><span data-stu-id="df4a1-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="df4a1-118">使用  Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="df4a1-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="df4a1-119">设置数据的清除和导出</span><span class="sxs-lookup"><span data-stu-id="df4a1-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="df4a1-120">可在全局、站点或池级别设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="df4a1-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="df4a1-121">有关详细信息，请参阅[管理中业务服务器 2015年的 Skype 的存档选项](options.md)。</span><span class="sxs-lookup"><span data-stu-id="df4a1-121">For more information, see [Manage archiving options in Skype for Business Server 2015](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="df4a1-122">存档策略</span><span class="sxs-lookup"><span data-stu-id="df4a1-122">Archiving policies</span></span>

<span data-ttu-id="df4a1-123">存档策略确定是否存档以下：</span><span class="sxs-lookup"><span data-stu-id="df4a1-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="df4a1-124">内部通信</span><span class="sxs-lookup"><span data-stu-id="df4a1-124">Internal communications</span></span>
    
- <span data-ttu-id="df4a1-125">外部通信</span><span class="sxs-lookup"><span data-stu-id="df4a1-125">External communications</span></span>
    
<span data-ttu-id="df4a1-126">可在全局、站点或用户级别设置这些策略。</span><span class="sxs-lookup"><span data-stu-id="df4a1-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="df4a1-127">有关详细信息，请参阅[管理中业务服务器 2015年的 Skype 的存档策略](policies.md)。</span><span class="sxs-lookup"><span data-stu-id="df4a1-127">For more information, see [Manage archiving policies in Skype for Business Server 2015](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="df4a1-128">使用控制面板或 Windows PowerShell 管理存档</span><span class="sxs-lookup"><span data-stu-id="df4a1-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="df4a1-129">您可以使用控制面板或 Windows PowerShell 管理存档。</span><span class="sxs-lookup"><span data-stu-id="df4a1-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="df4a1-130">下表汇总了可帮助您管理存档的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="df4a1-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="df4a1-131">有关语法，包括所有的可用参数的详细信息请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="df4a1-131">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="df4a1-132">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="df4a1-132">**Cmdlet**</span></span>|<span data-ttu-id="df4a1-133">**说明**</span><span class="sxs-lookup"><span data-stu-id="df4a1-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df4a1-134">导出 CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="df4a1-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="df4a1-135">导出在 Skype 业务服务器存档数据库中已存储的记录。</span><span class="sxs-lookup"><span data-stu-id="df4a1-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="df4a1-136">获得 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="df4a1-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="df4a1-137">返回有关组织的存档配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="df4a1-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="df4a1-138">获得 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="df4a1-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="df4a1-139">返回有关组织的内部和外部通信存档策略的信息。</span><span class="sxs-lookup"><span data-stu-id="df4a1-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="df4a1-140">授予 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="df4a1-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="df4a1-141">将即时消息 (IM) 会话存档策略分配给用户或用户集。</span><span class="sxs-lookup"><span data-stu-id="df4a1-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="df4a1-142">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="df4a1-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="df4a1-143">调用 CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="df4a1-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="df4a1-144">手动清除存档数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="df4a1-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="df4a1-145">新 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="df4a1-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="df4a1-146">创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。</span><span class="sxs-lookup"><span data-stu-id="df4a1-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="df4a1-147">新 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="df4a1-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="df4a1-148">创建新的即时消息 (IM) 会话存档策略。</span><span class="sxs-lookup"><span data-stu-id="df4a1-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="df4a1-149">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="df4a1-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="df4a1-150">删除 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="df4a1-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="df4a1-151">删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。</span><span class="sxs-lookup"><span data-stu-id="df4a1-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="df4a1-152">删除 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="df4a1-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="df4a1-153">删除存档策略，用于确定是否 Skype 业务服务器自动将所有内部用户，和/或内部用户和联盟的用户之间的所有 IM 会话之间进行的 IM 会话指定即时消息 (IM)。</span><span class="sxs-lookup"><span data-stu-id="df4a1-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="df4a1-154">一组 CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="df4a1-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="df4a1-155">修改即时消息 (IM) 存档配置选项的现有集合。</span><span class="sxs-lookup"><span data-stu-id="df4a1-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="df4a1-156">一组 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="df4a1-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="df4a1-157">修改现有的即时消息 (IM) 存档策略。</span><span class="sxs-lookup"><span data-stu-id="df4a1-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="df4a1-158">通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。</span><span class="sxs-lookup"><span data-stu-id="df4a1-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="df4a1-159">一组 CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="df4a1-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="df4a1-160">使您可以为一个或多个存档服务器指定新数据库位置。</span><span class="sxs-lookup"><span data-stu-id="df4a1-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

