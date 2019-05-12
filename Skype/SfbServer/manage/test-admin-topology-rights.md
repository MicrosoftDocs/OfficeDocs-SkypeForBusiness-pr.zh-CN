---
title: Skype 中测试业务服务器管理员拓扑权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如何为业务服务器在 Skype 测试拓扑权限
ms.openlocfilehash: 239c35eba451166f4e9fb5755535cf15999cdaea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910366"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="28fe6-103">Skype 中测试业务服务器管理员拓扑权限</span><span class="sxs-lookup"><span data-stu-id="28fe6-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="28fe6-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="28fe6-104">Verification schedule</span></span>|<span data-ttu-id="28fe6-105">后 Business Server 部署的初始 Skype。</span><span class="sxs-lookup"><span data-stu-id="28fe6-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="28fe6-106">根据需要如果出现权限相关的问题。</span><span class="sxs-lookup"><span data-stu-id="28fe6-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="28fe6-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="28fe6-107">Testing tool</span></span>|<span data-ttu-id="28fe6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28fe6-108">Windows PowerShell</span></span>|
|<span data-ttu-id="28fe6-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="28fe6-109">Permissions required</span></span>|<span data-ttu-id="28fe6-110">运行时使用的业务 Server 命令行管理程序 Skype 本地，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="28fe6-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="28fe6-111">运行时使用远程 Windows PowerShell 实例，则必须为用户分配了有权运行 Test-cssetuppermission cmdlet RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="28fe6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="28fe6-112">若要查看可以使用此 cmdlet 的所有 RBAC 角色的列表，请在 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="28fe6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="28fe6-113">Get-csadminrole \| Where-object {$_。Cmdlet-匹配"Test-cssetuppermission"}</span><span class="sxs-lookup"><span data-stu-id="28fe6-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="28fe6-114">说明</span><span class="sxs-lookup"><span data-stu-id="28fe6-114">Description</span></span>

<span data-ttu-id="28fe6-115">默认情况下，只有域管理员可以启用企业服务器拓扑的 Skype 和更改业务服务器基础结构 Skype 的大型。</span><span class="sxs-lookup"><span data-stu-id="28fe6-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="28fe6-116">只要您的域管理员和业务服务器管理员将 Skype 是同一个，这不是问题。</span><span class="sxs-lookup"><span data-stu-id="28fe6-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="28fe6-117">在许多组织业务服务器管理员的 Skype 不保留对整个域管理权限。</span><span class="sxs-lookup"><span data-stu-id="28fe6-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="28fe6-118">默认情况下，这意味着，这些 （定义为 RTCUniversalServerAdmins 组的成员） 的管理员不能 Skype 的企业服务器拓扑的更改。</span><span class="sxs-lookup"><span data-stu-id="28fe6-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="28fe6-119">要授予 RTCUniversalServerAdmins 组的权限更改拓扑的成员，您必须使用[Grant-cssetuppermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet 分配所需的 Active Directory 权限。</span><span class="sxs-lookup"><span data-stu-id="28fe6-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="28fe6-120">Test-cssetuppermission cmdlet 验证在指定的 Active Directory 容器上配置了需要为业务服务器或其组件之一安装 Skype 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="28fe6-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="28fe6-121">如果未分配权限，然后可以运行 Grant-cssetuppermission cmdlet 授予 RTCUniversalServerAdmins 组成员的安装和启用业务 Server Skype 的权限。</span><span class="sxs-lookup"><span data-stu-id="28fe6-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="28fe6-122">运行测试</span><span class="sxs-lookup"><span data-stu-id="28fe6-122">Running the test</span></span>

<span data-ttu-id="28fe6-123">若要确定是否对 Active Directory 容器分配安装权限，请调用 Test-cssetuppermission cmdlet。</span><span class="sxs-lookup"><span data-stu-id="28fe6-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="28fe6-124">指定要检查的容器的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="28fe6-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="28fe6-125">例如，以下命令可验证安装权限的容器 ou = CsServers，dc = litwareinc，dc = com:</span><span class="sxs-lookup"><span data-stu-id="28fe6-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="28fe6-126">有关详细信息，请参阅[Test-cssetuppermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="28fe6-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="28fe6-127">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="28fe6-127">Determining success or failure</span></span>

<span data-ttu-id="28fe6-128">如果 Test-cssetuppermission 确定所需的权限已设置的 Active Directory 容器上 cmdlet 将返回值为 True:</span><span class="sxs-lookup"><span data-stu-id="28fe6-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="28fe6-129">True</span><span class="sxs-lookup"><span data-stu-id="28fe6-129">True</span></span> 

<span data-ttu-id="28fe6-130">如果未设置权限，Test-cssetuppermission 将返回值设置为 False。</span><span class="sxs-lookup"><span data-stu-id="28fe6-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="28fe6-131">请注意，此值将通常括在多个警告消息。</span><span class="sxs-lookup"><span data-stu-id="28fe6-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="28fe6-132">例如：</span><span class="sxs-lookup"><span data-stu-id="28fe6-132">For example:</span></span>

<span data-ttu-id="28fe6-133">警告： 访问控制项 (ACE) atl-cs-001\RTCUniversalServerAdmins;允许;ExtendedRight;无;无;1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="28fe6-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="28fe6-134">警告： 访问控制项 (Ace) 对象上的"CN = Computers，DC = litwareinc，DC = com"未准备就绪。</span><span class="sxs-lookup"><span data-stu-id="28fe6-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="28fe6-135">False</span><span class="sxs-lookup"><span data-stu-id="28fe6-135">False</span></span> 

<span data-ttu-id="28fe6-136">警告:"Test-cssetuppermission"处理已完成，但出现了警告。</span><span class="sxs-lookup"><span data-stu-id="28fe6-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="28fe6-137">在此运行期间记录了"2"警告。</span><span class="sxs-lookup"><span data-stu-id="28fe6-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="28fe6-138">警告： 在"C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"，可以找到详细的结果。</span><span class="sxs-lookup"><span data-stu-id="28fe6-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="28fe6-139">为什么测试可能已失败的原因</span><span class="sxs-lookup"><span data-stu-id="28fe6-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="28fe6-140">尽管有极少数例外，如果 Test-cssetuppermission 失败通常意味着安装权限未分配对指定的 Active Directory 容器。</span><span class="sxs-lookup"><span data-stu-id="28fe6-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="28fe6-141">可以通过使用 Grant-cssetuppermission cmdlet 分配这些权限。</span><span class="sxs-lookup"><span data-stu-id="28fe6-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="28fe6-142">例如，此命令授予对域 litwareinc.com 中的计算机容器的安装权限：</span><span class="sxs-lookup"><span data-stu-id="28fe6-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="28fe6-143">有关详细信息，请参阅[Test-cssetuppermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="28fe6-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
