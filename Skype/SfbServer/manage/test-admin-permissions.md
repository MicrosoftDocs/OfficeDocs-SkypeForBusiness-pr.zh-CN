---
title: 在管理中心中测试Skype for Business Server
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
description: 如何测试管理员权限Skype for Business Server
ms.openlocfilehash: 7dd9e1b95df35cb363617690cb9667c1a16ef904
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58232617"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>在管理中心中测试Skype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|验证计划|初始部署Skype for Business Server之后。 如果需要，出现与权限相关的问题。|
|测试工具|Windows PowerShell|
|所需的权限|使用命令行管理程序Skype for Business Server本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。<br><br/>在使用远程 cmdlet Windows PowerShell运行时，必须为用户分配具有运行 Test-CsOUPermission cmdlet 的权限的 RBAC 角色。 To see a list of all RBAC roles that can use this cmdlet， run the following command from the Windows PowerShell prompt：<br/><br/>Get-CsAdminRoleWhere-Object \| {$_.Cmdlet -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>描述

安装 Skype for Business Server 时，安装程序执行的任务之一会为 RTCUniversalUserAdmins 组提供管理用户、计算机、联系人、应用程序联系人和 InetOrg 人员所需的 Active Directory 权限。 如果已禁用 Active Directory 中的权限继承，则安装程序将无法分配这些权限。 因此，RTCUniversalUserAdmins 组的成员将无法管理Skype for Business Server实体。 这些管理权限将仅对域管理员可用。 

此Test-CsOUPermission cmdlet 验证在 Active Directory 容器中是否设置了管理用户、计算机和其他对象所需的权限。 如果未设置这些权限，您可以通过运行 [Grant-CsOUPermission cmdlet](/powershell/module/skype/Grant-CsOUPermission)来解决此问题。 

请注意，Grant-CsOUPermission只能向 RTCUniversalUserAdmins 组的成员分配权限。 不能使用此 cmdlet 向任意用户或组授予权限。 如果您希望其他用户或组具有用户管理权限，您应将该用户 (或组) RTCUniversalUserAdmins 组。 


## <a name="running-the-test"></a>运行测试

若要验证是否已在容器上设置管理权限，请运行 Test-CsOUPermission cmdlet，后跟容器的可分辨名称以及要验证的权限类型。 例如，此命令检查是否在 OU ou=Redmond，dc=litwareinc，dc=com 上设置用户权限：

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

若要使用单个命令验证多个权限，请用引号括住每个权限类型，然后使用逗号分隔这些类型。 例如，此命令验证用户、计算机和联系人权限：

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

有关详细信息，请参阅 Test-CsOUPermission [cmdlet 的帮助主题](/powershell/module/skype/test-csoupermission)。

## <a name="determining-success-or-failure"></a>确定成功或失败

如果已设置所需的权限，Test-CsOUPermission返回一个词的响应：

True

如果未设置所需的权限，Test-CsOUPermission返回值 False。 您可能需要搜索一些时间以查找此值。 它通常嵌入在附带的多个警告内。 例如：

警告：A) CE (atl-cs-001\RTCUniversalUserReadOnlyGroup 中的访问控制项;allow;ReadProperty;ContainerInherit;后代;bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

警告：对象"OU=NorthAmerica，DC=atl-cs-001\DC=litwareinc，DC=com"上的访问控制项 (AES) ）未准备好。 

错误 

警告："Test-CsOUPermission"处理已完成，并出现警告。 在此运行过程中记录了"2"警告。 

警告：可以在"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"找到详细结果。 

## <a name="reasons-why-the-test-might-have-failed"></a>测试失败的原因

如果Test-CsOUPermission失败，则通常意味着尚未将指定权限分配给 RTCUniversalUserAdmins 组。 您可以通过使用 cmdlet 来解决此问题并分配Grant-CsOUPermission权限。 例如，此命令为 RTCUniversalUserAdmins 组的用户、联系人和 inetOrgPersons 提供 OU 权限：

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

有关详细信息，请参阅 Test-CsOUPermission [cmdlet 的帮助主题](/powershell/module/skype/test-csoupermission)。