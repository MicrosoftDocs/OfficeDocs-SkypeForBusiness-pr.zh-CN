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
description: 阅读本主题，了解如何将 Skype 会议室系统电脑加入你的域。
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093566"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype 会议室系统域加入注意事项
 
阅读本主题，了解如何将 Skype 会议室系统电脑加入你的域。
  
## <a name="domain-joining-considerations"></a>域加入注意事项

你可以将 Skype 会议室系统电脑加入 Active Directory 域或将电脑留在工作组中。 做出此决定之前，请考虑以下几点：
  
- 域加入 Skype 会议室系统电脑有助于自动导入组织的专用根证书链。
    
- 通过加入 Skype 会议室系统电脑的域，可以授予域用户和组管理权限。 这样，就不需要记住本地计算机级别的管理员帐户密码。
    
- 将 Skype 会议室系统电脑加入域时，需要创建单独的组织单位 (OU) ，以便你可以向所有 Skype 会议室系统计算机对象所在的 OU 提供组策略对象 (GPO) 排除项。 当你这样做时，在 OU 中创建计算机对象，然后再将 Skype 会议室系统电脑加入域。
    
- 许多组织具有以下 GPO，这会影响 Skype 会议室系统设备电脑的功能。 确保覆盖或阻止 Skype 会议室系统 OU 中这些 GPO 的继承： 
    
  - 登录会话超时 (自动锁定) 
    
  - 与电源管理相关的策略
    
  - 需要其他身份验证步骤
    
  - 拒绝访问本地驱动器
    
  - 提示用户网络连接缓慢
    
  - 登录时启动特定程序
    
  - 在所有加入域的计算机上创建另一个域用户帐户。
    
  - 将 Windows 更新推送到 Skype 会议室系统
    
- 或者，你可能决定将电脑留在工作组中。 与桌面 Skype for Business 客户端一样，这需要你在 Skype 会议室系统电脑中手动导入根证书链。 如果你的 Skype for Business 部署使用公共证书 (例如，Entrust、VeriSign 等，则不需要导入根证书链) 。 
    
如果计划将 Skype 会议室系统计算机加入域，为避免无意中将 Skype 会议室系统计算机加入非预期 OU（可能无法从 GPO 中释放）请确保加入正确的 OU。 可以使用 Skype 会议室系统计算机中的以下 cmdlet 加入正确的 OU，并且不会接收可能会阻止 LRS 功能的 GPO。 请与系统管理员或 OEM 合作伙伴联系以运行以下 cmdlet：
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使您创建单独的 OU 并阻止继承，某些策略也会导致更高级别的问题。 具有"无替代"设置的组策略会超过具有阻止策略继承设置的 OU。 有关详细信息，请参阅组策略文档中的文章 No [Override as Compared to Block Policy Inheritance。](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))
  
你可能有多种方法来解决这些问题。 我们建议您咨询 Active Directory 专家，以确保为您提供具有相应 GPO 设置的 OU，或至少为您提供了不存在上述策略的 OU。 建议为 Skype 会议室系统设备 (QoS) 服务质量。

## <a name="see-also"></a>另请参阅
  
[设备配置：创建新的或编辑现有的](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服务质量](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)