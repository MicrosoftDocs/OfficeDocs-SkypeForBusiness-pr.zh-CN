---
title: 删除 Skype 中的企业服务器用户体验质量配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 摘要： 了解如何删除 Business Server Skype 中的用户体验质量 (QoE) 设置。
ms.openlocfilehash: e177b0870192eba996984e1eb3aae6d520db4661
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926625"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9fda5-103">删除 Skype 中的企业服务器用户体验质量配置设置</span><span class="sxs-lookup"><span data-stu-id="9fda5-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9fda5-104">**摘要：** 了解如何删除 Business Server Skype 中的用户体验质量 (QoE) 设置。</span><span class="sxs-lookup"><span data-stu-id="9fda5-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9fda5-p101">用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、"抖动"量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。</span><span class="sxs-lookup"><span data-stu-id="9fda5-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="9fda5-107">对于业务服务器，单个，安装 Skype 时为您创建的 QoE 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="9fda5-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="9fda5-108">管理员还可以选择可应用于各个站点的自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="9fda5-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="9fda5-109">根据设计，在站点作用域配置的设置优先于在全局作用域配置的设置。</span><span class="sxs-lookup"><span data-stu-id="9fda5-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="9fda5-110">如果您删除站点作用域设置，则将通过使用全局设置在该站点管理 QoE。</span><span class="sxs-lookup"><span data-stu-id="9fda5-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="9fda5-111">请注意，您还可以"删除"全局设置。</span><span class="sxs-lookup"><span data-stu-id="9fda5-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="9fda5-112">但将不会实际删除全局设置。</span><span class="sxs-lookup"><span data-stu-id="9fda5-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="9fda5-113">不过，该集合中的所有属性将重置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="9fda5-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="9fda5-114">例如，在 QoE 配置设置的集合中启用了默认清除功能。</span><span class="sxs-lookup"><span data-stu-id="9fda5-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="9fda5-115">假定您修改了全局集合，这样就会禁用清除功能。</span><span class="sxs-lookup"><span data-stu-id="9fda5-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="9fda5-116">如果稍后删除全局设置，则会将这些属性全部重置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="9fda5-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="9fda5-117">在这种情况下，这意味着又重新启用清除功能。</span><span class="sxs-lookup"><span data-stu-id="9fda5-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="9fda5-118">您可以使用适用于业务 Server Control Panel Skype 或使用[Remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet 删除 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="9fda5-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9fda5-119">使用适用于业务 Server Control Panel Skype 删除 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="9fda5-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9fda5-p104">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。</span><span class="sxs-lookup"><span data-stu-id="9fda5-p104">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="9fda5-122">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="9fda5-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9fda5-123">在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。</span><span class="sxs-lookup"><span data-stu-id="9fda5-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="9fda5-124">在“**用户体验质量数据**”上，单击所需的策略，单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="9fda5-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="9fda5-125">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9fda5-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9fda5-126">使用 Windows PowerShell Cmdlet 删除 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="9fda5-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9fda5-127">您可以使用 Windows PowerShell 和**Remove-csqoeconfiguration** cmdlet 删除 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="9fda5-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="9fda5-128">可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9fda5-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9fda5-129">有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="9fda5-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9fda5-130">过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="9fda5-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9fda5-131">删除 QoE 配置设置的指定的集合</span><span class="sxs-lookup"><span data-stu-id="9fda5-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="9fda5-132">此命令可用于删除应用于 Redmond 站点的 QoE 配置设置：</span><span class="sxs-lookup"><span data-stu-id="9fda5-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="9fda5-133">删除应用于该站点作用域的所有 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="9fda5-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="9fda5-134">此命令可用于删除应用于该站点作用域的所有 QoE 配置设置：</span><span class="sxs-lookup"><span data-stu-id="9fda5-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="9fda5-135">删除禁用 QoE 监控处的所有 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="9fda5-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="9fda5-136">此命令用于删除已禁用 QoE 监控处的所有 QoE 配置设置：</span><span class="sxs-lookup"><span data-stu-id="9fda5-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="9fda5-137">有关详细信息，请参阅[Remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9fda5-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9fda5-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fda5-138">See also</span></span>

[<span data-ttu-id="9fda5-139">为业务 Server 中手动清除呼叫详细信息记录和 Skype 中的用户体验质量数据库</span><span class="sxs-lookup"><span data-stu-id="9fda5-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

