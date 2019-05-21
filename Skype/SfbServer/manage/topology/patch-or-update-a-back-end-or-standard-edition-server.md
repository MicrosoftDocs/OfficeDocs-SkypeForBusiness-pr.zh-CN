---
title: 在 Skype for Business 服务器中修补或更新后端服务器或标准版服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '摘要: 了解如何在 Skype for Business 服务器的后端服务器上安装更新或修补程序。'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275120"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="8e379-103">在 Skype for Business 服务器中修补或更新后端服务器或标准版服务器</span><span class="sxs-lookup"><span data-stu-id="8e379-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="8e379-104">**摘要:** 了解如何在 Skype for Business 服务器的后端服务器上安装更新或修补程序。</span><span class="sxs-lookup"><span data-stu-id="8e379-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="8e379-105">本主题介绍如何在企业版后端服务器或标准版服务器上安装更新。</span><span class="sxs-lookup"><span data-stu-id="8e379-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="8e379-106">如果后端服务器在升级后至少30分钟, 则用户可能会进入恢复模式。</span><span class="sxs-lookup"><span data-stu-id="8e379-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="8e379-107">升级完成且后端服务器再次与池中的前端服务器连接时, 用户将返回到完整功能。</span><span class="sxs-lookup"><span data-stu-id="8e379-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="8e379-108">如果升级所用时间少于 30 分钟，则用户不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="8e379-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="8e379-109">更新后端服务器或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="8e379-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="8e379-110">以 CsAdministrator 角色的成员身份登录到要升级的服务器。</span><span class="sxs-lookup"><span data-stu-id="8e379-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="8e379-111">下载更新并将其提取到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="8e379-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="8e379-112">启动 Skype for Business 服务器命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **skype**for Business", 然后单击 " **skype for business 服务器管理外壳程序**"。</span><span class="sxs-lookup"><span data-stu-id="8e379-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="8e379-113">停止 Skype for Business 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="8e379-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="8e379-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="8e379-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="8e379-115">停止万维网服务。</span><span class="sxs-lookup"><span data-stu-id="8e379-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="8e379-116">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="8e379-116">At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="8e379-117">关闭所有 Skype for Business 服务器管理外壳程序窗口。</span><span class="sxs-lookup"><span data-stu-id="8e379-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="8e379-118">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="8e379-118">Install the update.</span></span>
    
8. <span data-ttu-id="8e379-119">启动 Skype for Business 服务器命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **skype**for Business", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="8e379-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="8e379-120">再次停止 Skype for Business 服务器服务以捕获全局程序集缓存 (GAC)-d 程序集。</span><span class="sxs-lookup"><span data-stu-id="8e379-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="8e379-121">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="8e379-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="8e379-p105">重新启动万维网服务。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="8e379-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="8e379-124">执行以下操作之一，将所做更改应用于 SQL Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="8e379-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="8e379-125">如果这是企业版后端服务器, 并且此服务器上没有 collocated 数据库 (如 "存档" 或 "监视数据库"), 请在命令行中键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="8e379-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="8e379-126">如果这是企业版后端服务器, 并且此服务器上有 collocated 数据库, 请在命令行中键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="8e379-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="8e379-127">如果这是标准版服务器, 请在命令行键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="8e379-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
