---
title: 准备一个标准版服务器 （调用）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在执行命令页，可以在任务窗格中查看安装 SQL Server Express 和配置作为中央管理存储的任务。 默认情况下，创建的名为 RTC 的基于 SQL Server 的数据库实例。 此外可以创建防火墙规则以允许入站和出站访问服务器和客户端与数据库和实例进行通信。 在任务完成后，您可以从下拉列表中选择日志文件。 启动本地计算机命名为日志文件。 选择日志文件之后, 单击查看日志。 检查所有错误和警告的日志文件。 当准备好继续时，单击完成。 如果您有不这样做，现在应该定义拓扑结构与拓扑生成器。
ms.openlocfilehash: d900c383d0f434176ff18b3f310c41042df75b2e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="e6476-111">准备一个标准版服务器 （调用）</span><span class="sxs-lookup"><span data-stu-id="e6476-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="e6476-112">在**执行命令**页中，可以在任务窗格中查看安装 SQL Server Express 和配置作为中央管理存储的任务。</span><span class="sxs-lookup"><span data-stu-id="e6476-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="e6476-113">默认情况下，创建的名为 RTC 的基于 SQL Server 的数据库实例。</span><span class="sxs-lookup"><span data-stu-id="e6476-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="e6476-114">此外可以创建防火墙规则以允许入站和出站访问服务器和客户端与数据库和实例进行通信。</span><span class="sxs-lookup"><span data-stu-id="e6476-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="e6476-115">在任务完成后，您可以从下拉列表中选择日志文件。</span><span class="sxs-lookup"><span data-stu-id="e6476-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="e6476-116">**启动本地计算机**命名为日志文件。</span><span class="sxs-lookup"><span data-stu-id="e6476-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="e6476-117">选择日志文件之后, 单击**查看日志**。</span><span class="sxs-lookup"><span data-stu-id="e6476-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="e6476-118">检查所有错误和警告的日志文件。</span><span class="sxs-lookup"><span data-stu-id="e6476-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="e6476-119">当准备好继续时，单击**完成。**</span><span class="sxs-lookup"><span data-stu-id="e6476-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="e6476-120">如果您有不这样做，现在应该定义拓扑结构与拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="e6476-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e6476-121">SQL Server Express 安装可能需要一些时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="e6476-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="e6476-122">安装期间，没有任何进度屏幕或任务窗格上的可见。</span><span class="sxs-lookup"><span data-stu-id="e6476-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="e6476-123">要监视安装，应使用 Windows 任务管理器并查找 SQL Server MSIExec 进程和安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="e6476-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="e6476-124">以这种方式，您可以查看安装状态并确保安装正在进行。</span><span class="sxs-lookup"><span data-stu-id="e6476-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="e6476-125">根据此帮助主题的范围之外的因素，它可以需要长达 15 分钟或更多安装 SQL Server 的实例来完成。</span><span class="sxs-lookup"><span data-stu-id="e6476-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

