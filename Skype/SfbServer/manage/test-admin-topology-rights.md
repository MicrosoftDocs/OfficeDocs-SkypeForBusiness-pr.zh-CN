---
title: 在 Skype for Business Server 中测试管理员拓扑权限
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
description: 如何在 Skype for Business Server 中测试拓扑权限
ms.openlocfilehash: d9c0ec5560dcb6f1a6872f0b38f2930e46b2364c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122386"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="e3378-103">在 Skype for Business Server 中测试管理员拓扑权限</span><span class="sxs-lookup"><span data-stu-id="e3378-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="e3378-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="e3378-104">Verification schedule</span></span>|<span data-ttu-id="e3378-105">初始 Skype for Business Server 部署后。</span><span class="sxs-lookup"><span data-stu-id="e3378-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="e3378-106">如果需要，出现与权限相关的问题。</span><span class="sxs-lookup"><span data-stu-id="e3378-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="e3378-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="e3378-107">Testing tool</span></span>|<span data-ttu-id="e3378-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3378-108">Windows PowerShell</span></span>|
|<span data-ttu-id="e3378-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="e3378-109">Permissions required</span></span>|<span data-ttu-id="e3378-110">使用 Skype for Business Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="e3378-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="e3378-111">在使用远程 cmdlet Windows PowerShell运行时，必须为用户分配 RBAC 角色，该角色具有运行 Test-CsSetupPermission cmdlet 的权限。</span><span class="sxs-lookup"><span data-stu-id="e3378-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="e3378-112">To see a list of all RBAC roles that can use this cmdlet， run the following command from the Windows PowerShell prompt：</span><span class="sxs-lookup"><span data-stu-id="e3378-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="e3378-113">Get-CsAdminRoleWhere-Object \| {$_.Cmdlet -match "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="e3378-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="e3378-114">说明</span><span class="sxs-lookup"><span data-stu-id="e3378-114">Description</span></span>

<span data-ttu-id="e3378-115">默认情况下，只有域管理员可以启用 Skype for Business Server 拓扑，并针对 Skype for Business Server 基础结构进行大量更改。</span><span class="sxs-lookup"><span data-stu-id="e3378-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="e3378-116">只要域管理员和 Skype for Business Server 管理员是一个且相同的管理员，这就不会是问题。</span><span class="sxs-lookup"><span data-stu-id="e3378-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="e3378-117">在许多组织中，Skype for Business Server 管理员对整个域没有管理权限。</span><span class="sxs-lookup"><span data-stu-id="e3378-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="e3378-118">默认情况下，这意味着这些 (定义为 RTCUniversalServerAdmins 组) 无法更改 Skype for Business Server 拓扑。</span><span class="sxs-lookup"><span data-stu-id="e3378-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="e3378-119">若要向 RTCUniversalServerAdmins 组的成员授予更改拓扑的权限，必须使用 [Grant-CsSetupPermission](/powershell/module/skype/Grant-CsSetupPermission) cmdlet 分配所需的 Active Directory 权限。</span><span class="sxs-lookup"><span data-stu-id="e3378-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="e3378-120">此Test-CsSetupPermission cmdlet 验证在指定的 Active Directory 容器中配置了安装 Skype for Business Server 或其中一个组件所需的权限。</span><span class="sxs-lookup"><span data-stu-id="e3378-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="e3378-121">如果未分配权限，可以运行 Grant-CsSetupPermission cmdlet，向 RTCUniversalServerAdmins 组的成员授予安装和启用 Skype for Business Server 的权限。</span><span class="sxs-lookup"><span data-stu-id="e3378-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="e3378-122">运行测试</span><span class="sxs-lookup"><span data-stu-id="e3378-122">Running the test</span></span>

<span data-ttu-id="e3378-123">若要确定是否为 Active Directory 容器分配安装权限，请调用 Test-CsSetupPermission cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e3378-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="e3378-124">指定要检查的容器的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="e3378-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="e3378-125">例如，此命令验证对容器 ou=CsServers，dc=litwareinc，dc=com 的安装权限：</span><span class="sxs-lookup"><span data-stu-id="e3378-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="e3378-126">有关详细信息，请参阅 [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e3378-126">For more information, see the help topic for the [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e3378-127">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="e3378-127">Determining success or failure</span></span>

<span data-ttu-id="e3378-128">如果Test-CsSetupPermission确定已在 Active Directory 容器上设置了所需的权限，则 cmdlet 将返回值 True：</span><span class="sxs-lookup"><span data-stu-id="e3378-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="e3378-129">True</span><span class="sxs-lookup"><span data-stu-id="e3378-129">True</span></span> 

<span data-ttu-id="e3378-130">如果未设置权限，Test-CsSetupPermission返回值 False。</span><span class="sxs-lookup"><span data-stu-id="e3378-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="e3378-131">请注意，此值通常包含在许多警告消息中。</span><span class="sxs-lookup"><span data-stu-id="e3378-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="e3378-132">例如：</span><span class="sxs-lookup"><span data-stu-id="e3378-132">For example:</span></span>

<span data-ttu-id="e3378-133">警告：ACE (中的访问控制) atl-cs-001\RTCUniversalServerAdmins;允许;ExtendedRight;无;无;1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="e3378-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="e3378-134">警告：未准备好 ("CN=Computers，DC=litwareinc，DC=com"上) AES 的访问控制项。</span><span class="sxs-lookup"><span data-stu-id="e3378-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="e3378-135">False</span><span class="sxs-lookup"><span data-stu-id="e3378-135">False</span></span> 

<span data-ttu-id="e3378-136">警告："Test-CsSetupPermission"处理已完成，并出现警告。</span><span class="sxs-lookup"><span data-stu-id="e3378-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="e3378-137">在此运行过程中记录了"2"警告。</span><span class="sxs-lookup"><span data-stu-id="e3378-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="e3378-138">警告：可以在"C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"找到详细结果。</span><span class="sxs-lookup"><span data-stu-id="e3378-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e3378-139">测试失败的原因</span><span class="sxs-lookup"><span data-stu-id="e3378-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="e3378-140">尽管存在极少数例外情况，但如果Test-CsSetupPermission失败，这通常意味着未为指定的 Active Directory 容器分配安装权限。</span><span class="sxs-lookup"><span data-stu-id="e3378-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="e3378-141">可以使用 Grant-CsSetupPermission cmdlet 分配这些权限。</span><span class="sxs-lookup"><span data-stu-id="e3378-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="e3378-142">例如，以下命令向域中的 Computers 容器授予 litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="e3378-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="e3378-143">有关详细信息，请参阅 [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e3378-143">For more information, see the help topic for the [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>