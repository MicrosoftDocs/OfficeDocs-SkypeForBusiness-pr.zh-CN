---
title: 设备日志配置编辑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: 你可以将设备日志配置添加到 "编辑日志" 设置页面, 该页面确定日志文件的最大日志大小、最大日志文件大小或在清除之前保留日志文件的时间长度。 您可以根据组织的要求更改这些设置。
ms.openlocfilehash: 22eb2c37bb0403cf9abf94da8f2e1460d3757b44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300440"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="77529-104">设备日志配置：编辑</span><span class="sxs-lookup"><span data-stu-id="77529-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="77529-105">你可以将设备日志配置添加到 "**编辑日志" 设置**页面, 该页面确定日志文件的最大日志大小、最大日志文件大小或在清除之前保留日志文件的时间长度。</span><span class="sxs-lookup"><span data-stu-id="77529-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="77529-106">您可以根据组织的要求更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="77529-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="77529-p103">清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="77529-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="77529-109">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="77529-109">Tasks you can perform</span></span>

<span data-ttu-id="77529-110">可以在 "**编辑日志设置**" 页面上执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="77529-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="77529-111">全局或特定网站添加设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="77529-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="77529-112">修改现有设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="77529-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="77529-113">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="77529-113">UI Reference</span></span>

<span data-ttu-id="77529-114">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="77529-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="77529-115">**范围**标识设备日志配置的作用域 (全局或网站)。</span><span class="sxs-lookup"><span data-stu-id="77529-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="77529-116">**名称**你可以添加或修改设备日志配置的名称。</span><span class="sxs-lookup"><span data-stu-id="77529-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="77529-117">**最大文件大小 (字节)** 你可以指定日志文件在清除之前可以达到的最大大小。</span><span class="sxs-lookup"><span data-stu-id="77529-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="77529-118">默认值为1024000字节 (1 MB)。</span><span class="sxs-lookup"><span data-stu-id="77529-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="77529-119">**最大缓存大小 (字节)** 你可以指定必须在日志文件缓存中保留的最大信息量 (以字节为单位), 然后才能在该缓存中清除, 并将数据写入日志文件。</span><span class="sxs-lookup"><span data-stu-id="77529-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="77529-120">默认值为512000字节 (0.5 MB)。</span><span class="sxs-lookup"><span data-stu-id="77529-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="77529-121">**刷新缓存的分钟数 (1-60)** 你可以指定日志文件缓存中存储的信息写入实际日志文件的频率。</span><span class="sxs-lookup"><span data-stu-id="77529-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="77529-122">记录数据后, 将清除缓存。</span><span class="sxs-lookup"><span data-stu-id="77529-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="77529-123">默认值为5分钟。</span><span class="sxs-lookup"><span data-stu-id="77529-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="77529-124">**保留日志文件的天数 (1-365)** 你可以指定在清除日志文件之前保留日志文件的天数。</span><span class="sxs-lookup"><span data-stu-id="77529-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="77529-125">默认值为10天。</span><span class="sxs-lookup"><span data-stu-id="77529-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="77529-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77529-126">See also</span></span>

[<span data-ttu-id="77529-127">设备日志配置</span><span class="sxs-lookup"><span data-stu-id="77529-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
