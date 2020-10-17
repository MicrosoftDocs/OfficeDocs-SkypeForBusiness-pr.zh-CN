---
title: Lync Server 2013：将响应组移动到新池
description: Lync Server 2013：将响应组移动到新池。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b696963a28abbcd258f53fae12c3e281efa6ae4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541979"
---
# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="bfc50-103">将响应组移动到 Lync Server 2013 中的新池</span><span class="sxs-lookup"><span data-stu-id="bfc50-103">Moving response groups to a new pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfc50-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bfc50-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bfc50-105">Lync Server 2013 引入了新 cmdlet 支持，以便将响应组从一个池移动到另一个池，即使完全限定的域名 (FQDN) 不同。</span><span class="sxs-lookup"><span data-stu-id="bfc50-105">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="bfc50-106">使用以下过程中的步骤将响应组从一个前端池移动到另一个具有不同 FQDN 的前端池。</span><span class="sxs-lookup"><span data-stu-id="bfc50-106">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bfc50-107">在共存环境中，只能在 Lync Server 2013 前端池之间移动响应组 &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="bfc50-107">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="bfc50-108">将响应组移动到具有不同 FQDN 的池</span><span class="sxs-lookup"><span data-stu-id="bfc50-108">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="bfc50-109">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfc50-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bfc50-110">在源池中导出响应组。</span><span class="sxs-lookup"><span data-stu-id="bfc50-110">Export the response groups in the source pool.</span></span> <span data-ttu-id="bfc50-111">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bfc50-111">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="bfc50-112">例如：</span><span class="sxs-lookup"><span data-stu-id="bfc50-112">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="bfc50-113">若要在导出过程中从源池中删除响应组，请包含– RemoveExportedConfiguration 参数。</span><span class="sxs-lookup"><span data-stu-id="bfc50-113">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="bfc50-114">例如：</span><span class="sxs-lookup"><span data-stu-id="bfc50-114">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="bfc50-115">将响应组导入目标池，并将目标池指定为新的所有者。</span><span class="sxs-lookup"><span data-stu-id="bfc50-115">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="bfc50-116">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bfc50-116">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="bfc50-117">如果还要将响应组应用程序级别的设置从源池复制到目标池，请包含– ReplaceExistingRgsSettings 参数。</span><span class="sxs-lookup"><span data-stu-id="bfc50-117">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="bfc50-118">您只能针对每个池定义一组应用程序级别设置。</span><span class="sxs-lookup"><span data-stu-id="bfc50-118">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="bfc50-119">如果将应用程序级别的设置从源池复制到目标池，源池的设置将替换目标池的设置。</span><span class="sxs-lookup"><span data-stu-id="bfc50-119">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="bfc50-120">如果不从源池中复制应用程序级别的设置，则目标池中的现有设置将应用于导入的响应组。</span><span class="sxs-lookup"><span data-stu-id="bfc50-120">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="bfc50-121">例如：</span><span class="sxs-lookup"><span data-stu-id="bfc50-121">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfc50-122">应用程序级别的设置包括默认的保持音乐配置、默认的保持音乐的音频文件、代理回拨宽限期和呼叫上下文配置。</span><span class="sxs-lookup"><span data-stu-id="bfc50-122">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="bfc50-123">若要查看这些配置设置，请运行 <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfc50-123">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="bfc50-124">有关此 cmdlet 的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">CsRgsConfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="bfc50-124">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="bfc50-125">通过执行以下操作来验证导入是否成功：显示导入的响应组配置：</span><span class="sxs-lookup"><span data-stu-id="bfc50-125">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="bfc50-126">验证导入了所有工作流。</span><span class="sxs-lookup"><span data-stu-id="bfc50-126">Verify that all the workflows were imported.</span></span> <span data-ttu-id="bfc50-127">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bfc50-127">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="bfc50-128">验证是否已导入所有队列。</span><span class="sxs-lookup"><span data-stu-id="bfc50-128">Verify that all the queues were imported.</span></span> <span data-ttu-id="bfc50-129">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bfc50-129">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="bfc50-130">验证是否已导入所有代理组。</span><span class="sxs-lookup"><span data-stu-id="bfc50-130">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="bfc50-131">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bfc50-131">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="bfc50-132">验证是否已导入所有营业时间。</span><span class="sxs-lookup"><span data-stu-id="bfc50-132">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="bfc50-133">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bfc50-133">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="bfc50-134">验证是否已导入所有假日集。</span><span class="sxs-lookup"><span data-stu-id="bfc50-134">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="bfc50-135">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bfc50-135">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="bfc50-136">通过将呼叫放到其中一个响应组并验证是否正确处理了该呼叫，来验证导入是否成功。</span><span class="sxs-lookup"><span data-stu-id="bfc50-136">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="bfc50-137">请求代理是正式代理组的成员，以登录到目标池中的代理组。</span><span class="sxs-lookup"><span data-stu-id="bfc50-137">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="bfc50-138">如果以前未从源池中删除响应组，请从源池中删除响应组。</span><span class="sxs-lookup"><span data-stu-id="bfc50-138">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="bfc50-139">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bfc50-139">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="bfc50-140">例如：</span><span class="sxs-lookup"><span data-stu-id="bfc50-140">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

