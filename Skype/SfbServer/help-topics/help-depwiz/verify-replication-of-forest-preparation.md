---
title: 验证林准备的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 若要确认全局编录复制和林准备期间创建的对象已成功，执行以下操作：
ms.openlocfilehash: 23e3aa84cd00c68ae126991c714c35b5fdf33536
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887277"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="74c05-103">验证林准备的复制</span><span class="sxs-lookup"><span data-stu-id="74c05-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="74c05-104">若要确认全局编录复制和林准备期间创建的对象已成功，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="74c05-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="74c05-105">在运行林准备的林中的域控制器上（最好在其他域控制器的远程站点中），打开“**Active Directory 用户和计算机**”。</span><span class="sxs-lookup"><span data-stu-id="74c05-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="74c05-106">在“**Active Directory 用户和计算机**”中，展开林或子域的域名。</span><span class="sxs-lookup"><span data-stu-id="74c05-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="74c05-107">单击左侧窗格上的**用户**容器，并在右侧窗格中的通用组 CsAdministrator 查找。</span><span class="sxs-lookup"><span data-stu-id="74c05-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="74c05-108">如果存在 CsAdministrator （之间八个其他新通用组开头 Cs），林准备的复制已成功。</span><span class="sxs-lookup"><span data-stu-id="74c05-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="74c05-109">如果组尚不存在，您可以强制执行复制或等待 15 分钟和刷新右侧窗格。</span><span class="sxs-lookup"><span data-stu-id="74c05-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="74c05-110">显示组后，表明复制完成。</span><span class="sxs-lookup"><span data-stu-id="74c05-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="74c05-111">如果您想要查看日志文件中的业务 Server 部署向导创建的 Skype，您可以在其中运行部署向导中，运行该步骤的 Active Directory 域服务用户的用户目录中的计算机上找到这些。</span><span class="sxs-lookup"><span data-stu-id="74c05-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="74c05-112">例如，如果用户登录以域管理员的域 Contoso.net 中，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="74c05-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

