---
title: 删除 Skype for Business Server 中的 CDR 配置设置的现有集合
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 摘要：了解如何在 Skype for Business Server 中删除 CDR 配置设置。
ms.openlocfilehash: ca6691d6a1a19e0d9219a256986b683b719da885
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816962"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c1121-103">删除 Skype for Business Server 中的 CDR 配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="c1121-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c1121-104">**摘要：** 了解如何删除 Skype for Business Server 中的 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="c1121-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c1121-p101">利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="c1121-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="c1121-107">安装 Skype for Business Server 时，会创建一个 CDR 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="c1121-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="c1121-108">管理员还可以选择创建可应用于各个站点的自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="c1121-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="c1121-109">根据设计，在站点范围配置的设置优先于在全局范围配置的设置。</span><span class="sxs-lookup"><span data-stu-id="c1121-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="c1121-110">如果您删除站点范围的设置，则在该站点中使用全局设置管理 CDR。</span><span class="sxs-lookup"><span data-stu-id="c1121-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="c1121-111">请注意，您还可以"删除"全局设置。</span><span class="sxs-lookup"><span data-stu-id="c1121-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="c1121-112">但将不会实际删除全局设置。</span><span class="sxs-lookup"><span data-stu-id="c1121-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="c1121-113">不过，该集合中的所有属性将重置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="c1121-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="c1121-114">例如，默认情况下，在 CDR 配置设置集合中启用清除。</span><span class="sxs-lookup"><span data-stu-id="c1121-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="c1121-115">假定您修改了全局集合，这样就会禁用清除功能。</span><span class="sxs-lookup"><span data-stu-id="c1121-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="c1121-116">如果稍后删除全局设置，则会将这些属性全部重置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="c1121-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="c1121-117">在这种情况下，这意味着又重新启用清除功能。</span><span class="sxs-lookup"><span data-stu-id="c1121-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="c1121-118">可以使用 Skype for Business Server 控制面板或 [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet 删除 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="c1121-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="c1121-119">使用 Skype for Business Server 控制面板删除 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="c1121-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c1121-120">在 Skype for Business Server 控制面板中，单击 **"监控和存档"。**</span><span class="sxs-lookup"><span data-stu-id="c1121-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="c1121-p104">在“呼叫详细信息记录”选项卡上，选择要删除的 CDR 设置的集合。若要删除多个集合，请单击第一个集合，然后在按住 Ctrl 键的同时单击其他集合。</span><span class="sxs-lookup"><span data-stu-id="c1121-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="c1121-123">单击“编辑”，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="c1121-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="c1121-124">在 Skype for Business Server 控制面板对话框中，单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="c1121-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c1121-125">使用 cmdlet 删除 CDR Windows PowerShell设置</span><span class="sxs-lookup"><span data-stu-id="c1121-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c1121-126">可以使用 Windows PowerShell **和 Remove-CsCdrConfiguration** cmdlet 删除呼叫详细信息记录配置设置。</span><span class="sxs-lookup"><span data-stu-id="c1121-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="c1121-127">可以从 Skype for Business Server 命令行管理程序 或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c1121-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c1121-128">有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="c1121-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c1121-129">此过程在 Skype for Business Server 中相同。</span><span class="sxs-lookup"><span data-stu-id="c1121-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="c1121-130">删除指定的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="c1121-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="c1121-131">此命令删除适用于 Redmond 站点的 CDR 配置设置：</span><span class="sxs-lookup"><span data-stu-id="c1121-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="c1121-132">删除应用于站点范围的所有 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="c1121-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="c1121-133">此命令删除适用于站点范围的所有 CDR 配置设置：</span><span class="sxs-lookup"><span data-stu-id="c1121-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="c1121-134">有关详细信息，请参阅 [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="c1121-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c1121-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1121-135">See also</span></span>

[<span data-ttu-id="c1121-136">在 Skype for Business Server 中手动清除呼叫详细信息记录和用户体验质量数据库</span><span class="sxs-lookup"><span data-stu-id="c1121-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

