---
title: 测试中 Skype 业务服务器的管理员权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如何为业务服务器在 Skype 测试管理员权限
ms.openlocfilehash: f769870991cfd5578fc8bd809d26c0aea912d03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898288"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>测试中 Skype 业务服务器的管理员权限

| | |
|--|--|
|验证计划|后 Business Server 部署的初始 Skype。 根据需要如果出现权限相关的问题。|
|测试工具|Windows PowerShell|
|所需的权限|运行时使用的业务 Server 命令行管理程序 Skype 本地，用户必须是 RTCUniversalServerAdmins 安全组的成员。<br><br/>运行时使用远程 Windows PowerShell 实例，则必须为用户分配了有权运行 Test-csoupermission cmdlet RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的列表，请在 Windows PowerShell 提示符处运行以下命令：<br/><br/>Get-csadminrole \| Where-object {$_。Cmdlet-匹配"Test-csoupermission"}|
|||

## <a name="description"></a>说明

在安装 Skype 业务服务器时，由安装程序执行的任务之一提供 RTCUniversalUserAdmins 组管理用户、 计算机、 联系人、 应用程序联系人和 InetOrg 所需的 Active Directory 权限人员。 如果禁用了权限继承在 Active Directory 中的，安装程序将无法分配这些权限。 因此，RTCUniversalUserAdmins 组的成员将无法管理 Skype Business Server 实体。 只能域管理员可以使用这些管理权限。 

Test-csoupermission cmdlet 验证所需的权限管理用户、 计算机和其他对象所需的 Active Directory 容器上设置。 如果未设置这些权限，您可以通过运行[Grant-csoupermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)来解决此问题。 

请注意 Grant-csoupermission 只可以向 RTCUniversalUserAdmins 组的成员分配权限。 此 cmdlet 不能用于对任意用户或组授予权限。 如果您希望使其具有用户管理权限的其他用户或组，您应添加到 RTCUniversalUserAdmins 组的用户 （或组）。 


## <a name="running-the-test"></a>运行测试

若要验证的容器上设置了管理权限，运行 Test-csoupermission cmdlet 关注容器的可分辨名称和您要验证的权限的类型。 例如，以下命令检查用户权限是否都设置 OU ou = 雷德蒙德，dc = litwareinc，dc = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

若要验证通过使用单个命令的多个权限，请用引号引起来，每种权限类型，然后使用逗号分隔这些类型。 例如，以下一个命令可验证用户、 计算机和联系人权限：

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

有关详细信息，请参阅[Test-csoupermission cmdlet 的帮助主题](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)。

## <a name="determining-success-or-failure"></a>确定成功或失败

如果已设置所需的权限，Test-csoupermission 将返回一个单词响应：

True

如果未设置所需的权限，Test-csoupermission 将返回值设置为 False。 您可能需要一段时间，以查找此值搜索。 通常将嵌入内多个附带的警告。 例如：

警告： 访问控制项 (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;允许;ReadProperty;ContainerInherit;后代;bf967aba-0de6-11 d 0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

警告： 访问控制项 (Ace) 对象上的"OU = NorthAmerica，DC = atl-cs 001\DC = litwareinc，DC = com"未准备就绪。 

False 

警告:"Test-csoupermission"处理已完成，但出现了警告。 在此运行期间记录了"2"警告。 

警告： 在"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"，可以找到详细的结果。 

## <a name="reasons-why-the-test-might-have-failed"></a>为什么测试可能已失败的原因

如果 Test-csoupermission 失败，通常表示指定的权限尚未分配到 RTCUniversalUserAdmins 组。 您可以解决此问题，并将其分配所需的权限，使用 Grant-csoupermission cmdlet。 例如，此命令可提供 OU 权限的用户、 联系人和 Inetorgperson 到 RTCUniversalUserAdmins 组：

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

有关详细信息，请参阅[Test-csoupermission cmdlet 的帮助主题](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)。
