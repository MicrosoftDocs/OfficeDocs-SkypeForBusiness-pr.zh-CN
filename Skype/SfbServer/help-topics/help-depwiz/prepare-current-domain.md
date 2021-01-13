---
title: 准备当前域
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
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 若要准备域以托管运行 Skype for Business Server 2015 或 Skype for Business Server 用户的服务器，必须完成步骤 5：准备当前域，如使用安装程序运行域准备主题中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 要准备域，请执行以下操作：
ms.openlocfilehash: b43af552983a5a7aae998fab6de9ace4e96084b2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804959"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="6ec74-105">准备当前域</span><span class="sxs-lookup"><span data-stu-id="6ec74-105">Prepare Current Domain</span></span>

<span data-ttu-id="6ec74-106">若要准备域以托管运行 Skype for Business Server 2015 或 Skype for Business Server 用户的服务器，必须完成步骤 **5：准备当前域**，如使用安装程序运行域准备的主题 [中所述。](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)</span><span class="sxs-lookup"><span data-stu-id="6ec74-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="6ec74-107">要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="6ec74-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="6ec74-108">要准备域，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6ec74-108">To prepare the domain:</span></span>

1. <span data-ttu-id="6ec74-109">从 Skype for Business Server 2015 安装文件夹或媒体中，Setup.exe启动 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="6ec74-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="6ec74-110">单击“准备 Active Directory”，然后等待确定部署状态。</span><span class="sxs-lookup"><span data-stu-id="6ec74-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="6ec74-111">在“步骤 5: 准备当前域”中，单击“运行”。</span><span class="sxs-lookup"><span data-stu-id="6ec74-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="6ec74-112">在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。</span><span class="sxs-lookup"><span data-stu-id="6ec74-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="6ec74-113">在"**操作**"列下，展开"域准备"，在每项任务结束时查找执行结果以验证域准备是否成功完成， **\<Success\>** 关闭日志，然后单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="6ec74-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="6ec74-114">如果需要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，这些日志文件位于运行该步骤的 Active Directory 域服务用户的 Users 目录中。</span><span class="sxs-lookup"><span data-stu-id="6ec74-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="6ec74-115">例如，如果用户以域 Contoso.net 的域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="6ec74-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


