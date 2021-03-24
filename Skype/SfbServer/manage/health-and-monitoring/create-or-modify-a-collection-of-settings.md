---
title: 在 Skype for Business Server 中创建或修改 CDR 配置设置的集合
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要：了解 Skype for Business Server (CDR) 呼叫详细信息记录。
ms.openlocfilehash: da4383ef31b2d3ee781c445f2c935b79ea89bed8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095366"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6b080-103">在 Skype for Business Server 中创建或修改 CDR 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="6b080-103">Create or modify a collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="6b080-104">**摘要：** 了解 Skype for Business Server (CDR) 呼叫详细信息记录。</span><span class="sxs-lookup"><span data-stu-id="6b080-104">**Summary:** Learn about Call detail recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="6b080-105">呼叫详细信息记录 (CDR) 使您可以跟踪对等即时消息会话、Internet 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。</span><span class="sxs-lookup"><span data-stu-id="6b080-105">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="6b080-106">此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="6b080-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="6b080-107">安装 Skype for Business Server 时，将创建一个 CDR 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="6b080-107">When you install Skype for Business Server a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="6b080-108">管理员还可以选择在站点范围创建自定义设置。</span><span class="sxs-lookup"><span data-stu-id="6b080-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="6b080-109">每当使用这些站点范围的设置时，它们优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="6b080-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="6b080-110">例如，如果为 Redmond 站点创建站点作用域设置，则这些设置 (而不是全局设置) 用于管理 Redmond 中的 CDR。</span><span class="sxs-lookup"><span data-stu-id="6b080-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>
  
<span data-ttu-id="6b080-111">可以使用 Skype for Business Server 控制面板或 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 创建 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="6b080-111">You can create CDR configuration settings by using either Skype for Business Server Control Panel or the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="6b080-112">可以使用 Skype for Business Server 控制面板或 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="6b080-112">You can use Skype for Business Server Control Panel or the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet to modify existing settings.</span></span> <span data-ttu-id="6b080-113">如果使用 Skype for Business Server 控制面板创建或修改设置，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="6b080-113">If you are using Skype for Business Server Control Panel to create or modify settings, the following options will be available to you:</span></span>
  
|<span data-ttu-id="6b080-114">**UI 设置**</span><span class="sxs-lookup"><span data-stu-id="6b080-114">**UI setting**</span></span>|<span data-ttu-id="6b080-115">**PowerShell 参数**</span><span class="sxs-lookup"><span data-stu-id="6b080-115">**PowerShell parameter**</span></span>|<span data-ttu-id="6b080-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b080-116">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b080-117">名称</span><span class="sxs-lookup"><span data-stu-id="6b080-117">Name</span></span>  <br/> |<span data-ttu-id="6b080-118">标识</span><span class="sxs-lookup"><span data-stu-id="6b080-118">Identity</span></span>  <br/> |<span data-ttu-id="6b080-119">要创建的 CDR 配置设置的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6b080-119">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="6b080-120">只能在站点范围创建这些设置。</span><span class="sxs-lookup"><span data-stu-id="6b080-120">These settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="6b080-121">启用 CDR 监视</span><span class="sxs-lookup"><span data-stu-id="6b080-121">Enable monitoring of CDRs</span></span>  <br/> |<span data-ttu-id="6b080-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="6b080-122">EnableCDR</span></span>  <br/> |<span data-ttu-id="6b080-123">指示是否启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="6b080-123">Indicates whether or not CDR is enabled.</span></span>  <br/> |
|<span data-ttu-id="6b080-124">启用 CDR 清除</span><span class="sxs-lookup"><span data-stu-id="6b080-124">Enable purging of CDRs</span></span>  <br/> |<span data-ttu-id="6b080-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="6b080-125">EnablePurging</span></span>  <br/> |<span data-ttu-id="6b080-126">指示是否定期从 CDR 数据库中删除 CDR 记录。</span><span class="sxs-lookup"><span data-stu-id="6b080-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span>  <br/> |
|<span data-ttu-id="6b080-127">CDR 最长保留期限为 (天) </span><span class="sxs-lookup"><span data-stu-id="6b080-127">Keep CDRs for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="6b080-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="6b080-128">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="6b080-129">指示 CDR 记录在 CDR 数据库中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="6b080-129">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="6b080-130">超过指定天数的任何记录将自动删除。</span><span class="sxs-lookup"><span data-stu-id="6b080-130">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="6b080-131"> (请注意，只有在启用了清除后，才进行清除) </span><span class="sxs-lookup"><span data-stu-id="6b080-131">(Note that purging will take only place if purging has been enabled.)</span></span>  <br/> |
|<span data-ttu-id="6b080-132">将错误报告数据保留最长持续时间 (天) </span><span class="sxs-lookup"><span data-stu-id="6b080-132">Keep error report data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="6b080-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="6b080-133">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="6b080-134">指示 CDR 错误报告保留的天数。</span><span class="sxs-lookup"><span data-stu-id="6b080-134">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="6b080-135">超过指定天数的任何报告将自动删除。</span><span class="sxs-lookup"><span data-stu-id="6b080-135">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="6b080-136">CDR 错误报告是由客户端应用程序上载的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="6b080-136">CDR error reports are diagnostic reports uploaded by client applications.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="6b080-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="6b080-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="6b080-138">有关详细信息，请参阅 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) [和 Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6b080-138">See the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) and the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) help topics for more information.</span></span>
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6b080-139">使用 Skype for Business Server 控制面板创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="6b080-139">To create CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6b080-140">在 Skype for Business Server 控制面板中，单击 **"监控和存档"。**</span><span class="sxs-lookup"><span data-stu-id="6b080-140">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="6b080-141">在"**呼叫详细信息记录"选项卡上**，单击"**新建"。**</span><span class="sxs-lookup"><span data-stu-id="6b080-141">On the **Call Detail Recording** tab, click **New**.</span></span>
    
3. <span data-ttu-id="6b080-142">在 **"选择站点** "对话框中，选择要创建新配置设置的站点。</span><span class="sxs-lookup"><span data-stu-id="6b080-142">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="6b080-143">如果对话框为空，这意味着所有站点已分配有 CDR 配置设置的集合。</span><span class="sxs-lookup"><span data-stu-id="6b080-143">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="6b080-144">每个网站限制为一个此类集合。</span><span class="sxs-lookup"><span data-stu-id="6b080-144">Each site is limited to a single such collection.</span></span> <span data-ttu-id="6b080-145">在这种情况下，可以删除设置，然后重新创建设置，也可以只修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="6b080-145">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>
    
4. <span data-ttu-id="6b080-146">在"**新建呼叫详细信息记录 (CDR**) 设置"对话框中，进行所需的选择，然后单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="6b080-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6b080-147">使用 Skype for Business Server 控制面板修改现有 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="6b080-147">To modify existing CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6b080-148">在 Skype for Business Server 控制面板中，单击 **"监控和存档"。**</span><span class="sxs-lookup"><span data-stu-id="6b080-148">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="6b080-149">双击要修改的设置集合，或选择该集合，单击"编辑 **"，然后单击**"显示 **详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="6b080-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="6b080-150">请注意，一次只能修改一个集合。</span><span class="sxs-lookup"><span data-stu-id="6b080-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="6b080-151">若要对多个集合进行相同的更改，请改为使用 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="6b080-151">To make the same changes to multiple collections, use the Skype for Business Server Management Shell instead.</span></span>
    
3. <span data-ttu-id="6b080-152">在"**编辑呼叫详细信息记录 (CDR**) 设置"对话框中，进行所需的选择，然后单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="6b080-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6b080-153">使用 cmdlet 创建 CDR Windows PowerShell设置</span><span class="sxs-lookup"><span data-stu-id="6b080-153">Creating CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6b080-154">您还可以使用 **New-CsCdrConfiguration** cmdlet 和 Windows PowerShell创建 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="6b080-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="6b080-155">可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6b080-155">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6b080-156">有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="6b080-156">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6b080-157">此过程在 Skype for Business Server 中是相同的。</span><span class="sxs-lookup"><span data-stu-id="6b080-157">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="6b080-158">创建新的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="6b080-158">To create a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="6b080-159">此命令创建应用于 Redmond 站点的 CDR 配置设置的新集合：</span><span class="sxs-lookup"><span data-stu-id="6b080-159">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="6b080-160">创建禁用呼叫详细信息记录的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="6b080-160">To create a collection of CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="6b080-161">由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="6b080-161">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="6b080-162">要创建使用不同属性值的设置，只需包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="6b080-162">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="6b080-163">例如，要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用类似这样的命令：</span><span class="sxs-lookup"><span data-stu-id="6b080-163">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="6b080-164">在创建新的 CDR 配置设置集合时指定多个属性值</span><span class="sxs-lookup"><span data-stu-id="6b080-164">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="6b080-165">可以通过包含多个参数来修改多个属性值。</span><span class="sxs-lookup"><span data-stu-id="6b080-165">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="6b080-166">例如，此命令将新设置配置为将呼叫详细信息记录保留 30 天，将错误报告保留 90 天：</span><span class="sxs-lookup"><span data-stu-id="6b080-166">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

<span data-ttu-id="6b080-167">有关详细信息，请参阅 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6b080-167">For more information, see the help topic for the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
