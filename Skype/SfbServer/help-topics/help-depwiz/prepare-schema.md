---
title: 准备架构
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: 准备 Active Directory 域服务的架构，您运行架构准备步骤中 Skype 业务 Server 部署向导。 单击“运行”可开始准备架构。 架构准备步骤读取/程序文件/Microsoft Lync Server 2013/部署/安装目录中运行部署向导的系统上提供的架构定义文件。 这些文件也是支持/架构目录中的安装媒体上可用。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
ms.openlocfilehash: 8565a3474b309820714949b5aa6f4544c72a23bd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891006"
---
# <a name="prepare-schema"></a><span data-ttu-id="c9178-110">准备架构</span><span class="sxs-lookup"><span data-stu-id="c9178-110">Prepare Schema</span></span>
 
<span data-ttu-id="c9178-111">准备 Active Directory 域服务的架构，您运行架构准备步骤中 Skype 业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="c9178-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="c9178-112">单击“**运行**”可开始准备架构。</span><span class="sxs-lookup"><span data-stu-id="c9178-112">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="c9178-113">“准备架构”步骤会在运行部署向导的系统的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目录中读取提供的架构定义文件。</span><span class="sxs-lookup"><span data-stu-id="c9178-113">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="c9178-114">安装介质的 \Support\Schema 目录中也提供了这些文件。</span><span class="sxs-lookup"><span data-stu-id="c9178-114">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="c9178-115">“准备架构”步骤将扩展架构并报告准备过程的状态。</span><span class="sxs-lookup"><span data-stu-id="c9178-115">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="c9178-116">还将在完成准备过程时通知您。</span><span class="sxs-lookup"><span data-stu-id="c9178-116">It will also notify you when the process is complete.</span></span> <span data-ttu-id="c9178-117">通过摘要屏幕可以查看该过程的日志。</span><span class="sxs-lookup"><span data-stu-id="c9178-117">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="c9178-118">查看日志以确保准备工作已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c9178-118">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c9178-119">要扩展架构，必须以 Schema Admins 和 Enterprise Admins 组成员身份登录域。</span><span class="sxs-lookup"><span data-stu-id="c9178-119">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="c9178-120">添加的类和属性扩展 Active Directory 域服务架构以支持 Skype 业务服务器 2015年服务器、 服务和用户对象。</span><span class="sxs-lookup"><span data-stu-id="c9178-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span></span> <span data-ttu-id="c9178-121">在扩展架构之前，应该对担任架构主机角色的域控制器进行系统状态备份。</span><span class="sxs-lookup"><span data-stu-id="c9178-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="c9178-122">有关 Windows Server 2008 R2 sp1 的备份过程的详细信息，请参阅[https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)。</span><span class="sxs-lookup"><span data-stu-id="c9178-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="c9178-123">Windows Server 2003 和 Windows Server 2003 R2，请参阅[https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)。</span><span class="sxs-lookup"><span data-stu-id="c9178-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c9178-124">扩展架构是不可逆的。</span><span class="sxs-lookup"><span data-stu-id="c9178-124">Extending the schema is not reversible.</span></span> <span data-ttu-id="c9178-125">应尽一切努力限制失败的架构扩展的潜在影响，并确保架构扩展能够成功。</span><span class="sxs-lookup"><span data-stu-id="c9178-125">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="c9178-126">在通信中断或服务器上出现任何其他故障的情况下，这一点尤为重要。</span><span class="sxs-lookup"><span data-stu-id="c9178-126">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="c9178-127">您应执行备份的架构主机的域控制器和 Active Directory 的完整备份。</span><span class="sxs-lookup"><span data-stu-id="c9178-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="c9178-128">若要执行备份的架构主机的域控制器和 Active Directory 的完整备份：</span><span class="sxs-lookup"><span data-stu-id="c9178-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="c9178-129">断开担当架构主机角色的域控制器与网络的连接。</span><span class="sxs-lookup"><span data-stu-id="c9178-129">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="c9178-130">对担当架构主机角色的域控制器执行系统状态备份。</span><span class="sxs-lookup"><span data-stu-id="c9178-130">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="c9178-131">扩展架构。</span><span class="sxs-lookup"><span data-stu-id="c9178-131">Extend the schema.</span></span>
    
4. <span data-ttu-id="c9178-132">架构扩展成功后，将域控制器重新连接到网络，并确保复制为活动状态且正常工作。</span><span class="sxs-lookup"><span data-stu-id="c9178-132">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="c9178-133">万一架构扩展失败，使用您之前生成的系统状态备份还原域控制器和 Active Directory 的系统状态。</span><span class="sxs-lookup"><span data-stu-id="c9178-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c9178-134">如果您需要查看 Skype 业务 Server 部署向导创建的日志文件，您可以找到其中运行部署向导中，运行该步骤的 Active Directory 用户的用户目录中的计算机上的文件。</span><span class="sxs-lookup"><span data-stu-id="c9178-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="c9178-135">例如，如果用户登录以域管理员的域 Contoso.net 中，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="c9178-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

