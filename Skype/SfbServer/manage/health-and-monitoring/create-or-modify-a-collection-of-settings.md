---
title: 在 Skype for Business 服务器中创建或修改 CDR 配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: '摘要: 了解 Skype for Business 服务器中的呼叫详细记录 (CDR)。'
ms.openlocfilehash: c0a54835fe74a32a92996874cb6fd895fd49fafc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305828"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="51bcd-103">在 Skype for Business 服务器中创建或修改 CDR 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="51bcd-103">Create or modify a collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="51bcd-104">**摘要:** 了解 Skype for Business 服务器中的呼叫详细记录 (CDR)。</span><span class="sxs-lookup"><span data-stu-id="51bcd-104">**Summary:** Learn about Call detail recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="51bcd-p101">利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="51bcd-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="51bcd-107">安装 Skype for Business 服务器时, 将为你创建单个的 CDR 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="51bcd-107">When you install Skype for Business Server a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="51bcd-108">管理员还具有创建站点作用域的自定义设置的选项。</span><span class="sxs-lookup"><span data-stu-id="51bcd-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="51bcd-109">使用这些站点作用域设置时，它们将优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="51bcd-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="51bcd-110">例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置（而不是全局设置）将用于管理 Redmond 内的 CDR。</span><span class="sxs-lookup"><span data-stu-id="51bcd-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>
  
<span data-ttu-id="51bcd-111">你可以使用 Skype for Business Server 控制面板或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) CMDLET 创建 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="51bcd-111">You can create CDR configuration settings by using either Skype for Business Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="51bcd-112">你可以使用 Skype for Business Server 控制面板或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="51bcd-112">You can use Skype for Business Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet to modify existing settings.</span></span> <span data-ttu-id="51bcd-113">如果您使用的是 Skype for Business 服务器控制面板来创建或修改设置, 您将可以使用以下选项:</span><span class="sxs-lookup"><span data-stu-id="51bcd-113">If you are using Skype for Business Server Control Panel to create or modify settings, the following options will be available to you:</span></span>
  
|<span data-ttu-id="51bcd-114">**UI 设置**</span><span class="sxs-lookup"><span data-stu-id="51bcd-114">**UI setting**</span></span>|<span data-ttu-id="51bcd-115">**PowerShell 参数**</span><span class="sxs-lookup"><span data-stu-id="51bcd-115">**PowerShell parameter**</span></span>|<span data-ttu-id="51bcd-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="51bcd-116">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="51bcd-117">名称</span><span class="sxs-lookup"><span data-stu-id="51bcd-117">Name</span></span>  <br/> |<span data-ttu-id="51bcd-118">Identity</span><span class="sxs-lookup"><span data-stu-id="51bcd-118">Identity</span></span>  <br/> |<span data-ttu-id="51bcd-p104">所创建的 CDR 配置设置的唯一标识符。这些设置只能在站点作用域内创建。</span><span class="sxs-lookup"><span data-stu-id="51bcd-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="51bcd-121">启用 CDR 监控</span><span class="sxs-lookup"><span data-stu-id="51bcd-121">Enable monitoring of CDRs</span></span>  <br/> |<span data-ttu-id="51bcd-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="51bcd-122">EnableCDR</span></span>  <br/> |<span data-ttu-id="51bcd-123">指示是否启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="51bcd-123">Indicates whether or not CDR is enabled.</span></span>  <br/> |
|<span data-ttu-id="51bcd-124">启用 CDR 清除</span><span class="sxs-lookup"><span data-stu-id="51bcd-124">Enable purging of CDRs</span></span>  <br/> |<span data-ttu-id="51bcd-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="51bcd-125">EnablePurging</span></span>  <br/> |<span data-ttu-id="51bcd-126">指示是否将定期从 CDR 数据库中删除 CDR 记录。</span><span class="sxs-lookup"><span data-stu-id="51bcd-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span>  <br/> |
|<span data-ttu-id="51bcd-127">CDR 最长保留期限（天）</span><span class="sxs-lookup"><span data-stu-id="51bcd-127">Keep CDRs for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="51bcd-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="51bcd-128">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="51bcd-p105">指示 CDR 记录在 CDR 数据库中保留的天数。任何早于指定天数的记录都将被自动删除。（请注意，仅当启用清除后，才会执行清除操作。）</span><span class="sxs-lookup"><span data-stu-id="51bcd-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span>  <br/> |
|<span data-ttu-id="51bcd-132">错误报告数据最长保留期限（天）</span><span class="sxs-lookup"><span data-stu-id="51bcd-132">Keep error report data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="51bcd-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="51bcd-133">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="51bcd-p106">指示 CDR 错误报告的保留天数。任何早于指定天数的记录都将被自动删除。CDR 错误报告是客户端应用程序上传的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="51bcd-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="51bcd-137">CsCdrConfiguration 和 CsCdrConfiguration cmdlet 包括 Skype for Business Server 控制面板中不提供的其他选项。</span><span class="sxs-lookup"><span data-stu-id="51bcd-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="51bcd-138">有关详细信息, 请参阅[新的 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)和[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="51bcd-138">See the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) and the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) help topics for more information.</span></span>
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="51bcd-139">使用 Skype for Business 服务器控制面板创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="51bcd-139">To create CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="51bcd-140">在 Skype for Business 服务器控制面板中, 单击 "**监视和存档**"。</span><span class="sxs-lookup"><span data-stu-id="51bcd-140">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="51bcd-141">在 "**呼叫详细记录**" 选项卡上, 单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="51bcd-141">On the **Call Detail Recording** tab, click **New**.</span></span>
    
3. <span data-ttu-id="51bcd-p108">在“**选择站点**”对话框中，选择要在其中创建新配置设置的站点。如果该对话框为空，则表示所有站点均已被分配 CDR 配置设置集合。每个站点均限制为只有一个此类集合。在这种情况下，您可以删除设置然后重新创建，也可以只修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="51bcd-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>
    
4. <span data-ttu-id="51bcd-146">在“**新建呼叫详细信息记录 (CDR) 设置**”  对话框中进行所需选择，然后单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="51bcd-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="51bcd-147">使用 Skype for Business 服务器控制面板修改现有 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="51bcd-147">To modify existing CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="51bcd-148">在 Skype for Business 服务器控制面板中, 单击 "**监视和存档**"。</span><span class="sxs-lookup"><span data-stu-id="51bcd-148">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="51bcd-149">双击要修改的设置集合，或选择集合后单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="51bcd-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="51bcd-150">请注意，一次只能修改一个集合。</span><span class="sxs-lookup"><span data-stu-id="51bcd-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="51bcd-151">若要对多个集合进行相同的更改, 请改用 Skype for Business 服务器管理外壳。</span><span class="sxs-lookup"><span data-stu-id="51bcd-151">To make the same changes to multiple collections, use the Skype for Business Server Management Shell instead.</span></span>
    
3. <span data-ttu-id="51bcd-152">在“**编辑呼叫详细信息记录 (CDR) 设置**”对话框中进行所需选择，然后单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="51bcd-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="51bcd-153">使用 Windows PowerShell Cmdlet 创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="51bcd-153">Creating CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="51bcd-154">你可以创建 CDR 配置设置, 也可以使用 Windows PowerShell 和**CsCdrConfiguration** cmdlet 创建 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="51bcd-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="51bcd-155">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51bcd-155">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="51bcd-156">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅博客文章["快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="51bcd-156">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="51bcd-157">在 Skype for Business 服务器中, 此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="51bcd-157">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="51bcd-158">创建新的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="51bcd-158">To create a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="51bcd-159">以下命令将创建新的应用于 Redmond 站点的 CDR 配置设置集合：</span><span class="sxs-lookup"><span data-stu-id="51bcd-159">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="51bcd-160">创建可禁用呼叫详细信息记录的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="51bcd-160">To create a collection of CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="51bcd-p111">由于上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="51bcd-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="51bcd-164">在创建新的 CDR 配置设置集合时指定多个属性值</span><span class="sxs-lookup"><span data-stu-id="51bcd-164">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="51bcd-p112">您可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为将呼叫详细信息记录保留 30 天，而将错误报告保留 90 天：</span><span class="sxs-lookup"><span data-stu-id="51bcd-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

<span data-ttu-id="51bcd-167">有关详细信息, 请参阅[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="51bcd-167">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

