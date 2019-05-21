---
title: 在 Skype for Business 服务器中测试管理员权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如何测试 Skype for Business 服务器中的管理员权限
ms.openlocfilehash: 1bae61dd4e8d5a8636a64687d279536b4989d104
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279246"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="9cafc-103">在 Skype for Business 服务器中测试管理员权限</span><span class="sxs-lookup"><span data-stu-id="9cafc-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="9cafc-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="9cafc-104">Verification schedule</span></span>|<span data-ttu-id="9cafc-105">初始 Skype for Business 服务器部署后。</span><span class="sxs-lookup"><span data-stu-id="9cafc-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="9cafc-106">如果出现权限相关问题, 则根据需要。</span><span class="sxs-lookup"><span data-stu-id="9cafc-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="9cafc-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="9cafc-107">Testing tool</span></span>|<span data-ttu-id="9cafc-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cafc-108">Windows PowerShell</span></span>|
|<span data-ttu-id="9cafc-109">需要权限</span><span class="sxs-lookup"><span data-stu-id="9cafc-109">Permissions required</span></span>|<span data-ttu-id="9cafc-110">在使用 Skype for Business Server Management Shell 本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="9cafc-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="9cafc-111">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsOUPermission cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9cafc-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="9cafc-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="9cafc-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="9cafc-113">CsAdminRole \| -对象 {$ _。Cmdlet-匹配的 "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="9cafc-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="9cafc-114">说明</span><span class="sxs-lookup"><span data-stu-id="9cafc-114">Description</span></span>

<span data-ttu-id="9cafc-115">安装 Skype for Business 服务器时, 安装程序执行的任务之一为 RTCUniversalUserAdmins 组提供管理用户、计算机、联系人、应用程序联系人和 InetOrg 所需的 Active Directory 权限。者.</span><span class="sxs-lookup"><span data-stu-id="9cafc-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="9cafc-116">如果您已在 Active Directory 中禁用权限继承, 则安装程序将无法分配这些权限。</span><span class="sxs-lookup"><span data-stu-id="9cafc-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="9cafc-117">因此, RTCUniversalUserAdmins 组的成员将无法管理 Skype for business 服务器实体。</span><span class="sxs-lookup"><span data-stu-id="9cafc-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="9cafc-118">这些管理权限将仅可供域管理员使用。</span><span class="sxs-lookup"><span data-stu-id="9cafc-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="9cafc-119">CsOUPermission cmdlet 验证管理用户、计算机和其他对象所需的权限是否在 Active Directory 容器上设置。</span><span class="sxs-lookup"><span data-stu-id="9cafc-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="9cafc-120">如果未设置这些权限, 则可以通过运行[CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="9cafc-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="9cafc-121">请注意, CsOUPermission 只能将权限分配给 RTCUniversalUserAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="9cafc-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="9cafc-122">不能使用此 cmdlet 向任意用户或组授予权限。</span><span class="sxs-lookup"><span data-stu-id="9cafc-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="9cafc-123">如果您希望其他用户或组拥有用户管理权限, 则应将该用户 (或组) 添加到 RTCUniversalUserAdmins 组。</span><span class="sxs-lookup"><span data-stu-id="9cafc-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="9cafc-124">运行测试</span><span class="sxs-lookup"><span data-stu-id="9cafc-124">Running the test</span></span>

<span data-ttu-id="9cafc-125">若要验证管理权限是否已在容器上设置, 请运行 CsOUPermission cmdlet, 后跟容器的可分辨名称, 以及你要验证的权限类型。</span><span class="sxs-lookup"><span data-stu-id="9cafc-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="9cafc-126">例如, 此命令将检查是否在 OU ou = Redmond、dc = litwareinc、dc = com 上设置了用户权限:</span><span class="sxs-lookup"><span data-stu-id="9cafc-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="9cafc-127">若要使用单个命令验证多个权限, 请将每个权限类型括在引号内, 然后使用逗号分隔这些类型。</span><span class="sxs-lookup"><span data-stu-id="9cafc-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="9cafc-128">例如, 下面的命令验证用户、计算机和联系人权限:</span><span class="sxs-lookup"><span data-stu-id="9cafc-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="9cafc-129">有关详细信息, 请参阅[CsOUPermission cmdlet 的帮助主题](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)。</span><span class="sxs-lookup"><span data-stu-id="9cafc-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9cafc-130">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="9cafc-130">Determining success or failure</span></span>

<span data-ttu-id="9cafc-131">如果已设置所需权限, CsOUPermission 将返回一个 word 响应:</span><span class="sxs-lookup"><span data-stu-id="9cafc-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="9cafc-132">True</span><span class="sxs-lookup"><span data-stu-id="9cafc-132">True</span></span>

<span data-ttu-id="9cafc-133">如果未设置所需权限, 则 CsOUPermission 将返回值 False。</span><span class="sxs-lookup"><span data-stu-id="9cafc-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="9cafc-134">您可能需要搜索一段时间才能找到此值。</span><span class="sxs-lookup"><span data-stu-id="9cafc-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="9cafc-135">它通常会嵌入到几个伴随的警告中。</span><span class="sxs-lookup"><span data-stu-id="9cafc-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="9cafc-136">例如：</span><span class="sxs-lookup"><span data-stu-id="9cafc-136">For example:</span></span>

<span data-ttu-id="9cafc-137">警告: 访问控制项 (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;帮助ReadProperty;ContainerInherit;后代bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="9cafc-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="9cafc-138">警告: 对象 "OU = 北美洲, DC = atl-cs-001\DC = litwareinc, DC = com" 上的访问控制项 (Ace) 尚未准备就绪。</span><span class="sxs-lookup"><span data-stu-id="9cafc-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="9cafc-139">False</span><span class="sxs-lookup"><span data-stu-id="9cafc-139">False</span></span> 

<span data-ttu-id="9cafc-140">警告: "Test-CsOUPermission" 处理已完成, 但出现警告。</span><span class="sxs-lookup"><span data-stu-id="9cafc-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="9cafc-141">此运行期间录制了 "2" 条警告。</span><span class="sxs-lookup"><span data-stu-id="9cafc-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="9cafc-142">警告: 可在 "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" 中找到详细结果。</span><span class="sxs-lookup"><span data-stu-id="9cafc-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9cafc-143">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="9cafc-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="9cafc-144">如果 CsOUPermission 测试失败, 通常意味着指定的权限尚未分配给 RTCUniversalUserAdmins 组。</span><span class="sxs-lookup"><span data-stu-id="9cafc-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="9cafc-145">你可以使用 CsOUPermission cmdlet 来解决此问题, 并分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="9cafc-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="9cafc-146">例如, 此命令将用户、联系人和 inetOrgPersons 的 OU 权限授予 RTCUniversalUserAdmins 组:</span><span class="sxs-lookup"><span data-stu-id="9cafc-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="9cafc-147">有关详细信息, 请参阅[CsOUPermission cmdlet 的帮助主题](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)。</span><span class="sxs-lookup"><span data-stu-id="9cafc-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
