---
title: 安装镜像数据库选项页
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 您可以通过以下定义配置镜像数据库设置：
ms.openlocfilehash: 2cd793883baf5e5d567e9248e60f6601f8e1aa96
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19989760"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="cb141-103">安装镜像数据库选项页</span><span class="sxs-lookup"><span data-stu-id="cb141-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="cb141-104">您可以通过以下定义配置**镜像数据库设置**：</span><span class="sxs-lookup"><span data-stu-id="cb141-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="cb141-105">键入**文件的路径共享**定义要镜像的数据库的备份 SQL Server 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="cb141-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cb141-106">主要的 SQL Server 实例 （命名的实例或默认实例） 必须具有此处定义的文件共享的写入权限。</span><span class="sxs-lookup"><span data-stu-id="cb141-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="cb141-107">镜像 SQL Server 实例 （命名的实例或默认实例） 必须具有读取访问相同的文件共享的权限。</span><span class="sxs-lookup"><span data-stu-id="cb141-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
 <span data-ttu-id="cb141-108">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="cb141-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="cb141-109">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="cb141-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="cb141-110">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="cb141-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb141-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb141-111">See also</span></span>

[<span data-ttu-id="cb141-112">部署 SQL 镜像后端服务器高可用性 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="cb141-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server</span></span>](../../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)