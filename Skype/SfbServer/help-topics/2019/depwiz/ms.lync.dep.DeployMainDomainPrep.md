---
title: 准备当前域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 若要准备的企业服务器用户业务服务器或 Skype 运行 Skype 的主机服务器的域，您必须完成步骤 5： 准备当前域，使用安装程序运行域准备主题中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 若要准备域：
ms.openlocfilehash: 21440b3797b5c1f9d85113b5c180e7b8009c1528
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893677"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="17783-105">准备当前域</span><span class="sxs-lookup"><span data-stu-id="17783-105">Prepare Current Domain</span></span>

<span data-ttu-id="17783-106">若要准备的企业服务器用户业务服务器或 Skype 运行 Skype 的主机服务器的域，您必须完成**步骤 5： 准备当前域**、 主题[使用 Setup 运行域准备过程](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="17783-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="17783-107">要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="17783-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="17783-108">若要准备域：</span><span class="sxs-lookup"><span data-stu-id="17783-108">To prepare the domain:</span></span>

1. <span data-ttu-id="17783-109">从业务 Server 安装文件夹或介质 Skype，运行 Setup.exe 来启动 Skype 的业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="17783-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="17783-110">单击“**准备 Active Directory**”，然后等待确定部署状态。</span><span class="sxs-lookup"><span data-stu-id="17783-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="17783-111">在“**步骤 5：准备当前域**”中，单击“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="17783-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="17783-112">在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。</span><span class="sxs-lookup"><span data-stu-id="17783-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="17783-113">在**操作**列中，展开**域准备**，查找**\<成功\>** 每项任务结束时执行结果，以验证是否已成功完成该域准备和关闭该日志中，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="17783-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="17783-114">如果您需要查看日志文件中的业务 Server 部署向导创建的 Skype，可以在其中运行步骤的 Active Directory 域服务用户的用户目录中运行部署向导的计算机上找到这些。</span><span class="sxs-lookup"><span data-stu-id="17783-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="17783-115">例如，如果用户登录以域管理员的域 Contoso.net 中，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="17783-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


