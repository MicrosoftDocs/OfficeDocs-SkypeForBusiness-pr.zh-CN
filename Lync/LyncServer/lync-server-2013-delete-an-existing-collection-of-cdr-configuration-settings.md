---
title: Lync Server 2013：删除现有 CDR 配置设置集合
description: Lync Server 2013：删除现有 CDR 配置设置集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e80f6d9e9d878dad258e494095b10c402029932b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572888"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="2712e-103">在 Lync Server 2013 中删除现有 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="2712e-103">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2712e-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2712e-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2712e-p101">利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="2712e-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="2712e-107">安装 Microsoft Lync Server 2013 时，将为你创建一个 CDR 配置设置的单一全局集合。</span><span class="sxs-lookup"><span data-stu-id="2712e-107">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="2712e-108">管理员还可以选择创建可应用于各个站点的自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="2712e-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="2712e-109">根据设计，在站点范围配置的设置优先于在全局范围配置的设置。</span><span class="sxs-lookup"><span data-stu-id="2712e-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="2712e-110">如果您删除站点范围的设置，则在该站点中使用全局设置管理 CDR。</span><span class="sxs-lookup"><span data-stu-id="2712e-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="2712e-p103">请注意，您也可以“删除”全局设置。但是，这不会实际删除全局设置，而是将该集合中的所有属性重置为其默认值。例如，默认情况下，将在 CDR 配置设置集合中启用清除。假定您修改全局集合以便禁用清除。如果您稍后删除全局设置，则所有属性都将被重置为其默认值。在此情况下，这意味着将再次启用清除。</span><span class="sxs-lookup"><span data-stu-id="2712e-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="2712e-118">您可以使用 Lync Server 控制面板或 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) CMDLET 删除 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="2712e-118">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="2712e-119">使用 Lync Server 控制面板删除 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="2712e-119">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2712e-120">在 "Lync Server 控制面板" 中，单击 " **监控和存档**"。</span><span class="sxs-lookup"><span data-stu-id="2712e-120">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="2712e-p104">在“呼叫详细信息记录”\*\*\*\* 选项卡上，选择要删除的 CDR 设置的集合。若要删除多个集合，请单击第一个集合，然后在按住 Ctrl 键的同时单击其他集合。</span><span class="sxs-lookup"><span data-stu-id="2712e-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="2712e-123">单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2712e-123">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="2712e-124">在 "Lync Server 控制面板" 对话框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2712e-124">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2712e-125">使用 Windows PowerShell Cmdlet 删除 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="2712e-125">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2712e-126">您可以使用 Windows PowerShell 和 **set-cscdrconfiguration** cmdlet 删除呼叫详细信息记录配置设置。</span><span class="sxs-lookup"><span data-stu-id="2712e-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="2712e-127">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2712e-127">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2712e-128">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="2712e-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="2712e-129">删除指定的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="2712e-129">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="2712e-130">此命令删除适用于 Redmond 站点的 CDR 配置设置：</span><span class="sxs-lookup"><span data-stu-id="2712e-130">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="2712e-131">删除应用到站点范围的所有 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="2712e-131">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="2712e-132">此命令删除适用于站点范围的所有 CDR 配置设置：</span><span class="sxs-lookup"><span data-stu-id="2712e-132">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="2712e-133">删除禁用呼叫详细信息记录的 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="2712e-133">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="2712e-134">此命令删除已禁用呼叫详细信息记录的所有 CDR 配置设置：</span><span class="sxs-lookup"><span data-stu-id="2712e-134">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="2712e-135">有关详细信息，请参阅 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="2712e-135">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

