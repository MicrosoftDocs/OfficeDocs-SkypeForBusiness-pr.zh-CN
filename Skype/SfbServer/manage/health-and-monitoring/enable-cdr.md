---
title: 为业务服务器启用呼叫详细信息记录在 Skype
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 摘要： 了解如何启用呼叫详细信息记录 (CDR) 记录中 Skype 业务服务器。
ms.openlocfilehash: 8ba053c95dcb9e43b6951671853d2c064ad5542f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884510"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="057b3-103">为业务服务器启用呼叫详细信息记录在 Skype</span><span class="sxs-lookup"><span data-stu-id="057b3-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="057b3-104">**摘要：** 了解如何启用呼叫详细信息记录 (CDR) 记录中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="057b3-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="057b3-p101">呼叫详细记录 (CDR) 记录了有关对等活动（包括即时消息、IP 语音 (VoIP) 呼叫、应用程序共享、文件传输和会议）的使用和诊断信息。使用数据可以用于计算投资回报率 (ROI)，诊断数据可以用于解决对等活动和会议中遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="057b3-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="057b3-107">使用以下过程为整个组织或组织中的每个站点启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="057b3-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="057b3-p102">为了启用 CDR，必须配置监控和监控数据库。有关详细信息，请参阅[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="057b3-p102">In order to enable CDR you must configure monitoring and a monitoring database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="057b3-110">与 Skype 的 CDR 启用业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="057b3-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="057b3-111">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="057b3-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="057b3-112">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="057b3-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="057b3-113">在左侧导航栏中，单击“**监控和存档**”，然后单击“**呼叫详细信息记录**”。</span><span class="sxs-lookup"><span data-stu-id="057b3-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="057b3-114">在“**呼叫详细信息记录**”页上，单击表中的相应站点，再单击“**操作**”，然后单击“**启用 CDR**”。</span><span class="sxs-lookup"><span data-stu-id="057b3-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="057b3-115">默认情况下，CDR 处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="057b3-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="057b3-116">使用 Windows PowerShell cmdlet 启用 CDR</span><span class="sxs-lookup"><span data-stu-id="057b3-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="057b3-117">您可以通过使用 Windows PowerShell 和**Set-cscdrconfiguration** cmdlet 启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="057b3-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="057b3-118">可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="057b3-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="057b3-119">有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="057b3-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="057b3-120">过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="057b3-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="057b3-121">在单个位置启用 CDR</span><span class="sxs-lookup"><span data-stu-id="057b3-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="057b3-122">若要启用 CDR，请将 EnableCDR 参数设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="057b3-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="057b3-123">在单个位置禁用 CDR</span><span class="sxs-lookup"><span data-stu-id="057b3-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="057b3-p104">若要禁用 CDR，请将 EnableCDR 参数设置为 False ($False)。禁用 CDR 不会卸载监控。而只会暂停 CDR 数据的收集和存储。</span><span class="sxs-lookup"><span data-stu-id="057b3-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="057b3-127">使用单个命令在多个位置启用 CDR</span><span class="sxs-lookup"><span data-stu-id="057b3-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="057b3-128">此命令将为当前在组织中使用的所有 CDR 配置设置启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="057b3-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

<span data-ttu-id="057b3-129">有关详细信息，请参阅[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="057b3-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="057b3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="057b3-130">See also</span></span>

[<span data-ttu-id="057b3-131">规划监控</span><span class="sxs-lookup"><span data-stu-id="057b3-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="057b3-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="057b3-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
