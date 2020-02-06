---
title: 管理 Skype for Business 服务器中的存档
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要：了解如何管理 Skype for business 服务器的存档。
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818994"
---
# <a name="manage-archiving-in-skype-for-business-server"></a><span data-ttu-id="aa25e-103">管理 Skype for Business 服务器中的存档</span><span class="sxs-lookup"><span data-stu-id="aa25e-103">Manage archiving in Skype for Business Server</span></span>

<span data-ttu-id="aa25e-104">**摘要：** 了解如何管理 Skype for business 服务器的存档。</span><span class="sxs-lookup"><span data-stu-id="aa25e-104">**Summary:** Learn how to manage archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="aa25e-105">在为组织部署存档时，可以在部署期间指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="aa25e-105">When you deploy archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="aa25e-106">但是，有时您希望针对日常管理或为了满足组织的新需求而更改实施存档支持的方式。</span><span class="sxs-lookup"><span data-stu-id="aa25e-106">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements for your organization.</span></span> <span data-ttu-id="aa25e-107">例如，您可能需要为组织中的特定站点、特定池或特定用户单独设置存档支持。</span><span class="sxs-lookup"><span data-stu-id="aa25e-107">For example, you may need to set up archiving support differently for a specific site, a specific pool, or specific users within your organization.</span></span> <span data-ttu-id="aa25e-108">对于驻留在 Skype for business 服务器上的用户，可通过创建和自定义存档配置选项和用户策略来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="aa25e-108">For users homed on Skype for Business Server, you do this by creating and customizing archiving configuration options and user policies.</span></span> 
  
<span data-ttu-id="aa25e-109">在阅读本主题之前，请确保熟悉 " [skype for Business 服务器](../../plan-your-deployment/archiving/archiving.md)" 中的存档信息和[为 Skype For business 服务器部署存档](../../deploy/deploy-archiving/deploy-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="aa25e-109">Before you read this topic, be sure you are familiar with the information in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa25e-110">如果对部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否对驻留在 Exchange 上并将邮箱置于就地保留状态的用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="aa25e-110">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="aa25e-111">有关详细信息，请参阅[在 skype for Business 服务器中规划存档](../../plan-your-deployment/archiving/archiving.md)和[配置与 Skype for Business 服务器的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="aa25e-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="archiving-configuration-options"></a><span data-ttu-id="aa25e-112">存档配置选项</span><span class="sxs-lookup"><span data-stu-id="aa25e-112">Archiving configuration options</span></span>

<span data-ttu-id="aa25e-113">存档配置选项指定是否：</span><span class="sxs-lookup"><span data-stu-id="aa25e-113">Archiving configuration options specify whether to:</span></span>
  
- <span data-ttu-id="aa25e-114">启用或禁用存档</span><span class="sxs-lookup"><span data-stu-id="aa25e-114">Enable or disable archiving</span></span>
    
- <span data-ttu-id="aa25e-115">存档 IM 会话</span><span class="sxs-lookup"><span data-stu-id="aa25e-115">Archive IM sessions</span></span>
    
- <span data-ttu-id="aa25e-116">存档 Web 会议会话</span><span class="sxs-lookup"><span data-stu-id="aa25e-116">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="aa25e-117">在存档不可用时阻止活动</span><span class="sxs-lookup"><span data-stu-id="aa25e-117">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="aa25e-118">使用  Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="aa25e-118">Use Exchange integration</span></span>
    
- <span data-ttu-id="aa25e-119">设置数据的清除和导出</span><span class="sxs-lookup"><span data-stu-id="aa25e-119">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="aa25e-120">可在全局、站点或池级别设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="aa25e-120">These options can be set at the global, site, or pool level.</span></span> <span data-ttu-id="aa25e-121">有关详细信息，请参阅[管理 Skype For Business 服务器中的存档选项](options.md)。</span><span class="sxs-lookup"><span data-stu-id="aa25e-121">For more information, see [Manage archiving options in Skype for Business Server](options.md).</span></span>
  
## <a name="archiving-policies"></a><span data-ttu-id="aa25e-122">存档策略</span><span class="sxs-lookup"><span data-stu-id="aa25e-122">Archiving policies</span></span>

<span data-ttu-id="aa25e-123">存档策略确定是否存档以下内容：</span><span class="sxs-lookup"><span data-stu-id="aa25e-123">Archiving policies determine whether to archive the following:</span></span>
  
- <span data-ttu-id="aa25e-124">内部通信</span><span class="sxs-lookup"><span data-stu-id="aa25e-124">Internal communications</span></span>
    
- <span data-ttu-id="aa25e-125">外部通信</span><span class="sxs-lookup"><span data-stu-id="aa25e-125">External communications</span></span>
    
<span data-ttu-id="aa25e-126">可在全局、站点或用户级别设置这些策略。</span><span class="sxs-lookup"><span data-stu-id="aa25e-126">These policies can be set at the global, site, or user level.</span></span> <span data-ttu-id="aa25e-127">有关详细信息，请参阅[管理 Skype For Business 服务器中的存档策略](policies.md)。</span><span class="sxs-lookup"><span data-stu-id="aa25e-127">For more information, see [Manage archiving policies in Skype for Business Server](policies.md).</span></span>
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a><span data-ttu-id="aa25e-128">使用控制面板或 Windows PowerShell 管理存档</span><span class="sxs-lookup"><span data-stu-id="aa25e-128">Manage archiving by using the Control Panel or by using Windows PowerShell</span></span>

<span data-ttu-id="aa25e-129">您可以使用控制面板或 Windows PowerShell 管理存档。</span><span class="sxs-lookup"><span data-stu-id="aa25e-129">You can manage archiving by using the Control Panel or by using Windows PowerShell.</span></span> <span data-ttu-id="aa25e-130">下表汇总了可帮助您管理存档的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa25e-130">The following table summarizes the cmdlets available to help you manage archiving.</span></span> <span data-ttu-id="aa25e-131">有关语法的详细信息（包括所有可用参数），请参阅[Skype for Business Server 命令行管理](../management-shell.md)程序。</span><span class="sxs-lookup"><span data-stu-id="aa25e-131">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span> 


|<span data-ttu-id="aa25e-132">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="aa25e-132">**Cmdlet**</span></span>|<span data-ttu-id="aa25e-133">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa25e-133">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa25e-134">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="aa25e-134">Export-CsArchivingData</span></span>  <br/> |<span data-ttu-id="aa25e-135">导出存储在 Skype for Business 服务器存档数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="aa25e-135">Exports records that have been stored in the Skype for Business Server Archiving database.</span></span>  <br/> |
|<span data-ttu-id="aa25e-136">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa25e-136">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="aa25e-137">返回有关组织的存档配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="aa25e-137">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="aa25e-138">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="aa25e-138">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="aa25e-139">返回有关组织的内部和外部通信存档策略的信息。</span><span class="sxs-lookup"><span data-stu-id="aa25e-139">Returns information about your organization's archiving policies for internal and external communications.</span></span>  <br/> |
|<span data-ttu-id="aa25e-140">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="aa25e-140">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="aa25e-141">将即时消息 (IM) 会话存档策略分配给用户或用户集。</span><span class="sxs-lookup"><span data-stu-id="aa25e-141">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="aa25e-142">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="aa25e-142">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="aa25e-143">Invoke-CsArchivingDatabasePurge</span><span class="sxs-lookup"><span data-stu-id="aa25e-143">Invoke-CsArchivingDatabasePurge</span></span>  <br/> |<span data-ttu-id="aa25e-144">手动清除存档数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="aa25e-144">Manually purges records from the Archiving database.</span></span>  <br/> |
|<span data-ttu-id="aa25e-145">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa25e-145">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="aa25e-146">创建一组新的即时消息 (IM) 设置，这些设置可用于启用或禁用 IM 会话的自动保存功能，也可用于阻止无法存档的任何即时消息。</span><span class="sxs-lookup"><span data-stu-id="aa25e-146">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="aa25e-147">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="aa25e-147">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="aa25e-148">创建新的即时消息 (IM) 会话存档策略。</span><span class="sxs-lookup"><span data-stu-id="aa25e-148">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="aa25e-149">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="aa25e-149">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="aa25e-150">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa25e-150">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="aa25e-151">删除指定的存档设置集合，存档设置可用于启用或禁用即时消息 (IM) 会话自动保存功能，以及选择性地阻止任何无法存档的即时消息。</span><span class="sxs-lookup"><span data-stu-id="aa25e-151">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="aa25e-152">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="aa25e-152">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="aa25e-153">删除指定的即时消息（IM）存档策略，该策略确定 Skype for Business 服务器是否会自动保存内部用户和/或内部用户与联盟合作伙伴之间所有 IM 会话之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="aa25e-153">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="aa25e-154">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa25e-154">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="aa25e-155">修改即时消息 (IM) 存档配置选项的现有集合。</span><span class="sxs-lookup"><span data-stu-id="aa25e-155">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
|<span data-ttu-id="aa25e-156">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="aa25e-156">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="aa25e-157">修改现有的即时消息 (IM) 存档策略。</span><span class="sxs-lookup"><span data-stu-id="aa25e-157">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="aa25e-158">通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。</span><span class="sxs-lookup"><span data-stu-id="aa25e-158">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="aa25e-159">Set-CsArchivingServer</span><span class="sxs-lookup"><span data-stu-id="aa25e-159">Set-CsArchivingServer</span></span>  <br/> |<span data-ttu-id="aa25e-160">使您可以为一个或多个存档服务器指定新数据库位置。</span><span class="sxs-lookup"><span data-stu-id="aa25e-160">Enables you to specify a new database location for one or more Archiving Servers.</span></span>  <br/> |
   

