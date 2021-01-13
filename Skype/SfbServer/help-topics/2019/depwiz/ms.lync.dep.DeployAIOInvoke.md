---
title: 准备单个 Standard Edition Server（调用）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: 在"正在执行命令"页上，可以在任务窗格中查看安装 SQL Server Express 并配置为充当中央管理存储的任务。 默认情况下，将创建一SQL Server名为 RTC 的基于数据库的实例。 还会创建防火墙规则，以允许对服务器和客户端的入站和出站访问，从而与数据库和实例进行通信。 完成任务后，可从下拉列表中选择日志文件。 日志文件名为“Bootstrap local machine”。 选择此日志文件后，单击“查看日志”。 在日志文件中查看任何错误和警告信息。 准备好继续操作时，单击“完成”。 如果尚未定义拓扑生成器，现在应该使用拓扑生成器定义拓扑。
ms.openlocfilehash: c3e6e01f7aed0471d8f1eed0ad79f8ef6320f86a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820612"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="b7cdc-111">准备单个 Standard Edition Server（调用）</span><span class="sxs-lookup"><span data-stu-id="b7cdc-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="b7cdc-112">在 **"正在执行命令** "页上，可以在任务窗格中查看安装 SQL Server Express 并配置为充当中央管理存储的任务。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="b7cdc-113">默认情况下，将创建一SQL Server名为 RTC 的基于数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="b7cdc-114">还会创建防火墙规则，以允许对服务器和客户端的入站和出站访问，从而与数据库和实例进行通信。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="b7cdc-115">完成任务后，可从下拉列表中选择日志文件。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="b7cdc-116">日志文件名为“Bootstrap local machine”。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="b7cdc-117">选择此日志文件后，单击“查看日志”。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="b7cdc-118">在日志文件中查看任何错误和警告信息。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="b7cdc-119">准备好继续操作时，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="b7cdc-120">如果尚未定义拓扑生成器，现在应该使用拓扑生成器定义拓扑。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b7cdc-121">安装 SQL Server Express 可能需要一些时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="b7cdc-122">安装期间，屏幕或任务窗格上不会显示安装进度。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="b7cdc-123">若要监视安装，您应使用 Windows 任务管理器并查找 MSIExec 进程和安装程序文件SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="b7cdc-124">这样就可以查看安装状态并确保安装正在进行。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="b7cdc-125">根据此帮助主题范围以外的因素，可能需要 15 分钟或SQL Server安装实例。</span><span class="sxs-lookup"><span data-stu-id="b7cdc-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

