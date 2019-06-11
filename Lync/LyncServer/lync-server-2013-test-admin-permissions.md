---
title: 'Lync Server 2013: 测试管理员权限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da940b30822a5cfcc1fed302ff3db1f34bd8380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="281b5-102">在 Lync Server 2013 中测试管理员权限</span><span class="sxs-lookup"><span data-stu-id="281b5-102">Test admin permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="281b5-103">_**主题上次修改时间:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="281b5-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="281b5-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="281b5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="281b5-105">初始 Lync Server 部署后。</span><span class="sxs-lookup"><span data-stu-id="281b5-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="281b5-106">如果出现权限相关问题, 则根据需要。</span><span class="sxs-lookup"><span data-stu-id="281b5-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="281b5-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="281b5-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="281b5-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="281b5-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="281b5-109">需要权限</span><span class="sxs-lookup"><span data-stu-id="281b5-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="281b5-110">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="281b5-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="281b5-111">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsOUPermission cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="281b5-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="281b5-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="281b5-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="281b5-113">说明</span><span class="sxs-lookup"><span data-stu-id="281b5-113">Description</span></span>

<span data-ttu-id="281b5-114">当您安装 Lync Server 2013 1 时, 安装程序执行的任务将为 RTCUniversalUserAdmins 组提供管理用户、计算机、联系人、应用程序联系人和 InetOrg 人员所需的 Active Directory 权限。</span><span class="sxs-lookup"><span data-stu-id="281b5-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="281b5-115">如果您已在 Active Directory 安装程序中禁用权限继承, 则不能分配这些权限。</span><span class="sxs-lookup"><span data-stu-id="281b5-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="281b5-116">因此, RTCUniversalUserAdmins 组的成员将无法管理 Lync Server 实体。</span><span class="sxs-lookup"><span data-stu-id="281b5-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="281b5-117">这些管理权限将仅可供域管理员使用。</span><span class="sxs-lookup"><span data-stu-id="281b5-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="281b5-118">CsOUPermission cmdlet 验证管理用户、计算机和其他对象所需的权限是否在 Active Directory 容器上设置。</span><span class="sxs-lookup"><span data-stu-id="281b5-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="281b5-119">如果未设置这些权限, 则可以通过运行[CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet 来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="281b5-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="281b5-120">请注意, CsOUPermission 只能将权限分配给 RTCUniversalUserAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="281b5-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="281b5-121">不能使用此 cmdlet 向任意用户或组授予权限。</span><span class="sxs-lookup"><span data-stu-id="281b5-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="281b5-122">如果您希望其他用户或组拥有用户管理权限, 则应将该用户 (或组) 添加到 RTCUniversalUserAdmins 组。</span><span class="sxs-lookup"><span data-stu-id="281b5-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="281b5-123">有关 OU 权限的详细信息, 请参阅[在 Lync Server 2013 中的计算机、用户或 InetOrgPerson 容器上禁用权限继承](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)。</span><span class="sxs-lookup"><span data-stu-id="281b5-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="281b5-124">运行测试</span><span class="sxs-lookup"><span data-stu-id="281b5-124">Running the test</span></span>

<span data-ttu-id="281b5-125">若要验证管理权限是否已在容器上设置, 请运行 CsOUPermission cmdlet, 后跟容器的可分辨名称, 以及你要验证的权限类型。</span><span class="sxs-lookup"><span data-stu-id="281b5-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="281b5-126">例如, 此命令将检查是否在 OU ou = Redmond、dc = litwareinc、dc = com 上设置了用户权限:</span><span class="sxs-lookup"><span data-stu-id="281b5-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="281b5-127">若要使用单个命令验证多个权限, 请将每个权限类型括在引号内, 然后使用逗号分隔这些类型。</span><span class="sxs-lookup"><span data-stu-id="281b5-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="281b5-128">例如, 下面的命令验证用户、计算机和联系人权限:</span><span class="sxs-lookup"><span data-stu-id="281b5-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="281b5-129">有关详细信息, 请参阅[CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="281b5-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="281b5-130">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="281b5-130">Determining success or failure</span></span>

<span data-ttu-id="281b5-131">如果已设置所需权限, 则 CsOUPermission 将返回一个 word 响应:</span><span class="sxs-lookup"><span data-stu-id="281b5-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="281b5-132">True</span><span class="sxs-lookup"><span data-stu-id="281b5-132">True</span></span>

<span data-ttu-id="281b5-133">如果未设置所需权限, 则 Test-CsOUPermission 将返回值 False。</span><span class="sxs-lookup"><span data-stu-id="281b5-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="281b5-134">您可能需要搜索一段时间才能找到此值。</span><span class="sxs-lookup"><span data-stu-id="281b5-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="281b5-135">它通常会嵌入到几个伴随的警告中。</span><span class="sxs-lookup"><span data-stu-id="281b5-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="281b5-136">例如：</span><span class="sxs-lookup"><span data-stu-id="281b5-136">For example:</span></span>

<span data-ttu-id="281b5-137">警告: 访问控制项 (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup;帮助ReadProperty;ContainerInherit;后代bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="281b5-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="281b5-138">警告: 对象 "OU = 北美, DC = atl-001\\= LITWAREINC, dc = Com" 的访问控制项 (ace) 尚未准备就绪。</span><span class="sxs-lookup"><span data-stu-id="281b5-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="281b5-139">False</span><span class="sxs-lookup"><span data-stu-id="281b5-139">False</span></span>

<span data-ttu-id="281b5-140">警告: "Test-CsOUPermission" 处理已完成, 但出现警告。</span><span class="sxs-lookup"><span data-stu-id="281b5-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="281b5-141">此运行期间录制了 "2" 条警告。</span><span class="sxs-lookup"><span data-stu-id="281b5-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="281b5-142">警告: 可以在 "\\C: 用户\\管理员\\AppData\\本地\\临时\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de" 处找到详细结果。</span><span class="sxs-lookup"><span data-stu-id="281b5-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="281b5-143">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="281b5-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="281b5-144">如果 CsOUPermission 的测试失败, 通常意味着指定的权限尚未分配给 RTCUniversalUserAdmins 组。</span><span class="sxs-lookup"><span data-stu-id="281b5-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="281b5-145">你可以使用 CsOUPermission cmdlet 来解决此问题, 并分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="281b5-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="281b5-146">例如, 此命令将用户、联系人和 inetOrgPersons 的 OU 权限授予 RTCUniversalUserAdmins 组:</span><span class="sxs-lookup"><span data-stu-id="281b5-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="281b5-147">有关详细信息, 请参阅 CsOUPermission cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="281b5-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

