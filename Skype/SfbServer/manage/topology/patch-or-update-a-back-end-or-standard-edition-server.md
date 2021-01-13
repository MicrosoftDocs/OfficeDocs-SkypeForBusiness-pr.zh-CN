---
title: 在 Skype for Business Server 中修补或更新后端服务器或 Standard Edition Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 摘要：了解如何在 Skype for Business Server 的后端服务器上安装更新或修补程序。
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826302"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="26732-103">在 Skype for Business Server 中修补或更新后端服务器或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="26732-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="26732-104">**摘要：** 了解如何在 Skype for Business Server 的后端服务器上安装更新或修补程序。</span><span class="sxs-lookup"><span data-stu-id="26732-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="26732-105">本主题介绍如何在 Enterprise Edition 后端服务器或 Standard Edition 服务器上安装更新。</span><span class="sxs-lookup"><span data-stu-id="26732-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="26732-p101">如果在您升级后端服务器时它至少要停机 30 分钟，则用户可能会进入恢复能力模式。升级完成，且后端服务器又与池中的前端服务器连接后，用户会返回到全部功能。如果升级所用时间少于 30 分钟，将不会对用户造成影响。</span><span class="sxs-lookup"><span data-stu-id="26732-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="26732-109">更新后端服务器或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="26732-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="26732-110">以 CsAdministrator 角色的成员身份登录到要升级的服务器。</span><span class="sxs-lookup"><span data-stu-id="26732-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="26732-111">下载更新并将其提取到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="26732-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="26732-112">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，单击 **"Skype for Business"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="26732-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="26732-113">停止 Skype for Business Server 服务。</span><span class="sxs-lookup"><span data-stu-id="26732-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="26732-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="26732-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="26732-115">停止万维网服务。</span><span class="sxs-lookup"><span data-stu-id="26732-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="26732-116">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="26732-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="26732-117">关闭所有 Skype for Business Server 命令行管理程序窗口。</span><span class="sxs-lookup"><span data-stu-id="26732-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="26732-118">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="26732-118">Install the update.</span></span>
    
8. <span data-ttu-id="26732-119">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，单击 **"Skype for Business"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="26732-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="26732-120">再次停止 Skype for Business Server 服务，以捕获 GAC (程序集) 全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="26732-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="26732-121">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="26732-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="26732-122">重新启动万维网服务。</span><span class="sxs-lookup"><span data-stu-id="26732-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="26732-123">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="26732-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="26732-124">通过执行以下操作之SQL Server对数据库应用所做的更改：</span><span class="sxs-lookup"><span data-stu-id="26732-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="26732-125">如果这是 Enterprise Edition 后端服务器，并且此服务器上没有并排的数据库（如存档数据库或监控数据库），则命令行中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="26732-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="26732-126">如果这是 Enterprise Edition 后端服务器，并且此服务器上存在并排的数据库，则命令行中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="26732-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="26732-127">如果这是 Standard Edition Server，在命令行中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="26732-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
