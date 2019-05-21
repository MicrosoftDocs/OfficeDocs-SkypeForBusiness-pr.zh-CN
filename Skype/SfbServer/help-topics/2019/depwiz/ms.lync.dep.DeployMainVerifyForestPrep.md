---
title: 验证林准备的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: '若要在林准备中确认全局编录和创建对象的复制是否成功, 请执行下列操作:'
ms.openlocfilehash: c7fe425dcbecf2bfba02d4862bc3a29b75e16910
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303340"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="bd1a7-103">验证林准备的复制</span><span class="sxs-lookup"><span data-stu-id="bd1a7-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="bd1a7-104">若要在林准备中确认全局编录和创建对象的复制是否成功, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="bd1a7-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="bd1a7-105">在运行林准备的林中的域控制器上（最好在其他域控制器的远程站点中），打开“**Active Directory 用户和计算机**”。</span><span class="sxs-lookup"><span data-stu-id="bd1a7-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="bd1a7-106">在“**Active Directory 用户和计算机**”中，展开林或子域的域名。</span><span class="sxs-lookup"><span data-stu-id="bd1a7-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="bd1a7-107">单击左侧窗格中的 "**用户**" 容器, 然后在右侧窗格中查找 "通用组" CsAdministrator。</span><span class="sxs-lookup"><span data-stu-id="bd1a7-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="bd1a7-108">如果 CsAdministrator (在八个其他以 Cs 开头的新通用组中) 存在, 则林准备复制已成功。</span><span class="sxs-lookup"><span data-stu-id="bd1a7-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="bd1a7-109">如果组尚不存在, 则可以强制执行复制或等待15分钟, 并刷新右侧窗格。</span><span class="sxs-lookup"><span data-stu-id="bd1a7-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="bd1a7-110">显示组后，表明复制完成。</span><span class="sxs-lookup"><span data-stu-id="bd1a7-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="bd1a7-111">如果您想要查看由 Skype for Business 服务器部署向导创建的日志文件, 可以在运行该步骤的 Active Directory 域服务用户的用户目录中的 "部署向导" 计算机上找到它们。</span><span class="sxs-lookup"><span data-stu-id="bd1a7-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="bd1a7-112">例如, 如果用户在域 Contoso.net 中以域管理员身份登录, 则日志文件位于: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="bd1a7-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

