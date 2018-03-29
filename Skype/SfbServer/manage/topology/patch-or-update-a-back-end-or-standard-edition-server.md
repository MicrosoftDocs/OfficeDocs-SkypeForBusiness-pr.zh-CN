---
title: 修补或更新 Skype for Business Server 2015 中的后端服务器或 Standard Edition Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 摘要： 了解如何在 Skype 在后端服务器上的业务服务器安装更新程序或修补程序。
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a><span data-ttu-id="751f4-103">修补或更新 Skype for Business Server 2015 中的后端服务器或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="751f4-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="751f4-104">**摘要：**了解如何在 Skype 在后端服务器上的业务服务器安装更新程序或修补程序。</span><span class="sxs-lookup"><span data-stu-id="751f4-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="751f4-105">本主题介绍如何安装企业版后端服务器或标准版服务器上的更新。</span><span class="sxs-lookup"><span data-stu-id="751f4-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="751f4-106">如果后端服务器已关闭至少 30 分钟而对其进行升级，用户可能然后进入恢复模式。</span><span class="sxs-lookup"><span data-stu-id="751f4-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="751f4-107">在完成升级后端服务器已重新连接与前端服务器的池中，用户返回到完整功能。</span><span class="sxs-lookup"><span data-stu-id="751f4-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="751f4-108">如果升级所用时间少于 30 分钟，则用户不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="751f4-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="751f4-109">更新后端服务器或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="751f4-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="751f4-110">以 CsAdministrator 角色的成员身份登录到要升级的服务器。</span><span class="sxs-lookup"><span data-stu-id="751f4-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="751f4-111">下载更新并将其提取到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="751f4-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="751f4-112">为业务服务器管理外壳程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**业务 2015年的 Skype**，然后都单击**业务服务器管理外壳的 Skype**。.</span><span class="sxs-lookup"><span data-stu-id="751f4-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="751f4-113">停止业务服务器服务 Skype。</span><span class="sxs-lookup"><span data-stu-id="751f4-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="751f4-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="751f4-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="751f4-p103">停止万维网服务。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="751f4-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="751f4-117">关闭所有 Skype 业务服务器管理外壳程序窗口。</span><span class="sxs-lookup"><span data-stu-id="751f4-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="751f4-118">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="751f4-118">Install the update.</span></span>
    
8. <span data-ttu-id="751f4-119">为业务服务器管理外壳程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**业务 2015年的 Skype**，然后都单击**业务服务器管理外壳的 Skype**。.</span><span class="sxs-lookup"><span data-stu-id="751f4-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
9. <span data-ttu-id="751f4-120">停止业务服务器服务 Skype，再次以捕捉全局程序集缓存 (GAC)-d 程序集。</span><span class="sxs-lookup"><span data-stu-id="751f4-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="751f4-121">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="751f4-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="751f4-p105">重新启动万维网服务。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="751f4-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="751f4-124">执行以下操作之一，将所做更改应用于 SQL Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="751f4-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="751f4-125">如果这是企业版后端服务器，并且没有按顺序排列在此服务器上，如存档数据库或监视数据库，然后键入以下命令的命令行：</span><span class="sxs-lookup"><span data-stu-id="751f4-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="751f4-126">如果这是企业版后端服务器，此服务器上没有按顺序排列的数据库，然后键入以下命令的命令行：</span><span class="sxs-lookup"><span data-stu-id="751f4-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="751f4-127">如果这是一个标准版的服务器，请在命令行键入以下：</span><span class="sxs-lookup"><span data-stu-id="751f4-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


