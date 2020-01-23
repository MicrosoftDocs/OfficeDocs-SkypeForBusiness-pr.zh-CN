---
title: Skype 会议室系统域加入注意事项
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: 阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
ms.openlocfilehash: d6002174e067152b1aefee45899e291063f19853
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268794"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Skype 会议室系统域加入注意事项
 
阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
  
## <a name="domain-joining-considerations"></a>域加入注意事项

您可以将 Skype 会议室系统设备电脑加入到 Active Directory 域或将其留在工作组中。 做此决定之前请考虑以下事项：
  
- 域-加入 Skype 会议室系统设备电脑有助于自动导入组织的专用根证书链。
- 域-加入 Skype 会议室系统设备电脑使您能够授予域用户和组管理权限。 这样做，你不必记住本地计算机级别的管理员帐户密码。
- 当你将 Skype 会议室系统设备电脑加入域时，需要创建单独的组织单元（OU），以便你可以为所有 Skype 会议室系统计算机对象所在的 OU 提供组策略对象（GPO）排除项。 执行此操作时，先在 OU 中创建计算机对象，然后再将 Skype 会议室系统设备电脑加入域。
- 许多组织拥有以下 Gpo，这些 Gpo 会影响 Skype 会议室系统设备电脑功能。 确保在 Skype 会议室系统 OU 中覆盖或阻止这些 Gpo 的继承：

  - 登录会话的超时（自动锁定）
  - 电源管理相关的策略
  - 需要附加身份验证步骤
  - 拒绝访问本地驱动器
  - 提示用户网络连接较慢
  - 登录时启动特定程序
  - 在所有加入域的计算机上创建另一个域用户帐户。
  - 将 Windows 更新推送到 Skype 会议室系统
    
- 或者，你可能决定将家用电脑留在工作组中。 与桌面版 Microsoft 团队或 Skype for business 客户端一样，这需要你手动导入 Skype 会议室 System 设备电脑上的根证书链。 如果你的部署使用公共证书（如 Entrust、VeriSign 等），则无需导入根证书链。 
    
如果你计划将 Skype 会议室系统计算机加入到域，以避免将 Skype 会议室系统计算机从无意中加入非有意的 OU （这可能并非来自 Gpo），请确保加入正确的 OU。 你可以使用 Skype 会议室系统计算机中的以下 cmdlet 加入正确的 OU，并且不会收到可能会阻止 LRS 功能的 Gpo。 请联系你的系统管理员或 OEM 合作伙伴以运行这些 cmdlet：
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使你创建单独的 OU 并阻止集成，但是有些策略可能会在较高级别引起问题。 具有“禁止替代”设置的组策略会打败具有“阻止策略继承”设置的 OU。 有关详细信息，请参阅有关组策略文档中的 "[阻止策略继承](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))" 的文章没有替代。
  
你可能有多种方法来解决这些问题。 我们建议你咨询 Active Directory 专家来确保为你提供的 OU 具有合适的 GPO 设置或者至少其中不存在上面所述的策略。 建议为 Skype 会议室系统设备启用服务质量（QoS）。

## <a name="see-also"></a>另请参阅
  
[设备配置：创建新的或编辑现有的](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服务质量](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
