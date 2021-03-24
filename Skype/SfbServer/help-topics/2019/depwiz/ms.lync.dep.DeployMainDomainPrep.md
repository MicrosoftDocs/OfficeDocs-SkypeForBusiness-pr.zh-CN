---
title: 准备当前域
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 要准备用于托管运行 Skype for Business Server 或 Skype for Business Server 用户的服务器的域，必须完成步骤 5：准备当前域，如使用安装程序运行域准备主题中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 要准备域，请执行以下操作：
ms.openlocfilehash: a71e50b0f3d55709c3c22709177b41e541f7075f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097337"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="c1f18-105">准备当前域</span><span class="sxs-lookup"><span data-stu-id="c1f18-105">Prepare Current Domain</span></span>

<span data-ttu-id="c1f18-106">要准备用于托管运行 Skype for Business Server 或 Skype for Business Server 用户的服务器的域，必须完成步骤 **5：** 准备当前域，如使用安装程序运行域准备主题 [中所述](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)。</span><span class="sxs-lookup"><span data-stu-id="c1f18-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="c1f18-107">要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="c1f18-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="c1f18-108">要准备域，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c1f18-108">To prepare the domain:</span></span>

1. <span data-ttu-id="c1f18-109">从 Skype for Business Server 安装文件夹或媒体中，Setup.exe启动 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="c1f18-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="c1f18-110">单击“准备 Active Directory”，然后等待确定部署状态。</span><span class="sxs-lookup"><span data-stu-id="c1f18-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="c1f18-111">在“步骤 5: 准备当前域”中，单击“运行”。</span><span class="sxs-lookup"><span data-stu-id="c1f18-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="c1f18-112">在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。</span><span class="sxs-lookup"><span data-stu-id="c1f18-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="c1f18-113">在"**操作**"列下，展开"域准备"，在每项任务结束时查找"执行结果"以验证域准备是否成功完成，关闭日志，然后单击 **\<Success\>** "完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="c1f18-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="c1f18-114">如果需要查看 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，该计算机位于运行该步骤的 Active Directory 域服务用户的 Users 目录中。</span><span class="sxs-lookup"><span data-stu-id="c1f18-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="c1f18-115">例如，如果用户以域 Contoso.net 的域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="c1f18-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>