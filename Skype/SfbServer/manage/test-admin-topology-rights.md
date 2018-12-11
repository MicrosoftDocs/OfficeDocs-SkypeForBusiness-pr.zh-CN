---
title: Skype 中测试业务服务器管理员拓扑权限
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如何为业务服务器在 Skype 测试拓扑权限
ms.openlocfilehash: 6a1bbd6c052acb6488189e466522edf1aa59f2cb
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222819"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Skype 中测试业务服务器管理员拓扑权限

| | |
|--|--|
|验证计划|后 Business Server 部署的初始 Skype。 根据需要如果出现权限相关的问题。|
|测试工具|Windows PowerShell|
|所需的权限|运行时使用的业务 Server 命令行管理程序 Skype 本地，用户必须是 RTCUniversalServerAdmins 安全组的成员。<br/><br/>运行时使用远程 Windows PowerShell 实例，则必须为用户分配了有权运行 Test-cssetuppermission cmdlet RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的列表，请在 Windows PowerShell 提示符处运行以下命令：<br/><br/>Get-csadminrole \| Where-object {$_。Cmdlet-匹配"Test-cssetuppermission"}|
|||

## <a name="description"></a>说明

默认情况下，只有域管理员可以启用企业服务器拓扑的 Skype 和更改业务服务器基础结构 Skype 的大型。 只要您的域管理员和业务服务器管理员将 Skype 是同一个，这不是问题。 在许多组织业务服务器管理员的 Skype 不保留对整个域管理权限。 默认情况下，这意味着，这些 （定义为 RTCUniversalServerAdmins 组的成员） 的管理员不能 Skype 的企业服务器拓扑的更改。 要授予 RTCUniversalServerAdmins 组的权限更改拓扑的成员，您必须使用[Grant-cssetuppermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet 分配所需的 Active Directory 权限。
 
Test-cssetuppermission cmdlet 验证在指定的 Active Directory 容器上配置了需要为业务服务器或其组件之一安装 Skype 所需的权限。 如果未分配权限，然后可以运行 Grant-cssetuppermission cmdlet 授予 RTCUniversalServerAdmins 组成员的安装和启用业务 Server Skype 的权限。

## <a name="running-the-test"></a>运行测试

若要确定是否对 Active Directory 容器分配安装权限，请调用 Test-cssetuppermission cmdlet。 指定要检查的容器的可分辨的名称。 例如，以下命令可验证安装权限的容器 ou = CsServers，dc = litwareinc，dc = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

有关详细信息，请参阅[Test-cssetuppermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。

## <a name="determining-success-or-failure"></a>确定成功或失败

如果 Test-cssetuppermission 确定所需的权限已设置的 Active Directory 容器上 cmdlet 将返回值为 True:

True 

如果未设置权限，Test-cssetuppermission 将返回值设置为 False。 请注意，此值将通常括在多个警告消息。 例如：

警告： 访问控制项 (ACE) atl-cs-001\RTCUniversalServerAdmins;允许;ExtendedRight;无;无;1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告： 访问控制项 (Ace) 对象上的"CN = Computers，DC = litwareinc，DC = com"未准备就绪。 

False 

警告:"Test-cssetuppermission"处理已完成，但出现了警告。 在此运行期间记录了"2"警告。 

警告： 在"C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"，可以找到详细的结果。 

## <a name="reasons-why-the-test-might-have-failed"></a>为什么测试可能已失败的原因

尽管有极少数例外，如果 Test-cssetuppermission 失败通常意味着安装权限未分配对指定的 Active Directory 容器。 可以通过使用 Grant-cssetuppermission cmdlet 分配这些权限。 例如，此命令授予对域 litwareinc.com 中的计算机容器的安装权限：

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

有关详细信息，请参阅[Test-cssetuppermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。
