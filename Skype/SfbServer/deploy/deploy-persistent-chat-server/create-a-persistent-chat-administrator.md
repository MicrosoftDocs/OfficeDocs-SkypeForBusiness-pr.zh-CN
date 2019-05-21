---
title: 在 Skype for Business Server 2015 中创建持久聊天管理员
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '摘要: 阅读本主题, 了解如何创建持久聊天服务器管理员角色, 以便在 Skype for Business Server 2015 中启用持久聊天服务的初始配置和管理。'
ms.openlocfilehash: 1b593f1de776f1896d43bab35a15af7b6bcf7245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273880"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="de20a-103">在 Skype for Business Server 2015 中创建持久聊天管理员</span><span class="sxs-lookup"><span data-stu-id="de20a-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="de20a-104">**摘要:** 阅读本主题, 了解如何创建持久聊天服务器管理员角色, 以便在 Skype for Business Server 2015 中启用持久聊天服务的初始配置和管理。</span><span class="sxs-lookup"><span data-stu-id="de20a-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="de20a-105">在 Skype for Business 服务器中, 执行特定任务的用户必须分配为一个或多个特定组的成员。</span><span class="sxs-lookup"><span data-stu-id="de20a-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="de20a-106">基于角色的访问控制 (RBAC) 用于通过将用户分配给预定义的 Skype for business 服务器管理角色来授予权限。</span><span class="sxs-lookup"><span data-stu-id="de20a-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="de20a-107">这些角色对应 Active Directory 域服务中的通用安全组。</span><span class="sxs-lookup"><span data-stu-id="de20a-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="de20a-108">永久性聊天管理员安全组的成员 CsPersistentChatAdministrator 授予访问持久聊天服务器 cmdlet 的权限, 可以使用 Skype for Business 服务器管理外壳或 Skype for business 执行此 cmdlet"服务器控制面板"。</span><span class="sxs-lookup"><span data-stu-id="de20a-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="de20a-109">在配置和管理持久聊天服务器之前，请确保已分配相应的用户权限，并将充当持久聊天管理员的任何用户添加到持久聊天管理员安全组中。</span><span class="sxs-lookup"><span data-stu-id="de20a-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="de20a-110">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="de20a-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="de20a-111">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="de20a-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="de20a-112">有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="de20a-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="de20a-113">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="de20a-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="de20a-114">Create a Persistent Chat administrator</span><span class="sxs-lookup"><span data-stu-id="de20a-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="de20a-115">若要将用户添加到持久聊天管理员安全组, 请 CsPersistentChatAdministrator, 请执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="de20a-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="de20a-116">使用具有修改 Active Directory 组成员身份权限的帐户，登录到已安装“Active Directory 用户和计算机”的计算机。</span><span class="sxs-lookup"><span data-stu-id="de20a-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="de20a-117">依次单击“开始”、“所有程序”、“管理工具”，然后单击“Active Directory 用户和计算机”。</span><span class="sxs-lookup"><span data-stu-id="de20a-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="de20a-118">在“Active Directory 用户和计算机”中，展开域名并单击“用户”容器。</span><span class="sxs-lookup"><span data-stu-id="de20a-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="de20a-119">右键单击安全组 CsPersistentChatAdministrator，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="de20a-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="de20a-120">在“属性”对话框的“成员”选项卡上，单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="de20a-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="de20a-121">在“选择用户、计算机、联系人或组”对话框的“输入要选择的对象名称”框中，键入要添加到组的用户的用户名或显示名称，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="de20a-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="de20a-122">在“属性”对话框中，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="de20a-122">In the Properties dialog box, click OK.</span></span>
    

