---
title: 准备当前林
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: 若要准备 Active Directory 域服务林，必须成功扩展架构，如运行架构准备的主题中所述，并确保架构已复制。
ms.openlocfilehash: 0458fee54814f7f48382709a0509494e770d3e2b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798309"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="26287-103">准备当前林</span><span class="sxs-lookup"><span data-stu-id="26287-103">Prepare Current Forest</span></span>

<span data-ttu-id="26287-104">若要准备 Active Directory 域服务林，必须成功扩展架构，如[运行架构准备](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)的主题中所述，并确保架构已复制。</span><span class="sxs-lookup"><span data-stu-id="26287-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="26287-p101">完成这些先决任务后，即可开始“**步骤 3：准备当前林**”。要准备林，请以林根中 Domain Admins 组成员身份或正在准备的林的 Enterprise Admins 组成员身份登录到林根中的一台计算机。</span><span class="sxs-lookup"><span data-stu-id="26287-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="26287-107">在部署向导的“**步骤 3：准备当前林**”中，单击“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="26287-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="26287-108">在“**准备林**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="26287-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26287-109">林准备允许你选择放置 Skype for Business 服务器通用组的位置。</span><span class="sxs-lookup"><span data-stu-id="26287-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server.</span></span> <span data-ttu-id="26287-110">选择与组织要求一致的位置。</span><span class="sxs-lookup"><span data-stu-id="26287-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="26287-p103">在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。确保没有任何错误。查看警告以确定对于您的基础结构来说，它们是否为预期和典型的问题。</span><span class="sxs-lookup"><span data-stu-id="26287-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="26287-114">在日志中的 "**操作**" 列下，展开 "**林准备**"，查找每个任务末尾的\*\* \<成功\> **执行结果以验证林准备是否已成功完成，关闭日志，然后单击 "**完成\*\*"。</span><span class="sxs-lookup"><span data-stu-id="26287-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="26287-115">等待 Active Directory 域服务复制完成，或强制复制到林根域控制器的**Active Directory 站点和服务**管理单元中列出的所有域控制器，然后再运行域准备。</span><span class="sxs-lookup"><span data-stu-id="26287-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="26287-116">在所有 Active Directory 网站中的域控制器之间强制进行复制，以使网站内的复制在分钟内发生。</span><span class="sxs-lookup"><span data-stu-id="26287-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="26287-117">如果您需要查看由 Skype for Business 服务器部署向导创建的日志文件，则可以在运行该步骤的 Active Directory 域服务用户的用户目录中找到运行部署向导的计算机上的日志文件。</span><span class="sxs-lookup"><span data-stu-id="26287-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="26287-118">例如，如果用户在域 Contoso.net 中以域管理员身份登录，则日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="26287-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


