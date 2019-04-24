---
title: 准备单个 Standard Edition Server（调用）
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: 在正在执行命令页中，可以在任务窗格中查看 SQL Server Express 安装和配置为充当中央管理存储的任务。 默认情况下创建名为 RTC 的基于 SQL Server 数据库的实例。 此外可以创建防火墙规则允许入站和出站访问服务器和客户端与数据库和实例进行通信。 在任务完成后，您可以从下拉列表中选择日志文件。 日志文件中名为 Bootstrap 本地计算机。 选择日志文件之后，单击查看日志。 查看日志文件的任何错误和警告。 当您准备好继续时，单击完成。 如果您没有，现在应定义您的拓扑使用拓扑生成器。
ms.openlocfilehash: b4c1807f383e6933e15d49b6e486978d3afc087f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216548"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="0cba5-111">准备单个 Standard Edition Server（调用）</span><span class="sxs-lookup"><span data-stu-id="0cba5-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="0cba5-112">在**正在执行命令**页上的 SQL Server Express 安装和配置为充当中央管理存储的任务可以查看在任务窗格中。</span><span class="sxs-lookup"><span data-stu-id="0cba5-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="0cba5-113">默认情况下创建名为 RTC 的基于 SQL Server 数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="0cba5-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="0cba5-114">此外可以创建防火墙规则允许入站和出站访问服务器和客户端与数据库和实例进行通信。</span><span class="sxs-lookup"><span data-stu-id="0cba5-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="0cba5-115">在任务完成后，您可以从下拉列表中选择日志文件。</span><span class="sxs-lookup"><span data-stu-id="0cba5-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="0cba5-116">日志文件中名为**Bootstrap 本地计算机**。</span><span class="sxs-lookup"><span data-stu-id="0cba5-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="0cba5-117">选择日志文件之后，单击**查看日志**。</span><span class="sxs-lookup"><span data-stu-id="0cba5-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="0cba5-118">查看日志文件的任何错误和警告。</span><span class="sxs-lookup"><span data-stu-id="0cba5-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="0cba5-119">当您准备好继续时，单击**完成。**</span><span class="sxs-lookup"><span data-stu-id="0cba5-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="0cba5-120">如果您没有，现在应定义您的拓扑使用拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="0cba5-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0cba5-121">安装 SQL Server Express 可能需要一些时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="0cba5-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="0cba5-122">安装期间，没有任何进度屏幕或任务窗格可见。</span><span class="sxs-lookup"><span data-stu-id="0cba5-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="0cba5-123">若要监视安装，应使用 Windows 任务管理器，并为 SQL Server 查找 MSIExec 流程和安装程序文件。</span><span class="sxs-lookup"><span data-stu-id="0cba5-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="0cba5-124">这种方式，您可以查看的安装状态，并确保是继续安装。</span><span class="sxs-lookup"><span data-stu-id="0cba5-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="0cba5-125">根据此帮助主题的范围之外的因素，它可以需要长达 15 分钟或更多安装 SQL Server 实例完成。</span><span class="sxs-lookup"><span data-stu-id="0cba5-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

