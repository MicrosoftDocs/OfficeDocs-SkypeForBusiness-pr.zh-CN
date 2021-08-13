---
title: Skype 会议室系统域加入注意事项
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: 管理员可以了解如何将会议室Skype电脑加入 Active Directory 域，以及执行此操作的注意事项。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: caab82c853eb584ba304569daa49963eea847143b59a8413f77455ee9800c8fe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346159"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Skype 会议室系统域加入注意事项
 
阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
  
## <a name="domain-joining-considerations"></a>域加入注意事项

可以将会议室Skype设备电脑加入 Active Directory 域，或将该设备留在"工作组"中。 做此决定之前请考虑以下事项：
  
- 将会议室系统Skype电脑加入域有助于自动导入组织的专用根证书链。
- 使用会议室系统Skype电脑加入域可授予域用户和组管理权限。 这样做，你不必记住本地计算机级别的管理员帐户密码。
- 将 Skype 会议室系统设备电脑加入域时，需要创建单独的组织单位 (OU) ，以便可以将组策略对象 (GPO) 排除项提供到所有 Skype 会议室系统计算机对象所在的 OU。 执行此操作时，在 OU 中创建计算机对象，Skype会议室系统设备电脑加入域。
- 许多组织具有以下 GPO，这Skype会议室系统设备电脑功能。 确保在会议室系统 OU 中重写或阻止Skype GPO：

  - 登录会话的超时（自动锁定）
  - 与电源管理相关的策略
  - 需要附加身份验证步骤
  - 拒绝访问本地驱动器
  - 提示用户网络连接较慢
  - 登录时启动特定程序
  - 在所有加入域的计算机上创建另一个域用户帐户。
  - 将Windows更新推送Skype会议室系统
    
- 或者，你可能决定将家用电脑留在工作组中。 与桌面客户端Microsoft Teams Skype for Business一样，这要求在会议室系统设备电脑上Skype根证书链。 如果部署使用的是公共证书链，则不需要导入根证书链 (例如，Entrust、VeriSign 等) 。 
    
如果计划将 Skype Room System 计算机加入域，为了避免无意中将 Skype 会议室系统计算机加入意外的 OU（可能无法从 GPO 中释放）中，请确保加入正确的 OU。 可以使用会议室系统计算机中的以下 cmdlet Skype加入正确的 OU，并且不会收到可能会阻止 LRS 功能的 GPO。 请联系系统管理员或 OEM 合作伙伴来运行以下 cmdlet：
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使创建单独的 OU 和块继承，也有一些策略可能会导致更高级别的问题。 具有“禁止替代”设置的组策略会打败具有“阻止策略继承”设置的 OU。 有关详细信息，请参阅组 [策略文档中的"无替代"（](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 与阻止策略继承相比）。
  
你可能有多种方法来解决这些问题。 建议咨询 Active Directory 专家，确保获得具有适当 GPO 设置的 OU，或者至少提供不存在上述策略的 OU。 我们建议为会议室系统设备 (QoS) Skype服务质量。

## <a name="related-topics"></a>相关主题
  
[设备配置：创建新的或编辑现有的](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服务质量](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)