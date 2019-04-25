---
title: 迁移呼叫寄存应用程序设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 呼叫寄存应用程序包括设置为与保留文件中旧安装已上载的任何自定义保持音乐的业务服务器 2019年池 Skype 迁移，还原的服务级别设置和重定目标所有呼叫寄存轨道到业务服务器 2019年池的 Skype。 如果在池中已配置自定义的保留音乐文件，这些文件需要复制到新 Skype 业务服务器 2019年池。 此外，建议您备份任何呼叫寄存自定义保留音乐文件从至其他目标保留一份任何自定义保留音乐文件已上载的呼叫寄存的单独备份。 呼叫寄存应用程序的自定义的保留音乐文件存储在文件存储的池。 若要从一个池的文件存储的音频文件复制到 Skype 业务服务器 2019年文件存储，请与以下参数使用 Xcopy 命令：
ms.openlocfilehash: 3d9c2904d66ac5d35bdd94631ec23c67288a5c3a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238371"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="023f3-107">迁移呼叫寄存应用程序设置</span><span class="sxs-lookup"><span data-stu-id="023f3-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="023f3-108">呼叫寄存应用程序的迁移包括设置 Skype 业务服务器 2019年池与旧 install，还原的服务级别设置和重新设定所有呼叫寄存轨道已上载的任何自定义保留音乐文件为业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="023f3-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="023f3-109">如果在池中已配置自定义的保留音乐文件，这些文件需要复制到新 Skype 业务服务器 2019年池。</span><span class="sxs-lookup"><span data-stu-id="023f3-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="023f3-110">此外，建议您备份任何呼叫寄存自定义保留音乐文件至其他目标保留一份任何自定义保留音乐文件已上载的呼叫寄存的单独备份。</span><span class="sxs-lookup"><span data-stu-id="023f3-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="023f3-111">呼叫寄存应用程序的自定义的保留音乐文件存储在文件存储的池。</span><span class="sxs-lookup"><span data-stu-id="023f3-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="023f3-112">若要从一个池的文件存储的音频文件复制到 Skype 业务服务器 2019年文件存储，请与以下参数使用**Xcopy**命令：</span><span class="sxs-lookup"><span data-stu-id="023f3-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="023f3-113">当所有自定义音频文件已复制到业务服务器 2019年文件存储的 Skype 时，必须配置池，业务服务器 2019年 Skype 的呼叫寄存应用程序设置和呼叫寄存通道范围与旧池关联的必须重新分配给业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="023f3-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="023f3-114">呼叫寄存应用程序设置包括分拣超时阈值，启用或禁用音乐、 最大呼叫分拣次数和超时请求。</span><span class="sxs-lookup"><span data-stu-id="023f3-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="023f3-115">您必须通过使用 Business Server 命令行管理程序 Skype 运行**Set-cscpsconfiguration** cmdlet 来管理呼叫寄存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="023f3-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="023f3-116">您无法管理用于业务 Server Control Panel Skype 的呼叫寄存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="023f3-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="023f3-117">重新配置呼叫寄存服务设置</span><span class="sxs-lookup"><span data-stu-id="023f3-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="023f3-118">从业务 Server 2019 前端服务器的 Skype，打开业务 Server 命令行管理程序 Skype。</span><span class="sxs-lookup"><span data-stu-id="023f3-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="023f3-119">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="023f3-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="023f3-120">如果您的业务服务器 2019年呼叫寄存应用程序设置的 Skype 到旧设置相同，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="023f3-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="023f3-121">如果呼叫寄存应用程序设置的不同而不同业务服务器 2019年和旧环境 Skype，使用下面的 cmdlet 为模板更新这些更改。</span><span class="sxs-lookup"><span data-stu-id="023f3-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="023f3-122">要重新分配所有呼叫寄存轨道范围从旧池中到业务服务器 2019年池 Skype，可以为业务 Server 命令行管理程序中使用的业务 Server Control Panel Skype 或 Skype。</span><span class="sxs-lookup"><span data-stu-id="023f3-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="023f3-123">重新分配所有呼叫寄存轨道范围 Skype 用于业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="023f3-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="023f3-124">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="023f3-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="023f3-125">在左窗格中，选择**语音功能**。</span><span class="sxs-lookup"><span data-stu-id="023f3-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="023f3-126">选择**呼叫寄存**选项卡。</span><span class="sxs-lookup"><span data-stu-id="023f3-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="023f3-127">对于分配给旧池的每个呼叫寄存通道范围，编辑**目标服务器的 FQDN**设置并选择将处理呼叫寄存请求的业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="023f3-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="023f3-128">选择**提交**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="023f3-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="023f3-129">重新分配所有呼叫寄存轨道范围 Skype 用于业务 Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="023f3-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="023f3-130">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="023f3-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="023f3-131">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="023f3-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="023f3-132">此 cmdlet 列出所有部署中的呼叫寄存通道范围。</span><span class="sxs-lookup"><span data-stu-id="023f3-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="023f3-133">必须重新分配所有呼叫寄存轨道已设置为旧池的**CallParkServiceId**和**CallParkServerFqdn**参数。</span><span class="sxs-lookup"><span data-stu-id="023f3-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="023f3-134">若要重新分配旧的呼叫寄存轨道范围到业务服务器 2019年池，请在命令行中的 Skype 键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="023f3-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="023f3-135">后重新分配到业务服务器 2019年池 Skype 的所有呼叫寄存轨道范围，将完成迁移过程的呼叫寄存应用程序和业务服务器 2019年池 Skype 将用来处理所有将来的呼叫寄存请求。</span><span class="sxs-lookup"><span data-stu-id="023f3-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


