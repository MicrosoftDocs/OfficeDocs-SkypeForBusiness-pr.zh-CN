---
title: 在 Skype for Business Server 中创建用户体验质量配置设置
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 摘要：了解 Skype for Business Server (QoE) 设置用户体验质量。
ms.openlocfilehash: d1d0b299b5cf0bbaf3627b7c90f90e7e1d958d10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816992"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="69a1f-103">在 Skype for Business Server 中创建用户体验质量配置设置</span><span class="sxs-lookup"><span data-stu-id="69a1f-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="69a1f-104">**摘要：** 了解 Skype for Business Server (QoE) 设置用户体验质量。</span><span class="sxs-lookup"><span data-stu-id="69a1f-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="69a1f-p101">用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、“抖动”量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。</span><span class="sxs-lookup"><span data-stu-id="69a1f-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="69a1f-107">安装 Skype for Business Server 时，会创建一个 QoE 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="69a1f-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="69a1f-108">管理员还可以选择在站点范围创建自定义设置。</span><span class="sxs-lookup"><span data-stu-id="69a1f-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="69a1f-109">每当使用这些站点范围的设置时，它们优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="69a1f-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="69a1f-110">例如，如果为 Redmond 站点创建站点作用域设置，则这些设置 (而不是全局设置) 在 Redmond 中管理 QoE。</span><span class="sxs-lookup"><span data-stu-id="69a1f-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="69a1f-111">QoE 配置设置可以使用 Skype for Business Server 控制面板或 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet 创建。</span><span class="sxs-lookup"><span data-stu-id="69a1f-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="69a1f-112">如果你使用 Skype for Business Server 控制面板创建新设置，以下选项将可供你使用：</span><span class="sxs-lookup"><span data-stu-id="69a1f-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="69a1f-113">**UI 设置**</span><span class="sxs-lookup"><span data-stu-id="69a1f-113">**UI setting**</span></span>|<span data-ttu-id="69a1f-114">**PowerShell 参数**</span><span class="sxs-lookup"><span data-stu-id="69a1f-114">**PowerShell parameter**</span></span>|<span data-ttu-id="69a1f-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="69a1f-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69a1f-116">名称</span><span class="sxs-lookup"><span data-stu-id="69a1f-116">Name</span></span>  <br/> |<span data-ttu-id="69a1f-117">标识</span><span class="sxs-lookup"><span data-stu-id="69a1f-117">Identity</span></span>  <br/> |<span data-ttu-id="69a1f-118">要创建的设置的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="69a1f-118">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="69a1f-119">只能在站点范围创建 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="69a1f-119">QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="69a1f-120">启用 QoE 数据的监控</span><span class="sxs-lookup"><span data-stu-id="69a1f-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="69a1f-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="69a1f-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="69a1f-122">指定是否收集 QoE 记录并将其保存到监控数据库。</span><span class="sxs-lookup"><span data-stu-id="69a1f-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="69a1f-123">启用 QoE 数据的清除</span><span class="sxs-lookup"><span data-stu-id="69a1f-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="69a1f-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="69a1f-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="69a1f-125">指定在保留 **QoE** 数据中定义的最长持续时间后是否清除记录， (天数) 属性。</span><span class="sxs-lookup"><span data-stu-id="69a1f-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="69a1f-126">QoE 数据最长保留期限为 (天) </span><span class="sxs-lookup"><span data-stu-id="69a1f-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="69a1f-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="69a1f-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="69a1f-128">从数据库中清除 QoE 数据之前存储的天数。</span><span class="sxs-lookup"><span data-stu-id="69a1f-128">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="69a1f-129">如果禁用清除，则忽略此值。</span><span class="sxs-lookup"><span data-stu-id="69a1f-129">This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="69a1f-130">New-CsQoEConfiguration cmdlet 包括 Skype for Business Server 控制面板中不可用的其他选项。</span><span class="sxs-lookup"><span data-stu-id="69a1f-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="69a1f-131">有关详细信息，请参阅 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="69a1f-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="69a1f-132">使用 Skype for Business Server 控制面板创建 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="69a1f-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="69a1f-133">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="69a1f-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="69a1f-134">有关详细信息，请参阅 **Delegate Setup Permissions**。</span><span class="sxs-lookup"><span data-stu-id="69a1f-134">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="69a1f-135">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="69a1f-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="69a1f-136">在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。</span><span class="sxs-lookup"><span data-stu-id="69a1f-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="69a1f-137">在"**用户体验质量数据"页上**，单击"**新建"。**</span><span class="sxs-lookup"><span data-stu-id="69a1f-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="69a1f-138">在 **"选择站点**"中，单击要应用策略的站点，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="69a1f-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="69a1f-139">在 **"全新用户体验质量"设置** 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="69a1f-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="69a1f-140">选择 **"启用 QoE 数据的监控"** 以启用监控。</span><span class="sxs-lookup"><span data-stu-id="69a1f-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="69a1f-141">选择 **"启用 QoE** 数据清除"以启用清除。</span><span class="sxs-lookup"><span data-stu-id="69a1f-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="69a1f-142">在 **"QoE 最长保留 (天) ，** 选择 QoE 记录应保留的最大天数。</span><span class="sxs-lookup"><span data-stu-id="69a1f-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="69a1f-143">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="69a1f-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="69a1f-144">使用 cmdlet Windows PowerShell QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="69a1f-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="69a1f-145">可以使用 Windows PowerShell 和 New-CsQoEConfiguration cmdlet 创建 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="69a1f-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="69a1f-146">可以从 Skype for Business Server 命令行管理程序 或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="69a1f-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="69a1f-147">有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="69a1f-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="69a1f-148">此过程在 Skype for Business Server 中相同。</span><span class="sxs-lookup"><span data-stu-id="69a1f-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="69a1f-149">创建新的 QoE 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="69a1f-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="69a1f-150">此命令创建应用于 Redmond 站点的 QoE 配置设置的新集合：</span><span class="sxs-lookup"><span data-stu-id="69a1f-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="69a1f-151">创建禁用 QoE 监控的新 QoE 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="69a1f-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="69a1f-152">由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="69a1f-152">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="69a1f-153">要创建使用不同属性值的设置，只需包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="69a1f-153">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="69a1f-154">例如，若要创建用户体验质量配置设置的集合，默认情况下允许禁用 QoE 记录，请使用类似这样的命令：</span><span class="sxs-lookup"><span data-stu-id="69a1f-154">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="69a1f-155">在创建新的 QoE 配置设置集合时指定多个属性值</span><span class="sxs-lookup"><span data-stu-id="69a1f-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="69a1f-156">可以通过包含多个参数来包含多个属性值。</span><span class="sxs-lookup"><span data-stu-id="69a1f-156">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="69a1f-157">例如，此命令将新设置配置为将 QoE 数据保留 30 天，并清除 3：00 AM 的旧数据：</span><span class="sxs-lookup"><span data-stu-id="69a1f-157">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="69a1f-158">有关详细信息，请参阅 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="69a1f-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

