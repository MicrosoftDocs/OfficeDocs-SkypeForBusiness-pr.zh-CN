---
title: 迁移呼叫寄存应用程序设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '此呼叫驻留应用程序的迁移包括预配 Skype for Business Server 2019 池, 其中包含已在旧安装中上载的任何自定义音乐 "暂停" 文件, 还原服务级别设置和 retargeting 所有呼叫公园轨道式Skype for Business Server 2019 池。 如果已在池中配置了自定义的 "已保留的音乐" 文件, 则需要将这些文件复制到新的 Skype for Business Server 2019 池。 此外, 建议将任何呼叫寄存自定义的 "外出时" 文件从另一个目的地备份到另一个目的地, 以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。 用于呼叫寄存应用程序的自定义的 "保留式音乐" 文件存储在该池的文件存储中。 若要将音频文件从池文件存储复制到 Skype for business Server 2019 文件存储, 请使用 Xcopy 命令和以下参数:'
ms.openlocfilehash: efb2bfbf8ac62ad05e2ee560c2aca4fb7b496006
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238030"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="6678e-107">迁移呼叫寄存应用程序设置</span><span class="sxs-lookup"><span data-stu-id="6678e-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="6678e-108">呼叫驻留应用程序的迁移包括预配 Skype for Business Server 2019 池, 其中包含已在旧安装中上载的任何自定义的音乐暂停文件, 还原服务级别设置并重新定向所有呼叫寄存的轨道式Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="6678e-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6678e-109">如果已在池中配置了自定义的 "已保留的音乐" 文件, 则需要将这些文件复制到新的 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="6678e-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6678e-110">此外, 建议您将任何呼叫寄存自定义的 "已保留的音乐" 文件备份到另一个目的地, 以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="6678e-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="6678e-111">用于呼叫寄存应用程序的自定义的 "保留式音乐" 文件存储在该池的文件存储中。</span><span class="sxs-lookup"><span data-stu-id="6678e-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="6678e-112">若要将音频文件从池文件存储复制到 Skype for business Server 2019 文件存储, 请使用**Xcopy**命令和以下参数:</span><span class="sxs-lookup"><span data-stu-id="6678e-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="6678e-113">将所有自定义音频文件复制到 Skype for business Server 2019 文件存储时, 必须配置 Skype for business Server 2019 池的 "呼叫驻留" 应用程序设置, 以及与旧版池相关联的 "呼叫驻留" 轨道范围必须重新分配给 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="6678e-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="6678e-114">"呼叫驻留" 应用程序设置包括 "装货超时阈值"、启用或禁用 "暂停的音乐"、"呼叫最多尝试次数" 和 "超时请求"。</span><span class="sxs-lookup"><span data-stu-id="6678e-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="6678e-115">你必须通过使用 Skype for Business Server Management Shell 运行**CsCpsConfiguration** cmdlet 来管理 "呼叫驻留" 应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="6678e-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="6678e-116">无法使用 Skype for Business Server 控制面板管理呼叫寄存应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="6678e-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="6678e-117">重新配置呼叫寄存服务设置</span><span class="sxs-lookup"><span data-stu-id="6678e-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="6678e-118">从 Skype for business 服务器2019前端服务器, 打开 Skype for business 服务器命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="6678e-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="6678e-119">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="6678e-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="6678e-120">如果您的 Skype for Business Server 2019 调用寄存应用程序设置与旧设置相同, 则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="6678e-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="6678e-121">如果 Skype for business Server 2019 和旧版环境中的 "调用寄存" 应用程序设置不同, 请将以下 cmdlet 用作模板以更新这些更改。</span><span class="sxs-lookup"><span data-stu-id="6678e-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="6678e-122">若要将所有呼叫公园轨道范围从旧版池重新分配到 Skype for business Server 2019 池, 可以使用 Skype for Business 服务器控制面板或 Skype for business 服务器命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="6678e-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6678e-123">使用 Skype for Business Server 控制面板重新分配所有呼叫寄存的 "轨道范围"</span><span class="sxs-lookup"><span data-stu-id="6678e-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6678e-124">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="6678e-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6678e-125">在左窗格中, 选择 "**语音功能**"。</span><span class="sxs-lookup"><span data-stu-id="6678e-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="6678e-126">选择 "**呼叫驻留**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6678e-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="6678e-127">对于分配给旧版池的每个呼叫寄存轨道范围, 请编辑 "**目标服务器的 FQDN** " 设置, 然后选择将处理呼叫寄存请求的 Skype For business server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="6678e-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="6678e-128">选择 "**提交**" 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="6678e-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6678e-129">使用 Skype for Business Server 命令行管理程序重新分配所有呼叫寄存的轨道范围</span><span class="sxs-lookup"><span data-stu-id="6678e-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6678e-130">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="6678e-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="6678e-131">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="6678e-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="6678e-132">此 cmdlet 列出部署中的所有呼叫寄存轨道范围。</span><span class="sxs-lookup"><span data-stu-id="6678e-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="6678e-133">所有设置为旧版池的 CallParkServiceId 和**CallParkServerFqdn**参数的所有调用寄存的\*\*\*\* 都必须重新分配。</span><span class="sxs-lookup"><span data-stu-id="6678e-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="6678e-134">若要将旧式呼叫公园轨道范围重新分配给 Skype for business Server 2019 池, 请在命令行键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="6678e-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="6678e-135">将所有呼叫公园轨道范围重新分配给 Skype for business Server 2019 池后, 将完成呼叫寄存应用程序的迁移过程, 并且 Skype for Business Server 2019 池将处理所有未来呼叫寄存请求。</span><span class="sxs-lookup"><span data-stu-id="6678e-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


