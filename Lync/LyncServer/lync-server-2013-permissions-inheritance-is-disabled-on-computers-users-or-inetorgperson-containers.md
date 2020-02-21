---
title: Lync Server 2013：权限继承在计算机、用户或 InetOrgPerson 容器上被禁用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6f0ac6b7614da844a35f97070b61f1b074a4367
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="f585d-102">在 Lync Server 2013 中的计算机、用户或 InetOrgPerson 容器上禁用权限继承</span><span class="sxs-lookup"><span data-stu-id="f585d-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f585d-103">_**上次修改的主题：** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="f585d-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="f585d-104">在锁定的 Active Directory 域服务中，用户和计算机对象通常放在特定的组织单位（Ou）中，并禁用权限继承，以帮助保护管理委派和启用组策略对象（Gpo）的使用强制实施安全策略。</span><span class="sxs-lookup"><span data-stu-id="f585d-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="f585d-105">域准备和服务器激活设置 Lync Server 2013 所需的访问控制项（Ace）。</span><span class="sxs-lookup"><span data-stu-id="f585d-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="f585d-106">禁用权限继承后，Lync Server 安全组将无法继承这些 Ace。</span><span class="sxs-lookup"><span data-stu-id="f585d-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="f585d-107">如果不继承这些权限，Lync Server 安全组将无法访问设置，并且会出现以下两个问题：</span><span class="sxs-lookup"><span data-stu-id="f585d-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="f585d-108">若要管理用户、InetOrgPersons 和联系人以及操作服务器，Lync Server 安全组需要对每个用户的属性集、实时通信（RTC）、RTC 用户搜索和公共信息进行域准备过程设置的 Ace.</span><span class="sxs-lookup"><span data-stu-id="f585d-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="f585d-109">如果禁用了权限继承，安全组就不会继承这些 ACE，因此无法管理服务器或用户。</span><span class="sxs-lookup"><span data-stu-id="f585d-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="f585d-110">若要发现服务器和池，运行 Lync Server 的服务器依赖于在与计算机相关的对象（包括 Microsoft 容器和服务器对象）上激活时设置的 Ace。</span><span class="sxs-lookup"><span data-stu-id="f585d-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="f585d-111">如果禁用了权限继承，安全组、服务器和池将不会继承这些 ACE，因而也无法利用这些 ACE。</span><span class="sxs-lookup"><span data-stu-id="f585d-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="f585d-112">为解决这些问题，Lync Server 提供了**CsOuPermission** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f585d-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="f585d-113">此 cmdlet 直接在指定的容器和组织单位以及容器或组织单位中的对象上设置所需的 Lync Server Ace。</span><span class="sxs-lookup"><span data-stu-id="f585d-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="f585d-114">在运行域准备之后为用户、InetOrgPerson 和联系人对象设置权限</span><span class="sxs-lookup"><span data-stu-id="f585d-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="f585d-115">在禁用了权限继承的锁定的 Active Directory 环境中，域准备无法对容纳域中用户或 InetOrgPerson 对象的容器或组织单位设置必要的 ACE。</span><span class="sxs-lookup"><span data-stu-id="f585d-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="f585d-116">在这种情况下，必须对禁用了其权限继承的容纳用户或 InetOrgPerson 对象的每个容器或 OU 运行 **Grant-CsOuPermission** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f585d-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="f585d-117">如果拥有中央林拓扑，则还必须对容纳联系人对象的容器或 OU 执行此过程。</span><span class="sxs-lookup"><span data-stu-id="f585d-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="f585d-118">有关中央林拓扑的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的受支持的 Active Directory 拓扑](lync-server-2013-supported-active-directory-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="f585d-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="f585d-119">ObjectType 参数指定对象类型。</span><span class="sxs-lookup"><span data-stu-id="f585d-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="f585d-120">OU 参数指定组织单位。</span><span class="sxs-lookup"><span data-stu-id="f585d-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="f585d-121">此 cmdlet 会在指定的容器或 OU 上以及该容器内的用户或 InetOrgPerson 对象上直接添加所需的 ACE。</span><span class="sxs-lookup"><span data-stu-id="f585d-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="f585d-122">如果执行此命令的 OU 具有包含 User 或 InetOrgPerson 对象的子 Ou，则不会对这些对象应用这些权限。</span><span class="sxs-lookup"><span data-stu-id="f585d-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="f585d-123">您需要分别在每个子 OU 上运行此命令。</span><span class="sxs-lookup"><span data-stu-id="f585d-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="f585d-124">这是 Lync 托管部署的常见方案，例如父 OU = OCS 租户、DC = CONTOSO、DC = 本地和子 OU = Tenant1、OU = OCS 租户、DC = CONTOSO、DC = LOCAL。</span><span class="sxs-lookup"><span data-stu-id="f585d-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="f585d-125">您需要与 Domain Admins 组成员身份等效的用户权限来运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f585d-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="f585d-126">如果已在锁定环境中删除经过身份验证的用户 Ace，则必须在林根域的相关容器或 Ou 中授予此帐户读取访问 Ace，如在[Lync Server 2013 中删除了已验证用户权限](lync-server-2013-authenticated-user-permissions-are-removed.md)中所述，或使用的帐户是 Enterprise Admins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="f585d-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="f585d-127">**为用户、InetOrgPerson 和联系人对象设置所需的 ACE**</span><span class="sxs-lookup"><span data-stu-id="f585d-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="f585d-128">以 Domain Admins 组成员的帐户或具有同等用户权限的帐户登录到加入域的计算机。</span><span class="sxs-lookup"><span data-stu-id="f585d-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="f585d-129">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f585d-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f585d-130">以</span><span class="sxs-lookup"><span data-stu-id="f585d-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="f585d-131">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="f585d-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="f585d-132">例如：</span><span class="sxs-lookup"><span data-stu-id="f585d-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="f585d-133">在日志文件中，在每个任务的末尾查找 " \*\* \<成功\> \*\*执行" 结果以验证是否设置了权限，然后关闭 "日志" 窗口。</span><span class="sxs-lookup"><span data-stu-id="f585d-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="f585d-134">或者，可以运行以下命令确定是否设置了权限：</span><span class="sxs-lookup"><span data-stu-id="f585d-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="f585d-135">例如：</span><span class="sxs-lookup"><span data-stu-id="f585d-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="f585d-136">在运行域准备之后为计算机对象设置权限</span><span class="sxs-lookup"><span data-stu-id="f585d-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="f585d-137">在禁用了权限继承的锁定的 Active Directory 环境中，域准备无法对容纳域中计算机对象的容器或 OU 设置必要的 ACE。</span><span class="sxs-lookup"><span data-stu-id="f585d-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="f585d-138">在这种情况下，您必须在运行了禁用了权限继承的运行 Lync Server 的计算机的每个容器或 OU 上运行**CsOuPermission** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f585d-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="f585d-139">ObjectType 参数指定对象类型。</span><span class="sxs-lookup"><span data-stu-id="f585d-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="f585d-140">此过程将在指定的容器上直接添加所需的 ACE。</span><span class="sxs-lookup"><span data-stu-id="f585d-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="f585d-141">您需要与 Domain Admins 组成员身份等效的用户权限来运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f585d-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="f585d-142">如果已删除经过身份验证的用户 Ace，则必须在林根域的相关容器上授予此帐户读取访问 Ace，如在[Lync Server 2013 中删除了已验证用户权限](lync-server-2013-authenticated-user-permissions-are-removed.md)中所述，或使用的帐户是 Enterprise Admins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="f585d-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="f585d-143">**为计算机对象设置所需的 ACE**</span><span class="sxs-lookup"><span data-stu-id="f585d-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="f585d-144">以 Domain Admins 组成员的帐户或具有同等用户权限的帐户登录到域计算机。</span><span class="sxs-lookup"><span data-stu-id="f585d-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="f585d-145">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f585d-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f585d-146">以</span><span class="sxs-lookup"><span data-stu-id="f585d-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="f585d-147">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="f585d-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="f585d-148">例如：</span><span class="sxs-lookup"><span data-stu-id="f585d-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="f585d-149">在示例日志文件 C：\\log\\OUPermissions 中，您将在每个任务的结尾处查找\*\* \<成功\> \*\*执行结果，并验证没有任何错误，然后关闭该日志。</span><span class="sxs-lookup"><span data-stu-id="f585d-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="f585d-150">您可以运行以下 cmdlet 来测试权限：</span><span class="sxs-lookup"><span data-stu-id="f585d-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="f585d-151">例如：</span><span class="sxs-lookup"><span data-stu-id="f585d-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f585d-152">如果在锁定的 Active Directory 环境中对林根域运行域准备，请注意，Lync Server 需要访问 Active Directory 架构和配置容器。</span><span class="sxs-lookup"><span data-stu-id="f585d-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="f585d-153">如果从 AD&nbsp;DS 中的架构或配置容器中删除了默认的经过身份验证的用户权限，则仅允许架构管理员组（针对架构容器）或 Enterprise admins 组（对于配置容器）的成员访问给定容器。</span><span class="sxs-lookup"><span data-stu-id="f585d-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="f585d-154">由于 setup.exe、Lync Server 命令行管理程序 cmdlet 和 Lync Server 控制面板需要访问这些容器，因此，除非运行安装的用户具有与架构等效的用户权限，否则管理工具的安装将会失败。管理员和企业管理员组成员身份。</span><span class="sxs-lookup"><span data-stu-id="f585d-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="f585d-155">要解决此问题，必须向 RTCUniversalGlobalWriteGroup 组授予对“架构”和“配置”容器的读取和写入访问权限。</span><span class="sxs-lookup"><span data-stu-id="f585d-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

