---
title: 创建 Skype for Business Server 控制面板管理员
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 向 Skype 授予访问权限的业务服务器 2015年，执行以下操作：
ms.openlocfilehash: 5d01066da5be34ba53f4eca37d35a3913d07142a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201337"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="9e5c5-103">创建 Skype for Business Server 控制面板管理员</span><span class="sxs-lookup"><span data-stu-id="9e5c5-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="9e5c5-104">向 Skype 授予访问权限的业务服务器 2015年，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e5c5-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="9e5c5-105">以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="9e5c5-106">打开“**Active Directory 用户和计算机**”，展开域，并右键单击“**用户**”容器，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="9e5c5-107">在“**CSAdministrator 属性**”中，单击“**成员**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="9e5c5-p101">在“成员”选项卡上，单击“**添加**”。在“**选择用户、联系人、计算机、服务帐户或组**”中，找到“**输入要选择的对象名称**”。键入要添加到 CSAdministrators 组的用户名或组名。单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="9e5c5-p102">在“成员”选项卡上，确认所选的用户或组存在。单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="9e5c5-114">为业务 Server Control Panel Skype 是一个基于角色的访问控制工具。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="9e5c5-115">CsAdministrator 组的成员提供的业务 Server Control Panel 完全控制的所有可用的配置函数使用 Skype 的用户。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="9e5c5-116">还有其他为特定功能设计的专门角色可用。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="9e5c5-117">用户没有要启用 Skype 业务服务器才能成为管理组的成员。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="9e5c5-118">其他角色包括：</span><span class="sxs-lookup"><span data-stu-id="9e5c5-118">Other roles include:</span></span>
  
- <span data-ttu-id="9e5c5-119">**CsArchiving:** 此组的成员可以执行所有存档功能，如配置和管理存档服务器角色。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="9e5c5-p104">**CsHelpDesk：** 该组的成员可以查看配置和部署，包括用户属性和策略。成员还可以执行特定的故障排除任务。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="9e5c5-p105">**CsLocationAdministrator：** 成员具有与管理增强型 9-1-1 (E9-1-1) 相关的最低用户权限。他们可以在部署中创建 E9-1-1 位置和网络标识符并关联它们。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="9e5c5-124">**CsResponseGroupAdministrator：** 成员可以管理和配置响应组服务。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="9e5c5-125">**CsServerAdministrator:** 成员可以管理、 监视和解决业务服务器运行 Skype 的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="9e5c5-126">**CsUserAdministrator：** 成员可以管理、启用和禁用用户，以及将现有策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="9e5c5-127">**CsViewOnlyAdministrator:** 成员可以查看部署和配置服务器信息。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="9e5c5-128">此成员资格使成员 to monitor the health 的业务服务器 2015年运行 Skype 的服务器。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="9e5c5-129">**CsVoiceAdministrator:** 成员可以创建、 配置和管理 Skype 中的业务服务器的语音相关的设置。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="9e5c5-130">若要帮助保留安全性和基于角色的访问控制完整性，请将用户添加到定义了用户执行的业务服务器部署 Skype 的管理角色组。</span><span class="sxs-lookup"><span data-stu-id="9e5c5-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

