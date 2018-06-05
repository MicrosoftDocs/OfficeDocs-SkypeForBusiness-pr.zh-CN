---
title: 在 Skype for Business Server 2015 中查看 CDR 配置信息
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 摘要： 了解如何使用业务服务器 2015 Skype 中呼叫详细信息记录 (CDR)。
ms.openlocfilehash: cd143db6ebc0c4e284763ccf4beb9c545fa24ff5
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569440"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a><span data-ttu-id="7c7aa-103">在 Skype for Business Server 2015 中查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="7c7aa-103">View CDR configuration information in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7c7aa-104">**摘要：** 了解如何使用业务服务器 2015 Skype 中呼叫详细信息记录 (CDR)。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7c7aa-p101">利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="7c7aa-107">为业务服务器 2015，单个，安装 Skype 时为您创建的 CDR 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-107">When you install Skype for Business Server 2015, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="7c7aa-108">管理员还可以选择创建可应用于各个站点的自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="7c7aa-109">可以使用 Skype 业务 Server Control Panel 或[Get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 的 CDR 配置设置中使用查看您的组织中。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7c7aa-110">使用适用于业务 Server Control Panel Skype 查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="7c7aa-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7c7aa-111">Skype 的业务 Server Control Panel 中单击**监控和存档**。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="7c7aa-p103">所有 CDR 配置设置的列表将显示在“**呼叫详细信息记录**”选项卡中；对于每个设置集合，您将看到集合“**名称**”；是否已启用 CDR（“**CDR**”属性）；是否已启用清除（“**CDR 清除**”属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“**编辑**”，然后单击“**显示详细信息**”。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7c7aa-115">通过使用 Windows PowerShell cmdlet 查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="7c7aa-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7c7aa-116">您可以使用 Windows PowerShell 和 Get-cscdrconfiguration cmdlet 查看 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="7c7aa-117">可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7c7aa-118">有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7c7aa-119">过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="7c7aa-120">查看 CDR 配置信息</span><span class="sxs-lookup"><span data-stu-id="7c7aa-120">To view CDR configuration information</span></span>

- <span data-ttu-id="7c7aa-121">若要查看有关所有 CDR 配置设置的信息，业务 Server 命令行管理程序 Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="7c7aa-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="7c7aa-122">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="7c7aa-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="7c7aa-123">有关详细信息，请参阅[Get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7c7aa-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

