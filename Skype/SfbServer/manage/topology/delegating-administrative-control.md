---
title: Skype 的管理控制权限委派业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 64d1b33c7ee41c028d3af7454a131f67de2c9146
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214699"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="e3e07-102">Skype 的管理控制权限委派业务服务器</span><span class="sxs-lookup"><span data-stu-id="e3e07-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="e3e07-103">在业务服务器 Skype，管理任务将委派给用户通过使用基于角色的访问控制 (RBAC) 功能。</span><span class="sxs-lookup"><span data-stu-id="e3e07-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="e3e07-104">业务服务器安装 Skype 时，将为您创建多个 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e3e07-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="e3e07-105">这些角色对应 Active Directory 域服务中的通用安全组。</span><span class="sxs-lookup"><span data-stu-id="e3e07-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="e3e07-106">例如，RBAC 角色 CsHelpDesk 对应于 Active Directory 域服务中的用户容器中找到的 CsHelpDesk 组。</span><span class="sxs-lookup"><span data-stu-id="e3e07-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="e3e07-107">此外，每个 RBAC 角色相关联的 Skype 一组业务 Server Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e3e07-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e3e07-108">这些 cmdlet 表示由已分配的给定的 RBAC 角色的用户可以执行的任务。</span><span class="sxs-lookup"><span data-stu-id="e3e07-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="e3e07-109">例如，已分配 CsHelpDesk 角色 Lock-csclientpin 和 UnlockCsClientPin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e3e07-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="e3e07-110">这意味着已分配 CsHelpDesk 角色的用户可以锁定和解除锁定用户 PIN 号码。</span><span class="sxs-lookup"><span data-stu-id="e3e07-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="e3e07-111">但是，CsHelpDesk 角色尚未分配 New-csvoicepolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e3e07-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="e3e07-112">这意味着已分配 CsHelpDesk 角色的用户无法创建新的语音策略。</span><span class="sxs-lookup"><span data-stu-id="e3e07-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="e3e07-113">查看有关 RBAC 角色的信息</span><span class="sxs-lookup"><span data-stu-id="e3e07-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="e3e07-114">可以通过为业务 Server Management Shell 中运行以下命令从 Skype 中的检索有关 RBAC 角色的基本信息：</span><span class="sxs-lookup"><span data-stu-id="e3e07-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="e3e07-115">请记住，RBAC 角色 (例如，CsVoiceAdministrator) 的标识直接映射到 Active Directory 域服务中的用户容器中找到的安全组。</span><span class="sxs-lookup"><span data-stu-id="e3e07-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="e3e07-116">若要查看已分配给某个角色的 cmdlet 的列表，请使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="e3e07-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="e3e07-117">将 RBAC 角色分配给用户</span><span class="sxs-lookup"><span data-stu-id="e3e07-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="e3e07-118">若要 RBAC 角色分配给用户，必须将该用户添加到相应的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="e3e07-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="e3e07-119">例如，若要将 CsLocationAdministrator 角色分配给用户，必须将该用户添加到 CsLocationAdministrator 组中。</span><span class="sxs-lookup"><span data-stu-id="e3e07-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="e3e07-120">可通过执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="e3e07-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="e3e07-121">使用 Active Directory 用户和计算机已安装的帐户有权修改的 Active Directory 组的成员身份，登录到计算机上。</span><span class="sxs-lookup"><span data-stu-id="e3e07-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="e3e07-122">单击**开始**，单击**所有程序**，都单击**管理工具**，然后都单击**Active Directory 用户和计算机**。</span><span class="sxs-lookup"><span data-stu-id="e3e07-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="e3e07-123">在 Active Directory 用户和计算机，展开您的域的名称，然后单击**用户**容器。</span><span class="sxs-lookup"><span data-stu-id="e3e07-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="e3e07-124">右键单击安全组**CsLocationAdministrator**，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="e3e07-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="e3e07-125">在**属性**对话框中，在**成员**选项卡上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="e3e07-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="e3e07-126">在**选择用户、 计算机、 联系人或组**对话框中，键入用户名或要添加到组 (例如，Ken Myer) 中的**输入要选择的对象名称**框中，用户的显示名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e3e07-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="e3e07-127">在**属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e3e07-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="e3e07-128">若要验证已分配的 RBAC 角色，使用 Get-csadminroleassignment cmdlet，传递此 cmdlet 的用户的 SamAccountName （Active Directory 登录名）。</span><span class="sxs-lookup"><span data-stu-id="e3e07-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="e3e07-129">例如，运行 Business Server 命令行管理程序中 Skype 此命令：</span><span class="sxs-lookup"><span data-stu-id="e3e07-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
