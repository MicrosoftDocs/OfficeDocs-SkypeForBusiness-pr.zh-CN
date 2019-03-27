---
title: 测试中 Skype 业务服务器的管理员权限
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如何为业务服务器在 Skype 测试管理员权限
ms.openlocfilehash: 3f3f649ea01f974cf0462cabb7784bedc7a6df4f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873357"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="34747-103">测试中 Skype 业务服务器的管理员权限</span><span class="sxs-lookup"><span data-stu-id="34747-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="34747-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="34747-104">Verification schedule</span></span>|<span data-ttu-id="34747-105">后 Business Server 部署的初始 Skype。</span><span class="sxs-lookup"><span data-stu-id="34747-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="34747-106">根据需要如果出现权限相关的问题。</span><span class="sxs-lookup"><span data-stu-id="34747-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="34747-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="34747-107">Testing tool</span></span>|<span data-ttu-id="34747-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34747-108">Windows PowerShell</span></span>|
|<span data-ttu-id="34747-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="34747-109">Permissions required</span></span>|<span data-ttu-id="34747-110">运行时使用的业务 Server 命令行管理程序 Skype 本地，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="34747-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="34747-111">运行时使用远程 Windows PowerShell 实例，则必须为用户分配了有权运行 Test-csoupermission cmdlet RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="34747-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="34747-112">若要查看可以使用此 cmdlet 的所有 RBAC 角色的列表，请在 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="34747-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="34747-113">Get-csadminrole \| Where-object {$_。Cmdlet-匹配"Test-csoupermission"}</span><span class="sxs-lookup"><span data-stu-id="34747-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="34747-114">说明</span><span class="sxs-lookup"><span data-stu-id="34747-114">Description</span></span>

<span data-ttu-id="34747-115">在安装 Skype 业务服务器时，由安装程序执行的任务之一提供 RTCUniversalUserAdmins 组管理用户、 计算机、 联系人、 应用程序联系人和 InetOrg 所需的 Active Directory 权限人员。</span><span class="sxs-lookup"><span data-stu-id="34747-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="34747-116">如果禁用了权限继承在 Active Directory 中的，安装程序将无法分配这些权限。</span><span class="sxs-lookup"><span data-stu-id="34747-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="34747-117">因此，RTCUniversalUserAdmins 组的成员将无法管理 Skype Business Server 实体。</span><span class="sxs-lookup"><span data-stu-id="34747-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="34747-118">只能域管理员可以使用这些管理权限。</span><span class="sxs-lookup"><span data-stu-id="34747-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="34747-119">Test-csoupermission cmdlet 验证所需的权限管理用户、 计算机和其他对象所需的 Active Directory 容器上设置。</span><span class="sxs-lookup"><span data-stu-id="34747-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="34747-120">如果未设置这些权限，您可以通过运行[Grant-csoupermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="34747-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="34747-121">请注意 Grant-csoupermission 只可以向 RTCUniversalUserAdmins 组的成员分配权限。</span><span class="sxs-lookup"><span data-stu-id="34747-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="34747-122">此 cmdlet 不能用于对任意用户或组授予权限。</span><span class="sxs-lookup"><span data-stu-id="34747-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="34747-123">如果您希望使其具有用户管理权限的其他用户或组，您应添加到 RTCUniversalUserAdmins 组的用户 （或组）。</span><span class="sxs-lookup"><span data-stu-id="34747-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="34747-124">运行测试</span><span class="sxs-lookup"><span data-stu-id="34747-124">Running the test</span></span>

<span data-ttu-id="34747-125">若要验证的容器上设置了管理权限，运行 Test-csoupermission cmdlet 关注容器的可分辨名称和您要验证的权限的类型。</span><span class="sxs-lookup"><span data-stu-id="34747-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="34747-126">例如，以下命令检查用户权限是否都设置 OU ou = 雷德蒙德，dc = litwareinc，dc = com:</span><span class="sxs-lookup"><span data-stu-id="34747-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="34747-127">若要验证通过使用单个命令的多个权限，请用引号引起来，每种权限类型，然后使用逗号分隔这些类型。</span><span class="sxs-lookup"><span data-stu-id="34747-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="34747-128">例如，以下一个命令可验证用户、 计算机和联系人权限：</span><span class="sxs-lookup"><span data-stu-id="34747-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="34747-129">有关详细信息，请参阅[Test-csoupermission cmdlet 的帮助主题](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)。</span><span class="sxs-lookup"><span data-stu-id="34747-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="34747-130">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="34747-130">Determining success or failure</span></span>

<span data-ttu-id="34747-131">如果已设置所需的权限，Test-csoupermission 将返回一个单词响应：</span><span class="sxs-lookup"><span data-stu-id="34747-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="34747-132">True</span><span class="sxs-lookup"><span data-stu-id="34747-132">True</span></span>

<span data-ttu-id="34747-133">如果未设置所需的权限，Test-csoupermission 将返回值设置为 False。</span><span class="sxs-lookup"><span data-stu-id="34747-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="34747-134">您可能需要一段时间，以查找此值搜索。</span><span class="sxs-lookup"><span data-stu-id="34747-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="34747-135">通常将嵌入内多个附带的警告。</span><span class="sxs-lookup"><span data-stu-id="34747-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="34747-136">例如：</span><span class="sxs-lookup"><span data-stu-id="34747-136">For example:</span></span>

<span data-ttu-id="34747-137">警告： 访问控制项 (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;允许;ReadProperty;ContainerInherit;后代;bf967aba-0de6-11 d 0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="34747-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="34747-138">警告： 访问控制项 (Ace) 对象上的"OU = NorthAmerica，DC = atl-cs 001\DC = litwareinc，DC = com"未准备就绪。</span><span class="sxs-lookup"><span data-stu-id="34747-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="34747-139">False</span><span class="sxs-lookup"><span data-stu-id="34747-139">False</span></span> 

<span data-ttu-id="34747-140">警告:"Test-csoupermission"处理已完成，但出现了警告。</span><span class="sxs-lookup"><span data-stu-id="34747-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="34747-141">在此运行期间记录了"2"警告。</span><span class="sxs-lookup"><span data-stu-id="34747-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="34747-142">警告： 在"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"，可以找到详细的结果。</span><span class="sxs-lookup"><span data-stu-id="34747-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="34747-143">为什么测试可能已失败的原因</span><span class="sxs-lookup"><span data-stu-id="34747-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="34747-144">如果 Test-csoupermission 失败，通常表示指定的权限尚未分配到 RTCUniversalUserAdmins 组。</span><span class="sxs-lookup"><span data-stu-id="34747-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="34747-145">您可以解决此问题，并将其分配所需的权限，使用 Grant-csoupermission cmdlet。</span><span class="sxs-lookup"><span data-stu-id="34747-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="34747-146">例如，此命令可提供 OU 权限的用户、 联系人和 Inetorgperson 到 RTCUniversalUserAdmins 组：</span><span class="sxs-lookup"><span data-stu-id="34747-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="34747-147">有关详细信息，请参阅[Test-csoupermission cmdlet 的帮助主题](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)。</span><span class="sxs-lookup"><span data-stu-id="34747-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
