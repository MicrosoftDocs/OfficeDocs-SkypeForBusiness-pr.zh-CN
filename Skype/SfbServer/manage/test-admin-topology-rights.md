---
title: 测试管理员拓扑中的Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 如何测试拓扑中的拓扑Skype for Business Server
ms.openlocfilehash: 6f4eed0271d9dd6d099d19287f7caa37148f6026
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861309"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>测试管理员拓扑中的Skype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|验证计划|初始部署Skype for Business Server之后。 如果需要，出现与权限相关的问题。|
|测试工具|Windows PowerShell|
|所需的权限|使用命令行管理程序Skype for Business Server运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。<br/><br/>当使用远程 Windows PowerShell 实例运行时，必须为用户分配 RBAC 角色，该角色具有运行 Test-CsSetupPermission cmdlet 的权限。 To see a list of all RBAC roles that can use this cmdlet， run the following command from the Windows PowerShell prompt：<br/><br/>Get-CsAdminRoleWhere-Object \| {$_.Cmdlet -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>说明

默认情况下，只有域管理员才能启用Skype for Business Server拓扑，并大量更改Skype for Business Server基础结构。 只要域管理员和域管理员相同，Skype for Business Server就不会出现问题。 在许多组织中，Skype for Business Server管理员对整个域没有管理权限。 默认情况下，这意味着这些 (定义为 RTCUniversalServerAdmins 组的成员) 无法对拓扑Skype for Business Server进行更改。 若要向 RTCUniversalServerAdmins 组的成员授予更改拓扑的权限，必须使用 [Grant-CsSetupPermission](/powershell/module/skype/Grant-CsSetupPermission) cmdlet 分配所需的 Active Directory 权限。
 
此Test-CsSetupPermission cmdlet 验证在指定的 Active Directory 容器上配置安装 Skype for Business Server 或其中一个组件所需的权限。 如果未分配权限，您可以运行 Grant-CsSetupPermission cmdlet，以授予 RTCUniversalServerAdmins 组的成员安装和启用 Skype for Business Server。

## <a name="running-the-test"></a>运行测试

若要确定是否为 Active Directory 容器分配安装权限，请调用 Test-CsSetupPermission cmdlet。 指定要检查的容器的可分辨名称。 例如，此命令验证对容器 ou=CsServers，dc=litwareinc，dc=com 的安装权限：

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

有关详细信息，请参阅 [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。

## <a name="determining-success-or-failure"></a>确定成功或失败

如果Test-CsSetupPermission确定已在 Active Directory 容器上设置了所需的权限，则 cmdlet 将返回值 True：

True 

如果未设置权限，Test-CsSetupPermission返回值 False。 请注意，此值通常包含在许多警告消息中。 例如：

警告：ACE (访问控制项) atl-cs-001\RTCUniversalServerAdmins;允许;ExtendedRight;无;无;1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告：未准备好 ("CN=Computers，DC=litwareinc，DC=com"上) AES 的访问控制项。 

错误 

警告："Test-CsSetupPermission"处理已完成，并出现警告。 在此运行过程中记录了"2"警告。 

警告：详细结果可在"C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"找到。 

## <a name="reasons-why-the-test-might-have-failed"></a>测试失败的原因

尽管极少数例外情况，但如果Test-CsSetupPermission，这通常意味着未为指定的 Active Directory 容器分配安装权限。 可以使用 Grant-CsSetupPermission cmdlet 分配这些权限。 例如，以下命令向域中的 Computers 容器授予 litwareinc.com：

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

有关详细信息，请参阅 [Test-CsSetupPermission](/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。