---
title: Skype 会议室系统域加入注意事项
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
ms.openlocfilehash: 9e6260ae852d66fd435ce236e28df0c992369eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895185"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype 会议室系统域加入注意事项
 
阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
  
## <a name="domain-joining-considerations"></a>域加入注意事项

可以将 Skype 会议室系统装置 PC 加入到 Active Directory 域或将其保留在工作组。 做此决定之前请考虑以下事项：
  
- 域加入 Skype 会议室系统装置 PC 帮助自动导入您的组织的私有根证书链。
    
- 域加入 Skype 会议室系统装置 PC 使您能够授予域用户和组管理权限。 这样做，你不必记住本地计算机级别的管理员帐户密码。
    
- Skype 会议室系统装置 PC 加入域，时，需要您创建单独组织单位 (OU)，以便您可以为所有的 Skype 会议室系统计算机对象所在的 OU 提供组策略对象 (GPO) 排除。 当执行此操作时，创建的 OU 中计算机对象 Skype 会议室系统装置 PC 加入域之前。
    
- 许多组织的以下 Gpo，这会影响 Skype 会议室系统装置 PC 函数。 确保您重写或阻止的 Skype 会议室系统 OU 中的这些 Gpo 的继承： 
    
  - 登录会话的超时（自动锁定）
    
  - 电源管理相关的策略
    
  - 需要附加身份验证步骤
    
  - 拒绝访问本地驱动器
    
  - 提示用户网络连接较慢
    
  - 登录时启动特定程序
    
  - 在所有加入域的计算机上创建另一个域用户帐户。
    
  - 推送到 Skype 会议室系统的 Windows 更新
    
- 或者，你可能决定将家用电脑留在工作组中。 与桌面 Skype 业务客户端，这也需要您手动导入根证书链 Skype 会议室系统装置 PC 上。 您不需要导入根证书链，如果您的业务部署 Skype 正在使用的公共证书 （例如，Entrust、 VeriSign、 等）。 
    
如果您打算将 Skype 会议室系统计算机加入到域，以避免无意中将 Skype 会议室系统计算机联接意外的 OU，这可能不是从 Gpo 免费，请确保您加入正确的 OU。 您可以使用以下 cmdlet 从 Skype 会议室系统机的正确的 OU 中加入并不会收到可能阻止 LRS 功能的 Gpo。 请联系你的系统管理员或 OEM 合作伙伴以运行这些 cmdlet：
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

即使你创建单独的 OU 并阻止集成，但是有些策略可能会在较高级别引起问题。 具有“禁止替代”设置的组策略会打败具有“阻止策略继承”设置的 OU。 有关详细信息，请参阅[禁止替代与阻止策略继承](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))的组策略文档中的文章。
  
你可能有多种方法来解决这些问题。 我们建议你咨询 Active Directory 专家来确保为你提供的 OU 具有合适的 GPO 设置或者至少其中不存在上面所述的策略。 建议为 Skype 会议室系统设备启用服务质量 (QoS)。

## <a name="see-also"></a>另请参阅
  
[设备配置：创建新的或编辑现有的](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[管理服务质量](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
