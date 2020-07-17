---
title: 迁移呼叫寄存应用程序设置
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 呼叫寄存应用程序的迁移包括预配 Skype for Business Server 2019 池，其中包含已在旧安装中上载的任何自定义音乐 "保留" 文件，并将所有呼叫寄存轨道式还原到 Skype for Business Server 2019 池。 如果已在池中配置了自定义的保持音乐的文件，则需要将这些文件复制到新的 Skype for Business Server 2019 池。 此外，建议您将任何呼叫寄存自定义的即用音乐文件从另一个目标备份到另一个目标，以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。 呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。 若要将音频文件从池文件存储复制到 Skype for Business Server 2019 文件存储，请使用 Xcopy 命令和以下参数：
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752814"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="ff57e-107">迁移呼叫寄存应用程序设置</span><span class="sxs-lookup"><span data-stu-id="ff57e-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="ff57e-108">呼叫寄存应用程序的迁移包括预配 Skype for Business Server 2019 池，其中包含已在旧安装中上载的任何自定义的音乐文件，还原服务级别设置并将所有呼叫寄存轨道式重新定向到 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="ff57e-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ff57e-109">如果已在池中配置了自定义的保持音乐的文件，则需要将这些文件复制到新的 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="ff57e-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ff57e-110">此外，建议您将任何呼叫寄存自定义的即用音乐文件备份到另一个目标，以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="ff57e-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="ff57e-111">呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。</span><span class="sxs-lookup"><span data-stu-id="ff57e-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="ff57e-112">若要将音频文件从池文件存储复制到 Skype for Business Server 2019 文件存储，请使用**Xcopy**命令和以下参数：</span><span class="sxs-lookup"><span data-stu-id="ff57e-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="ff57e-113">将所有自定义音频文件复制到 Skype for business Server 2019 文件存储后，必须配置 Skype for business Server 2019 池的呼叫寄存应用程序设置，并且与旧版池关联的呼叫寄存通道范围必须重新分配给 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="ff57e-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="ff57e-114">呼叫寄存应用程序设置包括装货超时阈值、启用或禁用保留的音乐、最大呼叫尝试次数和超时请求。</span><span class="sxs-lookup"><span data-stu-id="ff57e-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="ff57e-115">您必须通过使用 Skype for Business Server 命令行管理程序运行**CsCpsConfiguration** cmdlet 来管理呼叫寄存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="ff57e-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="ff57e-116">您无法使用 Skype for Business Server 控制面板管理呼叫寄存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="ff57e-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="ff57e-117">重新配置呼叫寄存服务设置</span><span class="sxs-lookup"><span data-stu-id="ff57e-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="ff57e-118">在 Skype for Business Server 2019 前端服务器中，打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="ff57e-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="ff57e-119">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ff57e-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff57e-120">如果 Skype for Business Server 2019 呼叫寄存应用程序设置与旧设置相同，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="ff57e-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="ff57e-121">如果 Skype for business Server 2019 和旧版环境的呼叫寄存应用程序设置不同，请将下面的 cmdlet 用作模板以更新这些更改。</span><span class="sxs-lookup"><span data-stu-id="ff57e-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="ff57e-122">若要将所有呼叫寄存通道范围从旧版池重新分配到 Skype for Business Server 2019 池，可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="ff57e-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ff57e-123">使用 Skype for Business Server 控制面板重新分配所有呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="ff57e-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ff57e-124">打开 "Skype for Business Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ff57e-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ff57e-125">在左窗格中，选择“语音功能”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ff57e-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="ff57e-126">选择“呼叫寄存”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ff57e-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="ff57e-127">对于分配给旧版池的每个呼叫寄存通道范围，请编辑 "**目标服务器的 FQDN** " 设置，然后选择将处理呼叫寄存请求的 Skype For business server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="ff57e-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="ff57e-128">单击“提交”\*\*\*\* 保存所做更改。</span><span class="sxs-lookup"><span data-stu-id="ff57e-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ff57e-129">使用 Skype for Business Server 命令行管理程序重新分配所有呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="ff57e-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ff57e-130">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="ff57e-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="ff57e-131">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ff57e-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="ff57e-132">此 cmdlet 列出了部署中的所有呼叫寄存轨道范围。</span><span class="sxs-lookup"><span data-stu-id="ff57e-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="ff57e-133">将**CallParkServiceId**和**CallParkServerFqdn**参数设置为旧版池的所有呼叫寄存轨道都必须重新分配。</span><span class="sxs-lookup"><span data-stu-id="ff57e-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="ff57e-134">若要将旧式呼叫寄存通道范围重新分配给 Skype for Business Server 2019 池，请在命令行中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ff57e-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="ff57e-135">将所有呼叫寄存通道区域重新分配给 Skype for Business Server 2019 池后，呼叫寄存应用程序的迁移过程将完成，Skype for Business Server 2019 池将处理所有将来的呼叫寄存请求。</span><span class="sxs-lookup"><span data-stu-id="ff57e-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


