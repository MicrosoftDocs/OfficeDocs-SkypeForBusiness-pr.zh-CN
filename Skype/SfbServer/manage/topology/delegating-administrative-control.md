---
title: 委派 Skype for Business 服务器的管理控制权
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 5c295ed1233cb8a0900828cb1d1c074de1d0f16f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817268"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="d9ca1-102">委派 Skype for Business 服务器的管理控制权</span><span class="sxs-lookup"><span data-stu-id="d9ca1-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="d9ca1-103">在 Skype for Business 服务器中，使用基于角色的访问控制（RBAC）功能将管理任务委派给用户。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="d9ca1-104">安装 Skype for Business 服务器时，将为你创建许多 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="d9ca1-105">这些角色对应 Active Directory 域服务中的通用安全组。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="d9ca1-106">例如，RBAC 角色 CsHelpDesk 对应于 Active Directory 域服务中的用户容器内找到的 CsHelpDesk 组。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="d9ca1-107">此外，每个 RBAC 角色都与一组 Skype for Business 服务器 Windows PowerShell cmdlet 相关联。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d9ca1-108">这些 cmdlet 表示分配了给定的 RBAC 角色的用户可以执行的任务。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="d9ca1-109">例如，已向 CsHelpDesk 角色分配了 Lock CsClientPin 和 UnlockCsClientPin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="d9ca1-110">这意味着分配了 CsHelpDesk 角色的用户可以锁定和解锁用户 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="d9ca1-111">但是，尚未向 CsHelpDesk 角色分配 CsVoicePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="d9ca1-112">这意味着分配了 CsHelpDesk 角色的用户无法创建新的语音策略。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="d9ca1-113">查看有关 RBAC 角色的信息</span><span class="sxs-lookup"><span data-stu-id="d9ca1-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="d9ca1-114">通过在 Skype for Business Server Management Shell 中运行以下命令，你可以检索有关你的 RBAC 角色的基本信息：</span><span class="sxs-lookup"><span data-stu-id="d9ca1-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="d9ca1-115">请记住，RBAC 角色的标识（例如，CsVoiceAdministrator）与 Active Directory 域服务中的用户容器中找到的安全组有直接映射。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="d9ca1-116">若要查看已分配给某个角色的 cmdlet 的列表，请使用类似下面的命令：</span><span class="sxs-lookup"><span data-stu-id="d9ca1-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="d9ca1-117">向用户分配 RBAC 角色</span><span class="sxs-lookup"><span data-stu-id="d9ca1-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="d9ca1-118">若要向用户分配 RBAC 角色，必须将该用户添加到相应的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="d9ca1-119">例如，若要将 CsLocationAdministrator 角色分配给用户，必须将该用户添加到 CsLocationAdministrator 组。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="d9ca1-120">可通过执行以下过程来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="d9ca1-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="d9ca1-121">使用有权修改 Active Directory 组成员身份的帐户，登录到已安装 Active Directory 用户和计算机的计算机。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="d9ca1-122">单击 "**开始**"，单击 "**所有程序**"，单击 "**管理工具**"，然后单击 " **Active Directory 用户和计算机**"。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="d9ca1-123">在 "Active Directory 用户和计算机" 中，展开您的域的名称，然后单击 "**用户**" 容器。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="d9ca1-124">右键单击安全组 " **CsLocationAdministrator**"，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="d9ca1-125">在 "**属性**" 对话框中的 "**成员**" 选项卡上，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="d9ca1-126">在 "**选择用户、计算机、联系人或组**" 对话框中，在 "**输入要选择的对象名称**" 框中键入要添加到组的用户的用户名或显示名称（例如 Ken Myer），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="d9ca1-127">在 "**属性**" 对话框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="d9ca1-128">若要验证 RBAC 角色是否已分配，请使用 CsAdminRoleAssignment cmdlet 将 cmdlet 传递给用户的 SamAccountName （Active Directory 登录名称）。</span><span class="sxs-lookup"><span data-stu-id="d9ca1-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="d9ca1-129">例如，在 Skype for Business Server Management Shell 中运行此命令：</span><span class="sxs-lookup"><span data-stu-id="d9ca1-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
