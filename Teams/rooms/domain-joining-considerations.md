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
description: 管理员可以了解如何将 Skype 会议室系统设备电脑加入 Active Directory 域，以及执行此操作的注意事项。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 806dcac8f73f555227c03f7612f30fe4a598812f
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997410"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Skype 会议室系统域加入注意事项
 
阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
  
## <a name="domain-joining-considerations"></a>域加入注意事项

你可以将 Skype 会议室系统设备电脑加入 Active Directory 域或将电脑留在"工作组"中。 做此决定之前请考虑以下事项：
  
- 加入 Skype 会议室系统设备电脑有助于自动导入组织的专用根证书链。
- 通过加入 Skype 会议室系统设备电脑的域，可授予域用户和组管理权限。 这样做，你不必记住本地计算机级别的管理员帐户密码。
- 将 Skype 会议室系统设备电脑加入域时，需要创建单独的组织单位 (OU) ，以便你可以向所有 Skype 会议室系统计算机对象所在的 OU 提供组策略对象 (GPO) 排除项。 当你这样做时，在将 Skype 会议室系统设备电脑加入域之前，在 OU 中创建计算机对象。
- 许多组织具有以下 GPO，这会影响 Skype 会议室系统设备电脑功能。 确保在 Skype 会议室系统 OU 中替代或阻止这些 GPO 的继承：

  - 登录会话的超时（自动锁定）
  - 与电源管理相关的策略
  - 需要附加身份验证步骤
  - 拒绝访问本地驱动器
  - 提示用户网络连接较慢
  - 登录时启动特定程序
  - 在所有加入域的计算机上创建另一个域用户帐户。
  - 将 Windows 更新推送到 Skype 会议室系统
    
- 或者，你可能决定将家用电脑留在工作组中。 与桌面版 Microsoft Teams 或 Skype for Business 客户端一样，这要求在 Skype 会议室系统设备电脑上手动导入根证书链。 如果部署使用的是公共证书链，则不需要导入根证书链 (例如，Entrust、VeriSign 等) 。 
    
如果你计划将 Skype 会议室系统计算机加入域，为了避免无意中将 Skype 会议室系统计算机加入意外的 OU（可能无法从 GPO 中免费）中，请确保你加入正确的 OU。 可以使用 Skype 会议室系统计算机中的以下 cmdlet 加入正确的 OU，并且不会收到可能会阻止 LRS 功能的 GPO。 请联系系统管理员或 OEM 合作伙伴来运行以下 cmdlet：
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使创建单独的 OU 和块继承，也有一些策略可能会导致更高级别的问题。 具有“禁止替代”设置的组策略会打败具有“阻止策略继承”设置的 OU。 有关详细信息，请参阅组 [策略文档中的"无替代"（](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 与阻止策略继承相比）。
  
你可能有多种方法来解决这些问题。 建议咨询 Active Directory 专家，确保获得具有适当 GPO 设置的 OU，或者至少提供不存在上述策略的 OU。 我们建议为 Skype 会议室系统设备 (QoS) 服务质量。

## <a name="related-topics"></a>相关主题
  
[设备配置：创建新的或编辑现有的](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服务质量](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)
