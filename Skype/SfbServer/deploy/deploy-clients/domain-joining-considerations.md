---
title: Skype 会议室系统域加入注意事项
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
ms.openlocfilehash: 93aa983080ee93f38143224b6c74bdcd6490842c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype 会议室系统域加入注意事项
 
阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
  
## <a name="domain-joining-considerations"></a>域加入注意事项

可以将 Skype 的空间系统装置电脑加入到 Active Directory 域或将其保留在工作组中。 做此决定之前请考虑以下事项：
  
- 域加入 Skype 的空间系统装置电脑有助于自动导入您的组织的专用根目录证书链。
    
- 域加入 Skype 的空间系统装置的 PC，您可以授予域用户和组的管理权限。 这样做，你不必记住本地计算机级别的管理员帐户密码。
    
- 当 Skype 的空间系统装置计算机加入到域中时，很需要您创建单独组织单位 (OU)，以便向所有 Skype 的空间系统计算机对象都所在的 OU 组策略对象 (GPO) 排除。 当您执行此操作时，计算机对象在 OU 中创建在 Skype 的空间系统装置计算机加入域之前。
    
- 许多组织都有以下 Gpo，Skype 的空间系统装置 PC 功能的影响。 确保您重写或阻止这些在 Skype 的空间系统 OU 的 gpo 继承： 
    
  - 登录会话的超时（自动锁定）
    
  - 电源管理相关的策略
    
  - 需要附加身份验证步骤
    
  - 拒绝访问本地驱动器
    
  - 提示用户网络连接较慢
    
  - 登录时启动特定程序
    
  - 在所有加入域的计算机上创建另一个域用户帐户。
    
  - 将 Windows 更新推送到 Skype 的空间系统
    
- 或者，你可能决定将家用电脑留在工作组中。 作为与桌面 Skype 业务客户端，这需要您手动导入根证书链，Skype 的空间系统装置的 PC 上。 您不需要导入根证书链，如果您的业务部署 Skype 使用公钥证书 （例如，委托、 VeriSign，等等）。 
    
如果您打算将 Skype 的空间系统机加入到域时，为了避免 Skype 的空间系统机无意中加入意外 OU，这可能不是免费从 Gpo，请确保加入正确的 OU。 可以使用以下 cmdlet 从 Skype 的空间系统计算机加入正确的 OU 中并没有收到可能会阻止 LRS 功能的 Gpo。 请联系你的系统管理员或 OEM 合作伙伴以运行这些 cmdlet：
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"

```

即使你创建单独的 OU 并阻止集成，但是有些策略可能会在较高级别引起问题。 具有“禁止替代”设置的组策略会打败具有“阻止策略继承”设置的 OU。 详细信息，请参阅文章"不重写进行比较的阻止策略继承"的组策略文档中http://technet.microsoft.com/en-us/library/cc978255.aspx。
  
你可能有多种方法来解决这些问题。 我们建议你咨询 Active Directory 专家来确保为你提供的 OU 具有合适的 GPO 设置或者至少其中不存在上面所述的策略。 它建议让 Skype 的空间系统的服务质量 (QoS)。
  

