---
title: 在 Skype for Business 服务器中测试管理员拓扑权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如何在 Skype for Business 服务器中测试拓扑权限
ms.openlocfilehash: d70809ba929c4f1934adce2bd3c60b261bd30d71
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279241"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="fa560-103">在 Skype for Business 服务器中测试管理员拓扑权限</span><span class="sxs-lookup"><span data-stu-id="fa560-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="fa560-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="fa560-104">Verification schedule</span></span>|<span data-ttu-id="fa560-105">初始 Skype for Business 服务器部署后。</span><span class="sxs-lookup"><span data-stu-id="fa560-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="fa560-106">如果出现权限相关问题, 则根据需要。</span><span class="sxs-lookup"><span data-stu-id="fa560-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="fa560-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="fa560-107">Testing tool</span></span>|<span data-ttu-id="fa560-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa560-108">Windows PowerShell</span></span>|
|<span data-ttu-id="fa560-109">需要权限</span><span class="sxs-lookup"><span data-stu-id="fa560-109">Permissions required</span></span>|<span data-ttu-id="fa560-110">在使用 Skype for Business Server Management Shell 本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="fa560-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="fa560-111">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsSetupPermission cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="fa560-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="fa560-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="fa560-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="fa560-113">CsAdminRole \| -对象 {$ _。Cmdlet-匹配的 "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="fa560-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="fa560-114">说明</span><span class="sxs-lookup"><span data-stu-id="fa560-114">Description</span></span>

<span data-ttu-id="fa560-115">默认情况下, 只有域管理员可以启用 Skype for business 服务器拓扑, 并对 Skype for business 服务器基础结构进行较大的更改。</span><span class="sxs-lookup"><span data-stu-id="fa560-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="fa560-116">只要您的域管理员和您的 Skype for business 服务器管理员是同一个, 这就不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="fa560-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="fa560-117">在许多组织中, Skype for Business 服务器管理员不拥有对整个域的管理权限。</span><span class="sxs-lookup"><span data-stu-id="fa560-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="fa560-118">默认情况下, 这意味着这些管理员 (定义为 RTCUniversalServerAdmins 组的成员) 无法进行 Skype for business 服务器拓扑更改。</span><span class="sxs-lookup"><span data-stu-id="fa560-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="fa560-119">若要为 RTCUniversalServerAdmins 组的成员授予拓扑更改权限, 必须通过使用[CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet 分配所需的 Active Directory 权限。</span><span class="sxs-lookup"><span data-stu-id="fa560-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="fa560-120">CsSetupPermission cmdlet 验证安装 Skype for Business 服务器或其组件之一所需的权限是否在指定的 Active Directory 容器上配置。</span><span class="sxs-lookup"><span data-stu-id="fa560-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="fa560-121">如果未分配权限, 则可以运行 CsSetupPermission cmdlet 授予 RTCUniversalServerAdmins 组的成员安装和启用 Skype for Business 服务器的权限。</span><span class="sxs-lookup"><span data-stu-id="fa560-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="fa560-122">运行测试</span><span class="sxs-lookup"><span data-stu-id="fa560-122">Running the test</span></span>

<span data-ttu-id="fa560-123">若要确定是否为 Active Directory 容器分配了设置权限, 请调用 CsSetupPermission cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fa560-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="fa560-124">指定要检查的容器的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="fa560-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="fa560-125">例如, 此命令将验证容器 ou = CsServers、dc = litwareinc、dc = com 的设置权限:</span><span class="sxs-lookup"><span data-stu-id="fa560-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="fa560-126">有关详细信息, 请参阅[CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fa560-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fa560-127">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="fa560-127">Determining success or failure</span></span>

<span data-ttu-id="fa560-128">如果测试 CsSetupPermission 确定已在 Active Directory 容器上设置了所需的权限, 则 cmdlet 将返回值 True:</span><span class="sxs-lookup"><span data-stu-id="fa560-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="fa560-129">True</span><span class="sxs-lookup"><span data-stu-id="fa560-129">True</span></span> 

<span data-ttu-id="fa560-130">如果未设置权限, 则 CsSetupPermission 将返回值 False。</span><span class="sxs-lookup"><span data-stu-id="fa560-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="fa560-131">请注意, 此值通常会包含在许多警告消息中。</span><span class="sxs-lookup"><span data-stu-id="fa560-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="fa560-132">例如：</span><span class="sxs-lookup"><span data-stu-id="fa560-132">For example:</span></span>

<span data-ttu-id="fa560-133">警告: 访问控制项 (ACE) atl-cs-001\RTCUniversalServerAdmins;帮助ExtendedRight;尚尚1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="fa560-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="fa560-134">警告: 对象 "CN = 计算机, DC = litwareinc, dc = com" 上的访问控制项 (Ace) 尚未准备就绪。</span><span class="sxs-lookup"><span data-stu-id="fa560-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="fa560-135">False</span><span class="sxs-lookup"><span data-stu-id="fa560-135">False</span></span> 

<span data-ttu-id="fa560-136">警告: "Test-CsSetupPermission" 处理已完成, 但出现警告。</span><span class="sxs-lookup"><span data-stu-id="fa560-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="fa560-137">此运行期间录制了 "2" 条警告。</span><span class="sxs-lookup"><span data-stu-id="fa560-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="fa560-138">警告: 可在 "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" 中找到详细结果。</span><span class="sxs-lookup"><span data-stu-id="fa560-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fa560-139">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="fa560-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="fa560-140">虽然不太常见的例外, 但如果测试 CsSetupPermission 失败, 通常意味着不会为指定的 Active Directory 容器分配设置权限。</span><span class="sxs-lookup"><span data-stu-id="fa560-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="fa560-141">可以使用 CsSetupPermission cmdlet 分配这些权限。</span><span class="sxs-lookup"><span data-stu-id="fa560-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="fa560-142">例如, 此命令向域 litwareinc.com 中的计算机容器授予设置权限:</span><span class="sxs-lookup"><span data-stu-id="fa560-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="fa560-143">有关详细信息, 请参阅[CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fa560-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
