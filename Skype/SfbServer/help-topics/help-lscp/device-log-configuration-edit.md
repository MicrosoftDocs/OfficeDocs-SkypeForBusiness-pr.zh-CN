---
title: 设备日志配置编辑
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 您可以向编辑日志设置页上，确定最大日志缓存大小、 最大日志文件大小或在被清除之前保留日志文件的时间长度添加设备日志配置。 您可以更改这些设置根据贵组织的要求。
ms.openlocfilehash: fac6dd8aae7c1081c268d35ea0336b41eb7c6f55
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969992"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="394fe-104">设备日志配置： 编辑</span><span class="sxs-lookup"><span data-stu-id="394fe-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="394fe-105">您可以向**编辑日志设置**页上，确定最大日志缓存大小、 最大日志文件大小或在被清除之前保留日志文件的时间长度添加设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="394fe-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="394fe-106">您可以更改这些设置根据贵组织的要求。</span><span class="sxs-lookup"><span data-stu-id="394fe-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="394fe-p103">清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="394fe-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="394fe-109">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="394fe-109">Tasks you can perform</span></span>

<span data-ttu-id="394fe-110">在**编辑日志设置**页上，可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="394fe-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="394fe-111">在全局范围或针对特定站点添加设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="394fe-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="394fe-112">修改现有设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="394fe-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="394fe-113">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="394fe-113">UI Reference</span></span>

<span data-ttu-id="394fe-114">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="394fe-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="394fe-115">**范围**标识设备日志配置的范围 （全局或站点）。</span><span class="sxs-lookup"><span data-stu-id="394fe-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="394fe-116">**名称**您可以添加或修改设备日志配置的名称。</span><span class="sxs-lookup"><span data-stu-id="394fe-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="394fe-117">**最大文件大小 （字节）** 您可以指定日志文件在被清除之前可以成为的最大大小。</span><span class="sxs-lookup"><span data-stu-id="394fe-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="394fe-118">默认值为 1,024,000 字节 (1 MB)。</span><span class="sxs-lookup"><span data-stu-id="394fe-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="394fe-119">**最大缓存大小 （字节）** 您可以指定的最大量 （以字节为单位） 必须清除缓存和数据写入到日志文件可以之前日志文件缓存中保留的信息。</span><span class="sxs-lookup"><span data-stu-id="394fe-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="394fe-120">默认值为 512,000 字节 (0.5 MB)。</span><span class="sxs-lookup"><span data-stu-id="394fe-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="394fe-121">**分钟时间来刷新缓存 (1-60)** 您可以指定频率存储在日志文件缓存的信息写入实际的日志文件。</span><span class="sxs-lookup"><span data-stu-id="394fe-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="394fe-122">数据记录后，将清除缓存。</span><span class="sxs-lookup"><span data-stu-id="394fe-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="394fe-123">默认值为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="394fe-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="394fe-124">**天数保留日志文件 (1-365)** 您可以指定清除之前保留的日志文件的天数。</span><span class="sxs-lookup"><span data-stu-id="394fe-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="394fe-125">默认值为 10 天。</span><span class="sxs-lookup"><span data-stu-id="394fe-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="394fe-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="394fe-126">See also</span></span>

[<span data-ttu-id="394fe-127">设备日志配置</span><span class="sxs-lookup"><span data-stu-id="394fe-127">Device Log Configuration</span></span>](device-log-configuration.md)