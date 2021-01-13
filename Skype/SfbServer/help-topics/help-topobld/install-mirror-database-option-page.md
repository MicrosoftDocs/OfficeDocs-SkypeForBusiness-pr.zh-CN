---
title: 安装镜像数据库选项页
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 通过以下定义配置“镜像数据库设置”：
ms.openlocfilehash: 63e3795cc52b9b8e3601b2260df253fdcd2d9c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806892"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="dda3e-103">安装镜像数据库选项页</span><span class="sxs-lookup"><span data-stu-id="dda3e-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="dda3e-104">通过以下定义配置“镜像数据库设置”：</span><span class="sxs-lookup"><span data-stu-id="dda3e-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="dda3e-105">键入 **文件共享的路径** ，以定义要镜像SQL Server备份文件的位置。</span><span class="sxs-lookup"><span data-stu-id="dda3e-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dda3e-106">主SQL Server实例 (实例或默认实例) 必须具有您在此处定义的文件共享的写入权限。</span><span class="sxs-lookup"><span data-stu-id="dda3e-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="dda3e-107">镜像SQL Server实例 (实例或默认实例) 必须具有对同一文件共享的读取权限。</span><span class="sxs-lookup"><span data-stu-id="dda3e-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="dda3e-108">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="dda3e-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="dda3e-109">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="dda3e-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="dda3e-110">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="dda3e-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dda3e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dda3e-111">See also</span></span>

[<span data-ttu-id="dda3e-112">在 skype SQL Server 2015 中部署后端服务器高可用性的镜像</span><span class="sxs-lookup"><span data-stu-id="dda3e-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
