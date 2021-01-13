---
title: 设备日志配置编辑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: 你可以将设备日志配置添加到"编辑日志设置"页，该页确定在清除之前保留的最大日志缓存大小、最大 日志文件 大小或日志文件保留的时间长度。 您可以根据组织的要求更改这些设置。
ms.openlocfilehash: ac6c341460d0e196548a86620d89f67bc51d7b4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830292"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="d078d-104">设备日志配置：编辑</span><span class="sxs-lookup"><span data-stu-id="d078d-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="d078d-105">可以将设备日志配置添加到"编辑日志设置"页，该页确定在清除 日志文件 之前保留的最大日志缓存大小、最大 日志文件 大小或保留时间长度。</span><span class="sxs-lookup"><span data-stu-id="d078d-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="d078d-106">您可以根据组织的要求更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="d078d-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d078d-p103">清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="d078d-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="d078d-109">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="d078d-109">Tasks you can perform</span></span>

<span data-ttu-id="d078d-110">您可以在"编辑日志设置"页上 **执行以下** 任务：</span><span class="sxs-lookup"><span data-stu-id="d078d-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="d078d-111">全局或特定站点添加设备日志配置。</span><span class="sxs-lookup"><span data-stu-id="d078d-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="d078d-112">修改现有设备日志配置的选项。</span><span class="sxs-lookup"><span data-stu-id="d078d-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="d078d-113">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="d078d-113">UI Reference</span></span>

<span data-ttu-id="d078d-114">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="d078d-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="d078d-115">**范围** 标识设备 (全局) 站点范围。</span><span class="sxs-lookup"><span data-stu-id="d078d-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="d078d-116">**名称** 可以添加或修改设备日志配置的名称。</span><span class="sxs-lookup"><span data-stu-id="d078d-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="d078d-117">**最大文件大小 (字节数)** 可以指定在清除日志文件大小。</span><span class="sxs-lookup"><span data-stu-id="d078d-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="d078d-118">默认值为 1，024，000 字节 (1 MB) 。</span><span class="sxs-lookup"><span data-stu-id="d078d-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="d078d-119">**最大缓存大小 (字节数)** 可以指定在必须清除缓存 (数据写入缓存之前) 在 日志文件 缓存中保留的最大信息量（以字节日志文件）。</span><span class="sxs-lookup"><span data-stu-id="d078d-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="d078d-120">默认值为 512，000 字节 (0.5 MB) 。</span><span class="sxs-lookup"><span data-stu-id="d078d-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="d078d-121">**刷新缓存的分钟数 (1-60)** 可以指定将存储在缓存中的日志文件写入实际缓存日志文件。</span><span class="sxs-lookup"><span data-stu-id="d078d-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="d078d-122">记录数据后，将清除缓存。</span><span class="sxs-lookup"><span data-stu-id="d078d-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="d078d-123">默认值为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="d078d-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="d078d-124">**日志文件保留天数 (1-365)** 可以指定日志文件在清除之前保留的天数。</span><span class="sxs-lookup"><span data-stu-id="d078d-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="d078d-125">默认值为 10 天。</span><span class="sxs-lookup"><span data-stu-id="d078d-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d078d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d078d-126">See also</span></span>

[<span data-ttu-id="d078d-127">设备日志配置</span><span class="sxs-lookup"><span data-stu-id="d078d-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
