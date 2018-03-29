---
title: 在 Skype for Business Server 2015 中创建持久聊天管理员
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 摘要： 阅读本主题，以了解如何创建启用初始配置和管理的持久聊天服务 Skype 业务服务器 2015年的持久聊天服务器管理员角色。
ms.openlocfilehash: 4efe5dff2821784a24f51712b8a19dad83e47c3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="a6530-103">在 Skype for Business Server 2015 中创建持久聊天管理员</span><span class="sxs-lookup"><span data-stu-id="a6530-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a6530-104">**摘要：**阅读本主题，以了解如何创建启用初始配置和管理的持久聊天服务 Skype 业务服务器 2015年的持久聊天服务器管理员角色。</span><span class="sxs-lookup"><span data-stu-id="a6530-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a6530-105">在 Skype 业务服务器，必须为一个或多个特定组的成员分配用户执行特定任务。</span><span class="sxs-lookup"><span data-stu-id="a6530-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="a6530-106">使用基于角色的访问控制 (RBAC) 是通过将用户分配到预定义的 Skype 业务服务器管理角色授予的权限。</span><span class="sxs-lookup"><span data-stu-id="a6530-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="a6530-107">这些角色对应 Active Directory 域服务中的通用安全组。</span><span class="sxs-lookup"><span data-stu-id="a6530-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="a6530-108">持续聊天管理员安全组，CsPersistentChatAdministrator 的成员会被授予访问持久聊天服务器的 cmdlet，可以为企业使用的业务服务器管理外壳 Skype 或 Skype 执行服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="a6530-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="a6530-109">在配置和管理持久聊天服务器之前，请确保已分配相应的用户权限，并将充当持久聊天管理员的任何用户添加到持久聊天管理员安全组中。</span><span class="sxs-lookup"><span data-stu-id="a6530-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="a6530-110">创建持久聊天管理员</span><span class="sxs-lookup"><span data-stu-id="a6530-110">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="a6530-111">若要将用户添加到的持续聊天管理员安全组中，CsPersistentChatAdministrator，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a6530-111">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="a6530-112">使用具有修改 Active Directory 组成员身份权限的帐户，登录到已安装“Active Directory 用户和计算机”的计算机。</span><span class="sxs-lookup"><span data-stu-id="a6530-112">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="a6530-113">依次单击“开始”、“所有程序”、“管理工具”，然后单击“Active Directory 用户和计算机”。</span><span class="sxs-lookup"><span data-stu-id="a6530-113">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="a6530-114">在“Active Directory 用户和计算机”中，展开域名并单击“用户”容器。</span><span class="sxs-lookup"><span data-stu-id="a6530-114">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="a6530-115">右键单击安全组 CsPersistentChatAdministrator，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="a6530-115">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="a6530-116">在“属性”对话框的“成员”选项卡上，单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="a6530-116">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="a6530-117">在“选择用户、计算机、联系人或组”对话框的“输入要选择的对象名称”框中，键入要添加到组的用户的用户名或显示名称，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="a6530-117">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="a6530-118">在“属性”对话框中，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="a6530-118">In the Properties dialog box, click OK.</span></span>
    

