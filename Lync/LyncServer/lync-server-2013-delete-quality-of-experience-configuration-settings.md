---
title: Lync Server 2013：删除体验质量配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a313e80674a7eefd57320a5a30a9dd999fc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e883a-102">删除 Lync Server 2013 中的体验质量配置设置</span><span class="sxs-lookup"><span data-stu-id="e883a-102">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e883a-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e883a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e883a-p101">用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、“抖动”量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。</span><span class="sxs-lookup"><span data-stu-id="e883a-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="e883a-106">安装 Microsoft Lync Server 2013 时，将为您创建一个 QoE 配置设置的单一全局集合。</span><span class="sxs-lookup"><span data-stu-id="e883a-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="e883a-107">管理员还可以选择创建可应用于各个站点的自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="e883a-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="e883a-108">根据设计，在站点作用域配置的设置优先于在全局作用域配置的设置。</span><span class="sxs-lookup"><span data-stu-id="e883a-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="e883a-109">如果您删除站点作用域设置，则将通过使用全局设置在该站点管理 QoE。</span><span class="sxs-lookup"><span data-stu-id="e883a-109">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="e883a-p103">请注意，您还可以“删除”全局设置。但将不会实际删除全局设置。不过，该集合中的所有属性将重置为其默认值。例如，在 QoE 配置设置的集合中启用了默认清除功能。假定您修改了全局集合，这样就会禁用清除功能。如果稍后删除全局设置，则会将这些属性全部重置为其默认值。在这种情况下，这意味着又重新启用清除功能。</span><span class="sxs-lookup"><span data-stu-id="e883a-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of QoE configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="e883a-117">您可以使用 Lync Server 控制面板或使用[new-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) Cmdlet 删除 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="e883a-117">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e883a-118">使用 Lync Server 控制面板删除 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="e883a-118">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e883a-119">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="e883a-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e883a-120">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e883a-120">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e883a-121">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e883a-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e883a-122">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="e883a-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e883a-123">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“用户体验质量数据”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e883a-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="e883a-124">在“用户体验质量数据”\*\*\*\* 上，单击所需的策略，单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e883a-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="e883a-125">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e883a-125">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e883a-126">使用 Windows PowerShell Cmdlet 删除 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="e883a-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e883a-127">您可以使用 Windows PowerShell 和**new-csqoeconfiguration** Cmdlet 删除 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="e883a-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="e883a-128">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e883a-128">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e883a-129">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="e883a-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="e883a-130">删除 QoE 配置设置的指定的集合</span><span class="sxs-lookup"><span data-stu-id="e883a-130">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="e883a-131">此命令可用于删除应用于 Redmond 站点的 QoE 配置设置：</span><span class="sxs-lookup"><span data-stu-id="e883a-131">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="e883a-132">删除应用于该站点作用域的所有 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="e883a-132">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="e883a-133">此命令可用于删除应用于该站点作用域的所有 QoE 配置设置：</span><span class="sxs-lookup"><span data-stu-id="e883a-133">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="e883a-134">删除禁用 QoE 监控处的所有 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="e883a-134">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="e883a-135">此命令用于删除已禁用 QoE 监控处的所有 QoE 配置设置：</span><span class="sxs-lookup"><span data-stu-id="e883a-135">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="e883a-136">有关详细信息，请参阅[new-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="e883a-136">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

