---
title: 迁移呼叫寄存应用程序设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1afd2e53bd29571818b9194fe77d3d350386f1
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="601af-102">迁移呼叫寄存应用程序设置</span><span class="sxs-lookup"><span data-stu-id="601af-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="601af-103">_**主题上次修改时间：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="601af-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="601af-104">将 Lync Server 2010 中的呼叫驻留应用程序迁移到 Lync Server 2013 包括预配 Lync Server 2013 池，其中包含已在 Lync Server 2010 中上载的任何自定义音乐暂停文件，还原服务级别设置和 retargeting所有呼叫公园轨道式到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="601af-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="601af-105">如果已在 Lync Server 2010 池中配置了自定义的 "已保留的音乐" 文件，则需要将这些文件复制到新的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="601af-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="601af-106">此外，建议您将任何呼叫寄存自定义的 "Lync Server 2010" 文件从 Lync Server 备份到另一个目的地，以保留针对呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="601af-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="601af-107">用于呼叫寄存应用程序的自定义的 "保留式音乐" 文件存储在该池的文件存储中。</span><span class="sxs-lookup"><span data-stu-id="601af-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="601af-108">若要将音频文件从 Lync Server 2010 池文件存储复制到 Lync Server 2013 文件存储，请使用带有以下参数的**Xcopy**命令：</span><span class="sxs-lookup"><span data-stu-id="601af-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="601af-109">当所有自定义音频文件已复制到 Lync Server 2013 文件存储时，必须配置 Lync Server 2013 池的 "呼叫驻留" 应用程序设置，并且与 Lync Server 2010 池中关联的呼叫寄存轨道范围必须重新分配给Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="601af-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="601af-110">"呼叫驻留" 应用程序设置包括 "装货超时阈值"、"启用" 或 "禁用暂停的音乐"、最大的呼叫装货尝试和超时请求。</span><span class="sxs-lookup"><span data-stu-id="601af-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="601af-111">你必须使用 Lync Server Management Shell 运行**CsCpsConfiguration** cmdlet 来管理调用寄存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="601af-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="601af-112">无法使用 Lync Server 控制面板管理 "呼叫驻留" 应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="601af-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="601af-113">**重新配置呼叫寄存服务设置**</span><span class="sxs-lookup"><span data-stu-id="601af-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="601af-114">从 Lync Server 2013 前端服务器，打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="601af-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="601af-115">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="601af-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="601af-116">如果您的 Lync Server 2013 调用寄存应用程序设置与旧版 Lync Server 2010 设置相同，则可以跳过运行此步骤。</span><span class="sxs-lookup"><span data-stu-id="601af-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="601af-117">如果对于 Lync Server 2013 和 Lync Server 2010 环境，调用寄存应用程序设置不同，请将以下 cmdlet 用作模板以更新这些更改。</span><span class="sxs-lookup"><span data-stu-id="601af-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="601af-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold"<LS2010 CPS TimeSpan>"-EnableMusicOnHold"<LS2010 CPS value>"-MaxCallPickupAttempts"<LS2010 CPS pickup attempts>"-OnTimeoutURI"<LS2010 CPS timeout URI>"```</span><span class="sxs-lookup"><span data-stu-id="601af-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="601af-119">要将所有呼叫公园轨道范围从 Lync Server 2010 池中重新分配到 Lync Server 2013 池，您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="601af-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="601af-120">**使用 Lync Server 控制面板重新分配所有呼叫寄存的 "轨道" 范围**</span><span class="sxs-lookup"><span data-stu-id="601af-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="601af-121">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="601af-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="601af-122">在左窗格中，选择 "**语音功能**"。</span><span class="sxs-lookup"><span data-stu-id="601af-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="601af-123">选择 "**呼叫驻留**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="601af-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="601af-124">对于分配给 Lync Server 2010 池的每个呼叫寄存轨道范围，请编辑 "**目标服务器的 FQDN** " 设置，然后选择将处理呼叫寄存请求的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="601af-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="601af-125">选择 "**提交**" 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="601af-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="601af-126">**使用 Lync Server 命令行管理程序重新分配所有呼叫寄存的轨道范围**</span><span class="sxs-lookup"><span data-stu-id="601af-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="601af-127">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="601af-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="601af-128">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="601af-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="601af-129">此 cmdlet 列出部署中的所有呼叫寄存轨道范围。</span><span class="sxs-lookup"><span data-stu-id="601af-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="601af-130">必须重新分配将**CallParkServiceId**和**CallParkServerFqdn**参数设置为 Lync Server 2010 池的所有呼叫寄存 "轨道式"。</span><span class="sxs-lookup"><span data-stu-id="601af-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="601af-131">若要将 Lync Server 2010 调用寄存轨道范围重新分配给 Lync Server 2013 池，请在命令行键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="601af-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="601af-132">将所有调用寄存轨道范围重新分配给 Lync Server 2013 池后，将完成呼叫寄存应用程序的迁移过程，并且 Lync Server 2013 池将处理所有未来呼叫驻留请求。</span><span class="sxs-lookup"><span data-stu-id="601af-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

