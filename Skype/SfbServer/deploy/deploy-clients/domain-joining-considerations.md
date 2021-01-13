---
title: Skype 会议室系统域加入注意事项
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 阅读本主题，了解如何将 Skype 会议室系统设备电脑加入你的域。
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805912"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype 会议室系统域加入注意事项
 
阅读本主题，了解如何将 Skype 会议室系统设备电脑加入你的域。
  
## <a name="domain-joining-considerations"></a>域加入注意事项

你可以将 Skype 会议室系统设备电脑加入 Active Directory 域或将电脑留在工作组中。 在做出此决定之前，请考虑以下几点：
  
- 加入 Skype 会议室系统设备电脑的域有助于自动导入组织的专用根证书链。
    
- 通过加入 Skype 会议室系统设备电脑，可以授予域用户和组管理权限。 这样，您就不需要记住本地计算机级别的管理员帐户密码。
    
- 将 Skype 会议室系统设备电脑加入域时，需要创建单独的组织单位 (OU) ，以便你可以在所有 Skype 会议室系统计算机对象所在的 OU 中提供组策略对象 (GPO) 排除项。 当你这样做时，在 OU 中创建计算机对象，然后再将 Skype 会议室系统设备电脑加入域。
    
- 许多组织都有以下 GPO，这会影响 Skype 会议室系统设备电脑的功能。 确保在 Skype 会议室系统 OU 中覆盖或阻止这些 GPO 的继承： 
    
  - 登录会话超时 (自动锁定) 
    
  - 与电源管理相关的策略
    
  - 需要其他身份验证步骤
    
  - 拒绝访问本地驱动器
    
  - 提示用户网络连接缓慢
    
  - 登录时启动特定程序
    
  - 在所有加入域的计算机上创建另一个域用户帐户。
    
  - 将 Windows 更新推送到 Skype 会议室系统
    
- 或者，你可能会决定将设备电脑留在工作组中。 与桌面 Skype for Business 客户端一样，这需要你在 Skype 会议室系统设备电脑上手动导入根证书链。 如果你的 Skype for Business 部署使用公共证书（例如， (、VeriSign 等）) ，则无需导入根证书链。 
    
如果你计划将 Skype 会议室系统计算机加入域，以避免无意中将 Skype 会议室系统计算机加入意外的 OU（可能无法从 GPO 中释放）中，请确保你加入正确的 OU。 你可以从 Skype 会议室系统计算机使用以下 cmdlet 加入正确的 OU，并且不会收到可能会阻止 LRS 功能的 GPO。 请与系统管理员或 OEM 合作伙伴联系以运行以下 cmdlet：
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使您创建单独的 OU 并阻止继承，某些策略也可能导致较高级别的问题。 具有"无替代"设置的组策略会通过阻止策略继承设置来阻止 OU。 有关详细信息，请参阅组策略文档中的文章 [No Override as Compared to Block](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) Policy Inheritance。
  
你可能有多种方法来解决这些问题。 我们建议您咨询 Active Directory 专家，以确保为您提供具有相应 GPO 设置的 OU，或至少为您提供了不存在上述策略的 OU。 建议为 Skype 会议室系统设备 (QoS) 服务质量。

## <a name="see-also"></a>另请参阅
  
[设备配置：创建新的或编辑现有的](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服务质量](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
