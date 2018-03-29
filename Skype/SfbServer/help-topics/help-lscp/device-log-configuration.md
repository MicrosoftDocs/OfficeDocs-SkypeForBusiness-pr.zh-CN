---
title: 设备日志配置
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: 设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为您的组织的数据管理策略的一部分，您可以对日志数据的高速缓存大小、 日志文件大小或的日志文件在被清除之前的保留的时间长度设置阈值。 您可以更改这些设置，根据您的组织的要求。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
ms.openlocfilehash: e5a88c7437b654846fd464133b953465cd5d3e2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="device-log-configuration"></a><span data-ttu-id="65145-107">设备日志配置</span><span class="sxs-lookup"><span data-stu-id="65145-107">Device Log Configuration</span></span>
 
<span data-ttu-id="65145-108">设备更新 Web 服务会自动创建记录设备更新活动的日志文件。</span><span class="sxs-lookup"><span data-stu-id="65145-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="65145-109">作为您的组织的数据管理策略的一部分，您可以对日志数据的高速缓存大小、 日志文件大小或的日志文件在被清除之前的保留的时间长度设置阈值。</span><span class="sxs-lookup"><span data-stu-id="65145-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="65145-110">您可以更改这些设置，根据您的组织的要求。</span><span class="sxs-lookup"><span data-stu-id="65145-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="65145-111">如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。</span><span class="sxs-lookup"><span data-stu-id="65145-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="65145-112">可以在全局范围或针对每个站点更改日志设置。</span><span class="sxs-lookup"><span data-stu-id="65145-112">Log settings can be changed globally or per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="65145-113">您还可以配置某个时间您配置要保留日志文件 （默认情况下，即是 10 天以前的日志文件） 的服务时所需设备更新 Web 服务来自动删除早于天数的日志文件的一天。</span><span class="sxs-lookup"><span data-stu-id="65145-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="65145-114">不能使用 Skype 业务服务器控件面板修改此设置。</span><span class="sxs-lookup"><span data-stu-id="65145-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="65145-115">相反，您必须使用业务服务器管理外壳 Skype。</span><span class="sxs-lookup"><span data-stu-id="65145-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="65145-116">若要指定一天中删除过期的日志文件的时间，请用-LogCleanUpTimeOfDay 参数使用**New CsDeviceUpdateConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65145-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="65145-117">有关详细信息，请参阅[新建 CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="65145-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="65145-p104">清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="65145-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="65145-120">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="65145-120">Tasks you can perform</span></span>

<span data-ttu-id="65145-121">您可以在“**设备日志配置**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="65145-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>
  
- <span data-ttu-id="65145-122">在全局范围或针对特定站点或池添加设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="65145-122">Add a device log configuration globally or for a particular site or pool.</span></span>
    
- <span data-ttu-id="65145-123">修改现有设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="65145-123">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="65145-124">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="65145-124">UI Reference</span></span>

<span data-ttu-id="65145-125">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="65145-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="65145-126">**新**您可以添加新的设备日志配置具有以下作用：</span><span class="sxs-lookup"><span data-stu-id="65145-126">**New** You can add a new device log configuration with the following scope:</span></span>
    
  - <span data-ttu-id="65145-127">全局</span><span class="sxs-lookup"><span data-stu-id="65145-127">Global</span></span>
    
  - <span data-ttu-id="65145-128">站点</span><span class="sxs-lookup"><span data-stu-id="65145-128">Site</span></span>
    
- <span data-ttu-id="65145-129">**编辑**您可以更改设备日志配置列表中的选项。</span><span class="sxs-lookup"><span data-stu-id="65145-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="65145-130">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65145-130">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="65145-131">**显示详细信息**此选项将打开一个对话框，您可以在其中更改设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="65145-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>
    
  - <span data-ttu-id="65145-132">**选择全部**此选项在列表中选择所有设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="65145-132">**Select All** This option selects all device log configuration in the list.</span></span>
    
  - <span data-ttu-id="65145-133">**删除**此选项将删除所有选定的设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="65145-133">**Delete** This option deletes all selected device log configuration.</span></span>
    
- <span data-ttu-id="65145-134">**刷新**您可以刷新设备日志配置列表来验证所有设备日志配置选项的状态。</span><span class="sxs-lookup"><span data-stu-id="65145-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="65145-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65145-135">See also</span></span>

#### 

[<span data-ttu-id="65145-136">修改设备更新活动的日志文件的设置</span><span class="sxs-lookup"><span data-stu-id="65145-136">Modify Settings for Log Files of Device Update Activity</span></span>](http://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)

