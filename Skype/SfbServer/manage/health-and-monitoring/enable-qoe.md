---
title: 在 Skype for Business 服务器中启用体验质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: '摘要: 了解如何在 Skype for Business 服务器中启用体验质量 (QoE)。'
ms.openlocfilehash: 90110c5664e80ac1d4f9d382c20e0fd58d9ce134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305708"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="7b384-103">在 Skype for Business 服务器中启用体验质量</span><span class="sxs-lookup"><span data-stu-id="7b384-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="7b384-104">**摘要:** 了解如何在 Skype For business 服务器中启用体验质量 (QoE)。</span><span class="sxs-lookup"><span data-stu-id="7b384-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="7b384-p101">用户体验质量 (QoE) 记录指示媒体质量以及有关呼叫和会话中所涉及参与者、设备名称、驱动程序、IP 地址和终结点类型的信息的数值型数据。有关详细信息，请参阅规划文档中的[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7b384-p101">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions. For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="7b384-107">使用以下过程为整个组织或组织中的每个站点启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="7b384-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="7b384-p102">为了启用 QoE，必须首先配置监控和监控后端数据库。有关详细信息，请参阅[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7b384-p102">To enable QoE, you must first configure monitoring and a monitoring back-end database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7b384-110">使用 Skype for Business 服务器控制面板启用 QoE</span><span class="sxs-lookup"><span data-stu-id="7b384-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="7b384-111">从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你部署了 Skype for Business 服务器的网络中的任何计算机.</span><span class="sxs-lookup"><span data-stu-id="7b384-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="7b384-112">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="7b384-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="7b384-113">在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。</span><span class="sxs-lookup"><span data-stu-id="7b384-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="7b384-114">在“**用户体验质量数据**”页上，单击表中相应的集合，再单击“**操作**”，然后单击“**启用 QoE**”。</span><span class="sxs-lookup"><span data-stu-id="7b384-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7b384-115">使用 Windows PowerShell Cmdlet 启用 QoE</span><span class="sxs-lookup"><span data-stu-id="7b384-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7b384-116">你可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="7b384-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="7b384-117">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b384-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7b384-118">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅博客文章["快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="7b384-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7b384-119">在 Skype for Business 服务器中, 此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="7b384-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="7b384-120">对单个位置启用 QoE</span><span class="sxs-lookup"><span data-stu-id="7b384-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="7b384-121">要启用 QoE，请将 EnableQoE 参数设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="7b384-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="7b384-122">对单个位置禁用 QoE</span><span class="sxs-lookup"><span data-stu-id="7b384-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="7b384-p104">要禁用 QoE，请将 EnableQoE 参数设置为 False ($False)。这不会卸载监控。但会暂停 QoE 数据的收集和存储。</span><span class="sxs-lookup"><span data-stu-id="7b384-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="7b384-126">使用单个命令在多个位置启用 QoE</span><span class="sxs-lookup"><span data-stu-id="7b384-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="7b384-127">以下命令可对组织中当前使用的所有 QoE 配置设置启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="7b384-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="7b384-128">有关详细信息, 请参阅[Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7b384-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="7b384-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b384-129">See also</span></span>

[<span data-ttu-id="7b384-130">规划监视</span><span class="sxs-lookup"><span data-stu-id="7b384-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="7b384-131">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="7b384-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

