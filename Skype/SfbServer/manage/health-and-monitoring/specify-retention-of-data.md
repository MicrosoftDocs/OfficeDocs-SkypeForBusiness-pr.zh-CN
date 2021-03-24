---
title: 在 Skype for Business Server 中指定 CDR 数据的保留
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 摘要：了解如何管理 Skype for Business Server (CDR) 数据的呼叫详细信息记录。
ms.openlocfilehash: abf6461a76ced9d3ba07e4c5157dd4d14bab60a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104388"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="0c8e9-103">在 Skype for Business Server 中指定 CDR 数据的保留</span><span class="sxs-lookup"><span data-stu-id="0c8e9-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="0c8e9-104">**摘要：** 了解如何管理 Skype for Business Server (CDR) 数据的呼叫详细信息记录。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="0c8e9-p101">默认情况下，呼叫详细信息记录 (CDR) 数据会在 60 天后清除。可以使用“呼叫详细信息记录”页上的设置将该数据保留更长或更短的时间。如果禁用 CDR，则在启用 CDR 之前捕获的数据也将清除。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c8e9-p102">应该对 CDR 和用户体验质量 (QoE) 进行配置，使二者保留数据的天数相同。监控服务器报告网页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="0c8e9-111">使用以下过程来配置 CDR 数据的清除设置。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="0c8e9-112">指定 CDR 数据的保留</span><span class="sxs-lookup"><span data-stu-id="0c8e9-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="0c8e9-113">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="0c8e9-114">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0c8e9-115">在左侧导航栏中，单击“监控和存档”，然后单击“呼叫详细信息记录”。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="0c8e9-116">在“呼叫详细信息记录”页上，单击表中的相应站点，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="0c8e9-117">要打开清除，请选择“启用 CDR 清除”。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="0c8e9-118">在“CDR 最长保留期限(天):”中选择呼叫详细信息记录的最长保留天数。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="0c8e9-119">在“错误报告数据最长保留期限(天):”中选择错误报告的最长保留天数。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="0c8e9-120">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0c8e9-121">使用 cmdlet 指定 CDR Windows PowerShell保留</span><span class="sxs-lookup"><span data-stu-id="0c8e9-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0c8e9-122">您可以使用 Windows PowerShell 和 Set-CsCdrConfiguration cmdlet 来创建 CDR 保留设置。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="0c8e9-123">可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0c8e9-124">有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="0c8e9-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="0c8e9-125">此过程在 Skype for Business Server 中是相同的。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="0c8e9-126">指定特定位置的 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="0c8e9-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="0c8e9-127">此命令允许清除 Redmond 站点的 CDR 数据，并将该站点配置为将 CDR 数据和错误报告数据保留 20 天。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="0c8e9-128">指定多个位置的 CDR 保留</span><span class="sxs-lookup"><span data-stu-id="0c8e9-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="0c8e9-129">此命令会为组织中使用的所有 CDR 配置设置配置 CDR 保留。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="0c8e9-130">有关详细信息，请参阅 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0c8e9-130">For more information, see the help topic for the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c8e9-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c8e9-131">See also</span></span>

[<span data-ttu-id="0c8e9-132">Skype for Business Server (CDR) 呼叫详细信息记录</span><span class="sxs-lookup"><span data-stu-id="0c8e9-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)