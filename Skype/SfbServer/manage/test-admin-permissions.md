---
title: 在 Skype for Business Server 中测试管理员权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如何测试 Skype for Business Server 中的管理员权限
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030155"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>在 Skype for Business Server 中测试管理员权限

| | |
|--|--|
|验证计划|初始 Skype for Business Server 部署之后。 如果出现权限相关问题，则根据需要。|
|测试工具|Windows PowerShell|
|所需的权限|在使用 Skype for Business Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。<br><br/>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsOUPermission cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：<br/><br/>CsAdminRole \| ，其中-对象 {$ _。Cmdlet-匹配的 "Test-CsOUPermission"}|
|||

## <a name="description"></a>说明

当您安装 Skype for Business Server 时，安装程序执行的一项任务是为 RTCUniversalUserAdmins 组提供管理用户、计算机、联系人、应用程序联系人和 InetOrg 所需的 Active Directory 权限。人员. 如果已在 Active Directory 中禁用权限继承，则安装程序将无法分配这些权限。 因此，RTCUniversalUserAdmins 组的成员将无法管理 Skype for business Server 实体。 这些管理权限将仅适用于域管理员。 

CsOUPermission cmdlet 验证在 Active Directory 容器上是否设置了管理用户、计算机和其他对象所需的权限。 如果未设置这些权限，则可以通过运行[CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)来解决此问题。 

请注意，CsOUPermission 只能将权限分配给 RTCUniversalUserAdmins 组的成员。 不能使用此 cmdlet 向任意用户或组授予权限。 如果您希望不同的用户或组拥有用户管理权限，则应将该用户（或组）添加到 RTCUniversalUserAdmins 组。 


## <a name="running-the-test"></a>运行测试

若要验证是否在容器上设置了管理权限，请运行 CsOUPermission cmdlet，然后运行容器的可分辨名称和要验证的权限类型。 例如，以下命令将检查是否在 OU ou = Redmond，dc = litwareinc，dc = com 上设置了用户权限：

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

若要使用单个命令验证多个权限，请将每个权限类型括在引号中，然后使用逗号分隔这些类型。 例如，下面的一个命令验证用户、计算机和联系人权限：

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

有关详细信息，请参阅[CsOUPermission cmdlet 的帮助主题](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)。

## <a name="determining-success-or-failure"></a>确定成功或失败

如果已设置所需的权限，则 CsOUPermission 将返回一个单字响应：

True

如果未设置所需的权限，则 CsOUPermission 将返回值 False。 您可能需要搜索一段时间才能找到此值。 它通常嵌入到多个伴随的警告中。 例如：

警告：访问控制项（ACE） atl-cs-001\RTCUniversalUserReadOnlyGroup;允许ReadPropertyContainerInherit;其子bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

警告：对象 "OU = 北美，DC = atl-cs-001\DC = litwareinc，DC = com" 上的访问控制项（Ace）未准备就绪。 

False 

警告： "Test-CsOUPermission" 处理已完成，但出现警告。 在此运行过程中记录了 "2" 警告。 

警告：在 "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" 处可以找到详细的结果。 

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 CsOUPermission 失败，则通常意味着尚未将指定的权限分配给 RTCUniversalUserAdmins 组。 您可以使用 CsOUPermission cmdlet 来解决此问题，并分配所需的权限。 例如，以下命令将用户、联系人和 inetOrgPersons 的 OU 权限提供给 RTCUniversalUserAdmins 组：

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

有关详细信息，请参阅[CsOUPermission cmdlet 的帮助主题](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)。
