---
title: 验证林准备的复制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 若要确认在林准备期间成功复制全局编录和创建对象，请执行下列操作：
ms.openlocfilehash: 010cf3fbadf8e07b4ccb80c33c34057024dde896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800552"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="f126f-103">验证林准备的复制</span><span class="sxs-lookup"><span data-stu-id="f126f-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="f126f-104">若要确认在林准备期间成功复制全局编录和创建对象，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f126f-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="f126f-105">在域控制器 (最好在其他域控制器) 的远程站点中，在运行林准备的林中，打开 **Active Directory 用户和计算机**。</span><span class="sxs-lookup"><span data-stu-id="f126f-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="f126f-106">在 **“Active Directory 用户和计算机”** 中，展开林或子域的域名。</span><span class="sxs-lookup"><span data-stu-id="f126f-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="f126f-107">单击 **左侧窗格** 上的"用户"容器，在右侧窗格中查找通用组 CsAdministrator。</span><span class="sxs-lookup"><span data-stu-id="f126f-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="f126f-108">如果 CsAdministrator (以 Cs) 开头的其他八个新通用组，则林准备复制已成功完成。</span><span class="sxs-lookup"><span data-stu-id="f126f-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="f126f-p102">如果未显示这些组，可以强制复制或等待 15 分钟后再刷新右侧窗格。显示组后，表明复制完成。</span><span class="sxs-lookup"><span data-stu-id="f126f-p102">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane. When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="f126f-111">如果要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，位于运行该步骤的 Active Directory 域服务用户的 Users 目录中。</span><span class="sxs-lookup"><span data-stu-id="f126f-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="f126f-112">例如，如果用户以域 Contoso.net 域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="f126f-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

