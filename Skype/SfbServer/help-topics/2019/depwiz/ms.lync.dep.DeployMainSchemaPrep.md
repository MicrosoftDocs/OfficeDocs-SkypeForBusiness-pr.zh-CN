---
title: 准备架构
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要为 Active Directory 域服务准备架构，请运行 Skype for Business Server 部署向导中的"准备架构"步骤。 单击“运行”可开始准备架构。
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833772"
---
# <a name="prepare-schema"></a><span data-ttu-id="c07e5-104">准备架构</span><span class="sxs-lookup"><span data-stu-id="c07e5-104">Prepare Schema</span></span>
 
<span data-ttu-id="c07e5-105">若要为 Active Directory 域服务准备架构，请运行 Skype for Business Server 部署向导中的"准备架构"步骤。</span><span class="sxs-lookup"><span data-stu-id="c07e5-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="c07e5-106">单击“运行”可开始准备架构。</span><span class="sxs-lookup"><span data-stu-id="c07e5-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="c07e5-107">"准备架构"步骤读取运行部署向导的系统上的 \Program Files\Skype for Business Server 2019\Deployment\Setup 目录中提供的架构定义文件。</span><span class="sxs-lookup"><span data-stu-id="c07e5-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="c07e5-108">安装介质的 \Support\Schema 目录中也提供了这些文件。</span><span class="sxs-lookup"><span data-stu-id="c07e5-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="c07e5-109">“准备架构”步骤将扩展架构并报告准备过程的状态。</span><span class="sxs-lookup"><span data-stu-id="c07e5-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="c07e5-110">还将在完成准备过程时通知您。</span><span class="sxs-lookup"><span data-stu-id="c07e5-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="c07e5-111">通过摘要屏幕可以查看该过程的日志。</span><span class="sxs-lookup"><span data-stu-id="c07e5-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="c07e5-112">查看日志以确保准备工作已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c07e5-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c07e5-113">要扩展架构，必须以 Schema Admins 和 Enterprise Admins 组成员身份登录域。</span><span class="sxs-lookup"><span data-stu-id="c07e5-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="c07e5-114">添加类和属性以扩展 Active Directory 域服务架构以支持 Skype for Business Server 服务器、服务和用户对象。</span><span class="sxs-lookup"><span data-stu-id="c07e5-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="c07e5-115">在扩展架构之前，应该对担任架构主机角色的域控制器进行系统状态备份。</span><span class="sxs-lookup"><span data-stu-id="c07e5-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="c07e5-116">扩展架构是不可逆的。</span><span class="sxs-lookup"><span data-stu-id="c07e5-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="c07e5-117">应尽一切努力限制失败的架构扩展的潜在影响，并确保架构扩展能够成功。</span><span class="sxs-lookup"><span data-stu-id="c07e5-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="c07e5-118">在丧失通信或服务器上出现任何其他故障的情况下，这尤其重要。</span><span class="sxs-lookup"><span data-stu-id="c07e5-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="c07e5-119">您应执行架构主机域控制器的备份和 Active Directory 的完整备份。</span><span class="sxs-lookup"><span data-stu-id="c07e5-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="c07e5-120">若要执行架构主机域控制器的备份和 Active Directory 的完整备份，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c07e5-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="c07e5-121">断开担当架构主机角色的域控制器与网络的连接。</span><span class="sxs-lookup"><span data-stu-id="c07e5-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="c07e5-122">对担当架构主机角色的域控制器执行系统状态备份。</span><span class="sxs-lookup"><span data-stu-id="c07e5-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="c07e5-123">扩展架构。</span><span class="sxs-lookup"><span data-stu-id="c07e5-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="c07e5-124">架构扩展成功后，将域控制器重新连接到网络，并确保复制为活动状态且正常工作。</span><span class="sxs-lookup"><span data-stu-id="c07e5-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="c07e5-125">如果架构扩展失败，则使用之前采用的系统状态备份还原域控制器和 Active Directory 的系统状态。</span><span class="sxs-lookup"><span data-stu-id="c07e5-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c07e5-126">如果需要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到运行该步骤的 Active Directory 用户的 Users 目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="c07e5-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="c07e5-127">例如，如果用户以域 Contoso.net 域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="c07e5-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

