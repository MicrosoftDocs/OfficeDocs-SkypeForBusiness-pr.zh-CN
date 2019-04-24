---
title: 设备日志配置
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: 设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为您的组织数据管理策略的一部分，您可能想要设置阈值日志数据缓存大小、 日志文件大小或的日志文件在被清除之前保留的时间长度。 您可以更改这些设置根据贵组织的要求。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
ms.openlocfilehash: 68e5e7d569f3a0436f80bb081b0785e5278bcb0d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216009"
---
# <a name="device-log-configuration"></a><span data-ttu-id="9bcd9-107">设备日志配置</span><span class="sxs-lookup"><span data-stu-id="9bcd9-107">Device Log Configuration</span></span>

<span data-ttu-id="9bcd9-108">设备更新 Web 服务会自动创建记录设备更新活动的日志文件。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="9bcd9-109">作为您的组织数据管理策略的一部分，您可能想要设置阈值日志数据缓存大小、 日志文件大小或的日志文件在被清除之前保留的时间长度。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="9bcd9-110">您可以更改这些设置根据贵组织的要求。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="9bcd9-111">如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="9bcd9-112">可以在全局范围或针对每个站点更改日志设置。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="9bcd9-113">您还可以配置一次您希望自动删除早于天数的日志文件的设备更新 Web 服务的一天中的配置要保留日志文件 （默认情况下，即超过 10 天的日志文件） 的服务。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="9bcd9-114">不能用于业务 Server Control Panel Skype 修改此设置。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9bcd9-115">相反，您必须为业务 Server 命令行管理程序中使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9bcd9-116">若要指定一天中删除过期的日志文件的时间，请使用-LogCleanUpTimeOfDay 参数**New-csdeviceupdateconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="9bcd9-117">有关详细信息，请参阅[New-csdeviceupdateconfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="9bcd9-p104">清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9bcd9-120">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="9bcd9-120">Tasks you can perform</span></span>

<span data-ttu-id="9bcd9-121">您可以在“**设备日志配置**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="9bcd9-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="9bcd9-122">在全局范围或针对特定站点或池添加设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="9bcd9-123">修改现有设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9bcd9-124">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="9bcd9-124">UI Reference</span></span>

<span data-ttu-id="9bcd9-125">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="9bcd9-126">**新**您可以添加新的设备日志配置具有以下作用域：</span><span class="sxs-lookup"><span data-stu-id="9bcd9-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="9bcd9-127">全局</span><span class="sxs-lookup"><span data-stu-id="9bcd9-127">Global</span></span>

  - <span data-ttu-id="9bcd9-128">站点</span><span class="sxs-lookup"><span data-stu-id="9bcd9-128">Site</span></span>

- <span data-ttu-id="9bcd9-129">**编辑**您可以更改设备日志配置列表中的选项。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="9bcd9-130">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9bcd9-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="9bcd9-131">**显示详细信息**此选项可打开一个对话框，您可以在其中更改设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="9bcd9-132">**选择全部**此选项可选择列表中所有设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="9bcd9-133">**删除**此选项可删除所有选定的设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="9bcd9-134">**刷新**您可以刷新设备日志配置列表以验证所有设备日志配置的选项状态。</span><span class="sxs-lookup"><span data-stu-id="9bcd9-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bcd9-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bcd9-135">See also</span></span>

[<span data-ttu-id="9bcd9-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="9bcd9-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
