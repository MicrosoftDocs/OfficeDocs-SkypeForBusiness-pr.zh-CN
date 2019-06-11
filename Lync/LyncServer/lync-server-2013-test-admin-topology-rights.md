---
title: 'Lync Server 2013: 测试管理员拓扑权限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365c879678ff3fd51dcaaf89d4b2593eccf645f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="86041-102">Lync Server 2013 中的测试管理员拓扑权限</span><span class="sxs-lookup"><span data-stu-id="86041-102">Test admin topology rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86041-103">_**主题上次修改时间:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="86041-103">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86041-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="86041-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="86041-105">初始 Lync Server 部署后。</span><span class="sxs-lookup"><span data-stu-id="86041-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="86041-106">如果出现权限相关问题, 则根据需要。</span><span class="sxs-lookup"><span data-stu-id="86041-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86041-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="86041-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="86041-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="86041-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86041-109">需要权限</span><span class="sxs-lookup"><span data-stu-id="86041-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="86041-110">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="86041-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="86041-111">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsSetupPermission cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="86041-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="86041-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="86041-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="86041-113">说明</span><span class="sxs-lookup"><span data-stu-id="86041-113">Description</span></span>

<span data-ttu-id="86041-114">默认情况下, 只有域管理员可以启用 Lync Server 拓扑, 并对 Lync Server 基础结构进行较大的更改。</span><span class="sxs-lookup"><span data-stu-id="86041-114">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="86041-115">只要您的域管理员和您的 Lync 服务器管理员是同一个, 这就不会出现问题。在许多组织中, Lync Server 管理员不拥有对整个域的管理权限。</span><span class="sxs-lookup"><span data-stu-id="86041-115">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="86041-116">默认情况下, 这意味着这些管理员 (定义为 RTCUniversalServerAdmins 组的成员) 无法更改 Lync 服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="86041-116">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="86041-117">若要为 RTCUniversalServerAdmins 组的成员授予拓扑更改权限, 必须通过使用[CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet 分配所需的 Active Directory 权限。</span><span class="sxs-lookup"><span data-stu-id="86041-117">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="86041-118">CsSetupPermission cmdlet 验证安装 Lync Server 或其组件之一所需的权限是否在指定的 Active Directory 容器上配置。</span><span class="sxs-lookup"><span data-stu-id="86041-118">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="86041-119">如果未分配权限, 则可以运行 CsSetupPermission cmdlet 授予 RTCUniversalServerAdmins 组的成员安装和启用 Lync Server 的权限。</span><span class="sxs-lookup"><span data-stu-id="86041-119">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86041-120">有关由授权 CsSetupPermission 分配的权限的详细列表, 请参阅博客帖子<A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">授予-CsSetupPermission 和 Grant CsOUPermission</A>。</span><span class="sxs-lookup"><span data-stu-id="86041-120">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="86041-121">运行测试</span><span class="sxs-lookup"><span data-stu-id="86041-121">Running the test</span></span>

<span data-ttu-id="86041-122">若要确定是否为 Active Directory 容器分配了设置权限, 请调用 CsSetupPermission cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86041-122">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="86041-123">指定要检查的容器的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="86041-123">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="86041-124">例如, 此命令将验证容器 ou = CsServers、dc = litwareinc、dc = com 的设置权限:</span><span class="sxs-lookup"><span data-stu-id="86041-124">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="86041-125">有关详细信息, 请参阅[CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="86041-125">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="86041-126">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="86041-126">Determining success or failure</span></span>

<span data-ttu-id="86041-127">如果测试 CsSetupPermission 确定已在 Active Directory 容器上设置了所需的权限, 则 cmdlet 将返回值 True:</span><span class="sxs-lookup"><span data-stu-id="86041-127">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="86041-128">True</span><span class="sxs-lookup"><span data-stu-id="86041-128">True</span></span>

<span data-ttu-id="86041-129">如果未设置权限, 则 CsSetupPermission 将返回值 False。</span><span class="sxs-lookup"><span data-stu-id="86041-129">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="86041-130">请注意, 此值通常会包含在许多警告消息中。</span><span class="sxs-lookup"><span data-stu-id="86041-130">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="86041-131">例如：</span><span class="sxs-lookup"><span data-stu-id="86041-131">For example:</span></span>

<span data-ttu-id="86041-132">警告: 访问控制项 (ACE) atl-cs-001\\RTCUniversalServerAdmins;帮助ExtendedRight;尚尚1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="86041-132">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="86041-133">警告: 对象 "CN = 计算机, DC = litwareinc, dc = com" 上的访问控制项 (Ace) 尚未准备就绪。</span><span class="sxs-lookup"><span data-stu-id="86041-133">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="86041-134">False</span><span class="sxs-lookup"><span data-stu-id="86041-134">False</span></span>

<span data-ttu-id="86041-135">警告: "Test-CsSetupPermission" 处理已完成, 但出现警告。</span><span class="sxs-lookup"><span data-stu-id="86041-135">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="86041-136">此运行期间录制了 "2" 条警告。</span><span class="sxs-lookup"><span data-stu-id="86041-136">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="86041-137">警告: 可在 "\\C: 用户\\管理员\\AppData\\本地\\临时\\测试-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118" 处找到详细结果。</span><span class="sxs-lookup"><span data-stu-id="86041-137">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="86041-138">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="86041-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="86041-139">虽然不太常见的例外, 但如果测试 CsSetupPermission 失败, 通常意味着不会为指定的 Active Directory 容器分配设置权限。</span><span class="sxs-lookup"><span data-stu-id="86041-139">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="86041-140">可以使用 CsSetupPermission cmdlet 分配这些权限。</span><span class="sxs-lookup"><span data-stu-id="86041-140">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="86041-141">例如, 此命令向域 litwareinc.com 中的计算机容器授予设置权限:</span><span class="sxs-lookup"><span data-stu-id="86041-141">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="86041-142">有关详细信息, 请参阅[CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="86041-142">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

