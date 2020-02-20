---
title: Lync Server 2013：委派 Lync Server 的管理控制权
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74089690a9c37a753d9dad56fd7246f9d4cb6213
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="5b347-102">委派 Lync Server 2013 的管理控制</span><span class="sxs-lookup"><span data-stu-id="5b347-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b347-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5b347-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5b347-104">在 Lync Server 2013 中，管理任务通过使用新的基于角色的访问控制（RBAC）功能委派给用户。</span><span class="sxs-lookup"><span data-stu-id="5b347-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="5b347-105">当您安装 Lync Server 时，将为您创建许多 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="5b347-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="5b347-106">这些角色对应于 Active Directory 域服务中的通用安全组。</span><span class="sxs-lookup"><span data-stu-id="5b347-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="5b347-107">例如，RBAC 角色 CsHelpDesk 对应于 Active Directory 域服务中的用户容器中找到的 CsHelpDesk 组。</span><span class="sxs-lookup"><span data-stu-id="5b347-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="5b347-108">此外，每个 RBAC 角色都与一组 Lync Server Windows PowerShell cmdlet 相关联。</span><span class="sxs-lookup"><span data-stu-id="5b347-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5b347-109">这些 cmdlet 代表已分配了给定 RBAC 角色的用户可以执行的任务。</span><span class="sxs-lookup"><span data-stu-id="5b347-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="5b347-110">例如，已为 CsHelpDesk 角色分配 Unlock-csclientpin 和 UnlockCsClientPin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b347-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="5b347-111">这意味着分配了 CsHelpDesk 角色的用户可以锁定和解锁用户 PIN 号码。</span><span class="sxs-lookup"><span data-stu-id="5b347-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="5b347-112">但是，尚未为 CsHelpDesk 角色分配 Set-csvoicepolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b347-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="5b347-113">这意味着分配了 CsHelpDesk 角色的用户不能创建新的语音策略。</span><span class="sxs-lookup"><span data-stu-id="5b347-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="5b347-114">查看有关 RBAC 角色的信息</span><span class="sxs-lookup"><span data-stu-id="5b347-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="5b347-115">您可以通过在 Lync Server 命令行管理程序中运行以下命令来检索有关 RBAC 角色的基本信息：</span><span class="sxs-lookup"><span data-stu-id="5b347-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="5b347-116">请注意，RBAC 角色的标识（例如，CsVoiceAdministrator）与 Active Directory 域服务中的用户容器中的安全组的直接映射相同。</span><span class="sxs-lookup"><span data-stu-id="5b347-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="5b347-117">若要查看已分配给角色的 cmdlet 的列表，请使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="5b347-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="5b347-118">向用户分配 RBAC 角色</span><span class="sxs-lookup"><span data-stu-id="5b347-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="5b347-119">若要向用户分配 RBAC 角色，您必须将该用户添加到相应的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="5b347-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="5b347-120">例如，若要将 CsLocationAdministrator 角色分配给用户，您必须将该用户添加到 CsLocationAdministrator 组。</span><span class="sxs-lookup"><span data-stu-id="5b347-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="5b347-121">为此，可以执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="5b347-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="5b347-122">**将用户分配给安全组**</span><span class="sxs-lookup"><span data-stu-id="5b347-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="5b347-123">使用有权修改 Active Directory 组成员身份的帐户登录到已安装 Active Directory 用户和计算机的计算机。</span><span class="sxs-lookup"><span data-stu-id="5b347-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="5b347-124">依次单击 "**开始**"、"**所有程序**"、"**管理工具**" 和 " **Active Directory 用户和计算机**"。</span><span class="sxs-lookup"><span data-stu-id="5b347-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="5b347-125">在 "Active Directory 用户和计算机" 中，展开您的域的名称，然后单击 "**用户**" 容器。</span><span class="sxs-lookup"><span data-stu-id="5b347-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="5b347-126">右键单击安全组 " **CsLocationAdministrator**"，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="5b347-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="5b347-127">在 "**属性**" 对话框中的 "**成员**" 选项卡上，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="5b347-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="5b347-128">在 "**选择用户、计算机、联系人或组**" 对话框中，在 "**输入要选择的对象名称**" 框中键入要添加到组的用户的用户名或显示名称（例如， **Ken Myer**），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5b347-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="5b347-129">在“属性”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b347-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="5b347-130">若要验证是否已分配 RBAC 角色，请使用[CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet 将 cmdlet 传递给用户的 SamAccountName （Active Directory 登录名）。</span><span class="sxs-lookup"><span data-stu-id="5b347-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="5b347-131">例如，在 Lync Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5b347-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

