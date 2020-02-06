---
title: 准备单个 Standard Edition Server（调用）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在 "执行命令" 页面上，安装 SQL Server Express 和配置以充当中央管理存储的任务可以在任务窗格中查看。 默认情况下，将创建名为 "RTC" 的基于 SQL Server 的数据库实例。 还会创建防火墙规则，以允许服务器和客户端与数据库和实例通信的入站和出站访问。 任务完成后，您可以从下拉列表中选择日志文件。 日志文件被命名为 "引导本地计算机"。 选择日志文件后，单击 "查看日志"。 查看日志文件，查看是否有任何错误和警告。 准备好继续时，单击 "完成"。 现在，你应该使用拓扑生成器定义拓扑（如果尚未执行此操作）。
ms.openlocfilehash: 16cc6ada75ae90da4da2cb269aed26adbf472a33
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823436"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="4f3b9-111">准备单个 Standard Edition Server（调用）</span><span class="sxs-lookup"><span data-stu-id="4f3b9-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="4f3b9-112">在 "**执行命令**" 页面上，安装 SQL Server Express 和配置以充当中央管理存储的任务可以在任务窗格中查看。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="4f3b9-113">默认情况下，将创建名为 "RTC" 的基于 SQL Server 的数据库实例。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="4f3b9-114">还会创建防火墙规则，以允许服务器和客户端与数据库和实例通信的入站和出站访问。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="4f3b9-115">任务完成后，您可以从下拉列表中选择日志文件。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="4f3b9-116">日志文件被命名为 "**引导本地计算机**"。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="4f3b9-117">选择日志文件后，单击 "**查看日志**"。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="4f3b9-118">查看日志文件，查看是否有任何错误和警告。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="4f3b9-119">准备好继续时，单击 "**完成"。**</span><span class="sxs-lookup"><span data-stu-id="4f3b9-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="4f3b9-120">现在，你应该使用拓扑生成器定义拓扑（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4f3b9-121">SQL Server Express 安装可能需要一些时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="4f3b9-122">在安装期间，屏幕或任务窗格上不显示进度。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="4f3b9-123">若要监视安装，应使用 Windows 任务管理器，查找 MSIExec 进程和 SQL Server 的安装文件。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="4f3b9-124">通过这种方式，您可以查看安装的状态，并确保安装正在继续。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="4f3b9-125">根据本帮助主题范围之外的因素，安装 SQL Server 实例最多可能需要15分钟的时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="4f3b9-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

