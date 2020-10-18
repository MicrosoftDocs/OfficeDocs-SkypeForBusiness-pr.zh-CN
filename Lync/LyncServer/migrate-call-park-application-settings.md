---
title: 迁移呼叫寄存应用程序设置
description: 迁移呼叫寄存应用程序设置。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da90ca4ee4dd53451c29b8c39861dc76a17ca3c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579408"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="cffb3-103">迁移呼叫寄存应用程序设置</span><span class="sxs-lookup"><span data-stu-id="cffb3-103">Migrate Call Park application settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cffb3-104">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="cffb3-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="cffb3-105">从 Lync Server 2010 到 Lync Server 2013 的呼叫寄存应用程序的迁移包括：预配 Lync Server 2013 池，其中包含已在 Lync Server 2010 中上载的任何自定义音乐 "保留" 文件，同时将服务级别设置和 retargeting 所有呼叫寄存轨道式还原到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="cffb3-105">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="cffb3-106">如果已在 Lync Server 2010 池中配置了自定义的保持音乐的文件，则需要将这些文件复制到新的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="cffb3-106">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="cffb3-107">此外，建议您将任何呼叫寄存自定义的音乐保留文件从 Lync Server 2010 备份到另一个目标，以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="cffb3-107">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="cffb3-108">呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。</span><span class="sxs-lookup"><span data-stu-id="cffb3-108">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="cffb3-109">若要将音频文件从 Lync Server 2010 池文件存储复制到 Lync Server 2013 文件存储，请使用 **Xcopy** 命令和以下参数：</span><span class="sxs-lookup"><span data-stu-id="cffb3-109">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="cffb3-110">将所有自定义音频文件复制到 Lync Server 2013 文件存储后，必须配置 Lync Server 2013 池的呼叫寄存应用程序设置，并且与 Lync Server 2010 池关联的呼叫寄存通道范围必须重新分配给 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="cffb3-110">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="cffb3-111">呼叫寄存应用程序设置包括应答超时阈值，启用或禁用保持音乐，最大呼叫应答尝试次数和超时请求。</span><span class="sxs-lookup"><span data-stu-id="cffb3-111">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="cffb3-112">您必须使用 Lync Server 命令行管理程序运行 **CsCpsConfiguration** cmdlet 来管理呼叫寄存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="cffb3-112">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="cffb3-113">您无法使用 Lync Server 控制面板管理呼叫寄存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="cffb3-113">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="cffb3-114">**重新配置呼叫寄存服务设置**</span><span class="sxs-lookup"><span data-stu-id="cffb3-114">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="cffb3-115">在 Lync Server 2013 前端服务器中，打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="cffb3-115">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="cffb3-116">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="cffb3-116">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cffb3-117">如果你的 Lync Server 2013 呼叫寄存应用程序设置与旧版 Lync Server 2010 设置相同，则可以跳过运行此步骤。</span><span class="sxs-lookup"><span data-stu-id="cffb3-117">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="cffb3-118">如果 Lync Server 2013 和 Lync Server 2010 环境的呼叫寄存应用程序设置不同，请将下面的 cmdlet 用作模板以更新这些更改。</span><span class="sxs-lookup"><span data-stu-id="cffb3-118">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="cffb3-119"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-MaxCallPickupAttempts" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> " ```</span><span class="sxs-lookup"><span data-stu-id="cffb3-119"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="cffb3-120">若要将所有呼叫寄存通道范围从 Lync Server 2010 池重新分配到 Lync Server 2013 池，您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="cffb3-120">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="cffb3-121">**使用 Lync Server 控制面板重新分配所有呼叫寄存轨道范围**</span><span class="sxs-lookup"><span data-stu-id="cffb3-121">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="cffb3-122">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="cffb3-122">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="cffb3-123">在左窗格中，选择“语音功能”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cffb3-123">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="cffb3-124">选择“呼叫寄存”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cffb3-124">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="cffb3-125">对于分配给 Lync Server 2010 池的每个呼叫寄存通道范围，请编辑 " **目标服务器的 FQDN** " 设置，然后选择将处理呼叫寄存请求的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="cffb3-125">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="cffb3-126">单击“提交”\*\*\*\* 保存所做更改。</span><span class="sxs-lookup"><span data-stu-id="cffb3-126">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="cffb3-127">**使用 Lync Server 命令行管理程序重新分配所有呼叫寄存轨道范围**</span><span class="sxs-lookup"><span data-stu-id="cffb3-127">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="cffb3-128">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="cffb3-128">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="cffb3-129">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="cffb3-129">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="cffb3-130">此 cmdlet 列出了部署中的所有呼叫寄存轨道范围。</span><span class="sxs-lookup"><span data-stu-id="cffb3-130">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="cffb3-131">必须重新分配将 **CallParkServiceId** 和 **CallParkServerFqdn** 参数设置为 Lync Server 2010 池的所有呼叫寄存轨道。</span><span class="sxs-lookup"><span data-stu-id="cffb3-131">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="cffb3-132">若要将 Lync Server 2010 呼叫寄存通道区域重新分配给 Lync Server 2013 池，请在命令行中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="cffb3-132">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="cffb3-133">将所有呼叫寄存通道区域重新分配给 Lync Server 2013 池之后，呼叫寄存应用程序的迁移过程将完成，Lync Server 2013 池将处理所有未来呼叫寄存请求。</span><span class="sxs-lookup"><span data-stu-id="cffb3-133">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

