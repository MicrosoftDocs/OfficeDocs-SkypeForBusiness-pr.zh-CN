---
title: 修补程序或更新业务服务器中 Skype 的后端服务器或 Standard Edition 服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 摘要： 了解如何为业务服务器中 Skype 后端服务器上安装更新或修补程序。
ms.openlocfilehash: 7815c42443afae6fef7aaec71399120fb61ece82
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969129"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="e0347-103">修补程序或更新业务服务器中 Skype 的后端服务器或 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="e0347-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="e0347-104">**摘要：** 了解如何为业务服务器中 Skype 后端服务器上安装更新或修补程序。</span><span class="sxs-lookup"><span data-stu-id="e0347-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="e0347-105">本主题介绍如何在 Enterprise Edition 后端服务器或 Standard Edition server 上安装更新。</span><span class="sxs-lookup"><span data-stu-id="e0347-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="e0347-106">如果后端服务器已关闭至少 30 分钟内将对其进行升级时，用户可能然后转到恢复能力模式。</span><span class="sxs-lookup"><span data-stu-id="e0347-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="e0347-107">当升级完成和后端服务器再次已连接具有池中前端服务器时，用户将返回完整功能。</span><span class="sxs-lookup"><span data-stu-id="e0347-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="e0347-108">如果升级所用时间少于 30 分钟，则用户不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="e0347-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="e0347-109">更新后端服务器或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="e0347-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="e0347-110">以 CsAdministrator 角色的成员身份登录到要升级的服务器。</span><span class="sxs-lookup"><span data-stu-id="e0347-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="e0347-111">下载更新并将其提取到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="e0347-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="e0347-112">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**for Business 的 Skype**，，然后都单击**业务 Server Management Shell 的 Skype**正在</span><span class="sxs-lookup"><span data-stu-id="e0347-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="e0347-113">停止 Skype 业务服务器服务。</span><span class="sxs-lookup"><span data-stu-id="e0347-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="e0347-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e0347-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="e0347-p103">停止万维网服务。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e0347-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="e0347-117">关闭所有 Skype 业务 Server Management Shell windows。</span><span class="sxs-lookup"><span data-stu-id="e0347-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="e0347-118">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="e0347-118">Install the update.</span></span>
    
8. <span data-ttu-id="e0347-119">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**for Business 的 Skype**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="e0347-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="e0347-120">停止对业务 Server 服务的 Skype 再次以捕获-d 全局程序集缓存 (GAC) 的程序集。</span><span class="sxs-lookup"><span data-stu-id="e0347-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="e0347-121">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e0347-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="e0347-p105">重新启动万维网服务。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e0347-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="e0347-124">执行以下操作之一，将所做更改应用于 SQL Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="e0347-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="e0347-125">如果这是 Enterprise Edition 后端服务器，并且没有并置在此服务器上，如存档数据库或监控数据库，然后键入以下命令行：</span><span class="sxs-lookup"><span data-stu-id="e0347-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="e0347-126">如果这是 Enterprise Edition 后端服务器，并且此服务器上没有并置的数据库，然后键入以下命令行：</span><span class="sxs-lookup"><span data-stu-id="e0347-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="e0347-127">如果这是 Standard Edition 服务器，请键入以下命令行：</span><span class="sxs-lookup"><span data-stu-id="e0347-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```