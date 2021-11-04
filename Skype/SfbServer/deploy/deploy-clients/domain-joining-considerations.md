---
title: Skype会议室系统域加入注意事项
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 阅读本主题，了解如何将会议室Skype电脑加入你的域。
ms.openlocfilehash: a3a5e4b8fb1f4af7c67e0cfa91ff9237be438347
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751371"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype会议室系统域加入注意事项
 
阅读本主题，了解如何将会议室Skype电脑加入你的域。
  
## <a name="domain-joining-considerations"></a>域加入注意事项

你可以将会议室Skype电脑加入 Active Directory 域或将电脑留在工作组中。 做出此决定之前，请考虑以下几点：
  
- 将会议室系统Skype电脑加入域有助于自动导入组织的专用根证书链。
    
- 通过加入会议室Skype设备电脑，可以授予域用户和组管理权限。 这样，就不需要记住本地计算机级别的管理员帐户密码。
    
- 将 Skype 会议室系统设备电脑加入域时，需要创建单独的组织单位 (OU) ，以便向所有 Skype 会议室系统计算机对象所在的 OU 提供组策略对象 (GPO) 排除项。 当你这样做时，在 OU 中创建计算机对象，Skype会议室系统设备电脑加入域。
    
- 许多组织都具有以下 GPO，这Skype会议室系统设备电脑功能。 确保覆盖或阻止在会议室系统 OU 中Skype GPO： 
    
  - 登录会话超时 (自动锁定) 
    
  - 与电源管理相关的策略
    
  - 需要其他身份验证步骤
    
  - 拒绝访问本地驱动器
    
  - 提示用户网络连接缓慢
    
  - 登录时启动特定程序
    
  - 在所有加入域的计算机上创建另一个域用户帐户。
    
  - 将Windows更新推送Skype会议室系统
    
- 或者，你可能决定将电脑留在工作组中。 与桌面Skype for Business客户端一样，这要求您手动在会议室系统Skype导入根证书链。 如果您的 Skype for Business 部署使用公共证书 (例如，Entrust、VeriSign 等，则不需要导入根证书) 。 
    
如果计划将 Skype 会议室系统计算机加入域，为避免无意中将 Skype 会议室系统计算机加入非预期 OU（可能无法从 GPO 中释放）请确保加入正确的 OU。 可以使用会议室系统计算机中的以下 cmdlet Skype加入正确的 OU，并且不会接收可能会阻止 LRS 功能的 GPO。 请与系统管理员或 OEM 合作伙伴联系以运行以下 cmdlet：
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使您创建单独的 OU 并阻止继承，某些策略也可能导致更高级别的问题。 具有"无替代"设置的组策略会超过具有"阻止策略继承"设置的 OU。 有关详细信息，请参阅组策略文档中的文章 No [Override as Compared to Block Policy Inheritance。](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))
  
你可能有多种方法来解决这些问题。 我们建议您咨询 Active Directory 专家，以确保为您提供具有相应 GPO 设置的 OU，或至少为您提供了不存在上述策略的 OU。 建议为会议室系统设备 (服务质量) QoS Skype QoS。

## <a name="see-also"></a>另请参阅
  
[设备配置：创建新的或编辑现有的](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服务质量](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)