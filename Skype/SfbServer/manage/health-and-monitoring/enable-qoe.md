---
title: 在 Skype for Business Server 中启用用户体验质量
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
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 摘要：了解如何在 Skype for Business Server (QoE) 用户体验质量。
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095206"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="a374d-103">在 Skype for Business Server 中启用用户体验质量</span><span class="sxs-lookup"><span data-stu-id="a374d-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="a374d-104">**摘要：了解如何** 在 Skype for Business Server (QoE) 用户体验质量。</span><span class="sxs-lookup"><span data-stu-id="a374d-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="a374d-105">用户体验质量 (QoE) 记录指示媒体质量以及有关呼叫和会话中所涉及参与者、设备名称、驱动程序、IP 地址和终结点类型的信息的数值型数据。</span><span class="sxs-lookup"><span data-stu-id="a374d-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="a374d-106">有关详细信息，请参阅规划文档中的[Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="a374d-106">For details, see [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation.</span></span>

<span data-ttu-id="a374d-107">使用以下过程为整个组织或组织中的每个站点启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="a374d-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="a374d-108">为了启用 QoE，必须首先配置监控和监控后端数据库。</span><span class="sxs-lookup"><span data-stu-id="a374d-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="a374d-109">有关详细信息，请参阅[Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="a374d-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a374d-110">使用 Skype for Business Server 控制面板启用 QoE</span><span class="sxs-lookup"><span data-stu-id="a374d-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a374d-111">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a374d-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="a374d-112">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a374d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a374d-113">在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。</span><span class="sxs-lookup"><span data-stu-id="a374d-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="a374d-114">在“用户体验质量数据”页上，单击表中相应的集合，再单击“操作”，然后单击“启用 QoE”。</span><span class="sxs-lookup"><span data-stu-id="a374d-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a374d-115">使用 Cmdlet 启用 qoE Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a374d-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a374d-116">可以使用 Windows PowerShell **和 Set-CsQoEConfiguration** cmdlet 启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="a374d-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="a374d-117">可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a374d-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a374d-118">有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="a374d-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a374d-119">此过程在 Skype for Business Server 中是相同的。</span><span class="sxs-lookup"><span data-stu-id="a374d-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="a374d-120">对单个位置启用 QoE</span><span class="sxs-lookup"><span data-stu-id="a374d-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="a374d-121">要启用 QoE，请将 EnableQoE 参数设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="a374d-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="a374d-122">对单个位置禁用 QoE</span><span class="sxs-lookup"><span data-stu-id="a374d-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="a374d-p104">要禁用 QoE，请将 EnableQoE 参数设置为 False ($False)。这不会卸载监控。但会暂停 QoE 数据的收集和存储。</span><span class="sxs-lookup"><span data-stu-id="a374d-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="a374d-126">使用单个命令在多个位置启用 QoE</span><span class="sxs-lookup"><span data-stu-id="a374d-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="a374d-127">以下命令可对组织中当前使用的所有 QoE 配置设置启用 QoE。</span><span class="sxs-lookup"><span data-stu-id="a374d-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="a374d-128">有关详细信息，请参阅 [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a374d-128">For details, see [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="a374d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a374d-129">See also</span></span>

[<span data-ttu-id="a374d-130">规划监控</span><span class="sxs-lookup"><span data-stu-id="a374d-130">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="a374d-131">部署监控</span><span class="sxs-lookup"><span data-stu-id="a374d-131">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)