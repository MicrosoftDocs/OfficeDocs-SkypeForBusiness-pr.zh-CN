---
title: 在 Skype for Business Server 2015 中启用用户体验质量
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要： 了解如何启用业务服务器 2015年体验质量 (QoE) 在 Skype。
ms.openlocfilehash: 8c63a1bf493e601c4936b83cc9edfaa6e3727f26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-quality-of-experience-in-skype-for-business-server-2015"></a><span data-ttu-id="22ebc-103">在 Skype for Business Server 2015 中启用用户体验质量</span><span class="sxs-lookup"><span data-stu-id="22ebc-103">Enable Quality of Experience in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="22ebc-104">**摘要：**了解如何启用体验质量 (QoE) 在 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="22ebc-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="22ebc-105">用户体验质量 (QoE) 记录指示媒体质量以及有关呼叫和会话中所涉及参与者、设备名称、驱动程序、IP 地址和终结点类型的信息的数值型数据。</span><span class="sxs-lookup"><span data-stu-id="22ebc-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="22ebc-106">有关详细信息，请参阅规划文档中的[监视计划](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="22ebc-106">For details, see [Planning for Monitoring](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>
  
<span data-ttu-id="22ebc-107">使用以下过程为整个组织或组织中的每个站点启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="22ebc-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="22ebc-108">为了启用 QoE，必须首先配置监控和监控后端数据库。</span><span class="sxs-lookup"><span data-stu-id="22ebc-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="22ebc-109">有关详细信息，请参阅[部署监视](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="22ebc-109">For details, see [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span> 
  
### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="22ebc-110">若要启用 QoE 通过 Skype 业务服务器的控制面板</span><span class="sxs-lookup"><span data-stu-id="22ebc-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="22ebc-111">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="22ebc-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="22ebc-112">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="22ebc-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="22ebc-113">在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。</span><span class="sxs-lookup"><span data-stu-id="22ebc-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span> 
    
4. <span data-ttu-id="22ebc-114">在“**用户体验质量数据**”页上，单击表中相应的集合，再单击“**操作**”，然后单击“**启用 QoE**”。</span><span class="sxs-lookup"><span data-stu-id="22ebc-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>
    
## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="22ebc-115">通过使用 Windows PowerShell Cmdlet 启用 QoE</span><span class="sxs-lookup"><span data-stu-id="22ebc-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="22ebc-116">您可以通过使用 Windows PowerShell 和**一组 CsQoEConfiguration** cmdlet 启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="22ebc-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="22ebc-117">可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="22ebc-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="22ebc-118">有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="22ebc-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="22ebc-119">该过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="22ebc-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="22ebc-120">对单个位置启用 QoE</span><span class="sxs-lookup"><span data-stu-id="22ebc-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="22ebc-121">要启用 QoE，请将 EnableQoE 参数设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="22ebc-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="22ebc-122">对单个位置禁用 QoE</span><span class="sxs-lookup"><span data-stu-id="22ebc-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="22ebc-p104">要禁用 QoE，请将 EnableQoE 参数设置为 False ($False)。这不会卸载监控。但会暂停 QoE 数据的收集和存储。</span><span class="sxs-lookup"><span data-stu-id="22ebc-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="22ebc-126">使用单个命令在多个位置启用 QoE</span><span class="sxs-lookup"><span data-stu-id="22ebc-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="22ebc-127">以下命令可对组织中当前使用的所有 QoE 配置设置启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="22ebc-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="22ebc-128">有关详细信息，请参阅[设置 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="22ebc-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="22ebc-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22ebc-129">See also</span></span>

[<span data-ttu-id="22ebc-130">用于监视计划</span><span class="sxs-lookup"><span data-stu-id="22ebc-130">Planning for Monitoring</span></span>](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[<span data-ttu-id="22ebc-131">部署监视</span><span class="sxs-lookup"><span data-stu-id="22ebc-131">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

