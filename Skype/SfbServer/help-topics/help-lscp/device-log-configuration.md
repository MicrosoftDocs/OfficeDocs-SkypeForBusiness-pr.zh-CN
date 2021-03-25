---
title: 设备日志配置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: 设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为组织的数据管理策略的一部分，您可能需要设置日志数据缓存大小、日志文件 大小或 日志文件 在清除之前保留的时间长度的阈值。 您可以根据组织的要求更改这些设置。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
ms.openlocfilehash: b20c7bb088f46491c99ada7c815b8c11d4bfe456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115280"
---
# <a name="device-log-configuration"></a><span data-ttu-id="52c31-107">设备日志配置</span><span class="sxs-lookup"><span data-stu-id="52c31-107">Device Log Configuration</span></span>

<span data-ttu-id="52c31-108">设备更新 Web 服务会自动创建记录设备更新活动的日志文件。</span><span class="sxs-lookup"><span data-stu-id="52c31-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="52c31-109">作为组织的数据管理策略的一部分，您可能需要设置日志数据缓存大小、日志文件 大小或 日志文件 在清除之前保留的时间长度的阈值。</span><span class="sxs-lookup"><span data-stu-id="52c31-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="52c31-110">您可以根据组织的要求更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="52c31-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="52c31-111">如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。</span><span class="sxs-lookup"><span data-stu-id="52c31-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="52c31-112">可以在全局范围或针对每个站点更改日志设置。</span><span class="sxs-lookup"><span data-stu-id="52c31-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="52c31-113">您还可以配置一天中您希望设备更新 Web 服务自动删除超过您配置该服务保留日志文件 (的天数的日志文件（即超过 10 天的日志文件）的时间) 。</span><span class="sxs-lookup"><span data-stu-id="52c31-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="52c31-114">无法使用 Skype for Business Server 控制面板修改此设置。</span><span class="sxs-lookup"><span data-stu-id="52c31-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="52c31-115">相反，必须使用 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="52c31-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="52c31-116">若要指定删除过期日志文件的时间，请使用 **New-CsDeviceUpdateConfiguration** cmdlet 和 -LogCleanUpTimeOfDay 参数。</span><span class="sxs-lookup"><span data-stu-id="52c31-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="52c31-117">有关详细信息，请参阅 [New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="52c31-117">For details, see [New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="52c31-p104">清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="52c31-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="52c31-120">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="52c31-120">Tasks you can perform</span></span>

<span data-ttu-id="52c31-121">您可以在“设备日志配置”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="52c31-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="52c31-122">在全局范围或针对特定站点或池添加设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="52c31-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="52c31-123">修改现有设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="52c31-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="52c31-124">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="52c31-124">UI Reference</span></span>

<span data-ttu-id="52c31-125">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="52c31-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="52c31-126">**新建** 你可以添加具有以下作用域的新设备日志配置：</span><span class="sxs-lookup"><span data-stu-id="52c31-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="52c31-127">全局</span><span class="sxs-lookup"><span data-stu-id="52c31-127">Global</span></span>

  - <span data-ttu-id="52c31-128">Site</span><span class="sxs-lookup"><span data-stu-id="52c31-128">Site</span></span>

- <span data-ttu-id="52c31-129">**编辑** 你可以更改列表中的设备日志配置选项。</span><span class="sxs-lookup"><span data-stu-id="52c31-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="52c31-130">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="52c31-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="52c31-131">**显示详细信息** 此选项将打开一个对话框，可在其中更改设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="52c31-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="52c31-132">**全选** 此选项选择列表中的所有设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="52c31-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="52c31-133">**删除** 此选项将删除所有选定的设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="52c31-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="52c31-134">**刷新** 你可以刷新设备日志配置列表以验证所有设备日志配置的选项状态。</span><span class="sxs-lookup"><span data-stu-id="52c31-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="52c31-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52c31-135">See also</span></span>

[<span data-ttu-id="52c31-136">修改设备更新活动的日志文件的设置</span><span class="sxs-lookup"><span data-stu-id="52c31-136">Modify Settings for Log Files of Device Update Activity</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)