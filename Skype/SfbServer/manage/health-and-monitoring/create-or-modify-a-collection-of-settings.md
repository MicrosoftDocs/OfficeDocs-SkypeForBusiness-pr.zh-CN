---
title: 创建或修改的 Skype 中业务服务器的 CDR 配置设置集合
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要： 了解有关呼叫详细信息记录 (CDR) 中 Skype 业务服务器。
ms.openlocfilehash: f1bbf12f3766156b5f30ef3f2760669791e8c4c0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970370"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d092a-103">创建或修改的 Skype 中业务服务器的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="d092a-103">Create or modify a collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d092a-104">**摘要：** 了解有关呼叫详细信息记录 (CDR) 中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="d092a-104">**Summary:** Learn about Call detail recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="d092a-p101">利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="d092a-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="d092a-107">为业务 Server 单个安装 Skype 时，会为您创建的 CDR 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="d092a-107">When you install Skype for Business Server a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="d092a-108">管理员还具有创建站点作用域的自定义设置的选项。</span><span class="sxs-lookup"><span data-stu-id="d092a-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="d092a-109">使用这些站点作用域设置时，它们将优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="d092a-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="d092a-110">例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置（而不是全局设置）将用于管理 Redmond 内的 CDR。</span><span class="sxs-lookup"><span data-stu-id="d092a-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>
  
<span data-ttu-id="d092a-111">可以通过使用任一 Skype 业务 Server Control Panel 或[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 创建 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="d092a-111">You can create CDR configuration settings by using either Skype for Business Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d092a-112">Skype 业务 Server Control Panel 或[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 可用于修改现有的设置。</span><span class="sxs-lookup"><span data-stu-id="d092a-112">You can use Skype for Business Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet to modify existing settings.</span></span> <span data-ttu-id="d092a-113">如果使用的业务 Server Control Panel Skype 创建或修改设置，将对您可用下列选项：</span><span class="sxs-lookup"><span data-stu-id="d092a-113">If you are using Skype for Business Server Control Panel to create or modify settings, the following options will be available to you:</span></span>
  
|<span data-ttu-id="d092a-114">**UI 设置**</span><span class="sxs-lookup"><span data-stu-id="d092a-114">**UI setting**</span></span>|<span data-ttu-id="d092a-115">**PowerShell 参数**</span><span class="sxs-lookup"><span data-stu-id="d092a-115">**PowerShell parameter**</span></span>|<span data-ttu-id="d092a-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="d092a-116">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d092a-117">名称</span><span class="sxs-lookup"><span data-stu-id="d092a-117">Name</span></span>  <br/> |<span data-ttu-id="d092a-118">Identity</span><span class="sxs-lookup"><span data-stu-id="d092a-118">Identity</span></span>  <br/> |<span data-ttu-id="d092a-p104">所创建的 CDR 配置设置的唯一标识符。这些设置只能在站点作用域内创建。</span><span class="sxs-lookup"><span data-stu-id="d092a-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="d092a-121">启用 CDR 监控</span><span class="sxs-lookup"><span data-stu-id="d092a-121">Enable monitoring of CDRs</span></span>  <br/> |<span data-ttu-id="d092a-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="d092a-122">EnableCDR</span></span>  <br/> |<span data-ttu-id="d092a-123">指示是否启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="d092a-123">Indicates whether or not CDR is enabled.</span></span>  <br/> |
|<span data-ttu-id="d092a-124">启用 CDR 清除</span><span class="sxs-lookup"><span data-stu-id="d092a-124">Enable purging of CDRs</span></span>  <br/> |<span data-ttu-id="d092a-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="d092a-125">EnablePurging</span></span>  <br/> |<span data-ttu-id="d092a-126">指示是否将定期从 CDR 数据库中删除 CDR 记录。</span><span class="sxs-lookup"><span data-stu-id="d092a-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span>  <br/> |
|<span data-ttu-id="d092a-127">CDR 最长保留期限（天）</span><span class="sxs-lookup"><span data-stu-id="d092a-127">Keep CDRs for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="d092a-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="d092a-128">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="d092a-p105">指示 CDR 记录在 CDR 数据库中保留的天数。任何早于指定天数的记录都将被自动删除。（请注意，仅当启用清除后，才会执行清除操作。）</span><span class="sxs-lookup"><span data-stu-id="d092a-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span>  <br/> |
|<span data-ttu-id="d092a-132">错误报告数据最长保留期限（天）</span><span class="sxs-lookup"><span data-stu-id="d092a-132">Keep error report data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="d092a-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="d092a-133">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="d092a-p106">指示 CDR 错误报告的保留天数。任何早于指定天数的记录都将被自动删除。CDR 错误报告是客户端应用程序上传的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="d092a-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d092a-137">New-cscdrconfiguration 和 Set-cscdrconfiguration cmdlet 包括用于业务 Server Control Panel Skype 中不可用的其他选项。</span><span class="sxs-lookup"><span data-stu-id="d092a-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="d092a-138">请参阅[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)和[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)帮助主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d092a-138">See the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) and the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) help topics for more information.</span></span>
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d092a-139">使用适用于业务 Server Control Panel Skype 创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="d092a-139">To create CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d092a-140">Skype 的业务 Server Control Panel 中单击**监控和存档**。</span><span class="sxs-lookup"><span data-stu-id="d092a-140">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="d092a-141">在**呼叫详细信息记录**选项卡中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="d092a-141">On the **Call Detail Recording** tab, click **New**.</span></span>
    
3. <span data-ttu-id="d092a-p108">在“**选择站点**”对话框中，选择要在其中创建新配置设置的站点。如果该对话框为空，则表示所有站点均已被分配 CDR 配置设置集合。每个站点均限制为只有一个此类集合。在这种情况下，您可以删除设置然后重新创建，也可以只修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="d092a-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>
    
4. <span data-ttu-id="d092a-146">在“**新建呼叫详细信息记录 (CDR) 设置**”  对话框中进行所需选择，然后单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d092a-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d092a-147">使用适用于业务 Server Control Panel Skype 修改现有 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="d092a-147">To modify existing CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d092a-148">Skype 的业务 Server Control Panel 中单击**监控和存档**。</span><span class="sxs-lookup"><span data-stu-id="d092a-148">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="d092a-149">双击要修改的设置集合，或选择集合后单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="d092a-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="d092a-150">请注意，一次只能修改一个集合。</span><span class="sxs-lookup"><span data-stu-id="d092a-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="d092a-151">对多个集合进行相同的更改，改用 Skype 的业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="d092a-151">To make the same changes to multiple collections, use the Skype for Business Server Management Shell instead.</span></span>
    
3. <span data-ttu-id="d092a-152">在“**编辑呼叫详细信息记录 (CDR) 设置**”对话框中进行所需选择，然后单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d092a-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d092a-153">使用 Windows PowerShell Cmdlet 创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="d092a-153">Creating CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d092a-154">您可以创建 CDR 配置设置也可以创建使用 Windows PowerShell 和**New-cscdrconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d092a-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d092a-155">可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d092a-155">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d092a-156">有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="d092a-156">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d092a-157">过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="d092a-157">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="d092a-158">创建新的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="d092a-158">To create a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="d092a-159">以下命令将创建新的应用于 Redmond 站点的 CDR 配置设置集合：</span><span class="sxs-lookup"><span data-stu-id="d092a-159">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="d092a-160">创建可禁用呼叫详细信息记录的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="d092a-160">To create a collection of CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="d092a-p111">由于上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="d092a-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="d092a-164">在创建新的 CDR 配置设置集合时指定多个属性值</span><span class="sxs-lookup"><span data-stu-id="d092a-164">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="d092a-p112">您可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为将呼叫详细信息记录保留 30 天，而将错误报告保留 90 天：</span><span class="sxs-lookup"><span data-stu-id="d092a-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

<span data-ttu-id="d092a-167">有关详细信息，请参阅[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d092a-167">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

