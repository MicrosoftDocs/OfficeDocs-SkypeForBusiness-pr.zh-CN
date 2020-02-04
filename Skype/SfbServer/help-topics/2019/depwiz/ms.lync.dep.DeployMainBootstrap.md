---
title: 安装或删除 Skype for Business Server 组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 若要安装和激活、停用或卸载 Skype for Business 服务器组件，请使用步骤2：设置或删除 Skype 服务器组件。 你必须以你正在安装或修改的计算机上的本地管理员身份登录，并且必须能够读取当前域中的 Active Directory 域服务用户和组。 要开始，请单击“运行”。 执行此操作时，会读取基于中央管理存储的拓扑定义。 需要根据中央管理存储中定义的角色来安装和配置必需的软件组件。 安装完成后，请检查摘要，然后单击“完成”。
ms.openlocfilehash: a02c1aa99de32e42fd7d8352efc561b557ab91bc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705427"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="71eb3-108">安装或删除 Skype for Business Server 组件</span><span class="sxs-lookup"><span data-stu-id="71eb3-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="71eb3-109">若要安装和激活、停用或卸载 Skype for Business 服务器组件，请使用**步骤2：设置或删除 Skype 服务器组件**。</span><span class="sxs-lookup"><span data-stu-id="71eb3-109">To install and activate, or deactivate or uninstall Skype for Business Server components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="71eb3-110">你必须以你正在安装或修改的计算机上的本地管理员身份登录，并且必须能够读取当前域中的 Active Directory 域服务用户和组。</span><span class="sxs-lookup"><span data-stu-id="71eb3-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="71eb3-111">要开始，请单击“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="71eb3-111">To begin, click **Run**.</span></span> <span data-ttu-id="71eb3-112">执行此操作时，会读取基于中央管理存储的拓扑定义。</span><span class="sxs-lookup"><span data-stu-id="71eb3-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="71eb3-113">需要根据中央管理存储中定义的角色来安装和配置必需的软件组件。</span><span class="sxs-lookup"><span data-stu-id="71eb3-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="71eb3-114">安装完成后，请检查摘要，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="71eb3-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="71eb3-115">如果需要查看由部署向导创建的日志文件，可以在运行部署向导的计算机上的 "用户" 目录中找到这些文件，这些文件是在运行该步骤的 Active Directory 用户的用户目录中。</span><span class="sxs-lookup"><span data-stu-id="71eb3-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="71eb3-116">例如，如果用户在域 Contoso.net 中以域管理员身份登录，则日志文件位于： > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="71eb3-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="71eb3-117">如果之前已在此计算机上安装了 Skype for business 服务器组件，则部署向导将识别此问题，并且步骤2中的按钮将再次显示为 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="71eb3-117">If you have previously installed Skype for Business Server components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="71eb3-118">这样，您就可以根据需要多次运行此步骤，以正确配置或修改服务器。</span><span class="sxs-lookup"><span data-stu-id="71eb3-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

