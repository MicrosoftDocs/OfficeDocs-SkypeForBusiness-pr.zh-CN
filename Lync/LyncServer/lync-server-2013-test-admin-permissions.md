---
title: Lync Server 2013：测试管理员权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1653f2287e06db71f6e971a0a4f483b810734f2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519379"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="02436-102">在 Lync Server 2013 中测试管理员权限</span><span class="sxs-lookup"><span data-stu-id="02436-102">Test admin permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02436-103">_**上次修改的主题：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="02436-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02436-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="02436-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="02436-105">初始 Lync Server 部署之后。</span><span class="sxs-lookup"><span data-stu-id="02436-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="02436-106">如果出现权限相关问题，则根据需要。</span><span class="sxs-lookup"><span data-stu-id="02436-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02436-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="02436-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="02436-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02436-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02436-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="02436-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="02436-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="02436-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="02436-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsOUPermission cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="02436-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="02436-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="02436-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="02436-113">说明</span><span class="sxs-lookup"><span data-stu-id="02436-113">Description</span></span>

<span data-ttu-id="02436-114">当您安装 Lync Server 2013 1 时，安装程序执行的任务将为 RTCUniversalUserAdmins 组提供管理用户、计算机、联系人、应用程序联系人和 InetOrg 人员所需的 Active Directory 权限。</span><span class="sxs-lookup"><span data-stu-id="02436-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="02436-115">如果您已在 Active Directory 安装程序中禁用权限继承，则无法分配这些权限。</span><span class="sxs-lookup"><span data-stu-id="02436-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="02436-116">因此，RTCUniversalUserAdmins 组的成员将无法管理 Lync Server 实体。</span><span class="sxs-lookup"><span data-stu-id="02436-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="02436-117">这些管理权限将仅适用于域管理员。</span><span class="sxs-lookup"><span data-stu-id="02436-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="02436-118">Test-CsOUPermission cmdlet 验证在 Active Directory 容器上是否设置了管理用户、计算机和其他对象所需的权限。</span><span class="sxs-lookup"><span data-stu-id="02436-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="02436-119">如果未设置这些权限，则可以通过运行 [CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet 来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="02436-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="02436-120">请注意，Grant-CsOUPermission 只能将权限分配给 RTCUniversalUserAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="02436-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="02436-121">不能使用此 cmdlet 向任意用户或组授予权限。</span><span class="sxs-lookup"><span data-stu-id="02436-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="02436-122">如果您希望不同的用户或组拥有用户管理权限，则应将该用户添加 (或组) 到 RTCUniversalUserAdmins 组中。</span><span class="sxs-lookup"><span data-stu-id="02436-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="02436-123">有关 OU 权限的详细信息，请参阅文章 [：在计算机、用户或 InetOrgPerson 容器上禁用了 Lync Server 2013 中的权限继承](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)。</span><span class="sxs-lookup"><span data-stu-id="02436-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="02436-124">运行测试</span><span class="sxs-lookup"><span data-stu-id="02436-124">Running the test</span></span>

<span data-ttu-id="02436-125">若要验证是否在容器上设置了管理权限，请运行 Test-CsOUPermission cmdlet，后接容器的可分辨名称和要验证的权限类型。</span><span class="sxs-lookup"><span data-stu-id="02436-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="02436-126">例如，以下命令将检查是否在 OU ou = Redmond，dc = litwareinc，dc = com 上设置了用户权限：</span><span class="sxs-lookup"><span data-stu-id="02436-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="02436-127">若要使用单个命令验证多个权限，请将每个权限类型括在引号中，然后使用逗号分隔这些类型。</span><span class="sxs-lookup"><span data-stu-id="02436-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="02436-128">例如，下面的一个命令验证用户、计算机和联系人权限：</span><span class="sxs-lookup"><span data-stu-id="02436-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="02436-129">有关详细信息，请参阅 [CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="02436-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="02436-130">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="02436-130">Determining success or failure</span></span>

<span data-ttu-id="02436-131">如果已设置所需的权限，则 Test-CsOUPermission 将返回一个单字响应：</span><span class="sxs-lookup"><span data-stu-id="02436-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="02436-132">True</span><span class="sxs-lookup"><span data-stu-id="02436-132">True</span></span>

<span data-ttu-id="02436-133">如果未设置所需的权限，则 Test-CsOUPermission 将返回值 False。</span><span class="sxs-lookup"><span data-stu-id="02436-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="02436-134">您可能需要搜索一段时间才能找到此值。</span><span class="sxs-lookup"><span data-stu-id="02436-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="02436-135">它通常嵌入到多个伴随的警告中。</span><span class="sxs-lookup"><span data-stu-id="02436-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="02436-136">例如：</span><span class="sxs-lookup"><span data-stu-id="02436-136">For example:</span></span>

<span data-ttu-id="02436-137">警告： access control entry (ACE) atl-001 \\ RTCUniversalUserReadOnlyGroup; allow;ReadPropertyContainerInherit;其子bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="02436-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="02436-138">警告：对象 "OU = 北美，DC = litwareinc，dc = com" 上的 (Ace) 的访问控制项 \\ 未准备就绪。</span><span class="sxs-lookup"><span data-stu-id="02436-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="02436-139">False</span><span class="sxs-lookup"><span data-stu-id="02436-139">False</span></span>

<span data-ttu-id="02436-140">警告： "Test-CsOUPermission" 处理已完成，但出现警告。</span><span class="sxs-lookup"><span data-stu-id="02436-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="02436-141">在此运行过程中记录了 "2" 警告。</span><span class="sxs-lookup"><span data-stu-id="02436-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="02436-142">警告：可以在 "C： \\ Users \\ Admin \\ AppData \\ Local \\ Temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" 处找到详细结果。</span><span class="sxs-lookup"><span data-stu-id="02436-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="02436-143">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="02436-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="02436-144">如果 Test-CsOUPermission 失败，则通常意味着指定的权限尚未分配给 RTCUniversalUserAdmins 组。</span><span class="sxs-lookup"><span data-stu-id="02436-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="02436-145">您可以使用 Grant-CsOUPermission cmdlet 来解决此问题，并分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="02436-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="02436-146">例如，以下命令将用户、联系人和 inetOrgPersons 的 OU 权限提供给 RTCUniversalUserAdmins 组：</span><span class="sxs-lookup"><span data-stu-id="02436-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="02436-147">有关详细信息，请参阅 Grant-CsOUPermission cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="02436-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

