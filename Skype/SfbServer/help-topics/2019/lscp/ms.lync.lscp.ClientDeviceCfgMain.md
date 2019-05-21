---
title: 设备日志配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: 设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为组织的数据管理策略的一部分, 你可能想要在日志文件的数据缓存大小、日志文件大小或清除日志文件前的时间段内设置阈值。 您可以根据组织的要求更改这些设置。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
ms.openlocfilehash: 7c4f532af6e74f8ef13b3b2de17017b66afc0b59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300470"
---
# <a name="device-log-configuration"></a><span data-ttu-id="81ea3-107">设备日志配置</span><span class="sxs-lookup"><span data-stu-id="81ea3-107">Device Log Configuration</span></span>

<span data-ttu-id="81ea3-108">设备更新 Web 服务会自动创建记录设备更新活动的日志文件。</span><span class="sxs-lookup"><span data-stu-id="81ea3-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="81ea3-109">作为组织的数据管理策略的一部分, 你可能想要在日志文件的数据缓存大小、日志文件大小或清除日志文件前的时间段内设置阈值。</span><span class="sxs-lookup"><span data-stu-id="81ea3-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="81ea3-110">您可以根据组织的要求更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="81ea3-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="81ea3-111">如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。</span><span class="sxs-lookup"><span data-stu-id="81ea3-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="81ea3-112">可以在全局范围或针对每个站点更改日志设置。</span><span class="sxs-lookup"><span data-stu-id="81ea3-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="81ea3-113">你还可以配置你希望设备更新 Web 服务自动删除早于你配置了服务以保留日志文件的天数 (默认情况下是超过10天的日志文件) 的日志文件的时间。</span><span class="sxs-lookup"><span data-stu-id="81ea3-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="81ea3-114">无法使用 Skype for Business Server 控制面板修改此设置。</span><span class="sxs-lookup"><span data-stu-id="81ea3-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="81ea3-115">而必须使用 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="81ea3-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="81ea3-116">若要指定每天删除已过期日志文件的时间, 请将**CsDeviceUpdateConfiguration** cmdlet 与-LogCleanUpTimeOfDay 参数配合使用。</span><span class="sxs-lookup"><span data-stu-id="81ea3-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="81ea3-117">有关详细信息, 请参阅[CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="81ea3-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="81ea3-p104">清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="81ea3-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="81ea3-120">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="81ea3-120">Tasks you can perform</span></span>

<span data-ttu-id="81ea3-121">您可以在“**设备日志配置**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="81ea3-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="81ea3-122">在全局范围或针对特定站点或池添加设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="81ea3-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="81ea3-123">修改现有设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="81ea3-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="81ea3-124">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="81ea3-124">UI Reference</span></span>

<span data-ttu-id="81ea3-125">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="81ea3-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="81ea3-126">**新**你可以添加具有以下范围的新设备日志配置:</span><span class="sxs-lookup"><span data-stu-id="81ea3-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="81ea3-127">全局</span><span class="sxs-lookup"><span data-stu-id="81ea3-127">Global</span></span>

  - <span data-ttu-id="81ea3-128">站点</span><span class="sxs-lookup"><span data-stu-id="81ea3-128">Site</span></span>

- <span data-ttu-id="81ea3-129">**编辑**可以在列表中更改设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="81ea3-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="81ea3-130">使用此选项, 您可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="81ea3-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="81ea3-131">**显示详细信息**此选项将打开一个对话框, 您可以在其中更改设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="81ea3-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="81ea3-132">**全选**此选项选择列表中的所有设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="81ea3-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="81ea3-133">**Delete**此选项将删除所有选定的设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="81ea3-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="81ea3-134">**刷新**你可以刷新设备日志配置列表, 以验证所有设备日志配置的选项状态。</span><span class="sxs-lookup"><span data-stu-id="81ea3-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="81ea3-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81ea3-135">See also</span></span>

[<span data-ttu-id="81ea3-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="81ea3-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
