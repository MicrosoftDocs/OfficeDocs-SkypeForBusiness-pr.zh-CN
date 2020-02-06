---
title: 准备架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: 若要准备 Active Directory 域服务的架构，请在 "Skype for Business 服务器部署" 向导中运行 "准备架构" 步骤。 单击“运行”可开始准备架构。 准备架构步骤将在运行部署向导的系统上的/Program 文件/Microsoft Lync Server 2013/部署/安装目录中读取所提供的架构定义文件。 这些文件也可在支持/架构目录中的安装媒体上使用。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
ms.openlocfilehash: ae4c44adf8c94efa7b87c9f1a4f5f142a7117276
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823476"
---
# <a name="prepare-schema"></a><span data-ttu-id="19b7b-110">准备架构</span><span class="sxs-lookup"><span data-stu-id="19b7b-110">Prepare Schema</span></span>
 
<span data-ttu-id="19b7b-111">若要准备 Active Directory 域服务的架构，请在 "Skype for Business 服务器部署" 向导中运行 "准备架构" 步骤。</span><span class="sxs-lookup"><span data-stu-id="19b7b-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="19b7b-112">单击“**运行**”可开始准备架构。</span><span class="sxs-lookup"><span data-stu-id="19b7b-112">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="19b7b-113">“准备架构”步骤会在运行部署向导的系统的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目录中读取提供的架构定义文件。</span><span class="sxs-lookup"><span data-stu-id="19b7b-113">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="19b7b-114">安装介质的 \Support\Schema 目录中也提供了这些文件。</span><span class="sxs-lookup"><span data-stu-id="19b7b-114">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="19b7b-115">“准备架构”步骤将扩展架构并报告准备过程的状态。</span><span class="sxs-lookup"><span data-stu-id="19b7b-115">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="19b7b-116">还将在完成准备过程时通知您。</span><span class="sxs-lookup"><span data-stu-id="19b7b-116">It will also notify you when the process is complete.</span></span> <span data-ttu-id="19b7b-117">通过摘要屏幕可以查看该过程的日志。</span><span class="sxs-lookup"><span data-stu-id="19b7b-117">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="19b7b-118">查看日志以确保准备工作已成功完成。</span><span class="sxs-lookup"><span data-stu-id="19b7b-118">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="19b7b-119">要扩展架构，必须以 Schema Admins 和 Enterprise Admins 组成员身份登录域。</span><span class="sxs-lookup"><span data-stu-id="19b7b-119">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="19b7b-120">将添加类和属性以扩展 Active Directory 域服务架构，以支持 Skype for Business Server 2015 服务器、服务和用户对象。</span><span class="sxs-lookup"><span data-stu-id="19b7b-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span></span> <span data-ttu-id="19b7b-121">在扩展架构之前，应该对担任架构主机角色的域控制器进行系统状态备份。</span><span class="sxs-lookup"><span data-stu-id="19b7b-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="19b7b-122">有关 Windows Server 2008 R2 适用于 SP1 的备份过程的详细信息， [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)请参阅。</span><span class="sxs-lookup"><span data-stu-id="19b7b-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="19b7b-123">对于 Windows Server 2003 和 Windows Server 2003 R2，请[https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)参阅。</span><span class="sxs-lookup"><span data-stu-id="19b7b-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="19b7b-124">扩展架构是不可逆的。</span><span class="sxs-lookup"><span data-stu-id="19b7b-124">Extending the schema is not reversible.</span></span> <span data-ttu-id="19b7b-125">应尽一切努力限制失败的架构扩展的潜在影响，并确保架构扩展能够成功。</span><span class="sxs-lookup"><span data-stu-id="19b7b-125">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="19b7b-126">在通信中断或服务器上出现任何其他故障的情况下，这一点尤为重要。</span><span class="sxs-lookup"><span data-stu-id="19b7b-126">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="19b7b-127">你应该执行架构主机域控制器的备份和 Active Directory 的完整备份。</span><span class="sxs-lookup"><span data-stu-id="19b7b-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="19b7b-128">若要执行架构主机域控制器的备份和 Active Directory 的完整备份，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="19b7b-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="19b7b-129">断开担当架构主机角色的域控制器与网络的连接。</span><span class="sxs-lookup"><span data-stu-id="19b7b-129">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="19b7b-130">对担当架构主机角色的域控制器执行系统状态备份。</span><span class="sxs-lookup"><span data-stu-id="19b7b-130">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="19b7b-131">扩展架构。</span><span class="sxs-lookup"><span data-stu-id="19b7b-131">Extend the schema.</span></span>
    
4. <span data-ttu-id="19b7b-132">架构扩展成功后，将域控制器重新连接到网络，并确保复制为活动状态且正常工作。</span><span class="sxs-lookup"><span data-stu-id="19b7b-132">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="19b7b-133">在架构扩展出现故障的情况下，请使用之前的系统状态备份还原域控制器和 Active Directory 的系统状态。</span><span class="sxs-lookup"><span data-stu-id="19b7b-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="19b7b-134">如果需要查看由 Skype for Business 服务器部署向导创建的日志文件，可以在运行该步骤的 Active Directory 用户的用户目录中找到运行部署向导的计算机上的文件。</span><span class="sxs-lookup"><span data-stu-id="19b7b-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="19b7b-135">例如，如果用户在域 Contoso.net 中以域管理员身份登录，则日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="19b7b-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

