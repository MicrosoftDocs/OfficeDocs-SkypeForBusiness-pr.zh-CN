---
title: 在 Skype for Business 服务器中测试管理员拓扑权限
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
description: 如何在 Skype for Business 服务器中测试拓扑权限
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817308"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>在 Skype for Business 服务器中测试管理员拓扑权限

| | |
|--|--|
|验证计划|初始 Skype for Business 服务器部署后。 如果出现权限相关问题，则根据需要。|
|测试工具|Windows PowerShell|
|需要权限|在使用 Skype for Business Server Management Shell 本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。<br/><br/>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsSetupPermission cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：<br/><br/>CsAdminRole \| -对象 {$ _。Cmdlet-匹配的 "Test-CsSetupPermission"}|
|||

## <a name="description"></a>说明

默认情况下，只有域管理员可以启用 Skype for business 服务器拓扑，并对 Skype for business 服务器基础结构进行较大的更改。 只要您的域管理员和您的 Skype for business 服务器管理员是同一个，这就不会出现问题。 在许多组织中，Skype for Business 服务器管理员不拥有对整个域的管理权限。 默认情况下，这意味着这些管理员（定义为 RTCUniversalServerAdmins 组的成员）无法进行 Skype for business 服务器拓扑更改。 若要为 RTCUniversalServerAdmins 组的成员授予拓扑更改权限，必须通过使用[CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet 分配所需的 Active Directory 权限。
 
CsSetupPermission cmdlet 验证安装 Skype for Business 服务器或其组件之一所需的权限是否在指定的 Active Directory 容器上配置。 如果未分配权限，则可以运行 CsSetupPermission cmdlet 授予 RTCUniversalServerAdmins 组的成员安装和启用 Skype for Business 服务器的权限。

## <a name="running-the-test"></a>运行测试

若要确定是否为 Active Directory 容器分配了设置权限，请调用 CsSetupPermission cmdlet。 指定要检查的容器的可分辨名称。 例如，此命令将验证容器 ou = CsServers、dc = litwareinc、dc = com 的设置权限：

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

有关详细信息，请参阅[CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果测试 CsSetupPermission 确定已在 Active Directory 容器上设置了所需的权限，则 cmdlet 将返回值 True：

True 

如果未设置权限，则 CsSetupPermission 将返回值 False。 请注意，此值通常会包含在许多警告消息中。 例如：

警告：访问控制项（ACE） atl-cs-001\RTCUniversalServerAdmins;帮助ExtendedRight;尚尚1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

警告：对象 "CN = 计算机，DC = litwareinc，dc = com" 上的访问控制项（Ace）尚未准备就绪。 

False 

警告： "Test-CsSetupPermission" 处理已完成，但出现警告。 此运行期间录制了 "2" 条警告。 

警告：可在 "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" 中找到详细结果。 

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

虽然不太常见的例外，但如果测试 CsSetupPermission 失败，通常意味着不会为指定的 Active Directory 容器分配设置权限。 可以使用 CsSetupPermission cmdlet 分配这些权限。 例如，此命令向域 litwareinc.com 中的计算机容器授予设置权限：

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

有关详细信息，请参阅[CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。
