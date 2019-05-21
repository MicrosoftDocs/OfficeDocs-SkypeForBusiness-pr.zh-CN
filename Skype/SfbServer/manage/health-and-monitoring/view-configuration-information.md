---
title: 查看 Skype for Business 服务器中的 CDR 配置信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '摘要: 了解如何在 Skype for Business 服务器中使用呼叫详细记录 (CDR)。'
ms.openlocfilehash: e0aed0c26672b83cb223ba763eb6224025d68118
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279646"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="71ca5-103">查看 Skype for Business 服务器中的 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="71ca5-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="71ca5-104">**摘要:** 了解如何在 Skype for Business 服务器中使用呼叫详细记录 (CDR)。</span><span class="sxs-lookup"><span data-stu-id="71ca5-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="71ca5-p101">利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="71ca5-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="71ca5-107">安装 Skype for Business 服务器时, 将为你创建单个的 CDR 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="71ca5-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="71ca5-108">管理员还可以选择可应用于各个站点的自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="71ca5-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="71ca5-109">你可以使用 Skype for Business Server 控制面板或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 查看你的组织中使用的 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="71ca5-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="71ca5-110">使用 Skype for Business 服务器控制面板查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="71ca5-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="71ca5-111">在 Skype for Business 服务器控制面板中, 单击 "**监视和存档**"。</span><span class="sxs-lookup"><span data-stu-id="71ca5-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="71ca5-p103">所有 CDR 配置设置的列表将显示在“**呼叫详细信息记录**”选项卡中；对于每个设置集合，您将看到集合“**名称**”；是否已启用 CDR（“**CDR**”属性）；是否已启用清除（“**CDR 清除**”属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“**编辑**”，然后单击“**显示详细信息**”。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71ca5-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="71ca5-115">使用 Windows PowerShell cmdlet 查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="71ca5-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="71ca5-116">你可以使用 Windows PowerShell 和 CsCdrConfiguration cmdlet 查看 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="71ca5-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="71ca5-117">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71ca5-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="71ca5-118">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅博客文章["快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="71ca5-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="71ca5-119">在 Skype for Business 服务器中, 此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="71ca5-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="71ca5-120">查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="71ca5-120">To view CDR configuration information</span></span>

- <span data-ttu-id="71ca5-121">若要查看有关所有 CDR 配置设置的信息, 请在 Skype for Business Server 命令行管理器中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="71ca5-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="71ca5-122">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="71ca5-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="71ca5-123">有关详细信息, 请参阅[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="71ca5-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

