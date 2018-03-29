---
title: 在 Skype for Business Server 2015 中修改用户体验质量设置
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 摘要： 了解如何指定 QoE 数据保留在 Skype 业务服务器 2015年。
ms.openlocfilehash: 99a85a389b225d57b48b52b3f6f1d5b66e93f122
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="56e00-103">在 Skype for Business Server 2015 中修改用户体验质量设置</span><span class="sxs-lookup"><span data-stu-id="56e00-103">Modify Quality of Experience settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="56e00-104">**摘要：**了解如何指定 QoE 数据保留在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="56e00-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="56e00-p101">默认情况下，用户体验质量 (QoE) 数据会在 60 天后清除。可以使用“**用户体验质量数据**”页上的设置将该数据保留更长或更短的时间。如果禁用 QoE，则在启用 QoE 之前捕获的数据也将清除。</span><span class="sxs-lookup"><span data-stu-id="56e00-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56e00-p102">应该对呼叫详细信息记录 (CDR) 和 QoE 进行配置，使二者保留数据的天数相同。监控报告主页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。</span><span class="sxs-lookup"><span data-stu-id="56e00-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="56e00-111">以下过程介绍如何配置 QoE 数据的清除设置。</span><span class="sxs-lookup"><span data-stu-id="56e00-111">The following procedure describes how to configure purge settings for QoE data.</span></span> 
  
### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="56e00-112">若要指定保留的 QoE 数据通过 Skype 业务服务器的控制面板</span><span class="sxs-lookup"><span data-stu-id="56e00-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="56e00-113">作为 RTCUniversalServerAdmins 组的成员身份或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员登录到该计算机。</span><span class="sxs-lookup"><span data-stu-id="56e00-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="56e00-114">有关详细信息，请参阅**代理安装程序权限**。</span><span class="sxs-lookup"><span data-stu-id="56e00-114">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="56e00-115">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="56e00-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="56e00-116">在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。</span><span class="sxs-lookup"><span data-stu-id="56e00-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="56e00-117">在“**用户体验质量数据**”页上，单击表中的相应站点，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="56e00-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="56e00-118">要打开清除，请选择“**启用 QoE 清除**”。</span><span class="sxs-lookup"><span data-stu-id="56e00-118">To turn on purging, select **Enable Purging of QoE**.</span></span>
    
6. <span data-ttu-id="56e00-119">在“**QoE 最长保留期限（天）**”中选择 QoE 数据的最长保留天数。</span><span class="sxs-lookup"><span data-stu-id="56e00-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>
    
7. <span data-ttu-id="56e00-120">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="56e00-120">Click **Commit**.</span></span>
    
## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="56e00-121">通过使用 Windows PowerShell Cmdlet 指定 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="56e00-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="56e00-122">您可以通过使用 Windows PowerShell 和**一组 CsQoEConfiguration** cmdlet 创建 QoE 保留设置。</span><span class="sxs-lookup"><span data-stu-id="56e00-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="56e00-123">可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="56e00-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="56e00-124">有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="56e00-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="56e00-125">该过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="56e00-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="56e00-126">为特定位置指定 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="56e00-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="56e00-127">此命令会为 Redmond 站点启用 QoE 数据的清除，并将该站点配置为保留 QoE 数据 20 天。</span><span class="sxs-lookup"><span data-stu-id="56e00-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="56e00-128">为多个位置指定 QoE 保留</span><span class="sxs-lookup"><span data-stu-id="56e00-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="56e00-129">此命令会为组织中使用的所有 QoE 配置设置配置 QoE 保留。</span><span class="sxs-lookup"><span data-stu-id="56e00-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 
  ```

<span data-ttu-id="56e00-130">有关详细信息，请参阅[设置 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="56e00-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="56e00-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56e00-131">See also</span></span>

#### 

[<span data-ttu-id="56e00-132">部署监视</span><span class="sxs-lookup"><span data-stu-id="56e00-132">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

