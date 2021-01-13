---
title: 委派 Skype for Business Server 的管理控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832792"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="f2e9f-102">委派 Skype for Business Server 的管理控制</span><span class="sxs-lookup"><span data-stu-id="f2e9f-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="f2e9f-103">在 Skype for Business Server 中，通过使用基于角色的访问控制和 RBAC (功能，) 任务。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="f2e9f-104">安装 Skype for Business Server 时，会创建多个 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="f2e9f-105">这些角色对应于 Active Directory 域服务中的通用安全组。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="f2e9f-106">例如，RBAC 角色 CsHelpDesk 对应于在 Active Directory 域服务的用户容器中找到的 CsHelpDesk 组。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="f2e9f-107">此外，每个 RBAC 角色都与一组 Skype for Business Server Windows PowerShell cmdlet 相关联。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="f2e9f-108">这些 cmdlet 表示已分配有给定 RBAC 角色的用户可以执行的任务。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="f2e9f-109">例如，CsHelpDesk 角色已分配有 Lock-CsClientPin 和 UnlockCsClientPin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="f2e9f-110">这意味着分配了 CsHelpDesk 角色的用户可以锁定和解锁用户 PIN 号码。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="f2e9f-111">但是，尚未向 CsHelpDesk 角色分配 New-CsVoicePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="f2e9f-112">这意味着分配了 CsHelpDesk 角色的用户无法创建新的语音策略。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="f2e9f-113">查看有关 RBAC 角色的信息</span><span class="sxs-lookup"><span data-stu-id="f2e9f-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="f2e9f-114">可以通过在 Skype for Business Server 命令行管理程序 中运行以下命令来检索有关 RBAC 角色的基本信息：</span><span class="sxs-lookup"><span data-stu-id="f2e9f-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="f2e9f-115">请记住，RBAC 角色 (例如，CsVoiceAdministrator) 的 Identity 具有到 Active Directory 域服务中的 Users 容器中找到的安全组的直接映射。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="f2e9f-116">若要查看已分配给角色的 cmdlet 的列表，请使用以下类似命令：</span><span class="sxs-lookup"><span data-stu-id="f2e9f-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="f2e9f-117">向用户分配 RBAC 角色</span><span class="sxs-lookup"><span data-stu-id="f2e9f-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="f2e9f-118">若要向用户分配 RBAC 角色，必须将该用户添加到相应的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="f2e9f-119">例如，若要将 CsLocationAdministrator 角色分配给用户，必须将该用户添加到 CsLocationAdministrator 组。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="f2e9f-120">这可以通过执行以下过程完成：</span><span class="sxs-lookup"><span data-stu-id="f2e9f-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="f2e9f-121">使用有权修改 Active Directory 组成员身份的帐户登录到安装了 Active Directory 用户和计算机的计算机。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="f2e9f-122">单击 **"** 开始"，**单击**"所有程序"，**再单击**"管理工具"，然后单击 **"Active Directory 用户和计算机"。**</span><span class="sxs-lookup"><span data-stu-id="f2e9f-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="f2e9f-123">在"Active Directory 用户和计算机"中，展开域的名称，然后单击" **用户"** 容器。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="f2e9f-124">右键单击安全组 **CsLocationAdministrator，** 然后单击"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="f2e9f-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="f2e9f-125">在"**属性**"对话框中的"成员 **"选项卡** 上，单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="f2e9f-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="f2e9f-126">在"选择用户、计算机、联系人或组"对话框中，键入要添加到组 (的用户的用户名或 显示名称，例如，在"输入要选择的对象名称"框中键入 Ken Myer) ，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="f2e9f-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="f2e9f-127">在“属性”对话框中，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="f2e9f-128">若要验证已分配 RBAC 角色，请使用 Get-CsAdminRoleAssignment cmdlet，向该 cmdlet 传递用户的 SamAccountName (Active Directory) 名称。</span><span class="sxs-lookup"><span data-stu-id="f2e9f-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="f2e9f-129">例如，从 Skype for Business Server 命令行管理程序 中运行此命令：</span><span class="sxs-lookup"><span data-stu-id="f2e9f-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
